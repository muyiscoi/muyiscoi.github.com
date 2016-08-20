---
id: 755
title: Destruction by Forward Slash
date: 2015-07-16T14:27:16+00:00
author: muyiscoi
layout: post
guid: http://www.muyiscoi.com/?p=755
permalink: /?p=755
categories:
  - Technology
tags:
  - bash
  - linux
  - plex media server
  - server
---
I deployed a Raspberry Pi2 server at home to act as my Plex Media server and it has been working well for over a week now. I am also using it to learn more about server administration. Today, I realized that I had a lot of files in the Trash of my external hard drive connected to the Pi and decided to sort them out.

While doing the sorting, I intended to run this command

> mv \*/\*.* .

but instead, ran

> mv /\*/\*.* /

as root user.

If you&#8217;re familiar with the Linux command line, you realize the epic mistake I made. I realized the problem a little too late though, and now my server is completely ruined. Gotta go back home and reprovision everything from scratch.

Guess I have to be more careful in the future. See what forward slash in the wrong places can cause!.