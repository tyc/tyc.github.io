---
layout: post
title:  "Electron JS, installing problems"
date:   2017-06-19 22:06:54 +0200
comments: true
categories: ElectronJS
---

When I tried to install electron via the installation instructions [0], it did not really work the first time.

The installation of the node.js was fine and did not encounter any majob problem. When it come to installing electron, I encountered some problems. After about one hour of googling, it turns out that it has install correctly. It's just that the warning message was giving you a red herring.

it was complaing that it could not find the {% highlight text %}package.json{% endhighlight %}. I have assumed that if the installation went correctly, no warning message would have popped up. 

To test that it installed correctly, I followed the quick start [1]. It worked! So from that I concluded that the installation was OK.

[0] - https://electronjs.org/docs/tutorial/installation
[1] - https://electronjs.org/docs/tutorial/quick-start
