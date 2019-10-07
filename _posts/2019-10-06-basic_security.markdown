---
layout: post
title:      "Basic Security "
date:       2019-10-06 20:20:17 -0400
permalink:  basic_security
---

With all the hacks against big companies and sensitive data being compromised even if you, not a web-security expert it should be on your mind.
 
 There are 3 major ones that all Junior developers should be aware of as they start to build and write code. These are some basic definitions from Wikpedia.

1. SQL Injection - “An attack consists of insertion or "injection" of a SQL query via the input data from the client to the application. A successful SQL injection exploit can read sensitive data from the database, modify database data “ 
2. Cross-Site Scripting (XSS)-enables attackers to inject client-side scripts into web pages viewed by other users. A cross-site scripting vulnerability may be used by attackers to bypass access controls
3. Cross-site request forgery is a type of malicious exploit of a website where unauthorized commands are transmitted from a user that the web application trusts.

## SQL Injection
Why is it so scary ,first even a non-sesoned hacker with very basic coding skills can gain access to some of the info in a DB. Second, any form that is submitting data is bypassing all firewall and security measures and so we can update the info in the DB. What is stopping the user from injecting some SQL query to retrieve data? I will not get into specifics of what can be done as that would be liking giving a loaded gun to a child. I will just mention some measures that are taken to prevent such hacks.

In rails when we use active record, whaf if my name is ```  ' OR 1='1``` 

```User.where("name = '#{params[:name]'") # SQL Injection!```

Because now we are saying  give me a user whose name is  blank  or if 1=1 (which is true) so then return the whole table (OOHH )


```User.where(["name = ?", "#{params[:name]}"])```

We don't pass in a string directly but use “?“ as template or placeholder for the parameters.In this example we are clearly stating how to make the query! This is just one example if we are even just aware of the vulnerabilities,that will help us in finding the correct solution.







## Cross-Site Scripting (XSS)
**Stay-tuned coming soon**

## Cross-site request forgery
**stay tuned-coming soon**



All the best,

Simcha Greenbaum



References

1. [SQl Injection](https://www.beyondsecurity.com/about-sql-injection.html)
2. [CSRF](https://medium.com/rubyinside/a-deep-dive-into-csrf-protection-in-rails-19fa0a42c0ef)
3. 




