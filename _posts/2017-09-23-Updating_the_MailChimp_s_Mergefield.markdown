---
layout: post
title:  "Updating the MailChimp's Mergefield"
date:   2017-08-11 22:06:54 +0200
comments: true
categories: MailChimp
---

To use a customised data in the template, create a merge tag with a customised name. I had a item where I want to display the name of a hotel. 

In my template, I had a merge tag named as HOTEL1. In my template, I would insert the tag `*|HOTEL1|*` into template itself. I would also use it anywhere in the template when it needs to be display the customed data.

To get the details about the merge data, I would use the following command. I am showing it via a cURL command.

```
curl --request GET \
--url '<dc>.api.mailchimp.com/3.0/lists/cb262c7d85/merge-fields/<merge_tag_id>' \
--user '<username>:<api_key>'
```

Mailchimp will return the data for the particular merge tag. The key is to have the correct ID for the merge tag.

The field to udpate is 'default_value'

```
curl --request PATCH \
--url '<dc>.api.mailchimp.com/3.0/lists/cb262c7d85/merge-fields/<merge_tag_id>' \
--user '<username>:<api_key>'
--header 'content-type: application/json' \
--data '{"default_value":"Seaford Hotel Foxus"}' \
--include
```

When the template is sent out, the value specified in 'default_value' will be used.

