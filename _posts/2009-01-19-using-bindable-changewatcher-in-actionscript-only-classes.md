---
layout: post
title: Using [Bindable] & ChangeWatcher in ActionScript-only classes
link: http://www.psyked.co.uk/using-bindable-changewatcher-in-actionscript-only-classes/
author: psyked_james
description: 
post_id: 606
created: 2009/01/19 10:16:37
created_gmt: 2009/01/19 09:16:37
comment_status: open
post_name: using-bindable-changewatcher-in-actionscript-only-classes
status: publish
post_type: post
---

# Using [Bindable] & ChangeWatcher in ActionScript-only classes

### What are you talking about?

Recently I've been toying around with using [Bindable] Metadata in Flex and AS3, namely trying to not only make it so that my static variables can be used as bindings in Flex, but also that I can detect when the variables change. 

### How do you do that?

There's a few ways you can do that, and a whole plethora of other blogs that will give you rundowns on how.  What you need to look for are the ChangeWatcher and BindingUtils classes [[livedocs](http://livedocs.adobe.com/flex/3/html/help.html?content=databinding_7.html)].  There doesn't seem to be anything in particular thats different between them, ChangeWatcher lets you define a variable and function to call on changes, and BindingUtils lets you define functions to call when variables are set or properties change - all in all, not much difference. 

### But...

What none of the examples mention however, is that all of the tutorials on this are covering script in MXML components or extending existing MXML components and are therefore all using the Flex framework.  You can add in all the ChangeWatcher.watch()'s you want and get no errors, but if you're not extending the Flex framework, nothing is going to work! 

### So.

So, if you want to detect binding changes in an ActionScript-only class, you need to do it in something that's extending a Flex component, otherwise it just won't work!  Obvious really, but it took me a good few hours to figure out.  I haven't done extensive testing to see what the lowest level component to extend was, but I've plumbed for extending the UIComponent, and all of my binding detections work. 
    
    
    pulic class ImageSizerApplicationConfig extends UIComponent

## Comments

**[Troy Gilbert](#517 "2009-07-14 21:30:25"):** That's not actually correct. [Bindable] does not use any Flex Framework specific API (beyond the PropertyChangeEvent class), and the BindingUtils is similar. You do not have to derive from UIComponent or use this only in the context of MXML. I'd recommend watching the binding "deep dive" session from 360|Flex.

**[James](#518 "2009-07-15 00:42:09"):** Thanks for the link & clarification Troy. I guess I misunderstood what the Flex framework actually 'was' - and where the framework starts and stops with regards to visual / utilities classes.

**[Morgan Engel](#519 "2009-12-09 01:12:18"):** You might consider using a get and set and then just appending the Bindable attribute on the get method. something like: [Bindable] public function get property():Object{} public function set property(o:Object){} Then you can dispatch listeners in your set and you can listen to them just fine in your AS3 code.

**[Thomas James](#520 "2010-06-10 18:37:07"):** Yet if [Bindable] does not use any Flex framework in an ActionScript project in Flashdevelop or Flashbuilder this fails: [code]package { import flash.display.Sprite; import flash.events.EventDispatcher; import flash.events.Event; public class BindableTest extends Sprite { private var _maxFontSize:Number = 15; public function BindableTest() { this.maxFontSize = 100; } [Bindable(event="maxFontSizeChanged")] public function get maxFontSize():Number { trace(" max "); return _maxFontSize; } public function set maxFontSize(value:Number):void { _maxFontSize = value; var eventObj:Event = new Event("maxFontSizeChanged"); dispatchEvent(eventObj); } } } [/code] Any clues!?

