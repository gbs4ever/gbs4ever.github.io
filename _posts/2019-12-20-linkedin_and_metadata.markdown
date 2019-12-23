---
layout: post
title:      "Linkedin and Metadata"
date:       2019-12-20 13:54:06 -0500
permalink:  linkedin_and_metadata
---

Did you ever notice on Linkedin when you post a URL a cool preview picture shows up underneath? How does that work?

LinkedIn [scrapes](https://www.linkedin.com/help/linkedin/answer/46687/making-your-website-shareable-on-linkedin?lang=en) all the metadata which is located inside the Head tag of the HTML document, If you just have a plain HTML CSS JS site then all you need to do is just add these lines of code 


``` Html
<meta property='og:title' content="Title of the article"/>

<meta property='og:image' content="//media.example.com/ 1234567.jpg"/>

<meta property='og:description' content="Description that will show in the preview"/>

<meta property='og:url' content="//www.example.com/URL of the article" />
```



LinkedIn uses the Open Graph protocol, the code that  is important so we can get  a preview image for our posts is ,

```Html 
<meta property='og:image' content="//media.example.com/ 1234567.jpg"/>
```




Og stands for Open Graph which creates an object from the metadata tags.It can have many different attributes like title or image check out the docs [here](https://ogp.me/) . If you are not sure what the metadata of site will display LinkedIn has a great tool to [inspect the output](https://www.linkedin.com/post-inspector/). So just type in the URL you want to check, it will scrape that website’s Metadata and display it for you to see.


<a href="https://imgur.com/A1hqSQB"><img src="https://i.imgur.com/A1hqSQB.png" title="source: imgur.com" /></a>
<a href="https://imgur.com/5xYtTor"><img src="https://i.imgur.com/5xYtTor.png" title="source: imgur.com" /></a>

If you are using a framework like React or even Gatsby it is a little tricker. You have to figure out which folder your image content is stored. Additionally , make sure to find the root HTML it will be in a folder Public with a file name of  index.html. add the metadata tags there.


One piece of advice I would add, sometimes you change the website but LinkedIn has the old old metadata. A  good workaround is to use the inspector tool as this scrapes and guarantees that the metadata is accurate. 


All the best,

Simcha Greenbaum

