---
layout: post
title:      "Fetching from a Server"
date:       2019-08-22 18:57:57 -0400
permalink:  fetch_from_a_server
---


There is a common question among developers when they are building a new web app and retrieving from an API how should we fetch? If we are calling an external API do we pull data on the backend or front-end. To explain it on a little deeper level.

```javascript
$(".review").on("click", function (event) {
  event.preventDefault()
   let id = $(this).data("id")
   fetch(`www.someurl.com/books/${id}.json`).then(res => res.json())
     .then(data =>{console.log(data)}
	}}
)```
		 
When the user loads the page and creates the dom (and clicks the button) only then does the Js fire ; meaning whose computer just made that request the users. However if we were to be fetching that external api on the back-end even though the user triggered the server to fetch but whose computer actually fetched the data the server. 

Now that we have explained the difference between the two, let's discuss some pros and cons.  Many public API have [limits](http://developers.google.com/analytics/devguides/config/mgmt/v3/limits-quotas) on how many hits it can take from one person per month,  if the users computer makes the fetch each IP address is a different person and it will not reach the limits as fast. If we are fetching on the back-end our server’s IP address will hit the max limit on api calls very quickly even if the fetch may be triggered by a user. What it really boils down to is which computer is doing the work. In the old days  a personal computer was slow and there was a good chance the server was a  faster both in connection and computer speed) to get the data but with high speed internet and fast computers we seem to have forgotten this.

<a href="https://imgur.com/8UG2UDz"><img src="https://i.imgur.com/8UG2UDzl.png" title="source: imgur.com" /></a>


## Top  reasons why you would want to fetch on the backend 
1.  If this will be mobile app we want  the user experience to be great and with load times every second counts so there might be a lag .
2. If you target a population that works in areas that have weak cell or internet signal , there device will be much slower at getting that data from the external api .
3.  You may  want the data to be saved on the backend and it is easier to pass just the search query to the back -end .



This might be confusing but is important lesson to understand so even if doesn't make sense don't give up.


Signing off

**SIM**






