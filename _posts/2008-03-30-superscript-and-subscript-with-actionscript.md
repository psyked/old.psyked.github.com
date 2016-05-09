---
layout: post
title: Superscript and Subscript - with Actionscript*
link: http://www.psyked.co.uk/superscript-and-subscript-with-actionscript/
author: psyked_james
description: 
post_id: 200
created: 2008/03/30 22:11:21
created_gmt: 2008/03/30 21:11:21
comment_status: open
post_name: superscript-and-subscript-with-actionscript
status: publish
post_type: post
---

# Superscript and Subscript - with Actionscript*

### *******And a little bit of custom-font magic...**

### ![johnny.jpg](http://uploads.psyked.co.uk/2008/03/johnny.jpg)

Although I do like writing lovely elegant code I'm also a big fan of 'the cheap hack'! Here's one I used last week to get round the age old problem of dynamic text boxes in Flash not supporting superscript and subscript. You need to do the following: 

  1. Install the ggsuperscript and ggsubscript fonts, available from [GG's Flash Blog](http://blog.ggshow.com/index.php/reference?cat=121)
  2. Make sure that you have 2 dynamic text boxes offstage with the 2 fonts embedded.
  3. Then you can use the following code to insert text into a dynamic text box (in this example it's called 'textObject')
  4. Job done!

> //####################################### var myString:String = "Adobe<sup>TM</sup> C<sub>2</sub>H<sub>4</sub>"; var supStartExpression:RegExp = new RegExp("<sup>", "g") var supEndExpression:RegExp = new RegExp("</sup>", "g") var subStartExpression:RegExp = new RegExp("<sub>", "g") var subEndExpression:RegExp = new RegExp("</sub>", "g") myString = myString.replace(supStartExpression, "<font face="GG Superscript">") myString = myString.replace(supEndExpression, "</font>") myString = myString.replace(subStartExpression, "<font face="GG Subscript">") myString = myString.replace(subEndExpression, "</font>") textObject.htmlText = myString //#######################################

The above code uses the new AS3 'replace' method along with it's really cool new support for Regular Expressions (the "g" bit in the regular expression makes sure that it matches and replaces ALL instances of the string). Of course you could just use the <font> tags in your code and forget all the Regular Expression stuff. I was just being a ponce! If you could be bothered you could even extend the string class etc, etc. If you are using ActionScript 2.0 you could do something really nasty like: 

> //####################################### String.prototype.replace = function(find, replace) { return this.split(find).join(replace); }; var str = originalString.replace("<sup>", "<font face="GG Superscript">"); str = str.replace("</sup>", "</font>"); str = originalString.replace("<sub>", "<font face="GG Subscript">"); str = str.replace("</sub>", "</font>"); textField.htmlText = str; //#######################################

Have fun.....

## Comments

**[savil](#282 "2008-04-28 18:08:18"):** I got my Subscript and Superscript fonts from: http://www.subscriptfont.com They work perfect with dynamic fields too...abd better than GG since it's lowere than the baseline and it is real subscript..

**[savil](#283 "2008-05-04 06:45:00"):** I want just want to share with you the way I get may subscript and superscript inin dynamic and input text field in Flash: & tags are not supported by Flash :( but you can use Subscript & Superscript in dynamic and input text field in Flash: Download & install Subscript & Superscript fonts from http://www.subscriptfont.com or http://www.superscriptfont.com You will need to restart Flash software after installed fonts. Create a dynamic text field with Arial font embeded. Set the HTML property to true. Create a dynamic text field with Subscript font embeded. Create a dynamic text field with Superscript font embeded. Use HTML tag to set text to subscript or superscript like below: Some text© If you are using ActionScript to test the htmlText, use script like below: my_txt.htmlText = "Some textTM"; They are better than CG since it goes lower than the baseline and it's real subscript..

**[James](#284 "2008-05-05 12:11:33"):** Cheers savil, we really like those fonts (much more natural than the GG ones because [as you say] they actually go outside the line borders) If anyone is looking for a way to do this with custom fonts or non sans-serif fonts, then you might want to try out [FontCreator](http://www.high-logic.com/fontcreator.html) as an option. It's not free, and its not a quick solution - but you could use the font glyph editor to resize and reposition the characters in the font to act as superscript and subscript.

**[Kevin](#285 "2009-07-02 01:45:25"):** I can't seem to get it to work on my flash. I installed the font files and saved them in my C:...fonts folder, where all the rest are. I have the two dynamic text boxes and embedded them with the right font. I put in this line of code: instructText.htmlText = "goo blob "; instructText is my text field. My font that I have in the field is Calibri. But it doesn't work for me. All it does is put a space in between the words, but no superscript action. I create the text field dynamically on the line before that line. Does that have anything to do with it? Does the location where I saved it have anything? Does the fact that I have a different font in the box have anything to do with it? I saw on another site: instructText.html = true; but when I tried that it threw me an error. Is there something along those lines that I need to do? Does it have anything to do with the "face" class added to the ? In the end I want to import the text from an xml file, what will I need to do differently? Help would be highly appreciated! Thanks!

**[Kevin](#286 "2009-07-02 01:48:52"):** Ok, so the line instructText.htmlText = “goo blob “; should be instructText.htmlText = "goo (font face=”GG Superscript”>blob” where the first parenthesis is the tag opener, "<".

**[James](#287 "2009-07-02 08:14:44"):** Kevin - One immediate thing to try is turning off font embedding on your textfield, if you have it on. Flash can be a little difficult with font embedding, and I often find that if I can't see what I'm expecting, then it's a font embedding issue. So, turn off font embedding and see what happens when you test it. When Flash doesn't have a font embedded it tends to put a 4 pixel space in the place of the characters. Beyond that, it could be a number of different issues - your font names could not be matching up, for example. Do you have a file or some complete code you can post, to have a look at?

**[Kevin](#288 "2009-07-02 21:19:25"):** Yeah, I have the file you can look at. How can I best get it to you?

**[James](#289 "2009-07-04 17:47:17"):** Kevin - can you send an email to jford[at]psyked.co.uk with the files?

**[James](#290 "2009-07-07 22:54:50"):** I've had a look at the file you sent, and I believe I've figured it out. What you've got at the moment is function calls in the following order; [...] set htmlText [...] setTextFormat() What's actually happening is that the setTextFormat is overwriting the text formatting you've set with htmlText. An 'intricacy' of the way these things work. Switch these two functions around and you should find that things start to work! If you use setTextFormat() and setNewTextFormat() on your textfield before you set the htmlText, that should work.

**[Stephen](#291 "2010-01-21 10:29:21"):** This method doesn't seem to work when I uploaded my files online to my webserver. My guess is the font GG Superscript cannot be recognised by the server. Is there any method to make the font show in websites?

**[James](#292 "2010-01-21 15:05:15"):** Stephen - Your fonts should be embedded in Flash, so they should work wherever you upload your Flash. - It shouldn't matter that the server doesn't have the font installed, nor that the client doesn't have the font installed. I'm guessing you need to check that your fonts are being embedded correctly in the Flash movie.

**[Stef](#293 "2010-02-15 23:56:05"):** This hack has been around for a while. I still don't understand why flash has no supprot for this yet! It's unbelievable to be honest. I've been waiting for a decent implementation for these tags and tags since flash 4! They can make flash now work for mobile devices and th eiphone but still they can;t make a numbered list support by default!

**[James](#294 "2010-02-16 12:17:01"):** Stef - you might want to check out the new Text Layout Framework for Flash Player. It's only available for the newer Flash 10, but it introduces a whole new text rendering system, with far greater text formatting support. http://labs.adobe.com/technologies/textlayout/

**[Aditya](#295 "2010-05-15 13:26:49"):** @James nice to know the update in flash 10. Ive been using this particular HTML rendering to solve most of the super/subscript issues. Thanks

**[sonicoliver](#296 "2010-07-13 08:25:41"):** // I like the solution, but this CSS method works for me: var style:StyleSheet = new StyleSheet(); style.parseCSS('sub{font-family:"GG Subscript";}sup{font-family:"GG Superscript";}'); displaytext.styleSheet = style;

**[srinivas](#297 "2010-08-17 03:56:34"):** hi james, iam very new to action script.iam not gettiing superscript in flash10. i created the textfield ,and i embeded the superscript font from (http://blog.ggshow.com/index.php/reference?cat=121) my_txt.text = "AdobeTM"; still iam not getting..i have to submit the project urgently.. plz help me. plz let me explain clearly (step by step)how to embeded font for textfield..

**[Stephen](#298 "2010-09-11 08:55:27"):** Hello there, James. Thanks a lot for your tutorial and tricky tips. At first i'm confused about how to use it. But after i got the hang of it, its really fun. Saves me a lot of time writing Mathematics sign and numbers.

**[sonicoliver](#299 "2010-11-07 14:46:23"):** you can also do this... var style:StyleSheet = new StyleSheet(); style.parseCSS('sub{font-family:"GG Subscript Sans";display:run-in;}sup{font-family:"GG Superscript Sans";display:run-in;}'); displaytext.styleSheet = style; displaytext.htmlText = "This is normal text this is subscript and this is super script!";

**[Ali](#300 "2011-10-06 15:38:52"):** I also got a news here that I thought would be so useful for all of us as Flash devs, Now that we are talking about TextField thought to let you know about a class that is so powerful and is extended from the Adobe TextField class itself. It's named TextArea which allows you every possible tags even your own custom tag and has much more abilities too. Check out <http://doitflash.com/> for more information. It not only allows you to load different SWF files by calling different tags in line of your text but also you have much more control over your Text blocks and its contents... such as calling your custom functions right from your text blocks and passing multiple and different arguments through them; loading talking avatars, video players, buttons, slideshows and more... by calling their own tags and having full interaction between all of the loaded SWF modules and your text block. Check out the site for more information, downloading the platform is also free of charge :)

**[dian](#301 "2011-10-10 16:46:53"):** sorry, I wanted to ask. for the solution of this subscript is true can be applied. if flash games started, how to display the subscript and superscript as the game done? Please help. Thank you.

**[factor quema grasa pdf free](#302 "2013-10-14 05:41:25"):** The first line of attack is eating a high protein breakfast. It does not care where you live, but it certainly does seem to thrive on the way you live. It is also possible that you think you cannot stand water.

