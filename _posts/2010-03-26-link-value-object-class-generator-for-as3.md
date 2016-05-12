---
layout: post
title: Link&#58; Value Object Class generator for ActionScript 3
link: http://www.psyked.co.uk/link-value-object-class-generator-for-as3/
author: psyked_james
description: 
post_id: 1192
created: 2010/03/26 10:08:42
created_gmt: 2010/03/26 09:08:42
comment_status: open
post_name: link-value-object-class-generator-for-as3
status: publish
post_type: post
---

# Link: Value Object Class generator for ActionScript 3

A bit specialist perhaps, and the need for such a tool might become redundant if the Flash Builder hype is to be believed, but I found this quite useful for speeding up the process of writing a value-object class in AS3. <http://projects.stroep.nl/ValueObjectGenerator/>

### What is a value object anyway?

For the uninitiated, a value object class is essentially a class with very little or no application logic inside it. Instead of being a file that actually does something, it's more of a class for just storing data.  What makes it special is that AS3 classes are not all dynamic, so you have to plan what data you need to store and how you'll store it; and you can achieve a vast majority of that with value object classes. If you're coming from an AS2 or Flash IDE background you might think it's a bit unnecessary or even frustrating, but when you plug value object classes into a development environment like Flex Builder you see where it comes in useful, when it can actually gives you useful autocomplete suggestions, and warns you if you're passing the wrong type of data into your classes.

## Comments

**[Mark](#840 "2010-03-26 12:07:13"):** Thanks for sharing :)

**[Keith H](#841 "2010-03-27 17:04:21"):** I think it is useful. Many times I use a plain Object to store a small group of values , to later find out that that group of values is too large and complicated to remember its rules. So the Object needs to be class...a Value Object that the development environment can read better. As a class I, myself can even read it better after coming back to code I haven't touched in 3 months.

