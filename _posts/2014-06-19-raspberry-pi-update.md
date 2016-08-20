---
id: 621
title: Raspberry Pi update
date: 2014-06-19T07:52:03+00:00
author: muyiscoi
layout: post
guid: http://www.muyiscoi.com/?p=621
permalink: /?p=621
categories:
  - Technology
tags:
  - Raspberry Pi
  - Raspbmc
  - xbmc
---
So, it&#8217;s been a while, and I thought I should post up an update to my travails with the Raspberry pi.
  
Since I last posted about it, I&#8217;ve probably pivoted like twice on what I&#8217;ve used it for, but all that isn&#8217;t important. What&#8217;s important is what it&#8217;s being used for at the moment.
  
On a related note, one of the pi&#8217;s died out on me recently. I blame the terribly inconsistent power supply and unstable power generating sets. It could just be that the SD card slot has a bent pin though. I haven&#8217;t really had time to examine it, and all the lights still come up when I put it on, so I&#8217;m still hopeful.
  
Since I have another pi and, for now at least, only need one, I&#8217;m not too bothered.

So, on to what I&#8217;m doing with it.
  
I decided that using one pi only for xbmc and another as a file server was a waste, so I decided to combine both functions into one, and so far, it seems to work quite nicely.
  
I am now running Raspbmc as the base distro, which is based on Raspbian, so I have a very familiar debian base to work with.
  
Once I got xbmc up and running, doing all the updates and what not, I installed &#8220;XBMCtorrent&#8221; addon.
  
XBMCtorrent basically does the same thing as Popcorntime, but it proceeds it. It works as you&#8217;ll expect, and if you don&#8217;t know what popcorntime is, Google it.
  
Once I had that installed, I configured a static IP so I could SSH into the OS from my laptop.
  
From console on my laptop, I did an apt-get update, installed samba and bit torrent sync.
  
I then configured some folders to sync from my laptop to the external hdd connected to the pi. Again, if your unfamiliar with samba or bittorrent sync, Google it! :).

So, now, I&#8217;ve got a fully functional xbmc box with online media streaming capability via xbmctorrent, and local storage via the external hdd connected to it where I have my media collection properly indexed with metadata by xbmc.
  
On the same box, I also have shared folder capability with samba, even to Windows boxes,&nbsp; and Dropbox like syncing, albeit on a local network, across all my devices.

It&#8217;s a pretty sweet setup that I&#8217;m sure I&#8217;ll continue tweaking in the future, plus, now I have to look for something for the other pi to do, assuming it&#8217;s still working of course.