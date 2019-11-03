---
layout: post
title:      "Programing  languages"
date:       2019-11-03 21:39:06 +0000
permalink:  programing_languages
---


Learning any programming language is not just about the syntax but more about what is really going on under the hood. pass by value,   pass by reference, mutable  or immutable. Why is this so important ? 

You might say why I can write and read the code,if you don’t understand what is really going you will be very confused by many bugs and  will have trouble even finding them. 

* Mutable - the value can be changed 
* Immutable - the value cant be changed 
* Pass by value - the variable contains the value 
* Pass by reference - the variable just point to a place in memory that holds that piece of data.

##  Mutable/immutable
In Ruby, stings can be mutated  this means we can directly change the string, let’s say there is a spelling mistake in the string you can just access it  and make a direct change 

``` string = "hellyworld"```

```string[4] = "o"```

```stirng => "helloworld"```

In python a string is immutable and cant be changed if we try to run the above code we will get an error 
```TypeError: 'str' object does not support item assignment``` 

which means strings cant to be changed. We would need to slice and copy what we want and add it to a new variable 

``` newString = string[:4] +"o" + string[5:] ```

```newStirng >>> "helloworld" ```

## Pass by value/ Pass by reference

In python a varibale that has an imutable (cant be changed) the value is actulayy saved inside  the variable and if we copy one variblie to another the original varibale will be on touched and the addition will only affect the new varible.

For exapmle

```addString = newStirng```

```addString + " simcha "```

This will return

```>>>' helloworld simcha'```

But if we check the old variable, 

``` newStirng  >>> 'helloworld'```


However, a List in python which is mutable the variable is just a reference to a place in memory that holds that data so saving to a new variable has just created a new reference to that data. Think of it like this in Windows sometimes we create an icon on our desktop, a  shortcut to a file path for quick access. If we would make a copy of it we are just making a copy of the shortcut not the file. The same thing in python with mutable data variables are only a reference or a shortcut to that data. The reason for this is a list can hold thousands of pieces of data and we might be changing only one of them with index lookup

```myList[35] = “change me”```

Instead of loading the whole list everytime we call the variable, there is just a reference that will only look at that index  speeding up the execution. These concepts are not just a simple syntax but trulyunderstanding the mechanics behind a language, to be a true good developer make sure you understand these concepts well.



Stay tuned for more,

All the best,

Simcha Greenbaum




