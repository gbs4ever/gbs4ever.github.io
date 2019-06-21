---
layout: post
title:      "Async JavaScript"
date:       2019-06-21 01:59:06 -0400
permalink:  async_javascript
---


What is Async javascript ? Why  do we need it ? How will it affect us coding?


Async Javascript means Js will wait to  fully run that function(like a fetch) and just send back a promise object till   it resolves.It operates asynchronously using the event loop.We will talk more later how we code this, I think it is important to understand why the language was designed this way. 


JS is a single thread programming language basically it can only think(execute) and do one thing at a time. When our code needs to fetch from an API  it would need to choose one of two options. It could either  wait for the API and do nothing till it gets a response which seems like a really slow program. Rather it    sends back  a promise object that is telling the code you will get a response but  let me take care of some other stuff while I wait. So Async JS was designed because it can't multi-task so  when it receives a response it will finish off the code. We give it very clear instructions which snippet of code to run after it receives a response. This can get very confusing sometimes, so to keep  reviewing this topic is a very  important skill.In some other languages like ROR and Java which are multi thread it is not essential to have this option.When you start learning a new language and you come across Async you might think” this annoying and why  can't everything just  run synchronously” but now we see that if a language is a single thread ,** it needs Async to be able to perform well.**

So let's look at some code as if we were fetching from an API
``fetch("http://some.API", {
     method: "POST",
     credentials: "include",
     headers: {
       "Content-Type": "application/json"
     },
     body: JSON.stringify(data)
   }
   ).then(r => r.json())``
	 

 This is our fetch, we add a .then which means only run after the promise has been resolved  `r` here just a placeholder for  the response and we change it into json. Now we are ready to work with our data  `.then(d => { console.log("d)}` so this will only console.log after it receives a response  from the server, no matter what the response is . One more important point that I think is worth mentioning is to look at a whole logic flow  and see what happens first 


``callApi = () => {
    console.log('1')
     fetch("http://lsomeApi", {
      credentials: "include",
      method: "get",
      headers: {
        "Content-Type": "application/json"
      },``
``}
    ).then(r => (
      console.log('3')
       r.json())
      .then(d => {
        console.log('4')
       })
      console.log('2')
}``

So as you  see the code executes not in the order you  might have thought but once you come accustomed  to it and get the hang of it , it will make a lot of sense and you will appreciate its necessity.


**Signing off **

Sim

Some additional reading.

[Async Js](https://www.sohamkamani.com/blog/2016/03/14/wrapping-your-head-around-async-programming/)


[Async-blog](https://codeburst.io/how-node-js-single-thread-mechanism-work-understanding-event-loop-in-nodejs-230f7440b0ea)

  

