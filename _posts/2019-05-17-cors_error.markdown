---
layout: post
title:      "CORS ERROR"
date:       2019-05-17 14:09:08 -0400
permalink:  cors_error
---


When i first started JS I was so confused that there are too many differences  between ruby and 
JS, but i learnt to embrace the new challenge and to see the power in JS. With all new coding challenges our attitude has to be to one of  embracing it with a passion to learn.

 When I first got to lab that the test was broken but my code was good I would get frustrated and say "what a waste of time on fixing the errors " then I realized it can be a learning moment, learning how to figure out what test is broken , bcs in the real world we will write code against a test , we have to know how to deal with a broken test.This change in attitude helped me pass so many challenges and take on new ones.

While adding JS to my project and working with API I came across a new type of error CORS, What is that ? 
 	Here is how MDN defines it “Cross-Origin Resource Sharing (CORS) is a mechanism that uses additional HTTP headers to tell a browser to let a web application running at one origin (domain) have permission to access selected resources from a server at a different origin. A web application executes a cross-origin HTTP request when it requests a resource that has a different origin (domain, protocol, and port) than its own origin.” 

  Meaning if your front end is on a different server then you backend the browser will block the call but why? This is probably one of the most common security features a good web browser has  to prevent someone from writing a script to access our backend or db without permission. So API calls using Fetch would run into this issue.

How do we deal with this , we add CORS headers to our server, see [server side article ](https://developer.mozilla.org/en-US/docs/Web/HTTP/Server-Side_Access_Control
)   like this 
`Access-Control-Allow-Origin: http://example.com:8080 `   we  have  white listed one domain and port to  access the server from a different origin. If you don't have access to the server to make that change you can using a proxy service , and then you only fetch from the proxy . There are many ways to deal with it but the first solution is to understand the problem (or the need for it)


```$.ajax({
            headers: { "Accept": "application/json"},
            type: 'GET',
            url: 'http://www.example.com,
            crossDomain: true,
            beforeSend: function(xhr){
                xhr.withCredentials = true;
          },
            success: function(data, textStatus, request){
                console.log(data);
            }
 });```

This sometimes helps but many times you need to read the documentation of the api how to deal with the  issue.


**Signing off for now,**

*Sim*

