---
author: jose
date: 2014-08-01
title: '2 Penny Q&A: Experiences with Linux filesystems on VMWare+Netapp'
category: 2penny
layout: post
image: 
  feature: DevOpsDaysLogo.png
published: true
tags: linux filesystems netapp
comments: true
share: true
---

Recently our colleague Jose Riguera answered a question that a developer asked to our team. 

We found his answer fairly insteresting, so we want to share it.

Question
--------

> Do you have a Guide or some experience about etx3 and ext4 Filesystems Options (noatime, data=writeback, ) to use for better Performance in the VMWare / NetApp Environment you can recommend / share ? 

> What is you experience for the different types of Data usage and the NetApp. 

> Can you recommend Options typical Setup Situations, i.e. for Database  Filesystem use Xy, for Logging Filesystem use Xz and for “heavy Read” Filesystem use Xq ?

Answer
---------------------------------------------------

I think we do not have a fixed guide, because due to the amount of different servers with different purposes, most of the times it's better to use the default options and look for global solutions:

 1. We were trying to avoid direct nfs mounts from the VMs to the Netapp, because we think it's better to have VMware as proxy between them due to the NFS optimizations on vmware and  also to avoid adding complexity on each VM with nfs mounts.
 2. I think ext3 is not worth it because ext4 is mature enough and nowadays it is the default FS in most of the distributions. Probably in some cases XFS is a bit better than ext4 (when you have a lot of IO ...). Btrfs is mature to use, it has/will have a lot of functionalities but in terms of performance I think most of the times it does not beat the others.

Anyway, due to the amount of layers between a file and the storage, choosing one or the other does not matter (talking about VMs and NFS-Netapp)... probably you will notice more differences by running a process in non working hours ... and if you try to use aggressive performance options you are risking to lose data if the server crashes...

Anyway, here are my general recommendations:

 * You can use options like noatime (to avoid write the time-date access every time a file is accessed)
 * XFS for a FS with big files and a lot of IO
 * Mount /var/run or other fs as tmpfs (FS in memory)
 * Try to avoid swapping (http://en.wikipedia.org/wiki/Swappiness)
 * In some cases you can use huge pages  (JVM, DBs ...)
 * You can try to increase the buffers for IP communications and other network parameters
 * Change the kernel scheduler ...

For NFS and Netapp I think it is better if you go to the netapp support website, for example: https://communities.netapp.com/servlet/JiveServlet/download/107808-44106/tr-3633.pdf

But remember if you are running a VM, in the end it is a process on another server competing for shared resources ...
The key is the design of the application, the global architecture to scale, using distributed services, etc.

That's my two penny post, use the comments if you have a different view or if I have forgotten other options...


*-- by Jose Riguera*

