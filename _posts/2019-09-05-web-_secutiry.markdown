---
layout: post
title:      "Web-Security"
date:       2019-09-05 15:17:14 -0400
permalink: Web-Security
---


We are always reading in the new about security breach by some group of hackers and it seems like a never-ending battle between the white hats and the blackhats. That being said all developers must be secutriy-minded and secure our app and not blame the users.

## Password encryption 
> Bcrypt is a password hashing function designed by Niels Provos and David Mazières, based on the Blowfish cipher, and presented at USENIX in 1999.[1] Besides incorporating a salt to protect against rainbow table attacks, bcrypt is an adaptive function: over time, the iteration count can be increased to make it slower, so it remains resistant to brute-force search attacks even with increasing computation power.(https://www.wikipedia.org/)
 
In other words, it creates a hash  [check it out here](https://www.movable-type.co.uk/scripts/sha256.html) made up of your password and adding a salt or some random characters using the SHA-256 algorithm.

``hash(salt + password)    #=> <really unique hash>``

   This makes the process irreversible and an attacker cant get our password from the DB. So then how are we able to login and be authenticated?

In rails , we store the salt or kind of a key for the user inside the table, when a user logins in we retrieve the salt and we encrypt the entered password (and the salt) and see if it matches the stored password.

All we need to do is  just add this abstracted line to the user model.
``has_secure_password`` 

which is really doing this!


<a href="https://imgur.com/Vuve83e"><img src="https://i.imgur.com/Vuve83el.png" title="source: imgur.com" /></a>

Why do we need to salt , what are we gaining ?

An attacker could really just create a database using the same algorithm of hashes running all possible passwords. Then just try to get a match against our database. So we add salt which is 4 random characters that are unknown to the attacker. We store this in the user column and the end of the hash to retrieve.

Now that we have created an encrypted password what else can we do? 
* Require users to sign up and log in to access our app helps us keep track of “bad users which we can ban”
* Having a security audit
* There are many more ideas to implement but  that will be for future blogs 

[Google](https://www.bleepingcomputer.com/news/google/google-chrome-to-warn-if-logins-are-found-in-a-data-breach/) Has come out with an extension to chrome that will search your credentials against know breached user name and password but how are they doing this?


<a href="https://imgur.com/NZC94P2"><img src="https://i.imgur.com/NZC94P2l.png" title="source: imgur.com" /></a>
 
 I'm not 100 per cent sure but i think they are hashing your password and matching them against breached hashes but I would   <a href="mailto:gbs4ever2@gmail.com">love to hear your opinion </a> ?

All the best,

Simcha Greenbaum





**References**

* [Bcrypt](https://github.com/codahale/bcrypt-ruby)
* [Firefox-fix](https://www.troyhunt.com/were-baking-have-i-been-pwned-into-firefox-and-1password/)
* [Google](https://www.bleepingcomputer.com/news/google/google-chrome-to-warn-if-logins-are-found-in-a-data-breach/)





