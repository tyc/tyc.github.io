---
layout: post
title:  "Beautiful Soup."
date:   2017-07-13 22:06:54 +0200
comments: true
categories: python
---

I had some issues installing BeautifulSoup onto Python. On my setup, the default setup for Python is v2.7. This is the latest version of python that is not version 3. 

As a newbie, I also had to double check if BeautifulSoup was installed as well. I rang across this page on Stack Overflow that has a good start on scrapping a page. 

[https://stackoverflow.com/questions/33266000/scrape-booking-com-with-python-against-ajax-requests](https://stackoverflow.com/questions/33266000/scrape-booking-com-with-python-against-ajax-requests)

This code saves the page away into a file and it can be use as imput into BeautifulSoup. 

You can also open the saved .html into the webbrowser and inspect it by using the inspect tool in Firefox. This will allow you to identify the class that you need to filter for as well as the key needed to serach for.

Be careful as the booking.com is very much ill informed. There will be some logic needed to filter some items. For example, booking.com will return hotel listing that does not contain any prices, or average rating.

During further debugging, I found that the answer to the question in the Stack Overflow question is not really answered. It does not take care of the ajax calls from the website. Further Googling indicates that using a headless webbroswer like PhantomJS would help.