---
layout: post
title:      "What is Gatsby.js ? "
date:       2019-12-13 18:02:54 +0000
permalink:  what_is_gatsby_js
---


Gatsby is based on React.js so if you have built any front-end site you will love it. But that is not just all it puts together so many of the great front-end tools like Webpack, React-router Graphql. 

As a developer, we have seen so many new frameworks that are supposed to make your life easier but one of two things happen, either it makes it harder or their docs are horrible. You spend way to much time figuring out-there design than building what your really wanted. Gatsby has great docs and many different plugins setup will be so much easier.

Now let’s get talk about the most important point it extremely fast as it builds the page from all dynamic data and static data to a static website. For example, my [portfolio](http://www.simchagreenbaum.dev)page is pulling data from GitHub and displaying it to the page. Gatsby is taking that data and at build time creat it into a single HTML page with my static website. You can host the webpage even on servers that only will send back static pages as that is truly what you send to the client. From the user perspective, the browser just needs to load one page from one data point.



When you building your Gatsby site make sure to watch the server logs and if it fails to build you will get vital information to help you debug what is exactly wrong. One example you have the correct code on your side but the API it is querying failed, the webpage might not load at all. So if you are pulling data from an API that tends to be, well “not the greatest “  this might not be the best option. 


As you can see my dev server ran the queries and built the  static page correctly without any  errors,


```success building schema - 1.681s```

```success createPages - 0.009s```

```success run queries - 2.732s - 5/5 1.83/s```

```success Building development bundle - 25.463s```



All the best,

Simcha Greenbaum



