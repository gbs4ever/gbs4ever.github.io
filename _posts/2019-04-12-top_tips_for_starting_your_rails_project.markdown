---
layout: post
title:      "Top tips for starting your rails project."
date:       2019-04-12 15:25:24 -0400
permalink:  top_tips_for_starting_your_rails_project
---



Rails project  

The best  piece of advice I can give before you start building a project or a Rails app is to  sit down with a pen and paper(yes paper ) and draw out a basic structure of you project.

1. What DB tables will I need, is there a join table  ?
2. What attributes will each model  have?
3. Which routes do I know I need(we can always change this later)
4. Try to think of the control flow to the best of your ability at this early stage.


Now let's start coding since we want to host this app on [Heroku ](  https://www.heroku.com/)  we are going to use a different DB Postgresql ,not the standard Sqlite3 ;make sure it is installed on your system. The major diffrence is that Sqlite3 the data is included inside your app files while   Postgresql lives on your pc.  

 **For Windows  to get it working follow these steps [click here]( https://github.com/micahshute/wsl-setup)**

To start your rails app enter rails new  with this  additional flag
```rails new my-app --database=postgresql```

Next go into your  config/database.yml and add this 

```host: localhost```

```user: your-postgres-username```

```password: your-postgres-usernames-password```

Then back to our terminal and run this.

```rake db:create```
```rake db:migrate```


You will  most probally get an error at this point, just login into Pgadmin on  your PC  and refresh the db it should connect correctly.

```Rails  s```

If all went well ,it  should boot the server correctly, now that we have our basic app running  which hopefully has no errors.**** If you have errors fix them first before you continue and make you code more complex.****  In my opinion the next step is to  add all the gems to the gem file we  think  we will need (dont forget to run bundle install)
 
 ```gem 'pry'
gem 'devise'```


 Then the next logical step is to set up our **user table**  with devise the hardest part is done for us so  just run these commands 
 
``` rails generate devise:install```
```rails generate devise USER```
```rails db:migrate```
```rails g devise:views```

Now that we have our user table running , we need to think which rails generter we going to use see [this](https://medium.com/@kevinyckim33/rails-generators-cli-cheatsheet-711295e7a1ed) will be helpfull . Keep in mind  to only run what you need we dont want our code base to have  extra files we dont need which can cause unwanted bugs and perfomance issues.


Some other few improtant points when creating a rails app is to understand the control flow and how the user will interact with the app(what links to they need for the routes ). In addition don't be tempted to style the app in the begining as you may want to show it off, first build the** logic and  functionality **with the basic fetures then have fun.

Signing off,

**Sim** 

****References:****
* https://github.com/plataformatec/devise#the-devise-wiki
* https://github.com/hothero/awesome-rails-gem
* https://github.com/omniauth/omniauth
* https://www.ruby-toolbox.com/
