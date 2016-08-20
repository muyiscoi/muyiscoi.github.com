---
id: 998
title: Creating a simple Lab environment with Vagrant
date: 2016-08-09T18:50:56+00:00
author: muyiscoi
layout: post
guid: https://muyiscoi.com/?p=998
permalink: /?p=998
categories:
  - Sysadmin
  - Technology
tags:
  - ansible
  - devops
  - lab environment
  - libvirt
  - linux
  - puppet
  - sysadmin
  - vagrant
  - virtualbox
---
On my quest for &#8220;DevOps world domination&#8221; :D, I&#8217;ve been dipping my toes into tools like Puppet and Ansible. In order to fully understand these tools and use them in different scenarios, a lab environment consisting of several nodes is required. Vagrant makes it extremely easy to stand up such an environment.

Below, I&#8217;ll describe in broad strokes the steps I took to setup a 4+ node environment for Ansible using Vagrant.<!--more-->

The first thing to do was to install [Vagrant](https://www.vagrantup.com/docs/installation/). By default, Vagrant uses Oracle Virtualbox as its hypervisor, so this had to be installed as well on my laptop running Ubuntu 16.04. Virtualbox can be swapped out for something else like libvirt, hyper-V or even public cloud platforms like AWS. I&#8217;m perfectly fine with Virtualbox though, and even though I setup libvirt as a second virtualization provider for vagrant, I retained Virtualbox as the default.

After installing and configuring Vagrant, a [Vagrantfile](https://www.vagrantup.com/docs/vagrantfile/) had to be created describing the lab environment I needed. The Vagrantfile is written in ruby, however, knowledge of the language is not required in order to write one. The [Vagrant documentation](https://www.vagrantup.com/docs/) was very helpful in determining what was needed to get my Vagrantfile just how I wanted it.

The Vagrantfile described the following environment

**VM1** :management VM: a Virtual machine where Ansible will be installed for managing the rest of the nodes and itself.

**VM2** :load balancer: a VM acting as a HA-proxy for load balancing web servers

**VMs 3 &#8211; *** : a number of VMs to be configured as web servers

All VMs also need to be on the same network, able to communicate with each other, and the load balancer and Web server VMs need to forward their HTTP port to the host.

Vagrant provides functionality that allows the execution of shell scripts after a VM is created. As a result, the &#8220;Vagrantfile&#8221; was configured to run a shell script on VM1 that would install Ansible (following instructions for ansible installation from the [official docs](http://docs.ansible.com/ansible/intro_installation.html#latest-releases-via-apt-ubuntu)), as well as append configuration to the /etc/hosts file to allow host name resolution across the test environment.

After creating the Vagrantfile, it was placed in a root directory along with the bootstrap shell scripts. Vagrantfile and script can be found [here](https://github.com/muyiscoi/vagrantfiles).

The command

<pre>$ vagrant up</pre>

was then executed to provision the entire environment, and approximately 4 minutes later, I had 5 VMs fully operational with ansible installed and running on the first one.

<div id="attachment_1001" style="width: 590px" class="wp-caption aligncenter">
  <a href="https://muyiscoi.com/blog/wp-content/uploads/2016/08/test-envionment-bootstrapped-on-vagrant.png"><img class="wp-image-1001 size-medium" src="https://muyiscoi.com/blog/wp-content/uploads/2016/08/test-envionment-bootstrapped-on-vagrant-580x368.png" alt="test envionment bootstrapped on vagrant" width="580" height="368" srcset="https://muyiscoi.com/blog/wp-content/uploads/2016/08/test-envionment-bootstrapped-on-vagrant-580x368.png 580w, https://muyiscoi.com/blog/wp-content/uploads/2016/08/test-envionment-bootstrapped-on-vagrant-624x396.png 624w, https://muyiscoi.com/blog/wp-content/uploads/2016/08/test-envionment-bootstrapped-on-vagrant.png 732w" sizes="(max-width: 580px) 100vw, 580px" /></a>
  
  <p class="wp-caption-text">
    Final output after fully lanching test environment with Vagrant
  </p>
</div>

I can now get on with doing all kinds of cool stuff with Ansible and later, puppet.

Resources

  * <https://sysadmincasts.com/episodes/45-learning-ansible-with-vagrant-part-2-4>
  * <https://github.com/muyiscoi/vagrantfiles>
  * <https://www.vagrantup.com/docs/>