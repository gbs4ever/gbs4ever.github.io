---
layout: post
title:      "Childrens-Books-Libray "
date:       2019-03-18 04:13:17 +0000
permalink:  childrens-books-libray
---


As we know  reading for children is great as it helps them   with their cognitive development to develop their  language, physical, social, and emotional skills.At a certain age we encourage these young minds to start reading on their own. How can we insure that the books they read and the concepts  they are exsposed to  are  appropriate for that child? We know children develop at different rates and may be scared or not understand certain concepts.  I developed this app so as a community we could build a resource of books and if they are appropriate (with some comments) 


Please Fork  and clone this app [here]( https://github.com/gbs4ever/childrens-books),I would love to share some of my coding experience designing this  Sinatra app. First of all anyone who will building a sinatra app save yourself some time just to get the app setup  and use the corneal app it will set up an MVC , second it helps you create you DB with all the Activerecord inheritance and all the  gems required.

What is MVC, Model - logic or the roadmap for our ruby classes   Views - front end  , what the user/client sees  Controllers - the go between the views and model also sets the correct routes for the user. Ruby/Sinatra is not the only Language to implement this standard but is does fall  under DRY code (Don't Repeat Yourself) and keeps the responsibility of each file in our app separate , the more complex your code base is the more this will become issentional.

Quick Reference guide to build our debug your app
1. Gem file - always check the version of your app if the need to be changed 
2. Config.ru - have you listed you main controller  as run ApplicationController also in order to Patch /Delete we need to       add this                 ``` use Rack::MethodOverride```
3 Rake file ```  task :console do
Pry.start
end```    use this for debugging by accessing  our DB and RUBY objects.

4. Public dir - this is we we put out css/JS/images files
5. Config dir- will have our  environment  file  ```ActiveRecord::Base.establish_connection(
  :adapter => "sqlite3",
  :database => "db/#{ENV['SINATRA_ENV']}.sqlite"
)
require './app/controllers/application_controller'
require_all 'app' ``

6. In our views folder dont forget to make a standard layout and then add this erb tag ```<%=yield%>```
7. We use the ```<%=%>``` when we want the browser to display the rendered ruby code and ```<%%>``` just to render some ruby lines;  in the views folder we wan to keep our logic to a min. 
We may not always have to write this code  as many gems will do it for us but **it is essential that we can read and understand it **,as this will help us become great programmers by trying to never skip a code base we cant read and understand.


Signing off,

**SIM**



