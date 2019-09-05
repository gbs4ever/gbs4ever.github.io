---
layout: post
title:      "Final project "
date:       2019-06-19 18:13:05 -0400
permalink:  final_project
---

 The best advice I can give for anyone building a full web app -- full front-end and back-end project.

First thing to do is keep two different  windows of the code base open at all times,  having them separated is a **must** as it is very easy to get lost in your code so some structure will help a lot. Next open 3 terminals,

1. One for backend server  
2. One for  the front end server 
3. One for a rails console

We can't forget about setting up your dev tools they will be your best friend during this journey in   debugging. **-- redux dev tools , react , console, debugger , console.log , then for back-end  pry/byebug. **Also use the network tab in your dev tools to see what the back-end server has sent back if there are any errors 

Remember to  embrace your errors it is you program helping you work it out,  it is not a negative thing but a sign how things are going on under the hood.As dev's we hate hate errors that somehow only show up later on.  An error in the beginning is you best friend because it will lead you down the right path of how to fix. It will teach how to write clean code and minimize errors. 

 Before you build you project I would suggest  building  a dud so you can become familiar with the react setup and understand how it works especially with redux attached . My golden rule before any project is to map it out even with a pen and paper, it will save you endless hours of work.  If  you  think of the structures you will need from you back-end and front end etc you can go straight to programing. How you approach your project will determine how smoothly it devolps, so here are some tips to help you .


1.  First create your rails back-end `rails new project-name-here --api --database=postgresql` 
2.  We need to attach our rails app to postgres add this to  database.yml  

``database: your app``

``host:localhost ``

``user:`` 

``password:``

Use pgadmin to setup your DB then  
``db:create``

``db:migrate``
 
3.    Then create you front-end  type    `npx create-react-app my-app` then `cd my-app` and then boot it using `npm start`
4.  If you are plaining to add user -login do that first, there are many ways it can be done , I like using cookies and sessions. This can become  very comlicated so make sure it works and all bugs(related to login) are taken care of first before moving on.
5.    Go to cors.rb and uncomment  the file and add  these words
    `origins 'http://localhost:3000'` 
		
		we have just  whitelisted our front-end  server. Next  we need to go to the file  application.rb  make sure to add this 
		
		```config.middleware.use ActionDispatch::Cookies```
    
		``` config.middleware.use ActionDispatch::Session::CookieStore, key:_cookie_name``` .
		
		Last but not least you need to  add this to you application controller  
		
		```include ::ActionController::Cookies```

		 
	
Yay ! You back end is setup to be an api and also able to  accept cookies now you just have to make sure
you setup the front-end correctly .Good luck !

Signing off 

Sim


[React-Doc](https://github.com/facebook/create-react-app)

		 

   
