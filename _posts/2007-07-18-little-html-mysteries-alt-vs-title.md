---
layout: post
title: Little HTML mysteries...  alt vs. title
link: http://www.psyked.co.uk/little-html-mysteries-alt-vs-title/
author: psyked_james
description: 
post_id: 90
created: 2007/07/18 20:04:20
created_gmt: 2007/07/18 19:04:20
comment_status: open
post_name: little-html-mysteries-alt-vs-title
status: publish
post_type: post
---

# Little HTML mysteries...  alt vs. title

This is something that I've had a wee bit of an issue with recently, but I thought I'd mention it now. Why not, eh? For the uninitiated, alt tags are _alternative text_, a label if you will, that is used to explain the _content _of an image, when images are blocked or you're on some rubbishy connection. (or a non-standard or non-desktop browser like mobile web) Alt tags are also a basic requirement of the W3C WAI guidelines, and must be included for Accessible websites - something that is most important for UK based websites - which have to be accessible, under UK Disability Discrimination laws. _Title _tags on the other hand, perform the same basic function, but for any element of the page, not just images. So, you can describe where links will take you, that sort of thing. This all comes from the expanded later versions of web standards, usually xhtml standards, whereas the alt tag is a much older and comes from the earlier html standards. 

## What's the problem?

The issue I encountered recently, is due to the progressive alterations in browser behaviour, changing their interpretations of the page rendering, and a limitation of our own Content Management System at MMT, which currently only generates alt attributes and not title attributes. 

## When did this become an issue?

Historically, tooltips have appeared displaying the alt attribute of images in Internet Explorer, ignoring title attribute all the way up to version 6, whereas the title attribute is used for tooltips in other browsers. Internet Explorer 7 changes all this, and now the title attribute overrides the alt attribute, if it exists. Infuriatingly, browsers like Firefox don't use the alt attribute for tooltips at all, and only use the title attribute. The behaviour of both browsers would now indicate that title attributes are the way to go - both browsers use them as the primary source of tooltips, but the W3C reccommendations (and the legal validation requirements) are holding us to using alt attributes as well. 

## Why?

Practically, I can't see a difference in the information that is encoded into either of these attributes, it's slightly inefficient text duplications, caused by slightly outdated schemas that still require alt tagged images. Browsers follow the W3C guidelines, so the overriding properties of title vs. alt tags must be part of the spec? And if that's the case, why isn't the alt tag depriciated? And if that's the case, why do we need to include depriciated attributes?
  *[W3C WAI]: W3C Web Accessibility Initative

## Comments

**[Al](#159 "2008-05-01 11:18:30"):** I know I'm awfully late on this one, but there is a difference. Alt attributes are JUST for accessibility. They are meant to describe (not caption) an image. If you are providing a picture of your house, which happens to be a semi-detached blue house with ornate windows, the alt attribute describes just that. The title attribute is for captioning the picure - "My house" - and that's why title gets a tooltip and alt shouldn't. When you think about it it makes sense, and kinda annoys you more. That means that if you like being WAI-compliant you now have to come up with a description and a caption for an image. And then there's longdesc which I think can be either a very long thorough description or a link to a page that describes the image, but that's not required. Of course, the problem comes when you have images used for buttons or layout elements (horizontal rules, for instance). In my designs I tend to leave the title blank on layout images and use "[layout image]" for the alt text so that screen readers/mobile browsers/whatever know it's not of any importance to the semantics of the page. I guess a CSS background is a better choice there. For buttons, e.g. one that says "search" on a quick search form, title is quite obvious "Search" or maybe "Search our site". But the alt text is harder. Do you properly describe the image - "a button which has the text 'search' in blue on a light green background" - or simply describing the function - "Search"? I don't know the answer there, although I go for the latter.

**[James](#160 "2008-05-01 13:45:41"):** I agree with you - there are important differences between the attributes you can use, their purpose and usage. Unfortunately, the holy grail of website design for many business clients is consistancy - and that means consistant browser behaviour, modelled around Internet Explorer, and with backwards compatability. - So if alt tags make tooltips in IE, you can be damn sure they'll want tooltips in Firefox 2, Firefox 1.5, IE 5.5 and IE 5. Ah, the persistant legacy of progressive development. Does the end justify the means?

**[Bikr](#161 "2009-03-24 00:10:04"):** If a site provides both, that should satisfy both needs, right? I hate the fact that on Amazon.com, when I hover over a star rating image, I don't get the "4.3 out of 5 stars" tooltip if I'm using any browser other than Internet Explorer. Amazon only sets the ALT attribute for their "star" images. I wish Amazon would add the TITLE attribute so tooltips show up in other browsers. When searching for products with lots of ratings, the difference between 4.3 stars and 4.7 stars is significant, yet the actual image shows 4.5 stars.

**[Zeke Krahlin](#162 "2010-03-18 06:24:49"):** I adapted to include both [alt] and [target] on my images. But: New to WordPress, I have just discovered that when I save the draft of a blog entry, or publish it, the [alt] tag with accompanying text, is removed. The [title] tag remains as intended. That's not too helpful when you might get fined or even arrested, in those nations where the [alt] tag is mandated by law!

**[Hank Keamo](#163 "2013-04-30 21:36:25"):** CSS is designed primarily to enable the separation of document content (written in HTML or a similar markup language) from document presentation, including elements such as the layout, colors, and fonts.This separation can improve content accessibility, provide more flexibility and control in the specification of presentation characteristics, enable multiple pages to share formatting, and reduce complexity and repetition in the structural content (such as by allowing for tableless web design). *.. Take a look at all of the latest write-up on our very own web blog <http://www.caramoanpackage.com** **

