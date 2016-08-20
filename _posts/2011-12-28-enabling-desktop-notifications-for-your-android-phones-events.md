---
id: 218
title: 'Enabling desktop notifications for your Android Phone&#8217;s events'
date: 2011-12-28T22:36:43+00:00
author: muyiscoi
layout: post
guid: http://muyiscoi.com/?p=218
permalink: /?p=218
dsq_thread_id:
  - 519220397
categories:
  - Technology
tags:
  - android
  - android notifier
  - desktop
  - notification
  - phones
  - samsung galay fit
  - ubuntu
---
I recently joined the world of smartphones with a purchase of a [Samsung Galaxy Fit](http://www.gsmarena.com/samsung_galaxy_fit_s5670-3726.php). I mulled over the idea of doing a review of the phone for a while but later decided against it. The major reason being that there is nothing really spectacular about the device (and I am just too lazy to do it 🙂 ).
  
It is a budget Android phone running Android OS 2.2 (upgradeable to 2.3) with Samsung&#8217;s trademark TouchWiz UI. So far, I have enjoyed my experience with the phone and if you absolutely want a review, you can check out the one done by the guys over at [I recently joined the world of smartphones with a purchase of a [Samsung Galaxy Fit](http://www.gsmarena.com/samsung_galaxy_fit_s5670-3726.php). I mulled over the idea of doing a review of the phone for a while but later decided against it. The major reason being that there is nothing really spectacular about the device (and I am just too lazy to do it 🙂 ).
  
It is a budget Android phone running Android OS 2.2 (upgradeable to 2.3) with Samsung&#8217;s trademark TouchWiz UI. So far, I have enjoyed my experience with the phone and if you absolutely want a review, you can check out the one done by the guys over at](http://www.gsmarena.com/sansung_galaxy_fit-review-628.php) 

This post is about one of the cool things I have discovered while using the device.

**The Problem**

While on my laptop at home, I sometimes don&#8217;t remember where I dropped my phone, or forget to carry it along with me when going into another room. At other times, I might be watching a movie or listening to music with headphones on and not hear when the phone rings. As a result, I end up missing some calls and not seeing SMS messages on time, etc. I have had to endure this inconvenience for quite some time, however, with my purchase of a &#8220;smart phone&#8221;, I began looking for solutions. I found one that is perfect.

**<!--more-->The Solution**

Android Notifier is a two part application that you install on your Android Phone as well as your desktop operating system. It has versions for Windows, MacOSX and Linux; so all areas are covered. This is particularly of importance to me because I use [Ubuntu Linux](https://muyiscoi.com/2010/12/ubuntu-unity-and-gnome-shell/) for bulk of my computing on a day to day basis.

**How it works**

[Android Notifier](http://code.google.com/p/android-notifier/) works either by detecting the phone, if they are over the same local WiFi network, or by pairing both devices via Bluetooth. I chose the former method mainly because there is an always on WiFi network at home which my laptop and phone are always connected to.

Once Android Notifier has been setup, whenever you receive a call, an SMS, MMS, Battery Status notification, or virtually any other notification on your phone, you receive it as a notification on your computer as well. Don&#8217;t believe me? Let the screenshots below convince you!.

**The Result**

<div id="attachment_226" style="width: 310px" class="wp-caption aligncenter">
  <a href="https://muyiscoi.com/blog/wp-content/uploads/2011/12/Screenshot-at-2011-12-24-122025.png"><img class="size-medium wp-image-226" title="Screenshot at 2011-12-24 12:20:25" src="https://muyiscoi.com/blog/wp-content/uploads/2011/12/Screenshot-at-2011-12-24-122025-300x112.png" alt="" width="300" height="112" /></a>
  
  <p class="wp-caption-text">
    Ping test to confirm that "Aal izz Well"
  </p>
</div>

&nbsp;

<div id="attachment_221" style="width: 310px" class="wp-caption aligncenter">
  <a href="https://muyiscoi.com/blog/wp-content/uploads/2011/12/Screenshot-at-2011-12-24-122754.png"><img class="size-medium wp-image-221" title="Screenshot at 2011-12-24 12:27:54" src="https://muyiscoi.com/blog/wp-content/uploads/2011/12/Screenshot-at-2011-12-24-122754-300x110.png" alt="" width="300" height="110" /></a>
  
  <p class="wp-caption-text">
    Notification of a new SMS (actually came about a second before the phone chirped!)
  </p>
</div>

&nbsp;

<div id="attachment_219" style="width: 310px" class="wp-caption aligncenter">
  <a href="https://muyiscoi.com/blog/wp-content/uploads/2011/12/Screenshot-at-2011-12-26-162808.png"><img class="size-medium wp-image-219" title="Screenshot at 2011-12-26 16:28:08" src="https://muyiscoi.com/blog/wp-content/uploads/2011/12/Screenshot-at-2011-12-26-162808-300x107.png" alt="" width="300" height="107" /></a>
  
  <p class="wp-caption-text">
    Battery State Notification
  </p>
</div>

**Problems Encountered**

Setting up this service, I experienced a few minor issues. The main one was the fact that the notifications were not being properly rendered on Ubuntu. The application was not using the OS Notification System. So, instead of getting nice bubbles like those above, I got what is shown in the screenshot below

[<img class="aligncenter size-medium wp-image-222" title="Screenshot at 2011-12-24 12:11:33" src="https://muyiscoi.com/blog/wp-content/uploads/2011/12/Screenshot-at-2011-12-24-121133-300x195.png" alt="" width="300" height="195" />](https://muyiscoi.com/blog/wp-content/uploads/2011/12/Screenshot-at-2011-12-24-121133.png)I also noticed that I could not access the preferences of the Desktop Application.
  
I quickly realized that the problem lay with the recently deprecated notification tray which the application still used. In order to gain access to the application&#8217;s notification icon, I had to white-list it. If you are interested in how i did that, check out [this question thread on AskUbuntu](http://askubuntu.com/questions/30742/how-do-i-access-and-enable-more-icons-to-be-in-the-system-tray).

**Solving the Problems**

Once I had access to the Android Notifier&#8217;s notification tray icon, I could then access the preferences panel and change the notification display method to LibNotify, thereby making it appear native on Ubuntu.

**Final thoughts**

It puts a smile on my face whenever I see a notification from my phone on my laptop screen. The developers of Android Notifier have done a stellar job and made it no longer mandatory to always carry your phone with you everywhere you go around the house.

Resources

1. [Android Notifier Project page](http://code.google.com/p/android-notifier/)

2. [&#8220;Android Notifier&#8221; App on Android Market](https://market.android.com/details?id=org.damazio.notifier&hl=en)