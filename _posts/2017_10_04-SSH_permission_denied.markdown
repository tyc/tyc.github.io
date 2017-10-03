---
layout: post
title:  "SSH permission denied."
date:   2017-10-04 22:06:54 +0200
comments: true
categories: digitalocean
---

I tried to get onto my VPS instance on DigitalOcean from another machine. I must have stuffed it up because all of a sudden, I got the dreaded 

{% highlight text %}
localhost:~ tehnyitchin$ ssh tehnyitchin@aaa.bbb.ccc.ddd
Permission denied (publickey).
{% endhighlight %}

To overcome this problen, I had to copy my rsa key across to the server again. However, before I was able to do that, I renabled the `PassAuthenticaion` in `/etc/ssh/ssh_config` by setting it to `yes`.

I used the web console via the DigitalOcean's dashboard to get access to ssh configuration  

Don't forget the restard the sshd so that it takes on the new configuration.

{% highlight text %}
sudo systemctl reload sshd
{% endhighlight %}

When I executed the command to copy by ssh keys across

{% highlight text %}
ssh-copy-id tehnyitchin@aaa.bbb.ccc.ddd
{% endhighlight %}

The server would ask for the password, and then copied it to the correct location and correct filename.

Sometimes, it would also complain the the permissions if the keys on the local machine are not correct. 

The `.ssh` directory must be 
{% highlight text %}
drwx------    8 tehnyitchin  staff     272 Oct  3 23:47 .ssh
{% endhighlight %}


The keypair files must be configured as below.

{% highlight text %}
-rw-------   1 tehnyitchin  staff  1675 Oct  3 12:21 id_rsa
-rw-r--r--   1 tehnyitchin  staff   403 Oct  3 12:21 id_rsa.pub
{% endhighlight %}

This tutorial helped me a lot

https://www.digitalocean.com/community/tutorials/initial-server-setup-with-ubuntu-16-04

