---
layout: post
title:  "SSH for the new user."
date:   2017-07-15 22:06:54 +0200
comments: true
categories: digitalocean
---

I created a droplet on digitalocean server tonight to do some experimentation in a side project. I chose the most basic VPS that installed ubuntu. This is their 5€ per month option.
I followed the instructions to create a set of ssh keys so that I don't have to enter the password all the time.
Initially, the first mistake I made was not to add the ssh public keys when creating the droplet. When I did this, I was continously being asked for the password. There is probably a few ways to get around this problem, but I was too lasy, so the I destroy the droplet to start again. 
The second time I pasted in my public key during my the droplet creation. That seems to work beautifully. 
The only account available is `root`. Due to its unrestricted nature of `root`, it is probably not a good idea to use it as the daily account.
I create another user account using the instructions found [here][howto_guide].
To install the ssh keys that I had used for root, it just copied it across the .ssh directory of the user. I also had make sure that its owner is set to the user.
When is `ssh` into to the ubuntu VPS, it did not ask me for any of the password.


[howto_guide]: https://www.digitalocean.com/community/tutorials/how-to-add-and-delete-users-on-ubuntu-16-04
