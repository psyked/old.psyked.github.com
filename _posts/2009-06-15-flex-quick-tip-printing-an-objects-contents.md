---
layout: post
title: Flex Quick Tip: Printing an Objects' contents
link: http://www.psyked.co.uk/flex-quick-tip-printing-an-objects-contents/
author: psyked_james
description: 
post_id: 888
created: 2009/06/15 09:09:54
created_gmt: 2009/06/15 08:09:54
comment_status: open
post_name: flex-quick-tip-printing-an-objects-contents
status: publish
post_type: post
---

# Flex Quick Tip: Printing an Objects' contents

You quickly learn in Actionscript 3 that tracing an objects' contents is not always that simple.  Commands such as **trace(myObject);** often yeild the highly infuriating **[object Object]** return, which tells you mostly nothing of what you actually wanted to know.  After that you can move on to more advanced trace logic, like the handy; 
    
    
    **for(var i in n) {
        trace(i+":"+n[i]);
    }**

But that's a lot of stuff to type, and often yeilds infuriatingly long stacks of parameter traces. Flex can make things a little easier, with this useful utility class, the cunningly named **ObjectUtil **class.  Simply import the class (**import mx.utils.ObjectUtil;**) and call the following method; **trace(ObjectUtil.toString(myObject));** and you'll get a nice output of all the properties of your object. Kudos to flextutor.org for this, in their original post "[How to print an objects' contents in Flex](http://www.flextutor.org/flex-tips-suggestions/how-to-print-an-object-content-in-flex/)."  I thought I'd repost it here though, not least because there seems to be an issue loading their site as I' m writing this article.

## Comments

**[Kristofer Joseph](#636 "2009-06-15 21:29:06"):** This is not true for all object. For instance the NetStream info object cannot be traversed in this way. Instead you would need to use describeType(); package { import flash.display.Sprite; import flash.utils.describeType; public class DescribeTypeExample extends Sprite { public function DescribeTypeExample() { var child:Sprite = new Sprite(); var description:XML = describeType(child); trace(description..accessor.@name.toXMLString()); } } } As described here: http://livedocs.adobe.com/flex/2/langref/flash/utils/package.html#describeType()

**[Rory](#637 "2010-01-25 21:13:58"):** Thanks, needed help printing the contents of my Object (associative array) and this did the trick. And, the other blog where this appeared still does not load, so thanks for the "re-post"

**[Pim](#638 "2010-03-11 13:29:19"):** Very usefull information. Saved me alot of time so thank you!

**[cole](#639 "2011-01-20 21:38:47"):** Fantastic! Thank you! Just what I've been looking for!

**[Fixticks](#640 "2012-08-22 11:24:35"):** Life saver, thank you very very much

