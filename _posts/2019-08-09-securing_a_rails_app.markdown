---
layout: post
title:      "Securing a Rails App"
date:       2019-08-09 20:18:00 +0000
permalink:  securing_a_rails_app
---


We all love to build apps that are not just static websites but those that are interactive which is great from a user experience. However this leads to some security issues as we have created a window into our systems(codebase) which potentially could suffer an attack like  just to name a few XSS or SQL injection.
 
From Rails docs 

> The most common entry points are message posts, user comments, and guest books, but project titles, document names and search result pages have also been vulnerable - just about everywhere where the user can input data. But the input does not necessarily have to come from input boxes on websites, it can be in any URL parameter - obvious, hidden or internal. Remember that the user may intercept any traffic. Applications or client-site proxies make it easy to change requests. There are also other attack vectors like banner advertisements.
XSS attacks work like this: An attacker injects some code, the web application saves it and displays it on a page, later presented to a victim. Most XSS examples simply display an alert box, but it is more powerful than that. XSS can steal the cookie, hijack the session, redirect the victim to a fake website, display advertisements for the benefit of the attacker, change elements on the web site to get confidential information or install malicious software through security holes in the web browser.”
That is a lot to absorb and  before we  can fix any problem we must first  figure out what is exactly the problem and what are the symptoms.I am not a security expert and don't claim to be but what I do best is if a problem is presented to me I flip turn and  examine it on all sides. Then and only then do I look for a solution . Doctors do this all the time a patient can present with one of two aliments if we give him the medicine it might heal him but he might bleed to death because he might have another problem that prevents his blood clotting .As Devs we must examine the problem and figure out what it is the  true source of the bug.

In my app a user is asked to share a comment on a book. What if a user add this as a comment?

`<script>alert('Hello');</script>`

Not so bad but this is worse we are writing to the cookie

`<script>document.write(document.cookie);</script>`


 Rails by default will prevent the script from running  on any of its view pages.Rails will  actually sanitize the output by default not the input into the DB,  meaning what it displayed to the page/client of   a rails only app will be fine.This is good but still leaves us with two problems.

1. Rails view will not execute the code but it still displays on the page,not looking so nice.
2. My problem  was that on one page I was using ajax(JavaScript) to pull data from the DB and rails was  just rendering json, basically a mini api. From this angel  when JS picks up the data it was not sanitized and when it displayed the code  would fully execute .This was a great lesson for me  in finding the core of the issue pinpointing what is the source of the problem .

There are two approaches  we could take  strip the html tags(html escaping)and make sure the data never enters the db which might be good to solve the problem at hand  as the window that was open to my database has been closed .This was all my original thought but speaking to others I have learnt the best option is to never trust what is inside you db always assume some hacker has planted a worm inside waiting to execute so when you pull from db then sanitize.  Without going into too many  details it is considered bad practice to double escape .

So the next option was to deal only with the JS code 
And that was an easy fix 

```Review.prototype.formatIndex = function(){```

``` let review = $('<li>').text(this.comments).html()```
 
 ```let reviewHtml = `<li>${review}</li><br>```

We added the text ()
calling` .text(...)` on it will assign the passed value as  text only,  it will treat the html tag as pure text .Js will never be able to read any scriptid code that means even if the user somehow gets data into our database thru another window  we haven't found yet the output is still guarded. I had solved the the script from running but I didn't like that a user can still add HTML tags to my page.  


 Then I thought instead of escaping the html tags we should just strip any message that contains any HTML tags basically making it blank.

```full_sanitizer = Rails::Html::FullSanitizer.new```

  ```sanitized_review = review_params```
	
  ```sanitized_review[:comments] = full_sanitizer.sanitize(review_params[:comments])```
	
  ```@review = current_user.reviews.build(sanitized_review)```
	
     ```if  current_user.save```

Now let my validations kick in and it  wont save a blank reviews that don't have any  comments.So I have prevented it from even being saved to the db .I sure learnt a lot on this subject debugging it myself hope you will also.

On a side note if you are running a **rails only MVC app** then by default the scripts wont run and to just  clean  up the output  all you need to do is add the word sanitize in your views  [like this](https://edgeapi.rubyonrails.org/classes/ActionView/Helpers/SanitizeHelper.html)

``<%= sanitize @comment.body %>``

Signing off, 

Sim Greenbaum



[Rails guide](https://guides.rubyonrails.org/security.html#injection)

[Rails Gem ](https://guides.rubyonrails.org/security.html#injection)


