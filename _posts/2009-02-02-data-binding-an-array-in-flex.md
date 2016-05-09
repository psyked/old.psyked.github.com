---
layout: post
title: Data Binding an Array in Flex?
link: http://www.psyked.co.uk/data-binding-an-array-in-flex/
author: psyked_james
description: 
post_id: 673
created: 2009/02/02 10:45:35
created_gmt: 2009/02/02 09:45:35
comment_status: open
post_name: data-binding-an-array-in-flex
status: publish
post_type: post
---

# Data Binding an Array in Flex?

Can you do it?  No you can't. Not directly anyway - Arrays aren't something that data binding works with in Flex.  ArrayCollection however, is something you **can **work with.  To use an Array as a bindable object, you can wrap it in an ArrayCollection.  It's similar, but not the same as an Array - you can't push, pull, pop or shift things anymore - you have to work with other methods like addItem or removeItem. I would've liked to find that all of those classic array methods still worked, but what can you do?

## Comments

**[DavidD](#539 "2009-02-02 14:25:05"):** The property _ArrayCollection.source_ is the very array that resides inside an AC , thus it allows access to Array methods ( mycollectionAC.source.indexOf(...) ). Just experiment with that to see if it's of any help to you. It's feasible and can maybe be handy but I would advise you to test the limits of this way of doing so, especially if you plan to modify the ArrayCollection items. Or then you can replace your source array property with a modified one in your AC. It's for you to see.

**[James](#540 "2009-02-02 15:19:17"):** Oh, that makes a lot of sense! - I can see why they'd want to do it that way. - Cheers!

**[Bruce](#541 "2009-02-02 22:30:56"):** Don't forget that things you do to the array might not show up (since it's not bindable) and you might need to fire off an event like refresh() on the ArrayCollection if you using the .source property.

**[Bruce](#542 "2009-02-02 22:33:39"):** oh yeah, if you're using a DataService ArrayCollection you might find that the list property is populated instead of the .source, so be careful of that as well.

