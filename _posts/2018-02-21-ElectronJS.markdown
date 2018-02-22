---
layout: post
title:  "Electron JS, installing problems"
date:   2018-02-21 22:06:54 +0200
comments: true
categories: ElectronJS
---

When I tried to install electron via the installation instructions [0], it did not really work the first time.

The installation of the node.js was fine and did not encounter any majob problem. When it come to installing electron, I encountered some problems. After about one hour of googling, it turns out that it has install correctly. It's just that the warning message was giving you a red herring.

it was complaing that it could not find the package.json. It spitted out the following message

{% highlight text %}
npm WARN saveError ENOENT: no such file or directory, open '/Users/tehnyitchin/project/electron/package.json'
npm info lifecycle undefined~preshrinkwrap: undefined
npm info lifecycle undefined~shrinkwrap: undefined
npm verb shrinkwrap skipping write for package-lock.json because there were no changes.
npm info lifecycle undefined~postshrinkwrap: undefined
npm WARN enoent ENOENT: no such file or directory, open '/Users/tehnyitchin/project/electron/package.json'
npm verb enoent This is related to npm not being able to find a file.
npm verb enoent 
I have assumed that if the installation went correctly, no warning message would have popped up. 
{% endhighlight %}.

To test that it installed correctly, I followed the quick start [1]. It worked! So from that I concluded that the installation was OK.

[0] - https://electronjs.org/docs/tutorial/installation
[1] - https://electronjs.org/docs/tutorial/quick-start
