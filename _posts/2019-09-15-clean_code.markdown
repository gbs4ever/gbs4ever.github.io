---
layout: post
title:      "Clean Code"
date:       2019-09-15 00:29:38 -0400
permalink:  clean_code
---

As software developers, we are always trying to solve a problem whether it is a task that we have always been doing manually and want to be automated or a feature we want to add. The first thing we need to do is to think, then again think. Why? I know how to do it already.

The answer is the way you want to fix it might not be the best option. We need to ask ourselves,
* What are our needs (our client's)? 
* What are the pros and cons of this option?
* What has the quickest turn around?

Don't just build something because you can even if it can be done quickly. One example let's say we want to have a form submission on a static website There are two ways we can do it build a back-end server to deal with the form submission, then host the server somewhere or sign up for form spree and add this line,
```<form action="https://formspree.io/email@domain.tld" method="POST">
 <input type="text" name="name">
 <input type="email" name="_replyto">
 <input type="submit" value="Send">
</form>```

If we have this outlook and spend the time to think things over it will save us many hours of frustration and  we will learn to build cleaner code. I heard a great talk from [Shmuel Rosansky](https://www.linkedin.com/in/shmuelr/)  a Tech Lead at Google about clean code so  I thought I would share what I learnt.


## How to build Clean code 
1. Naming variables - You should be as expressive as possible, your code should read like a book that any other developer would understand(which might be you 2 weeks later). What is the code trying to accomplish? Comments are great to help you come back to your code and understand it but if you need to use comments to often time to rethink your variables.
2. One action -You should try to limit your methods to one action. They are easier to write, easier to read, easier to debug and easier to test. We should have one method that will call the other two methods.      <a href="https://imgur.com/wj3OZQO"><img src="https://i.imgur.com/wj3OZQOm.png" title="source: imgur.com" /></a>
3. You might hear about how singletons are great but they are highly prone to bugs, we build methods that should be predictable based on the input the output would be. [Click here ](https://cocoacasts.com/are-singletons-bad) to find out more.
4. [DRY](https://www.codementor.io/joshuaaroke/dry-code-vs-wet-code-89xjwv11w) -don't repeat yourself, extract code and call that method the rule of thumb don't repeat yourself 3 times. 
5. Lint checker - we need to keep to the styles of the language, we cant have laws without enforcement. There are many bots you can run to check as you submit a commit.
6. Testing you must test your code !! The best way is to build tests (like [TDD](http://agiledata.org/essays/tdd.html)) which can be automated that validate our code or at the very least you must manually test the code. The truth is doing both gives you much more coverage.
7. Continuous build- even if you are running a test against the new feature but how does it react with the current version of the full project? There are many different options you can test the whole repo which in a big environment might take a long time or we can just test the dependences. For instance, a few of my projects when I commit to Netlify it rebuilds the new commit ensuring that the code which was added can build correctly in a production environment.



Signing off

Sim Greenbaum





