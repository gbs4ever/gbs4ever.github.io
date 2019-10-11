---
layout: post
title:      "Basic Security Part 2"
date:       2019-10-11 19:57:38 +0000
permalink:  basic_security_part_2
---

The last blog we never got to explain our 3rd common vulnerability. 

## Cross-site Request Forgery

Why is this such an important topic?  Well imagine you go to a legitimate site like chase.com and login, the server recognizes your credentials and will now process any CRUD request. Well, our hacker has attached/embed a script that will run on your computer and pretend to be you and make requests to the server, as far as the server is concerned the requests are from you. It will assume you would like to transfer your 401k to some shady bank in the Caribbeans. There goes your hold retirement package! 


<a href="https://imgur.com/l71uSt9"><img src="https://i.imgur.com/l71uSt9l.png" title="source: imgur.com" /></a>



So how do we prevent this by making sure  there is a token in every header and that the server will only accept requests with that token. The tyipcal flow 

```protect_from_forgery with: :exception```

Like all rails “magic” we have one line that abstracts it all. Any Ajax or forms created by rails will automatically have a token and if we are using another front-end framework like React, the token will be inside the cookies. The common flow will be something like this.

1. The client request a form ( the CSRF token is hidden field and you won't see it on the page but it is there)
2. The client will submit the form with "hidden token" and  cookie 
3. The server will only process if both the cookie and token are correct 





>By default, Rails includes an unobtrusive scripting adapter, which adds a header called X-CSRF-Token with the security token on every non-GET Ajax call. Without this header, non-GET Ajax requests won't be accepted by Rails. When using another library to make Ajax calls, it is necessary to add the security token as a default header for Ajax calls in your library. To get the token, have a look at <meta name='csrf-token' content='THE-TOKEN'> tag printed by <%= csrf_meta_tags %> in your application view.

As you are building an app you might run into CSRF Token errors they might be really frustrating but know it is making the web a safer place. One important to raise with an  [XSS attack](http://simchagreenbaum.com/basic_security)  this could give the hacker access to the whole Dom and they could read the token and use it in a request.

All the best,

Simcha Greenbaum

For some great reading click  [here](https://medium.com/@charithra/introduction-to-csrf-a329badfca49) and [here](https://medium.com/rubyinside/a-deep-dive-into-csrf-protection-in-rails-19fa0a42c0ef) or see the [Rails Docs](https://guides.rubyonrails.org/security.html)



