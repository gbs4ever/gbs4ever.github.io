---
layout: post
title:      "Final project "
date:       2019-06-19 18:13:05 -0400
permalink:  final_project
---

 I would start by trying to give as much advice as  I can for anyone else who will be going down this path of building a full front-end and back-end project.

First thing is to keep two different  windows of the code base open at all time but having them separated it is very easy to get lost in your code so some structure will help a lot. Next open 
  3 terminals  one for backend server  2nd for the front end server 3rd for a rails console.
We can't forget about setting up our dev tools they will be your best friend in   **debugging -- redux dev tools , react , console, debugger , console.log , then for back-end  pry/byebug. **  Also use the network tab in your dev tools to see what the back end -server has sent back if there are any errors 

Remember to  embrace your errors it is you program helping you work it out  it is not a negative but a sign how things are going on under the hood.As dev we hate hate errors that somehow only show up later  an error in the beginning is you best friend because it will lead you down the right path of how to fix,It will teach how to write clean code and minimize errors. 

 Before you build you project I would suggest  building  a dud so you can become familiar with the react setup and understand how it works especially with redux attached . My golden rule before any project is to map it out even with a pen and paper it will save you endless hours of work.  If  you  think of the structures you will need from you back-end and front end etc you can go straight to programing.How you approach your project will determine many things so here are some tips to help.


1.  first create your rails back-end `rails new project-name-here --api --database=postgresql` 
2.  we need to attach our rails app to postgres add this to  database.yml  
```database: your app
host:localhost 
user: 
password:```
Use pgadmin to setup your DB then  
`db:create  db:migrate`
 
3.    then create you front-end      `npx create-react-app my-app` then `cd my-app` and then boot it `npm start`
4.  If you are plaining to add user -login do that first there are many ways  to do i like using cookies and sessions. This can be very comlicated so make sure it works first before moving on.
5.    Go to cors.rb uncomment  the file add `
   ` origins 'http://localhost:3000'`  we have whitelisted our front-end  server. Next    in application.rb add this ```config.middleware.use ActionDispatch::Cookies
     config.middleware.use ActionDispatch::Session::CookieStore, key:
     '_cookie_name'`` .Last but not least add this to you application controller  `include ::ActionController::Cookies`
		 
	You back end is setup to be an api and also accept cookies now you just have to make sure
	you setup the front-end correctly .Good luck !
	
	Signing off 
	Sim 
	
	[React-Doc](https://github.com/facebook/create-react-app)
   
