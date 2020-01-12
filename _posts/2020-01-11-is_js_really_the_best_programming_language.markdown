---
layout: post
title:      " Is JS really the best programming language"
date:       2020-01-12 03:52:47 +0000
permalink:  is_js_really_the_best_programming_language
---


Well, I think the jury is still out on the one , only time will tell for sure. Javascript was created in 1995 by  Brendan Eich for Netscape Communications and has a very long history and I won’t bore you with all the details. What is important to know is javascript has become a language that is both Object-oriented and functional programming. This might make it more powerful but also harder to understand the many concepts behind the language. 

 ## Prototypical inheritance vs class 
In Ruby, we create a class think of it like a blueprint and methods are different actions that the object can do. The only way to create an object is by creating an instinance of the class.

Our map

```ruby
class House
  def initialize(name)
  end
end
```

Create the object
```House.new('gracie mansion')```


However in javascript even though now we have classes they are very different a class is really a misnomer as it really is just a bunch of key-value pairs bundled together; we can just us the {} syntax.

In javascript you are creating an object that gets its prototype inherent from a prototype to think of is as a father-son relationship. It will form a link to the main object. See below how our house  __proto__  Object() meaning its prototype point to the javaScript Object(). This is really confusing at first but it is essential to understand the working of the language. 


```javaScript
let house = {house:'gracie mansion'}
{house: "gracie mansion"}
house: "gracie mansion"
__proto__:
constructor: ƒ Object()
__defineGetter__: ƒ __defineGetter__()
__defineSetter__: ƒ __defineSetter__()
hasOwnProperty: ƒ hasOwnProperty()
__lookupGetter__: ƒ __lookupGetter__()
__lookupSetter__: ƒ __lookupSetter__()
isPrototypeOf: ƒ isPrototypeOf()
propertyIsEnumerable: ƒ propertyIsEnumerable()
toString: ƒ toString()
valueOf: ƒ valueOf()
toLocaleString: ƒ toLocaleString()
get __proto__: ƒ __proto__()
set __proto__: ƒ __proto__()
`````



All the best,

Simcha Greenbaum

[www.simchagreenbaum.dev](www.simchagreenbaum.dev)      
