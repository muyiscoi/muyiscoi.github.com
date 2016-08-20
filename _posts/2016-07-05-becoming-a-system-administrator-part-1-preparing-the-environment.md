---
id: 918
title: 'Becoming a System Administrator Part 1: Preparing the environment'
date: 2016-07-05T15:38:46+00:00
author: muyiscoi
layout: post
guid: http://muyiscoi.com/?p=918
permalink: /?p=918
categories:
  - Sysadmin
  - Technology
tags:
  - '#becomingasysadmin'
  - centos7
  - linux
  - spacewalk server
  - sysadmin
---
_NOTE:  I&#8217;m attempting to accomplish all the tasks laid out in [this](https://www.reddit.com/r/linuxadmin/comments/2s924h/how_did_you_get_your_start/cnnw1ma) post. For more context, check out this [blog](https://muyiscoi.com/?p=915)._

Before getting started, I need to prepare the hardware to be used. This includes storage, networking and compute resources. I only have access to my laptop for all these, so I&#8217;m a bit limited but should be able to make it work.

I have taken the following steps to setup the environment

  1. Installed CentOS7 x86_64 on a partition of the second hard drive in my laptop.
  2. Ran an update
  3. Installed KVM hypervisor on the CentOS host, and virt-manager to manage the VMs
  4. Created a custom bridge for kvm (kvmbr0) and added the pNIC (enp1s0) as an interface in the bridge[<img class="aligncenter size-medium wp-image-920" src="http://muyiscoi.com/blog/wp-content/uploads/2016/07/network-580x102.png" alt="custom bridge " width="580" height="102" srcset="https://muyiscoi.com/blog/wp-content/uploads/2016/07/network-580x102.png 580w, https://muyiscoi.com/blog/wp-content/uploads/2016/07/network.png 613w" sizes="(max-width: 580px) 100vw, 580px" />](http://muyiscoi.com/blog/wp-content/uploads/2016/07/network.png)
  5. Installed a CentOS7 guest on the KVM hypervisor configured to use the custom bridge configured above.
  6. Installed [Spacewalk](http://spacewalkproject.org/download.html) server on the first VM
  7. Configured Dynamic DNS support on my home router using [noip](http://www.noip.com/)
  8. Configured port forwarding for the ssh port on my router in order to have access to my host and VMs outside my local network

The VMs configured to use kvmbr0 bridge get assigned DHCP addresses by my router, and are therefore addressable anywhere within my private network. In the future, I will configure one of the VMs as a local DNS and DHCP server, and that will take care of IP address assignment and name resolution.

Relevant link(s) used

  * [Installing Spacewalk](https://www.unixmen.com/install-and-configure-spacewalk-in-centos-7/)