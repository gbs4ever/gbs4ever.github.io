---
layout: post
title:      " Authorization and Authentication  part 2"
date:       2019-09-24 02:16:38 +0000
permalink:  authorization_and_authentication_part_2
---


Last week we discussed the difference between a cookies/session versus a token authorization. Today we will visit some of the pros and cons of each

## Performance 
In a cookies flow, we need to query the DB many more times  for example this code :
<a href="https://imgur.com/AM6CQzB"><img src="https://i.imgur.com/AM6CQzBl.png" title="source: imgur.com" /></a>

On each HTTP request, we need to query the DB to check the session if the user is logged in. In addition when the user logs-out we have to destroy the session on the server or the server will think the user is logged in. This was one bug I had when I built my React app I just cleared the cookies from the front-end but my app was still fetching the session which as the server was concerned was still valid.  

So that is a min of 4  queries to the DB that means our back-end server needs to perform lookups. We are now dependent on the server computing power and what it can handle in size and numbers (think twitter) If you have different roles like admin, teacher, student then that would require another DB query. With JWT would require 1-2 to verify the user and then we are just checking if it's a token is valid no DB query. We can even add privileges inside the token if the user is admin etc  Another way JWT is better on performance is when the user logs out we just clear the front-end token no need to speak to the server. We can even have to token automatically expire.


## Cors 
With JWT or any token approach, we don't have to be worried of exposing our API to the world as each request needs to a have valid token in its header or the server won't process the request.


## Mobile
Our API is not just written for a browser like Chrome or firefox but native mobile apps. Tokens are much more straightforward to use for a native mobile app which is built on iOS or Android; mobile platforms don't work so well with cookies. In addition IOT or Internet of Things, like your lights, it is pretty simple to add a token to the header when we fetch from our API but they have no option to store cookies. 

<a href="https://imgur.com/OWfzGiJ"><img src="https://i.imgur.com/OWfzGiJl.png" title="source: imgur.com" /></a>

## Some limitations of JWT
1. JWT tokens are a lot larger than your standard cookies 
2. JWT tokens are encrypted but the payload that is attached can easily be unencrypted so don't store sensitive data like username and password
 [see more here](https://jwt.io/) or  use JSON Web Encryption [JWE](https://medium.facilelogin.com/jwt-jws-and-jwe-for-not-so-dummies-b63310d201a3)
3. The server does not know who is logged in at any given time, it can just tell if the token’s are valid.



Signing off,

Sim Greenbaum










