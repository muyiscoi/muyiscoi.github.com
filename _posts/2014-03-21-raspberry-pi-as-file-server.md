---
id: 576
title: Raspberry Pi as File server
date: 2014-03-21T19:24:24+00:00
author: muyiscoi
layout: post
guid: http://www.muyiscoi.com/?p=576
permalink: /?p=576
categories:
  - Technology
tags:
  - file server
  - linux
  - openelec
  - Raspberry Pi
  - Raspbian
  - Raspbmc
---
<div id="attachment_589" style="width: 590px" class="wp-caption aligncenter">
  <a href="http://www.muyiscoi.com/blog/wp-content/uploads/2014/03/20140319_001115.jpg"><img class=" wp-image-589" alt="20140319_001115" src="http://www.muyiscoi.com/blog/wp-content/uploads/2014/03/20140319_001115-580x435.jpg" width="580" height="435" srcset="https://muyiscoi.com/blog/wp-content/uploads/2014/03/20140319_001115-580x435.jpg 580w, https://muyiscoi.com/blog/wp-content/uploads/2014/03/20140319_001115-940x705.jpg 940w, https://muyiscoi.com/blog/wp-content/uploads/2014/03/20140319_001115.jpg 1024w" sizes="(max-width: 580px) 100vw, 580px" /></a>
  
  <p class="wp-caption-text">
    Raspbian running on the Pi
  </p>
</div>

<p style="text-align: left;">
  I&#8217;ve been using the Raspberry Pi as a home theatre PC for a while now, however, since it doesn&#8217;t have a dedicated storage, I have had issues getting media on to the TV. I initially used  <a href="https://plex.tv/">Plex</a>, with Plex media server running on my laptop, RasPlex running on the RPi and Plex clients for Android and iOS on my phone and iPad respectively. This setup worked for a while, but it meant that I had to have my laptop on all the time. Also, updates to plex would routinely break some of the functionality, and after a while, this got pretty frustrating. I finally decided to dump this method and reloaded the Pi&#8217;s SD card with OpenELEC.
</p>

<div id="attachment_606" style="width: 590px" class="wp-caption aligncenter">
  <a href="http://www.muyiscoi.com/blog/wp-content/uploads/2014/03/vlcsnap-2014-03-21-20h01m40s53.png"><img class=" wp-image-606" title="OpenELEC XBMC" alt="vlcsnap-2014-03-21-20h01m40s53" src="http://www.muyiscoi.com/blog/wp-content/uploads/2014/03/vlcsnap-2014-03-21-20h01m40s53-580x326.png" width="580" height="326" srcset="https://muyiscoi.com/blog/wp-content/uploads/2014/03/vlcsnap-2014-03-21-20h01m40s53-580x326.png 580w, https://muyiscoi.com/blog/wp-content/uploads/2014/03/vlcsnap-2014-03-21-20h01m40s53-940x528.png 940w" sizes="(max-width: 580px) 100vw, 580px" /></a>
  
  <p class="wp-caption-text">
    OpenELEC XBMC
  </p>
</div>

<p style="text-align: left;">
  OpenELEC is basically a stripped down embedded operating system running XBMC. It is lightweight and runs smoothly on the Pi. Once I had that installed though, I had to figure out a way to get my media to OpenELEC without needing my laptop to be on all the time. Theoretically, I could just connect an external hard drive to one of the USB ports of the RPi and play the media that way, however, that would mean I would have to remove it and connect to my laptop whenever I need to add or remove a file to it. This can get tedious really quickly. Instead, I decided to buy another Raspberry Pi, this time locally from the fine folks at CoCreation Hub.
</p>

<p style="text-align: left;">
  I setup the second Pi as a file server which acts as storage for my media files streaming to OpenELEC on the other Pi, as well as general storage and backup server. For this, I used Raspbian (Debian Linux for Rapsberry Pi) with is the recommended Linux distribution for the Pi.
</p>

<p style="text-align: left;">
  I did some preliminary configuration such as setting a static IP and creating users directly on the device with its video out hooked up to a tv and a keyboard connected to it.<br /> Once I had it on a network, I did the rest of the configuration like device automount and samba (smb) file sharing over SSH on my Ubuntu laptop.
</p>

<p style="text-align: left;">
  I also configured weekly backup of my files from ubuntu using the default backup utility over SFTP, as well as adding a permanent bookmark to the network drive to my file manager for easy access.
</p>

<div id='gallery-2' class='gallery galleryid-576 gallery-columns-3 gallery-size-thumbnail'>
  <dl class='gallery-item'>
    <dt class='gallery-icon landscape'>
      <a href='https://muyiscoi.com/?attachment_id=603'><img width="150" height="150" src="https://muyiscoi.com/blog/wp-content/uploads/2014/03/20140318_235715-150x150.jpg" class="attachment-thumbnail size-thumbnail" alt="20140318_235715" /></a>
    </dt>
  </dl>
  
  <dl class='gallery-item'>
    <dt class='gallery-icon landscape'>
      <a href='https://muyiscoi.com/?attachment_id=602'><img width="150" height="150" src="https://muyiscoi.com/blog/wp-content/uploads/2014/03/20140318_235723-150x150.jpg" class="attachment-thumbnail size-thumbnail" alt="20140318_235723" /></a>
    </dt>
  </dl>
  
  <dl class='gallery-item'>
    <dt class='gallery-icon landscape'>
      <a href='https://muyiscoi.com/?attachment_id=601'><img width="150" height="150" src="https://muyiscoi.com/blog/wp-content/uploads/2014/03/20140318_211454-150x150.jpg" class="attachment-thumbnail size-thumbnail" alt="20140318_211454" /></a>
    </dt>
  </dl>
  
  <br style="clear: both" />
  
  <dl class='gallery-item'>
    <dt class='gallery-icon landscape'>
      <a href='https://muyiscoi.com/?attachment_id=600'><img width="150" height="150" src="https://muyiscoi.com/blog/wp-content/uploads/2014/03/20140318_211146-150x150.jpg" class="attachment-thumbnail size-thumbnail" alt="20140318_211146" /></a>
    </dt>
  </dl>
  
  <dl class='gallery-item'>
    <dt class='gallery-icon landscape'>
      <a href='https://muyiscoi.com/?attachment_id=599'><img width="150" height="150" src="https://muyiscoi.com/blog/wp-content/uploads/2014/03/20140318_235955-150x150.jpg" class="attachment-thumbnail size-thumbnail" alt="20140318_235955" /></a>
    </dt>
  </dl>
  
  <dl class='gallery-item'>
    <dt class='gallery-icon landscape'>
      <a href='https://muyiscoi.com/?attachment_id=598'><img width="150" height="150" src="https://muyiscoi.com/blog/wp-content/uploads/2014/03/20140318_235943-150x150.jpg" class="attachment-thumbnail size-thumbnail" alt="20140318_235943" /></a>
    </dt>
  </dl>
  
  <br style="clear: both" />
  
  <dl class='gallery-item'>
    <dt class='gallery-icon landscape'>
      <a href='https://muyiscoi.com/?attachment_id=597'><img width="150" height="150" src="https://muyiscoi.com/blog/wp-content/uploads/2014/03/20140318_235928-150x150.jpg" class="attachment-thumbnail size-thumbnail" alt="20140318_235928" /></a>
    </dt>
  </dl>
  
  <dl class='gallery-item'>
    <dt class='gallery-icon landscape'>
      <a href='https://muyiscoi.com/?attachment_id=596'><img width="150" height="150" src="https://muyiscoi.com/blog/wp-content/uploads/2014/03/20140319_000521-150x150.jpg" class="attachment-thumbnail size-thumbnail" alt="20140319_000521" /></a>
    </dt>
  </dl>
  
  <dl class='gallery-item'>
    <dt class='gallery-icon landscape'>
      <a href='https://muyiscoi.com/?attachment_id=595'><img width="150" height="150" src="https://muyiscoi.com/blog/wp-content/uploads/2014/03/20140319_000438-150x150.jpg" class="attachment-thumbnail size-thumbnail" alt="20140319_000438" /></a>
    </dt>
  </dl>
  
  <br style="clear: both" />
  
  <dl class='gallery-item'>
    <dt class='gallery-icon landscape'>
      <a href='https://muyiscoi.com/?attachment_id=594'><img width="150" height="150" src="https://muyiscoi.com/blog/wp-content/uploads/2014/03/20140319_000004-150x150.jpg" class="attachment-thumbnail size-thumbnail" alt="20140319_000004" /></a>
    </dt>
  </dl>
  
  <dl class='gallery-item'>
    <dt class='gallery-icon landscape'>
      <a href='https://muyiscoi.com/?attachment_id=593'><img width="150" height="150" src="https://muyiscoi.com/blog/wp-content/uploads/2014/03/20140319_000108-150x150.jpg" class="attachment-thumbnail size-thumbnail" alt="20140319_000108" /></a>
    </dt>
  </dl>
  
  <dl class='gallery-item'>
    <dt class='gallery-icon landscape'>
      <a href='https://muyiscoi.com/?attachment_id=592'><img width="150" height="150" src="https://muyiscoi.com/blog/wp-content/uploads/2014/03/20140319_000856-150x150.jpg" class="attachment-thumbnail size-thumbnail" alt="20140319_000856" /></a>
    </dt>
  </dl>
  
  <br style="clear: both" />
  
  <dl class='gallery-item'>
    <dt class='gallery-icon landscape'>
      <a href='https://muyiscoi.com/?attachment_id=591'><img width="150" height="150" src="https://muyiscoi.com/blog/wp-content/uploads/2014/03/20140319_000844-150x150.jpg" class="attachment-thumbnail size-thumbnail" alt="20140319_000844" /></a>
    </dt>
  </dl>
  
  <dl class='gallery-item'>
    <dt class='gallery-icon landscape'>
      <a href='https://muyiscoi.com/?attachment_id=590'><img width="150" height="150" src="https://muyiscoi.com/blog/wp-content/uploads/2014/03/20140319_000816-150x150.jpg" class="attachment-thumbnail size-thumbnail" alt="20140319_000816" /></a>
    </dt>
  </dl>
  
  <dl class='gallery-item'>
    <dt class='gallery-icon landscape'>
      <a href='https://muyiscoi.com/?attachment_id=589'><img width="150" height="150" src="https://muyiscoi.com/blog/wp-content/uploads/2014/03/20140319_001115-150x150.jpg" class="attachment-thumbnail size-thumbnail" alt="20140319_001115" /></a>
    </dt>
  </dl>
  
  <br style="clear: both" />
  
  <dl class='gallery-item'>
    <dt class='gallery-icon landscape'>
      <a href='https://muyiscoi.com/?attachment_id=588'><img width="150" height="150" src="https://muyiscoi.com/blog/wp-content/uploads/2014/03/20140319_000905-150x150.jpg" class="attachment-thumbnail size-thumbnail" alt="20140319_000905" /></a>
    </dt>
  </dl>
  
  <dl class='gallery-item'>
    <dt class='gallery-icon landscape'>
      <a href='https://muyiscoi.com/?attachment_id=587'><img width="150" height="150" src="https://muyiscoi.com/blog/wp-content/uploads/2014/03/20140319_000918-150x150.jpg" class="attachment-thumbnail size-thumbnail" alt="20140319_000918" /></a>
    </dt>
  </dl>
  
  <dl class='gallery-item'>
    <dt class='gallery-icon landscape'>
      <a href='https://muyiscoi.com/?attachment_id=586'><img width="150" height="150" src="https://muyiscoi.com/blog/wp-content/uploads/2014/03/20140319_001748-150x150.jpg" class="attachment-thumbnail size-thumbnail" alt="20140319_001748" /></a>
    </dt>
  </dl>
  
  <br style="clear: both" />
  
  <dl class='gallery-item'>
    <dt class='gallery-icon landscape'>
      <a href='https://muyiscoi.com/?attachment_id=585'><img width="150" height="150" src="https://muyiscoi.com/blog/wp-content/uploads/2014/03/20140319_001741-150x150.jpg" class="attachment-thumbnail size-thumbnail" alt="20140319_001741" /></a>
    </dt>
  </dl>
  
  <dl class='gallery-item'>
    <dt class='gallery-icon landscape'>
      <a href='https://muyiscoi.com/?attachment_id=584'><img width="150" height="150" src="https://muyiscoi.com/blog/wp-content/uploads/2014/03/20140319_001132-150x150.jpg" class="attachment-thumbnail size-thumbnail" alt="20140319_001132" /></a>
    </dt>
  </dl>
  
  <dl class='gallery-item'>
    <dt class='gallery-icon landscape'>
      <a href='https://muyiscoi.com/?attachment_id=583'><img width="150" height="150" src="https://muyiscoi.com/blog/wp-content/uploads/2014/03/20140319_001543-150x150.jpg" class="attachment-thumbnail size-thumbnail" alt="20140319_001543" /></a>
    </dt>
  </dl>
  
  <br style="clear: both" />
  
  <dl class='gallery-item'>
    <dt class='gallery-icon landscape'>
      <a href='https://muyiscoi.com/?attachment_id=582'><img width="150" height="150" src="https://muyiscoi.com/blog/wp-content/uploads/2014/03/20140319_002459-150x150.jpg" class="attachment-thumbnail size-thumbnail" alt="20140319_002459" /></a>
    </dt>
  </dl>
  
  <dl class='gallery-item'>
    <dt class='gallery-icon landscape'>
      <a href='https://muyiscoi.com/?attachment_id=581'><img width="150" height="150" src="https://muyiscoi.com/blog/wp-content/uploads/2014/03/20140319_002302-150x150.jpg" class="attachment-thumbnail size-thumbnail" alt="20140319_002302" /></a>
    </dt>
  </dl>
  
  <dl class='gallery-item'>
    <dt class='gallery-icon landscape'>
      <a href='https://muyiscoi.com/?attachment_id=580'><img width="150" height="150" src="https://muyiscoi.com/blog/wp-content/uploads/2014/03/20140319_002217-150x150.jpg" class="attachment-thumbnail size-thumbnail" alt="20140319_002217" /></a>
    </dt>
  </dl>
  
  <br style="clear: both" />
  
  <dl class='gallery-item'>
    <dt class='gallery-icon landscape'>
      <a href='https://muyiscoi.com/?attachment_id=579'><img width="150" height="150" src="https://muyiscoi.com/blog/wp-content/uploads/2014/03/20140319_002802-150x150.jpg" class="attachment-thumbnail size-thumbnail" alt="20140319_002802" /></a>
    </dt>
  </dl>
  
  <dl class='gallery-item'>
    <dt class='gallery-icon landscape'>
      <a href='https://muyiscoi.com/?attachment_id=578'><img width="150" height="150" src="https://muyiscoi.com/blog/wp-content/uploads/2014/03/20140319_002553-150x150.jpg" class="attachment-thumbnail size-thumbnail" alt="20140319_002553" /></a>
    </dt>
  </dl>
  
  <dl class='gallery-item'>
    <dt class='gallery-icon landscape'>
      <a href='https://muyiscoi.com/?attachment_id=577'><img width="150" height="150" src="https://muyiscoi.com/blog/wp-content/uploads/2014/03/20140319_002730-150x150.jpg" class="attachment-thumbnail size-thumbnail" alt="20140319_002730" /></a>
    </dt>
  </dl>
  
  <br style="clear: both" />
</div>

<p style="text-align: left;">
  After doing all these, I now have an almost complete media centre and file storage/backup solution.
</p>

<p style="text-align: left;">
  I&#8217;ll still continue tweaking and making necessary changes as time goes by. For example, i&#8217;m considering replacing OpenELEC with Raspbmc. I already have it flashed to a spare SD card. Its major advantage over OpenELEC for me at the moment is that it runs on a more traditional Linux OS foundation, and so I can do more with it, like running most XBMC addons, even those not in the official repos. That&#8217;s something to consider for the future.<br /> For now though, I&#8217;m pretty happy with how things stand.
</p>

<p style="text-align: left;">
  I didn&#8217;t go into a lot of details about the specifics of what I did, because most of it is already available online.
</p>

<p style="text-align: left;">
  For now, the next thing to do is to complete migrating my media collection to the external Hard drive connected to the File server Pi, and then index it with movie posters, album art and all that good stuff.
</p>

<p style="text-align: left;">
  I used a very nice tutorial from <a href="http://www.linuxjournal.com/content/raspberry-pi-perfect-home-server">Linux Journal </a>for pointers in configuring the Raspbian server, and everything you need to know about <a href="http://openelec.tv/">Ope</a><a href="http://openelec.tv/">nELEC</a> is readily available on their site and <a href="http://wiki.openelec.tv/index.php/Main_Page">Wiki</a>.
</p>

<p style="text-align: left;">
  For reference, you can check out previous posts I have done on what I&#8217;ve been doing with the Raspberry Pi <a title="Getting started with the Raspberry Pi" href="http://www.muyiscoi.com/?p=609">here</a> and <a href="http://www.muyiscoi.com/?p=612">here</a>.
</p>