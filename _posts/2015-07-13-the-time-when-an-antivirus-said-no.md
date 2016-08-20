---
id: 736
title: The time when an Antivirus said no!
date: 2015-07-13T12:00:08+00:00
author: muyiscoi
layout: post
guid: http://www.muyiscoi.com/?p=736
permalink: /?p=736
categories:
  - Stories
tags:
  - avast antivirus
  - technology
  - troubleshooting
---
<span style="line-height: 1.7;"><em>These are a series of posts from my time working in the retail division of the Commercial department at a major Nigerian Telco.</em></span>

<span style="line-height: 1.7;">I was the guy that always got to troubleshoot issues regarding internet connection on laptops, phones or tablets. Most of the time, the problem was easy to determine. It usually revolved around configuration on installation of Internet services on the customer&#8217;s account. In the case of Windows 8 laptops, the older modems have outdated drivers and so do not function reliably. There are a few other issues that cause browsing issues on devices, but generally, after a few months, I had them all to a fine science.</span>

So, I was indeed stumped when I couldn&#8217;t figure out what was wrong with a customer&#8217;s laptop one certain day. He had the newest modem, so it wasn&#8217;t a drivers issue. His line had all the necessary services installed on them (and I even reinstalled them just to be safe) so that wasn&#8217;t it either. The MiFi connected successfully; it just didn&#8217;t browse. No upload or download going on, despite the fact that the customer had just recharged a large amount of data on his line.

The modem worked on other devices though, so the problem was from the Laptop. I tried practically every trick I knew to troubleshoot it, and eventually decided that the problem must be from one of the installed software on the laptop. In cases like that, the likely culprit is the Antivirus software, in this case, Avast Antivirus. However, no customer would allow you to uninstall the Antivirus from his/her laptop, and I wouldn&#8217;t want to do so anyway.

Eventually, I had to go through thousands of options the Avast antivirus provides until I came across the &#8220;web shield&#8221; option. This option is supposed to make Avast act like a proxy and filter all packets to and from the internet, blocking malicious packets from coming though. Unfortunately, it was doing its job a bit too well and ended up blocking all packets instead of just the malicious ones.

Once &#8220;web shield&#8221; had been disabled, The internet immediately started working on the customer&#8217;s laptop and all was well with the world again.

I promptly sent an email to our &#8220;Geek Force&#8221; internal mailing list to inform everyone of the issue so they don&#8217;t have to go through what I did.