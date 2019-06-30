---
layout: post
title:      "CLI Project "
date:       2019-02-10 22:37:52 -0500
permalink:  cli_project
---




**Remember success is never owned it is only rented and rent is due every day!!**
 


I would guess that my CLI project had the most curveballs thrown at it. First I choose to scrape Amazon, the daily deals of Amazon. I hit two major problems, first there were over 30 pages to scrape, second their links were being manipulated by JS “ there goes one day”.

So someone gave me the idea that instead of the daily deal’s of Amazon find a website that has less traffic; sounds like a good idea? So let's try  Best Buy!  

The first problem I ran into was, that the page I needed to scrape with the daily deal had many ID numbers in the URL which meant there is a higher chance that the URL would change as many websites do. To overcome this problem I first scrapped www.bestbuy.com just to get the correct URL to scrape data from.  The next thing I worked on was to scrape the data from the “2nd” page which had its ups and downs but as I closed for the night at least I felt a sense of accomplishment I had got most of the data from level one. ( a little short lived lol)

The next morning I woke to see that best buy had changed the site and instead of an option to  'add to your cart' and purchase it was just giving a coupon to buy two different pieces of software. My CLI had broken and was spitting back false data oh no, now what!!!  With encouragement from some classmates, I wrote a conditional to check for the words “add cart” that should solve the problem ? Nope, since Best buy uses the same CSS selector on the whole page my conditional always returned true. Back to the drawing board!

I finally  realized that the page is split in two parts  so just check the top half !! (yay)  It worked, now to code out the CLI and all the classes etc. I think you get the drift one problem after the next but for some reason most of the time I took it with a smile on my face (i don't know how or why )and just learnt that this is the way of life “life throws you lemons make lemonade” just go with the flow. A few  important lessons this project taught me was to think out of the box ,not be scared of errors and  to  not be open  to take help from anyone.



All the best

**SIM**

