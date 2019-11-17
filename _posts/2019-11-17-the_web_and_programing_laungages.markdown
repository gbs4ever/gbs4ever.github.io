---
layout: post
title:      "The Web and programing laungages "
date:       2019-11-17 16:01:41 -0500
permalink:  the_web_and_programing_laungages
---


The web has become so ingrained in us that we take it for granted but every once in a while we need to take a step back and see how it really works.The basic flow is the (client) your computer makes a request to the server. The server then processes the request and sends back a response. 

<a href="https://imgur.com/XTrE74B"><img src="https://i.imgur.com/XTrE74B.png" title="source: imgur.com" /></a>


We need   to take a step back and understand the server can do many things.
1. It listens to  HTTP requests or better known as a web server
2. Bussniess logic
3. Acsses the DB 
4. Input validation for form input.
5. Authentication and Authorizations
6. Return HTTP response 



However, depending on the language you choose will decide how the server is setup. In Ruby Rack process just the Http request and we write our Ruby code to do the rest(no pun intended)  Talk to the DB, validate the user input, etc. It makes starting a web application very easy as there is no requirement to build out the webserver the same thing is with PHP  you use Apache. However, in Node.js we will actually add functionality to the web server and use Js to build it. Why is the important to know in any application the more you can understand what is going on the better you will be at dealing with errors and optimizing run time.


Top tip -- Don’t try to reinvent the wheel research there may be a library to help you deal with the issue you are facing. On the flip side when you are trying to learn a new concept it is some times might help you build it out on your own.

All the best,

Simcha Greenbaum
