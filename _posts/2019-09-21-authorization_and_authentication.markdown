---
layout: post
title:      "Authorization and Authentication "
date:       2019-09-22 02:39:58 +0000
permalink:  authorization_and_authentication
---

What is authorization and authentication, why is it important and some ways they can be hacked?
Authentication is confirming you are who you claim to be, this is the typical login process. Where we match your  input username and password against the DB if  is correct
Authorization is when we know who you, but what rights or access do you have to this system are you an admin with full access pass or maybe you only have read rights. 

To give an example, imagine you go to you a conf . You come with your ticket and id to get it that is Authentication. The employee checks your ticket to see what permissions you have are you VIP, vendor, all-access; where can you go is it backstage access?  The employee then gives you a neck badge to wear with your status that is your Authorization. The same process in with user credentials.

 There are two main processes we can use Sessions/cookies or [JWT](https://jwt.io/) (aka Tokens)
 
**With the typical flow of a  session/cookie system**

1. The user logins entering username password (front-end) 
2. The server verifies the data is correct (query db 1) and creates a session stored in the DB
3. A cookie with the session id is sent to the front-end and stored in the  place in the browser
4. Each HTTP request we will match the session-id against the DB
5.logout destroy the session on the server 

<a href="https://imgur.com/YaxweYp"><img src="https://i.imgur.com/YaxweYpl.png" title="source: imgur.com" /></a>


**Token based flow **

Token-based  auth is becoming very popular due to the way we design apps as single page-apps. The most common is JWT one big difference is JWT is stateless the DB does not save any session but the token is returned to the client to make use and added to every HTTP request header and the server just confirms it is a correct token. 



1. The user logins entering username password (front-end)
2. The server verifies the data is correct and returns a signed token 
3. The token is stored client-side 
4. Each HTTP request to the server will include the token in the header
5. The server just needs to decode the token and not query the DB  
5. Once a user logs out the token is destroyed client-side no interaction with the server needed

<a href="https://imgur.com/AM6CQzB"><img src="https://i.imgur.com/AM6CQzBl.png" title="source: imgur.com" /></a>

This is the basic difference between the way we log on, stay tuned to next weeks post where we will talk about the pros and cons of each one. 

Signing off

Sim  Greenbaum 

 
 Links
 
 [Tokens](https://dzone.com/articles/cookies-vs-tokens-the-definitive-guide)
 
 [Autho](https://medium.com/datadriveninvestor/authentication-vs-authorization-716fea914d55)




