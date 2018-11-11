---
layout: post
title:  "A quick word about the infrastructure for PrjMgr_weekly v1.0"
date:   2018-11-11 22:06:54 +0200
comments: true
categories: side projects 
---

The gathering of the stories is done by reading the articles, judge that they are Ok to be curated and add it to the list. The following is a quick run down of the tools involve to do the work. I am considering this as v1.0 of the tools stack.

# Mailchimp

Mailchimp is used to do the tool to manage the subscriber list. I have created the landing page with it as well. It does the mailout after creating the campaigns. GDPR compliance is provided for by Mailchimp, this is my assumption.

The newsletter is also created via Mailchimp. There is a template that I use. I formulate the content via a markdown, copy and paste it. More on this later.

# Instapaper

Once I have read the document and felt that it can be curated, I would save it via Instapaper. I have downloaded the instapaper for Chrome extension. Also installed it on my mobile devices. The links are saved onto my Instapaper account.

# IFTT

I use IFTT as the glue logic between Instapaper and Google Sheet. IFTT will copy the new content into a Google sheet account as a new line.

# Google Sheets

I am using Google sheet collect all the curated links so that I can add more detail to it. For each link, I add the amount of time it takes to read it, a more detail summary, the date which it was published and the categoriy it should be classified under.

For each articles, I put number then from 1 to 4, indicating the four articles that will appear in the newsletter. Article 1 will appear at the top  and article 4 will appear on the bottom.

I have a sheet "Post Builder" that searches through for the four highlighted articles and builds up the content of the an article.

# python - getdata.py

I have python script that access data from the Google Sheet "Post Builder" and build up a markdown document.

# Markdown

The output of the python script is needs to be rendered before it can be pasted into the editor in Mailchimp. It can either be rendered via Github or an open source Markdown editor like MacDown. Once rendered, the HTML output is copied and pasted into Mailchimp's editor.

# Github

Github is used contained the markdown documents and the python script.


