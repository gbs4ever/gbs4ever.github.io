---
layout: post
title:      "WSL -Windows Subsystem for Linux"
date:       2019-03-07 21:47:44 -0500
permalink:  wsl_-windows_subsystem_for_linux
---


It seems that most programmers love the mac and refuse to look at a pc, which is true, as mac comes preinstalled with a lot of stuff to set up a local environment.However, you might need to write some programs that are only windows based (.net framework) or your future client needs software for his business that only works on a pc.

**Now what?** 
But windows doesn't have bash or many of the  Linux based commands, so I need to stay on a mac which is Unix based.Well, we could try a dual-boot or a virtualbox on windows, I think just mentioning those  can make all of us go mad !! 


<a href="https://imgur.com/JxW1PVn"><img src="https://i.imgur.com/JxW1PVnh.png" title="source: imgur.com" /></a>





Well, In  Windows 10 has figured it out with  WSL -Windows Subsystem for Linux. I won't explain all the boring stuff but basically, it lets us install Ubuntu and use Linux based commands, programming language interpreters like Ruby and Python and a bunch of other cool stuff. We get the best of both worlds!!!

 We still need to understand how this works, basically, there is a connection or a *tunnel* from the MNT directory in Linux to the C:  drive in windows. But your Linux user name and programs are in the home directory of Linux.  There is one very important point to keep in mind is we want to use this setup only as a *one-way street*. We should only store our projects and files in our windows directory, **we use Linux to work or translate those files**(our gems and Linux codes would be saved in Linux home Dir)In newer builds of win 10 they did open it to a 2 way street, but that can get very confusing very fast. [For more info click here](https://blogs.msdn.microsoft.com/commandline/2016/11/17/do-not-change-linux-files-using-windows-apps-and-tools/)
 
 
 
 <a href="https://imgur.com/Qrt9iwU"><img src="https://i.imgur.com/Qrt9iwUl.png" title="source: imgur.com" /></a>
 
 
 
 


So to recap we only use Linux to operate on our Windows files, therefore our text editor and most of the programs we use we should only install the windows version. If you [click here](https://github.com/micahshute/wsl-setup) it gives you step by step instructions on how to get it all set up and you can do your learn.co labs on a local environment. One last thing to keep in mind if you have more than one hard drive or a partitioned  hard drive as of now, **you can only use bash on your c: drive where your main OS lives.**



Coding can be fun and frustrating at the same, time sounds weird, like either you like it or you hate it. Well welcome to be being a true developer, the frustration is our minds and brains trying to learn and retain a new concept and the fun comes from seeing how much we can do with programming. **To all future dev’s do not I repeat do not let the frustration kill that love and passion you have for coding !! As you move along hopefully there will be less frustration.**


Signing off

**SIM**



Links:
1. [Micahshute wsl-setup](https://github.com/micahshute/wsl-setup)
2. [Basic linux commands](https://maker.pro/linux/tutorial/basic-linux-commands-for-beginners)
3. [Microsoft](https://docs.microsoft.com/en-us/windows/wsl/install-win10)
 

