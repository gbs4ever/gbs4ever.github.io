---
layout: post
title:      "Docker Basics "
date:       2019-11-08 14:51:12 -0500
permalink:  docker_basics
---


Why is docker so popular and what does it do? 

I think the best place to start is why there was a need for docker?

Imagine you spend a few weeks creating an app on your laptop and it works you able to load a local server. The next step is to deploy the app to a server. You are not a DevOps you just know how to write good clean code or maybe you can handle a little deploying but setting up the server to be the same environment and dependence as your local system this can be daunting to say the very least. 

The shipping industry had similar issues as they transport via train,truck, ship and each dock might have different tools to remove the package. So the industry created a shipping container standard (the doors are the same the lock is in the same place etc) We see them all over and don't think much about them but they serve a purpose the movers just need to worry how to fit the package into the container. 

So what is Docker ?
"A container is a special type of process that is isolated from other processes. Containers are assigned resources that no other process can access, and they cannot access any resources not explicitly assigned to them."


That is a little complicated but in simple terms, it can't access anything outside the "box" creating unnecessary bugs. First thing is to create a container of your code with all its dependencies and then send that image to the server. All you have to do is make sure is docker is installed on the server. Docker sits on top of Linux but works well with all operating systems.





<img src="https://docs.docker.com/images/VM%402x.png" alt="Virtual machine stack example" width="300px"style="float:left; ">


<img src="https://docs.docker.com/images/Container%402x.png" alt="Container stack example" width="300px"width="300px"style = "padding-left: 40px;" >


<p></p>

## How to get started 

1. Install docker desktop [here](https://www.docker.com/products/docker-desktop)
2. ```docker login ```  Make sure to login into docker 
3. ```docker run tutum/hello-world```     this will look for the repo and create an image   and run it 
4. ```docker ps -a```   this will show you a list of containers  and their names 
5. ```docker stop``   will stop the image by name 

There are many flags you will need to add when  you run your app





Stay tuned for more,

All the best,

Simcha Greenbaum



