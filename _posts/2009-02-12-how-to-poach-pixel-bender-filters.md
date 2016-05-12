---
layout: post
title: How to&#58; poach Pixel Bender filters.
link: http://www.psyked.co.uk/how-to-poach-pixel-bender-filters/
author: psyked_james
description: 
post_id: 716
created: 2009/02/12 09:28:04
created_gmt: 2009/02/12 08:28:04
comment_status: open
post_name: how-to-poach-pixel-bender-filters
status: publish
post_type: post
---

# How to: poach Pixel Bender filters.

Pixel Bender is awesome - but I just haven't got into it yet, so I have no idea how to make my own useful or impressive filters.  Nevermind, there's always the [Pixel Bender Exchange](http://www.adobe.com/cfusion/exchange/index.cfm?event=productHome&exc=26) from Adobe.  Not enough?  Well, one thing I like about AIR applications is that - moreoften than not - there's a lot of raw source files available, if you know where to look. Pixel Bender files fall into this class.  [BlackBookSafe](http://www.adobe.com/devnet/air/ajax/articles/blackbooksafe_anatomy.html) is where I first pinched Pixel Bender source files from, simply by looking at the folder created for the application in my 'Program Files' folder.  [Fotobooth](http://www.adobe.com/cfusion/marketplace/index.cfm?event=marketplace.offering&offeringid=10080&marketplaceid=1) is another example - a little more difficult - but the source files for all those clever Pixel Bender filters are just sitting, waiting for you to hack around with them... ![Pixel Bender filter files](http://uploads.psyked.co.uk/2009/02/pixelbender.jpg)

### Enough yammering, tell me something useful!

So, when an AIR application is installed on your machine it places all of the files it needs in your 'Applications' or 'Program Files' directory. Usually external assets like Pixel Bender are available in the source files in a standalone format, and that's all you really need to incorporate those filters into your own projects. Well, almost.  The two types of source files you're likely to get are .pbj or .pbk.  If you get .pbk files you can use them directly in the Pixel Bender Toolkit.  If you get .pbj files - check out this [blog post](http://blog.minim.pl/?p=32) and [Flex application](http://blog.minim.pl/PBJtoAS/) which can help you get started converting those files into usable Actionscript classes.

## Comments

**[Rich Tretola](#549 "2009-02-12 12:53:55"):** I agree that it is easy to grab pixel bender filters if the developer does not secure them. When I created and distributed [FotoBooth](http://blog.everythingflex.com/fotobooth/), I was not concerned with this as these filters are ones that are freely distributed anyway so I simply included them within the app. However, one thing to point out is that the files included in the distribution are the compiled filters (.pbj) and not the actual source files (.pbk), so although you can poach them and reuse, you can't change them without the source.

**[James](#550 "2009-02-12 21:48:15"):** That's very true - the files are certainly poachable, but not in a format to modify - which is something, I suppose. Do you know if there is a better way to protect your Pixel Bender filters?

