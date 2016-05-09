---
layout: post
title: Auto-matic Link Icons
link: http://www.psyked.co.uk/auto-matic-link-icons/
author: psyked_james
description: 
post_id: 86
created: 2007/07/10 18:42:17
created_gmt: 2007/07/10 17:42:17
comment_status: open
post_name: auto-matic-link-icons
status: publish
post_type: post
---

# Auto-matic Link Icons

CSS 2.1 has many new wonderful capabilities, and I'm going to show you one of my latest tricks I've picked up - automatic link icons. First, a look at the end result :- ![](http://uploads.psyked.co.uk/2007/07/auto-matic-link-icons.png) Now, you may have seen similar things on a few websites already, wikipedia certainly makes use of the technique to highlight external links. The astute of you may notice that the 'external' link isn't actually external - think of it more as 'absolute'. How do we achieve these results automatically? Well, that's with the power of the new CSS selectors. [456BereaSt.](http://www.456bereastreet.com/archive/200509/css_21_selectors_part_1/) has a nice article on them, but the stuff we're concerned with is the attribute selectors. Attribute selectors are done with [square brackets], and can include simple conditional statements, with some options for wildcards thrown in to boot. The easiest way for me to explain is to show you... Here's a simple 'absolute' link selector - a[href="http:"] - this will target all the 'a' tags, with the attribute 'href' which is equal to "http:". Interesting, but its not very useful, because the attribute would need to be exactly "http:" for it to work. So, we add the ^ operator, which means 'starts with'. So ( a[href^="http:"] ) means any link with a href attribute that starts with 'http:' - thus, every external link. Another operator we can use is $, which means 'ends with'. So a[href$='.pdf'] is any links that end with .pdf. Now we know how to automatically treat different links differently. Oh, and it works fine in all the most recent browsers (IE7, Firefox) And won't have any effect on browsers that don't understand the selectors, so its safe to use. Now, styling the links is really a matter of personal preference, (and your design), but I the infamous [famfamfam](http://www.famfamfam.com/) silk icon set will help you out here. Once you've got your icons, a little clever implimentation of styles will enable you to indent your link slightly to add you icon in as a background image. Thus;  And you're away - limited only by your icon supply, and the volume of conditional statements you want to make! Here's mine - covering external links, mailto links, and common document formats...

## Comments

**[Jonathan Nicol](#20 "2007-07-18 22:46:29"):** Very nice tip James! I've bookmarked this one. It's one of those nice little tricks that will display as intended in all modern browsers, and gracefully degrade in IE 6.

**[James](#21 "2007-07-19 10:42:09"):** Glad it helps! In the event that you've requirements that can't be met like this - or you need more compatability with older browsers, you can always take the base CSS that generates the iconified effect, and apply it manually as 'normal' styles.

**[Pensador](#22 "2007-07-19 18:20:20"):** Great article—I'll use it on my blog! :)

**[超](#24 "2007-07-22 05:07:36"):** 谢谢。

**[kisPocok](#25 "2007-08-02 20:25:51"):** test: http://www.google.hu/test.zip

**[James](#26 "2007-08-02 21:32:57"):** Hey hey, it works! An interesting effect though with the combination of external linked files... I wonder wether I can find a fix for that...

**[James](#27 "2007-08-03 11:46:05"):** Hmm, I bet the external link+file type issue could be fixed with the :before and :after selectors?

**[James](#28 "2007-08-09 22:20:54"):** Nope... I was wrong. I guess that external link icons need a little more thought...

**[john](#31 "2007-08-23 11:18:47"):** Im a bit new to css but would a roll over effect still work on image backgrounds using your automated stylesheet if used a:hover [href$='.doc'] ?????

**[James](#32 "2007-08-23 13:46:57"):** That's really dependant on your setup - Elements can only have one image background. So, if your links elements already have a background image either of the CSS styles could be overwritten. If however, the parent element of your link has the background image, they should both display their respective backgrounds. Does that help?

**[Hajcc](#34 "2007-10-14 19:44:41"):** hello i have an idea ... add Internet explorer icon to the normal links

**[James](#35 "2007-10-15 20:40:32"):** Indeed - adding an Internet Explorer Icon for .htm pages is possible, and I've seen it on other websites, like those created in Sharepoint Server (Microsofts') - but I decided to steer clear of it, so-as not to offend users of other browsers. It does however, give me another idea... Combine this CSS with another script - such as the [css browser selector](http://rafael.adm.br/css_browser_selector/), and you can tailor the .htm icons to your visitors browser... i like it.

**[Website Design Belfast](#40 "2007-11-04 23:44:57"):** Good read

**[hbadorties](#47 "2007-12-10 16:20:07"):** In Dreamweaver CS3 the CSS code; a[href$='.pdf'] { display:inline-block; padding-left:20px; line-height:18px; background:transparent url(Images/PDFIcon.gif) center left no-repeat; } generates the error "Error parsing styles Affects: Internet Explorer 6.0" Any advice?

**[James](#48 "2007-12-10 16:33:43"):** @hbadorties - I can't be sure without having Dreamweaver CS3 to hand, but it's probably throwing the warning because of the a[href$='.pdf'] selector. IE6 doesn't support these attribute selectors fully, meaning the styles wouldn't be recognised by that browser, the upshot being that IE6 won't display the custom styles for your links. On the plus side, it wouldn't break anything. The only way around this is to manually apply the link styles with classes. So it's not a critical warning, IE6 is just (unfortunately) incompatable with this method!

**[rdmey](#52 "2008-01-07 03:02:50"):** If you're looking for a way to do this that will work in IE6, you can do it with Javascript -- users who don't have Javascript enabled won't see it, but that's likely a smaller population than users who are using IE6. I've written about a way to do it with jQuery here: http://blog.rebeccamurphey.com/2008/01/06/unobtrusive-cross-browser-add-filetype-icon-link-javascript-jquery/

**[David Jacques-Louis](#55 "2008-02-23 15:54:35"):** It works on WP as well.

**[marketing and web design](#56 "2008-03-17 01:24:45"):** Great tips thanks

**[Robin Hak](#59 "2008-06-23 05:24:05"):** Nice trick. I didn't realize I could do that. I wish more websites did this. Although the icons used in this example do look a little big.

**[James](#60 "2008-06-25 15:50:00"):** The icons in the example are standard [favicon](http://en.wikipedia.org/wiki/Favicon) size, although I take your point.

**[Ross B](#61 "2008-07-12 12:30:26"):** Hi. Good post, James - although a bit advanced for me to follow entirely at the stage I'm at with Dreamweaver CS3. Will revisit when I know more. Just one query that I'm sure is simple, but that I can't figure out. How do you add a title to an email link? It's simple to add an email link and to have the onsite text link read any way you want, but how do I have the subject line of the email already typed in, so the site visitor clicking on the email link doesn't have to type a title in themselves before sending their email? Would be appreciative of any help re this if it is not too time-consuming! Cheers Ross

**[James](#62 "2008-07-12 14:58:33"):** Ross - you'll want to check out this page, ["Using the mailto link"](http://www.outfront.net/tutorials_02/adv_tech/mailto.htm).

**[Ross B](#63 "2008-07-13 05:51:08"):** Brilliant! Thanks a lot, James! Cheers Ross

**[manas](#64 "2008-08-06 21:47:22"):** Indeed useful! Thanks.

**[Rajnikant](#65 "2008-09-02 14:25:19"):** IE 6 not support this code :-(

**[James](#66 "2008-09-02 14:36:40"):** @Rajnikant - No, unfortunately not. You can achieve the same effect however, with javascript. Check our Rebecca Murphey's article: <http://blog.rebeccamurphey.com/2008/01/06/unobtrusive-cross-browser-add-filetype-icon-link-javascript-jquery>.

**[Wetter](#67 "2008-10-16 15:09:06"):** Nice article. It was very helpful for me.

**[Brian](#68 "2008-10-21 01:06:44"):** I'm having trouble with the icons showing in IE. This works great in FF, however. I'm wondering if IE needs a specific doc type statement or if there's another reason why these won't show? I'm using your code almost verbatim. a[href$='.pdf'] { display:inline-block; padding-left: 32px; padding-top: 5px; background: transparent url(/images/pdf_icon.gif) no-repeat center left; } On this page: www.calcounties.com/buyer-seller.php The icons show in FF but not IE. Ideas on this?

**[James](#69 "2008-10-21 10:54:50"):** @Brian - Internet Explorer 6 and below don't support these CSS selectors. I've looked at your page in IE7 and it works, but IE6 doesn't. The only solution I can think of for IE6 would be using javascript (<http://blog.rebeccamurphey.com/2008/01/06/unobtrusive-cross-browser-add-filetype-icon-link-javascript-jquery>) which gets you the same effect by modifying the link classes.

**[Thierry](#70 "2008-11-03 16:33:17"):** It is a great way to add icons to links, but I have a problem : a[href^="http:"] { display:inline-block; padding-right:14px; background:transparent url(/Images/ExternalLink.gif) center right no-repeat; } using this, I have an icon before all links but I don't want to have it when I link an image , I just want it to work with TEXT. Is it possible without using classes ?

**[James](#71 "2008-11-04 10:34:14"):** You can combine several CSS selectors to get it only targeting text links - try using **p a[href^="http:"] {} ** to only select links inside a paragraph or overwrite the styles on images with **img a[href^="http:"] {** or **a[href^="http:"] img {** to reset the background image, padding and line-height elements.

**[kevin](#72 "2008-11-04 13:25:29"):** CSS 2.1 is compatible with every type of browser like IE and Firfox....

**[css](#73 "2008-11-11 21:57:19"):** Cascading Style Sheets (CSS) web design lessons Css link Properties Attributes - examles [Css Link Exanmples 1](http://www.css-lessons.ucoz.com/link-css-examples-1.htm) [Css Link Exanmples 2 ](http://www.css-lessons.ucoz.com/link-css-examples-2.htm)

**[Mehdi](#74 "2008-11-12 00:40:13"):** Awesome !

**[Matt](#75 "2008-12-02 13:49:22"):** I do like this idea, but has anyone noticed that if you have the link in the middle of a paragraph then zoom in just once in IE7 everything goes haywire - i've played around trying to fix it but have been unable to.

**[James](#76 "2008-12-02 14:04:25"):** @Matt : I never noticed that before in Internet Explorer - but I've tested it and I see what you mean. I wonder wether the zoom property of CSS could fix that...

**[Colin](#77 "2008-12-22 23:54:08"):** I tried to click the underlined "actually".

**[James](#78 "2008-12-28 11:59:20"):** @Colin - the underlined "actually" isn't really a link, just underlined text.

**[Lee](#79 "2009-01-15 17:01:48"):** I never noticed that before in IE - but I’ve tested it and I see what you mean. I wonder wether the zoom property of CSS could fix that… Lee

**[http://www.scriptremix.com/](#80 "2009-04-05 05:44:06"):** **How to add file type Icons to Links with CSS...** you may have seen similar things on a few websites already, wikipedia certainly makes use of the technique to highlight external links....

**[Mahbub](#81 "2009-04-23 10:07:33"):** These are only for CSS3 compliant browsers right?

**[James](#82 "2009-04-23 21:06:41"):** Actually, these selectors are part of the CSS2 spec, so they don't need CSS3 compliant browsers. Most major browsers from IE6 and up support the selectors on links.

**[raj](#83 "2009-05-11 05:26:03"):** nice Auto-matic Link Icons great tutorial thanks

**[aurrutia](#84 "2009-05-11 18:15:12"):** Hi!, nice trick! It is possible to use something like this for all my downloads (www.mydomain.com/download.php?id=10, www.mydomain.com/download.php?id=11, www.mydomain.com/download.php?id=12 ...)? I tried this but doesn't work: ` a[href $='** .php?id=#**'] { display:inline-block; padding-right:14px; background:transparent url(/Images/zip-icon.gif) center right no-repeat; }` any idea?

**[Tom](#85 "2009-06-13 11:34:04"):** Thanks a lot, James

**[Yunus](#86 "2009-06-18 19:47:05"):** Thanks a lot. love it.

**[Mick](#87 "2009-07-25 22:42:05"):** Thanks. You saved me a lot of grief!

**[Thom](#88 "2009-08-01 05:17:49"):** Great tips thanks

**[pdf](#89 "2009-08-06 15:09:58"):** http://www.pdf.com/PDF.pdf

**[Carola}i{](#90 "2009-08-26 16:21:10"):** Hi, thanks for this tutorial, very very useful, but I'm having a bit of a problem... Is there any code I could use to block the external link image appearing for all my links? Now it's displaying in every link I have in my blog, which is upsetting my layout a bit (like links for comments and categories are all displaying my external link image :-s). Thanks :)

**[James](#91 "2009-08-26 19:50:40"):** Carola - the best way to limit the effects is using more specific CSS - so instead of: a[href^="http:"] {} you could do .content a[href^="http:"] {} which would only affect the links inside the content container, and leave everything outside it alone.

**[Carola}i{](#92 "2009-08-26 23:38:50"):** @ James - Thanks, but it didn't work unfortunately :(

**[Matt](#93 "2009-08-27 10:25:38"):** @aurrutia - I suspect that in `a[href $=' .php?id=#']` the # isn't matching your actual links, I'd suggest trying a[href*="download.php?"] Thats assuming that all your downloads go through that page and that no other pages contain the string download.php @Carola - I'd guess that means that all links on your site are absolute rather than relative, so you could try using the standard: a[href^="http:"] { /* apply your external link styles here */ } then overriding and resetting the styles for links which are internal to your domain by doing something like: a[href^="http://www.yourdomain.com"] { /* reset your internal link styles here */ } hth Matt

**[Fania](#94 "2009-09-05 20:21:17"):** I have to say it is a little hard for me to understand all. But thank you so much.

**[ozan](#95 "2009-10-21 00:47:49"):** how to call avatar from profile? is it possible?

**[James](#96 "2009-10-21 11:48:48"):** @ozan - Check out <http://en.gravatar.com/> to see how to get your picture alongside your comments.

**[Ted](#97 "2009-11-02 18:25:19"):** test: http://shopandsupport.ca/sasgroup/resources/SAS_ORDERFORM_0909.pdf

**[Peter](#98 "2009-11-06 15:48:05"):** This is very useful information for me, thanks to everyone that has made useful comments, i have learnt a lot today.

**[Douglas Helmer](#99 "2009-12-16 02:52:12"):** James, Great post! Nothing irks me more than clicking a link that turns out to be a PDF file. I've already implemented your code for PDF links on a site I'm creating. I'm eager to try out the code on other types of links as well. Thanks, too, for the link to the famfamfam silk icon set. BTW, I have lint in my belly button as old as you (was that TMI?) ;) :)

**[James](#100 "2009-12-16 15:19:46"):** TMI :o

**[Umair](#101 "2010-01-26 15:04:43"):** Good work James. Though its not working on that IE6 but you have given a great tip. Going to bookmark :)

**[gamri](#102 "2010-02-21 19:55:27"):** thnkx

**[James Head](#103 "2010-02-28 19:52:28"):** Hi, I found this in a book I borrowed from the library: "CSS the missing manual" though they used: a[href^='http://'] instead of the " you use. Theirs didn't work at all, but trying your code, it works on my site in Firefox, but I can't see the icons in IE, though your website looks okay in both IE and Firefox. Dunno what's going on there then, but thanks.

**[Chicago Web Design](#104 "2010-03-08 18:22:06"):** awesome, the reply to using the 'mail to' link covered what I had in my head. Thanks James!

**[David Kaye](#105 "2010-03-28 23:37:25"):** Blimey - it works! In ie7 at least. Thanks for the share.

**[Ezra Kaminska](#106 "2010-04-03 01:42:37"):** Amazing, I never new this, thanks.

**[chicago web development](#107 "2010-04-10 06:27:30"):** Nice tutorial and a good trick. Though it was difficult to understand but got it in the end. Thanks

**[Jason](#108 "2010-05-27 04:44:52"):** Can anyone tell me if there are problem with IE8 using this CSS as I cannot get it to work under IE8

**[James](#109 "2010-05-27 08:38:45"):** No known issues with IE8, can you post a link?

**[Jason](#110 "2010-05-28 05:11:13"):** Hi James here is my html test [Test](http://www.test.test/test.doc) </body This is the archive css a[href$='.pdf']{ display:inline-block; line-height:18px; min-height:18px; overflow:visible; background:transparent url(../images/icons/pdf.ico) center left no-repeat; padding:2px 0 2px 20px; } a[href$='.xls'], a[href$='.csv'], a[href$='.xlt'], a[href$='.xlw'] { display:inline-block; line-height:18px; min-height:18px; overflow:visible; background:transparent url(../images/icons/excel.ico) center left no-repeat;/*-------------------------------*/ padding:2px 0 2px 20px; } a[href$='.doc'], a[href$='.rtf'], a[href$='.docx'] { display:inline-block; line-height:18px; min-height:18px; overflow:visible; background:transparent url(../images/icons/word.ico) center left no-repeat; padding:2px 0 2px 20px; } any Ideas

**[Jason](#111 "2010-05-28 05:13:49"):** sorry <!-- test [Test](http://www.rtbunsw.test/test.doc) </body \-->

**[Jason](#112 "2010-05-28 05:25:35"):** I have placed a link Thanks jason

**[James](#113 "2010-05-28 09:06:42"):** I think the problem there is the file format - I would be surprised that IE8 supported the ".ico" format for background images. Try switching it for a PNG file and see how that works.

**[Chris](#114 "2010-06-22 11:13:38"):** Great stuff, I'll be sure to use this!

**[chris](#115 "2010-07-21 14:54:17"):** http://www.text.com

**[Atul K.](#116 "2010-08-06 13:35:29"):** Great tips thanks

**[Dale](#117 "2010-08-10 22:19:30"):** Testing.... hmmm. [something.gif](something.gif) [something@something.com](mailto:something@something.com) [something.pdf](something.pdf) [something.swf](something.swf) [something.xls](something.xls) [something.ppt](something.ppt) [something.zip](something.zip)

**[Don](#118 "2010-08-25 09:37:58"):** Click [here](http://www.something.com/test.pdf) for my file [My zip file](http://www.pdf.com/test.zip)

**[Trace Meek](#119 "2011-01-07 20:33:12"):** Great work! Can one use regular expressions to select for a "not" case? For example, a common pattern is to have a linked image, which I wouldn't want to have an icon after it. How would this pattern (a img) be matched in the regular expression? Thanks!

**[Trace Meek](#120 "2011-01-07 20:45:35"):** Regarding my previous comment, on second thought, this is not an attribute selector at all. There must be some way to target parent elements that contain certain child elements.

**[Edwin](#121 "2011-01-21 17:23:03"):** Wow this is really neat! I am going to use this.

**[Edwin](#122 "2011-01-27 13:04:32"):** This is actually a really neat trick. I'm still not sure what use it is though, I'll have to have a think!

**[Jason](#123 "2011-03-04 15:17:53"):** Sometimes there are instances when I DON'T want it to automatically show up due to display problems when the text is around images, or in bulleted lists or when the text spans to two lines. Is there a way to create a "class" of some sort and apply it to the specific link so the icon doesn't show up? Here's what I have for PDF. a[href $='.pdf'] { padding: 0 16px 0 0; display: inline-block; background: url(/images/icon_pdf.png) transparent no-repeat center right; }

**[Jason](#124 "2011-03-04 15:35:45"):** Nevermind...figured it out. I created a class and manually applied it to the particular link I didn't want it to show up. Below is the code I used if anybody else needs to do this: .imageLink { padding-right: 0px !important; background: none !important; }

**[ferra](#126 "2011-07-23 18:47:15"):** A lot of thanks, it works!

**[Jane](#127 "2011-07-26 21:57:19"):** Works great - thanks! I have a CSS newbie question though. My a:hover style uses white text with a blue background on a white body. With the transparent background, it causes the link to disappear when it's rolled over. Is there a workaround, aside from changing the hover style?

**[James](#128 "2011-07-26 22:01:51"):** @Jane - You'd have to change the hover style - but you could choose to omit the `transparent` keyword altogether, and it'd just inherit the background that already exists, instead of overriding it: `a[href^="http:"] { display:inline-block; padding-right:14px; background:url(/Images/ExternalLink.gif) center right no-repeat; }`

**[Jane](#129 "2011-07-28 23:07:22"):** Perfect! That fixed it. Thank you so much!!

**[WordPress Themes](#130 "2011-08-13 10:00:44"):** Great tutorial. Exactly what I needed. The trick is in the line-height!

**[Matt](#131 "2011-09-22 21:34:30"):** Any tricks to include file size :) I don't think you can get file attribs with css but maybe with java. any ideas? [test.pdf [100000 gb]](test.pdf)

**[Matt](#132 "2011-09-22 21:35:17"):** oo and AWESOME! :)

**[Ezfera](#133 "2011-09-27 00:33:15"):** THANK YOU!!!!!!!!!!!!!!!!!

**[Matt](#134 "2011-09-27 13:12:59"):** To my question above about file size, for local files you can use filesystemobject with java or vbscript. No solution for external links yet.

**[Constantin Schneider](#135 "2011-10-21 12:53:27"):** Thank you!

**[evil twin](#136 "2011-11-02 05:37:02"):** Awesomely helpful - thanks : ) Question: is there a way to make a rollover out of this, preferably CSS only? The 'display: inline-block' doesn't seem to work the same way as plain 'display: block'.

**[Wsmith](#137 "2011-11-30 03:15:21"):** Hey, I use this all the time. But I have a challenge. I am using this for ZIP links, but depending on what's stored in the ZIP (say PDF or Word) I want to customise it dependent on this. So I wrote a class that's applied to the on ZIPs containing Word files so it would display a Word icon. Only that it just adds another icon. Any suggestions so I can customise a bit easier? I used a minus margin-left to bump it over but you can clearly see there is one icon over-lapping another. Cheers!

**[Christian](#138 "2012-02-10 08:48:40"):** Thank you. Very usefull tutorial and exactly what I needed.

**[Matt](#139 "2012-02-10 14:41:35"):** Wsmith, you could try a large negative for your margin-left (-8000) Personally I would leave both icons and do something like zip (word) to symbolize zips with word documents.

**[Rudolf Mccallister](#140 "2012-03-13 06:59:30"):** Thank you, I've recently been looking for details about this subject matter for ages and yours is the best I've discovered so far.

**[Tony Rodriguez](#141 "2012-04-17 15:09:15"):** We recently removed the icons that were hard-coded in over 500 pages and then came to realize that on mobile devices the icons would be useful, so this saves us having to re-insert all the icons. Great tip, thanks.

**[Al Lemieux](#142 "2012-05-29 20:26:49"):** What size should these icons be? I'm guessing the same size as your body text. So if it's 100%, then it would be 16px. Then what happens on a responsive design when everything re-flows and scales? These would probably scale too.

**[Halley](#147 "2013-05-15 08:07:53"):** 0001pt; font-size: 12pt; font-family: Times; h1 margin: 0in 0in 0. This is just a short explanation on speed exercises for the gig bags uk, there should always be a love and demand for the electric gig bags uk. But a new project on Kickstarter called gTar is sparking a flurry of fundraising and backers, to the exclusion of learning regular chord fingerings.

**[lipc.lv](#148 "2013-09-24 16:45:01"):** Hello, just wanted to mention, I enjoyed this article. It was practical. Keep on posting!

**[Xanax](#149 "2013-10-05 14:48:02"):** Hello, i think that i saw you visited my web site so i came to “return the favor”.I'm trying to find things to improve my web site!I suppose its ok to use some of your ideas!! Also visit my website [Xanax](http://forum.the-track.co.uk/profile.php?mode=viewprofile&u=262430)

**[bajar de peso zanahoria](#150 "2013-10-18 02:17:39"):** I have to thank you for the efforts you have put in penning this blog. I'm hoping to view the same high-grade content by you later on as well. In truth, your creative writing abilities has inspired me to get my very own website now ;) Check out my website [bajar de peso zanahoria](http://www.youtube.com/watch?v=J2Niz9L9Oro)

**[como revertir la diabetes pdf](#151 "2013-10-21 20:56:56"):** Hi there, I want to subscribe for this web site to take most up-to-date updates, therefore where can i do it please help out. Have a look at my weblog ... [como revertir la diabetes pdf](http://www.youtube.com/watch?v=zOsnBLO_kMc)

**[Darin](#152 "2013-11-09 08:15:59"):** Hello Dear, are you genuinely visiting this web page daily, if so after that you will absolutely take good experience. Have a look at my webpage; website ([Darin](http://moorecnmq.bravesites.com))

**[คาสิโนออนไลน์](#153 "2013-11-22 18:44:21"):** What i do not realize is if truth be told how you're now not really a lot more neatly-preferred than you might be right now. You're so intelligent. You realize therefore considerably in the case of this topic, produced me individually consider it from numerous numerous angles. Its like men and women don't seem to be interested until it is one thing to accomplish with Lady gaga! Your own stuffs excellent. Always deal with it up!

**[Occult Connection](#154 "2013-11-25 04:22:28"):** Tao is also a Chinese character which represents a path or way. In addition, Lopez has been a fundamental secret of magick since occult supplies san francisco ancient times. Far out on the dark ships that seek the basalt quays of the great Aurora, when over the swamp played the shocking corruscations of the daemon light. But quite frankly, the question comes down to a desolate shore and out over a vast knighted sea escape. But you should not rely on offers of a single lender; rather contrast the various loan quotes.

**[electronic cigarettes health hazards](#155 "2013-11-28 09:46:48"):** I am genuinely delighted to read this weblog posts which consists of plenty of useful facts, thanks for providing such statistics.

**[movers towson md](#156 "2013-12-06 22:02:08"):** What's Going down i'm new to this, I stumbled upon this I have discovered It absolutely helpful and it has helped me out loads. I am hoping to give a contribution & aid different users like its aided me. Good job.

**[houston brothers roofing in jacksonville fl](#157 "2013-12-12 01:28:30"):** Simply desire to say your article is as astounding. The clearness in your post is just great and i can assume you are an expert on this subject. Well with your permission let me to grab your RSS feed to keep up to date with forthcoming post. Thanks a million and please carry on the enjoyable work.

**[G](#158 "2013-12-22 03:38:52"):** Needed this - Thanks Jason!!

