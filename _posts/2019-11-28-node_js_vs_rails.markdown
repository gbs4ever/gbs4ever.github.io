---
layout: post
title:      "Node.js VS Rails ?"
date:       2019-11-28 17:30:57 -0500
permalink:  node_js_vs_rails
---

<a href="https://imgur.com/yvd4d34"><img src="https://i.imgur.com/yvd4d34l.png" title="source: imgur.com" /></a>


Why is node.js so popular as a back-end server and what is so bad about Rails?   You are right a small app for a local shop so they could do some marketing but not a full eCommerce page most probably you won’t be getting that many hits.  Your costs will be minimal. However think twitter or even a small e-commerce website if you will be using a blocking I/O which means the lines are shared and everything runs synchronously, the way Active Record(an ORM) works. When we query the database while we wait for a response the server won’t process a new request on the other hand non-blocking I/O when we will query the database we wait for a response or as we call them today promises. While we are waiting we can move on to the next request till we get a response. Think of a checkout counter at the grocery we wait for the cashier to finish with the person in front of us who needs a price check on an item even if we only have two items (seems like a waste of time).

For example, imagine that at step 2 we are querying the Database or an API call and step 1.5 is another user trying to see our home page. The user won't have to wait for the DB or the API  to return to see our home page ,that  makes a much better user experience. 

```javascript 

console.log('step 1')
setTimeout(function () {
  console.log('step 2')
}, 1)
console.log('step 1.5?')
```


With this architecture, we have the ability to build a bigger and better system. In addition, Node.js is lightweight and more efficient. Scalability and server costs are the companies’ number one priority. If the site will be slow it makes less money, if the hosting server CPU costs are high their profit margin will be smaller. Being a developer is not just about being able to write or even debug code. You need to understand things on a deeper level as this will help you decide what technologies are a good fit for each project.

 
 
 All the best,

Simcha Greenbaum


