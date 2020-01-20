---
layout: post
title:      "Truly understanding full-stack web development"
date:       2020-01-19 23:45:03 -0500
permalink:  truly_understanding_full-stack_web_development
---


I was asked to help build out functionality for a back-end developer so they could have a GUI  or graphical user interface.  This would enable non-technical employees to interact and update the DB.One point I made to the Project manager was that this “GUI” could live on the back-end server or it could be a file on a totally different server. The lesson I took from this before you start to code try to find out what will the production environment be ( many times this will change) 



In the end, they chose to keep it all in one repo kind of like you will see in a Rails app. However, they wanted the option to be able to update multiple records on the same page without refreshing. This sounds like a great option for Javascripts AJAX or Fetch where we could access the server in the background and then update the Dom(no refresh).

```javaScript
$(document).ready(function checkout() {
  $(".checkin").on("click", function (event) {
    event.preventDefault()
     let id = $(this).data("id");
    $.ajax({
      url: `/checkouts/${id}`,
      type: 'DELETE',
      dataType: 'json',
      success:
        () => {
          this.remove()
         $(`.status${id}`).html('<p class="success-message">Thank you for checking in your book</p>')
        }

    })
  });
})
````

This code is actually written in jquery which is a JS framework. Let’s go through this line by line,
The first line  makes sure our Javascript will only execute after the HTML has fully loaded. 

```$(document).ready(function checkout()```

We then add an event listener to our button which will  execute an Ajax request to our Rest API if clicked.Then when the server sends a success respone we add that data to the DOM.

``` $(".checkin").on("click", function (event)```

```
$.ajax({
      url: `/checkouts/${id}`,
      type: 'DELETE',
      dataType: 'json',
			 success:
	```
	
So even though this code is fairly simple it is essential to understand the exact steps needed especially when you will be working with a team or another developer. When the code isn’t working you need to be able to correctly problem solve which part of the code is not working.

All the best,
Simcha Greenbaum
www.simchagreenbaum.dev 
	
