---
layout: post
title:  "Sleep problem on the ubuntu"
date:   2019-07-02 22:06:54 +0200
comments: true
categories: linux 
---

My Intel NUC has Ubuntu installed. Before I installed it, I read that the Ubuntu has great support for it. 

To find out which Ubuntu, I did the following

    lsb_release -a

    Distributor ID:	Ubuntu
    Description:	Ubuntu 16.04.6 LTS
    Release:	16.04
    Codename:	xenial

I come across this question in StackOverflow asking the same question that I need answer for. So I read it, and it sounded reasonable.

[StackOverQuestion](https://askubuntu.com/questions/598236/ubuntu-wakes-up-after-few-seconds-of-sleep)

I followed the instruction. I had two devices waking up the Intel NUC. I disabled both of them and the Intel NUC was staying asleep. So I knew it was one of these two that kept waking up the system.

The two devices that were enabled were GLAN and XHC. By the process of disabling one of them and checking if the computer stayed asleep, I was able to determine that the XHC device was the culprit here.

Doing a futher googling, I came across this [article](https://codeyarns.com/2017/04/16/the-strange-case-of-the-notebook-that-woke-up-at-night/) where the system is also behaving in a similar manner. This author tracked it down to his wireless mouse waking the system due to vibrations.

His solution was to also disable the XHC device. By the way, XHC is the USB3.0 devices. This article shows a way to permanent set it so that the XHC wakeup is disabled.
