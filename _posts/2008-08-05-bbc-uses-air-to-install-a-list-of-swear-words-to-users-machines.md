---
layout: post
title: BBC uses Adobe AIR to install a list of swear words to users machines.
link: http://www.psyked.co.uk/bbc-uses-air-to-install-a-list-of-swear-words-to-users-machines/
author: psyked_james
description: 
post_id: 272
created: 2008/08/05 10:01:35
created_gmt: 2008/08/05 09:01:35
comment_status: open
post_name: bbc-uses-air-to-install-a-list-of-swear-words-to-users-machines
status: publish
post_type: post
---

# BBC uses Adobe AIR to install a list of swear words to users machines.

![](http://uploads.psyked.co.uk/2008/08/bbc-swear.jpg) **James Cannings** from **MMT Digital** alerted me to this, and has written a post about it at: <http://www.mmtdigital.co.uk/monkeymagic>, and here's my thoughts on it: You can install the BBC Sport’s Desktop Monkey at: <http://news.bbc.co.uk/sport1/hi/olympics/monkey/7479984.stm> If you do however, you’ll be unwittingly installing a rather comprehensive list of offensive words as a plain text file to your hard drive. Once it's installed, go to your application directory (Program Files) and **BBC Olympics** > **assets **> **data **> **[bbc-swear.txt **](/wp-content/uploads/2008/08/bbc-swear.txt) and you'll be privvy to a 15kb, 1399 lines long list of bad words. This is such an ridiculous error that I’m practically lost for words. For an audience as big as the BBC’s you think they’d be mindful about offending people – every other part of the development must have undergone a review process – but bundling a highly offensive text file with your application? 

## Why?

Perhaps there’s a reason for the BBC’s Olympics Application to contain a list of restricted words, but for the love of god, don’t store them in an unencrypted text file that’s written to the user’s hard drive - store it in a database format, a non .txt extension, encrypted storage, or even on a remote server – but **do not store it as a text file!**

## On the funny side...

Most of these words I haven’t heard since school, and many of them I’ve never heard of.  Although, beyond childish giggles, this isn't really funny - I don't think its nessessary, and looking at the contents, I have doubts about how useful it really is... 

## No really, why?

From an efficiency (programatic) point of view, the text file has some truly odd contents... If you’re going to search for the word ‘tosser’ then do a **regular expression** for the word ‘tosser’ – and perhaps a regular expression for the l33t-speak variant – don’t just search for these words: 

> “to$$ers, to**er, to55er, to55ers, tosser, tosser, tossers, tossurs”

Because a slight misspelling is going to get past, is it not? Anyway, there’s much that can be said about it - and I'm sure much will be said about it.  [Andrew Shorten](http://www.ashorten.com/2008/07/17/bbc-olympics-coverage-on-your-desktop-with-air-and-on-the-web-with-flash-player/) has been promoting it, I wonder what he has to say?

## Comments

**[Ryan Stewart](#394 "2008-08-05 10:13:19"):** Haha, that's actually pretty funny. Could have been a good use for the encrypted local store. =Ryan rstewart@adobe.com

**[FlashGen](#395 "2008-08-05 12:02:12"):** Yes it is pretty amusing for us and it should have been handled a different way, either via an encrypted store or a selection of regex's perhaps. On a more sobering note, one has to wonder if this contravenes any decency laws. While it could be argued that it is tricky to find if there was no age verification prior to downloading the app some may cry foul. I personally wouldn't be happy if a child of mine found this on their machine. Perhaps this is a case of "less haste more speed"

**[pjtr](#396 "2008-08-05 14:03:27"):** I guess this is the blacklist for some kind of commenting system? Like all the words you can't use in your comments to the website/desktop client. Why it is on the client's side and not on the server side is another question altogether.

**[FlashGen](#397 "2008-08-05 14:10:51"):** @pjtr It's because it's an AIR app and therefore doesn't necessarily need to have a permanent connection to the net to function. What they should have done is either stuffed all of that in a SQLite DB on the client machine (simple obfuscation) or put it in the EncryptedStore on the machine. That way it wouldn't have been so easy to open and view in the first place. The issue isn't the list itself it's the implementation. One plus point, we don't have to make a swear filter list ourselves now :p

**[James](#398 "2008-08-05 14:11:58"):** Indeed, the most logical explaination is that the file is part of a blacklisting system - but then there's so many other ways to impliment that system. I hope BBC have an auto-updater system built into the application - something that could fix this (hopefully before someone kicks up a stink)

**[James](#399 "2008-08-05 14:14:58"):** @FlashGen - indeed, we can use the BBC's swear list now! But I never realised that 'communities@bbc.co.uk' or 'Prince Phillip' were swear words? Kids these days!

**[FlashGen](#400 "2008-08-05 14:24:51"):** @James yeah there are a load of weird links. Plus the names , even with rhyming slang, could never be considered a swear word :p

**[Andrew Shorten](#401 "2008-08-05 14:54:23"):** I'll make sure the BBC is aware of this issue with the application. They have indeed used the auto updater feature in AIR so should be able to push out an update with an alternative implementation for this. I would say however, that unless you are in the habit of stepping into application installer files you would never come across this and therefore the BBC is unlikely to be offending the typical user of the application. Nice graphic for the blog entry ;)

**[Nick Reynolds (editor, BBC Internet Blog)](#402 "2008-08-05 15:12:52"):** Thanks for brining this to our attention. We are in the process of fixing it/removing the list. Nick Reynolds (editor, BBC Internet blog)

**[Nick Reynolds (editor, BBC Internet Blog)](#403 "2008-08-05 15:13:32"):** Should be "bringing" - sorry.

**[James](#404 "2008-08-05 15:35:08"):** The power of the internet - 5 hours later, and they're on the case! I'm curious to see how quickly (and how) things get fixed - lucky it's Adobe AIR, and not a CD-Rom based application!

**[James](#405 "2008-08-05 16:41:49"):** Well, you might say it's all over - an auto-update has just appeared which fixes the immediate issue: http://www.psyked.co.uk/adobe/apollo/bbc-sports-air-application-removes-its-offensive-language.htm

**[Dan](#406 "2008-08-14 11:15:51"):** There are some really weird ones in there - the swear words I can more-or-less understand, but why are the phrases "Duke of Edinburgh", "Prince Philip" (and Phillip) and "Philip the Greek" banned? And if anybody's ingenious enough to swear using phrases like "Foxtrot Oscar" then I really think they ought to be allowed to.

