---
id: 801
title: Self-Host all the things!
date: 2015-08-20T19:12:53+00:00
author: muyiscoi
layout: post
guid: http://muyiscoi.com/?p=801
permalink: /?p=801
categories:
  - Technology
tags:
  - keepassx
  - mail server
  - owncloud
  - passwords
  - self host
  - ssl
---
[<img class="size-full wp-image-802 aligncenter" src="https://muyiscoi.com/blog/wp-content/uploads/2015/08/1477559.jpg" alt="1477559" width="400" height="300" />](https://muyiscoi.com/blog/wp-content/uploads/2015/08/1477559.jpg)

I&#8217;ve been on a mission to self host as much stuff as possible. I am trying to improve my security on the web, as well as have more control over my data. I began by moving this blog from a shared hosting platform to Digital ocean. Next, I setup an email server on my domain, which gives me the ability to have *@muyiscoi.com email addresses. I naturally had to add an SSL cert to ensure that email clients don&#8217;t have trouble trusting my domain.

I have also setup owncloud on Digital ocean to facilitate syncing files between my devices without having to rely on third party services.

On the security side of things, I have gone round and enabled 2-factor Auth on as many services as I can that has that option. I have also changed virtually all my passwords to very strong passwords from an online Password generator, each account having its own password.

Naturally, I would not be able to remember all these passwords, so had to use a password manager. I setup KeepassX on the Fedora install on my laptop, and synchronized the keepass database file with Owncloud to my phone, and other devices. So, now, I can have access to all my passwords on any device I have that supports keepassx, which is virtually every OS at this point. The database file is protected as well, and I have setup pin codes on the apps, for an added layer of security.

This is an ongoing process, and I intend to implement more solutions to improve my control on the services I use, in turn having more control over my data and security.
  
The idea is to find a sweet spot that doesn&#8217;t sacrifice too much ease but provides better security.

&nbsp;