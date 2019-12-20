---
layout: post
title:      "Linkedin and Metadata"
date:       2019-12-20 18:54:04 +0000
permalink:  linkedin_and_metadata
---

What if you want to post a link to an article on LinkedIn and get a preview picture show up how does that work?

So  [LinkedIn scrapes](https://www.linkedin.com/help/linkedin/answer/46687/making-your-website-shareable-on-linkedin?lang=en) the metadata which is inside the head of the HTML page, If you just have a plain HTML CSS JS site then you just add these lines of code 


```HTML
<meta property='og:title' content="Title of the article"/>
<meta property='og:image' content="//media.example.com/ 1234567.jpg"/>
<meta property='og:description' content="Description that will show in the preview"/>
<meta property='og:url' content="//www.example.com/URL of the article" />```



LinkedIn uses the [Open Graph protocol](https://ogp.me/)  So the one we need  to get  a preview image for our posts is 

```<meta property='og:image' content="//media.example.com/ 1234567.jpg"/>```

<a href="https://imgur.com/rrAByCq"><img src="https://i.imgur.com/rrAByCql.png" title="source: imgur.com" /></a>


Og stands for Open Graph which creates an object from the metadata tags.It can have many different attributes like title or image. If you are not sure what the metadata of site will display LinkedIn has a great tool to [inspect the output](https://www.linkedin.com/post-inspector/). So just type in the URL you want to check, it will scrape that website’s Metadata and display it for you to see.
<a href="https://imgur.com/SIIz8Rv"><img src="https://i.imgur.com/SIIz8Rvl.png" title="source: imgur.com" /></a>


If you are using a framework like React or even Gatsby it is a little tricker. You have to figure out which folder your image content is stored. Additionally , make sure to find the root HTML it will be in a folder Public with a file name of  index.html. add the metadata tags there.


One piece of advice I would add, sometimes you change the website but LinkedIn has the old old metadata. A  good workaround is to use the inspector tool as this scrapes and guarantees that the metadata is accurate. 


All the best,

Simcha Greenbaum

