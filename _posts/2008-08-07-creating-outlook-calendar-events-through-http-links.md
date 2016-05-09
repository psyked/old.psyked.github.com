---
layout: post
title: Creating Outlook Calendar events through hyperlinks
link: http://www.psyked.co.uk/creating-outlook-calendar-events-through-http-links/
author: psyked_james
description: 
post_id: 265
created: 2008/08/07 23:45:02
created_gmt: 2008/08/07 22:45:02
comment_status: open
post_name: creating-outlook-calendar-events-through-http-links
status: publish
post_type: post
---

# Creating Outlook Calendar events through hyperlinks

You mightn't think it was possible, the lack of implimentations you see for it on a day-to-day basis, but actually you can create Calendar events for a wide range of email / organiser clients using the iCalendar file format. From the users' point of view, your Calendar event appears as every other hyperlink does in your html pages - but when they click on the link, instead of being taken to a new page, Outlook opens up an 'add event' just as if they'd clicked on a meeting request (in Outlook). From the developers' point of view, once you have your server configured correctly, it's just a case of creating and linking to an .ics file instead of a .htm file - at which point the client's email software should take over. ![](http://uploads.psyked.co.uk/2008/08/icalendar.jpg)

## Does it work for me?

I don't know - try clicking on [this link](/icalendar.ics).  If MIME types are incorrectly set you'll probably see a plain text file, and if you don't have an application setup that's compatable with iCalendar events, you'll probably just be asked to save the file to your hard drive. 

## How do you create a Calendar event then?

First up, you need to sort out your MIME-types.  I'm not going into that because it can get a little too complex, but just make sure you have the file extension .ics registered under the MIME-type "**text/calendar**" - if you're lucky it might already be setup! Next, you need to make the actual file, which is simple in one sense and complex in another.  iCalendar files are plain text files, so you just need notepad or something to create them, but they do have a very specific format. Wikipedia has a very [simple example](http://en.wikipedia.org/wiki/ICalendar#Core_object), so we're going to use that as a basis for our sample file. So lets create a working example - and we'll use the Flash on the Beach conference as a basis. This is the example on Wikipedia; 
    
    
    BEGIN:VCALENDAR
    VERSION:2.0
    PRODID:-//hacksw/handcal//NONSGML v1.0//EN
    BEGIN:VEVENT
    DTSTART:19970714T170000Z
    DTEND:19970715T035959Z
    SUMMARY:Bastille Day Party
    END:VEVENT
    END:VCALENDAR

The framework we need to keep is pretty self explanitory - there's elements like the beginning and ending of portions of the file, and a basic framework for the dates and summary.  According to the RFC iCalendar specification, VERSION and PRODID are both required, so we'll leave those in also - which just leaves us with some customizing to do on the dates and summary information; 
    
    
    BEGIN:VCALENDAR
    VERSION:2.0
    PRODID:-//hacksw/handcal//NONSGML v1.0//EN
    BEGIN:VEVENT
    DTSTART:20080928T000000Z
    DTEND:20081001T000000Z
    SUMMARY:Flash on the Beach 08 Conference
    DESCRIPTION:Flash on the Beach 08 is here again!
    Wow, Flash on the Beach is in it's third year already! FOTB06 was awesome,
    FOTB07 was even better, and we are now pulling out all the stops to make
    FOTB08 the best yet! We have the best talent around speaking, new speakers
    to FOTB, the Inspired Sessions, workshops, parties and more! It's gonna rock!
    END:VEVENT
    END:VCALENDAR

You can see that there's practically no special formatting for the actual content - just plain text.  (Which is a shock after working with XML and CDATA for so long.)  And date formatting is just a condensed string - 1/11/2008, 15:30:00 just becomes 20081101T153000Z. Whack that into notepad, change the file extension to .ics and you're away! 

## That's it?

That really is it. It's an incredibly easy thing to customize - I'd really recommend you skim through the [spec for iCalendar](http://tools.ietf.org/html/rfc2445) if you're thinking of doing more clever things - there's formats and properties that control priorities, due dates, durations, status, alarms, journal entries - practically everything that Outlook does (beyond emails) can be done with the iCalendar format. 

## Resources

  * [iCalendar information on Wikipedia](http://en.wikipedia.org/wiki/ICalendar)
  * [iCalendar technical specification](http://tools.ietf.org/html/rfc2445)

## Comments

**[Nathan McCance](#363 "2008-08-29 23:23:31"):** You may want to check your example "icalendar.ics" file. It won't open in Apple's iCal.

**[blackock](#364 "2008-10-06 23:42:01"):** Great stuff... how would you add other invitees automatically?

**[James](#365 "2008-10-07 09:21:09"):** So far as I can tell from the spec, you can add people with the ATTENDEE element, in which you can put a list of all the people (and email addresses) that you want to attend. e.g. ATTENDEE;DELEGATED-FROM="MAILTO:jsmith@host.com":MAILTO:jdoe@host.com ATTENDEE;DELEGATED-TO="MAILTO:jdoe@host.com","MAILTO:jqpublic@host.com":MAILTO:jsmith@host.com ATTENDEE;MEMBER="MAILTO:ietf-calsch@imc.org":MAILTO:jsmith@host.com Obviously there's no way for a simple text-based file to know who's attending dynamically, but you can specify some initial persons - or power the whole thing with a server side solution.

**[Lesta G](#366 "2008-11-06 02:11:01"):** Does not work in outlook 2003 errors with This error can appear if you have attempted to save a recurring Lunar appointment in iCalendar format. To avoid this error, set the appointment option to Gregorian instead of Lunar

**[Dave Ramsey](#367 "2009-05-14 21:21:00"):** If you want to take full advantage of the features offered via an .ics file, create the event while in Outlook and then save the event as an .ics file. That way you can include the a list of attendees and any other feature available via an Outlook event. Makes a "No Brainer" of the process of creating an .ics file.

**[varumr](#368 "2009-06-05 17:43:04"):** Hey Lesta G, Did you fian a fix to to problem you stated? I am having same problem. ANy help will be greatly appriciated. Thanks

**[Jay](#369 "2009-08-26 17:35:26"):** Lesta and varumr - I realize this is a little after the fact, but to get this to work with 2003, just add the line METHOD:PUBLISH to the VCALENDAR definition section.

**[Graeme](#370 "2009-09-04 14:31:47"):** When clicking on the .ics link above, Mozilla prompts me to open the file with my mail client or save it (as expected). However, I have created a similar .ics file and uploaded it to my web server, but when pasting the URL into the browser, all I see are the plain text details of the .ics file. Any ideas why?

**[James](#371 "2009-09-04 14:37:54"):** Graeme - That's all about MIME-types on your server. Server delivered files rely less on file extensions and more on MIME-Types. Make sure your server is set to deliver files with an extension of .ics with the MIME-type "text/calendar" and that should fix it. (More info and references are in the article)

**[Andrew](#372 "2009-09-24 17:13:04"):** I have saved a number of .ics files on my local machine (desktop), when I open one of the files, change some details, and click save. None of the information get's saved. When the file is opened it still shows the original meeting info from when the file was created. How can I save changes to .ics files saved locally with the intention of attaching links to them for a website for people to download?

**[James](#373 "2009-09-24 21:44:17"):** Andrew - my only guess is that when you're editing the files in Outlook (or whatever client you're using) it's making a copy of the file and editing that. Without using the same editor to 'export' the file again I guess you won't be able to see the changes. Or, I suppose you'd need a custom solution to not write the copied files out over the top of the original.

**[event calendar](#374 "2010-04-14 15:50:42"):** Thanks Jay I had this same issue. [ clever diaries](http://www.cleverdiaries.com/) downloading again properly.

**[James](#375 "2010-04-28 10:27:59"):** this is great, very useful resource, may I ask is there a way the calendar event can automatically be saved? I really would like to create a diary entry and have it populate a users diary without the event popping up and requiring the user to "save & close" Many thanks, James

**[James](#376 "2010-04-28 15:13:33"):** James - Being able to auto-save the calendar event is something that is down to individual machines and applications, so there isn't a way to avoid the "Save & Close' requirement of applications like Outlook.

**[david](#377 "2010-07-07 16:27:15"):** I want to let the user have his info (meetings etc.) as an ics file. How do I store the file in the DB? create the file on each clients request? thanks (we use j2ee)

**[James](#378 "2010-07-07 23:32:45"):** @david - Depends on your setup, but you could either store the contents of the file (it's only plain text, after all) in the database, or generate the file from multiple fields in the database. You could either generate downloadable icalendar files whenever the user requests them, and return those files, or you could even try doing it without generating a physical file, and just have a page request return the contents of the icalendar file, with the correct MIME-TYPE, and see how well that works. MIME-TYPEs are just as important (if not more) where server side stuff is concerned!

**[JohnM](#379 "2010-12-08 18:56:44"):** I'm running Win XP Pro SP3, and I checked under: File Explorer/Tools/Folder Options/File Types, but I cannot see how/where to set the MIME-type to “text/calendar” for .ICS files.

**[James](#380 "2010-12-08 20:46:30"):** Setting the MIME-type has to be done on the server that is offering the file as a download - it doesn't work if you're just doing it on your local machine. I think you'd have to set up the MIME-type in IIS, rather than your Explorer/File Types dialog, anyway.

**[Carlos](#381 "2011-02-22 16:21:57"):** Once the event is built, as in the example, how should be submitted to the Exchange server, over email?, over HTTP? Stored into a staging server for Exchenge to pick it up?

**[Maureen](#382 "2011-06-15 19:07:08"):** I can embed the .ics file in the email and have them accept. When I tried to update the invite, the invitees received and accepted but then the original invite fell off my calendar. Any ideas why??

**[Holden](#383 "2011-07-19 22:46:18"):** Hi James, Good page of useful information. I would like to know if you're using vcalendar or icalendar specifications? Also, how would you handle frequency or reoccurring events? Also are you following RFC5546 or 5545 for the standards? Do you find that oulook sticks to the standards outlined in the RFC's? Thanks again!

**[James](#384 "2011-07-20 08:26:32"):** @Holden - I'm afraid I'm not much of an expert on the exact formats, but iCalendar is supposedly based on the earlier vCalendar format. I haven't had any trouble using either of the specifications in any Calendar clients - generally they handle everything you throw at them, so either RFC is good.

**[Steve D](#385 "2011-08-18 03:34:43"):** Jay, You say to add "METHOD:PUBLISH to the VCALENDAR definition section." Where exactly is that? I can't get it to work. TIA, Steve

**[Daniel Foster](#386 "2012-01-12 20:00:54"):** This site works great for creating the iCalendar file and if you link to it on their server, the MIME type is already set: http://www.pratie.com/lab/icalendar/

**[Ganga](#387 "2012-02-27 13:11:42"):** Hi, Have change the MIME type to text/calendar on my server. However, it still opens the text and not the Calendar request. Please help.

**[Siddharth](#388 "2012-03-19 05:30:49"):** Hi , Tell me how to create a calender elemment using dreamweaver cs5 it will help me add in travel agency website which i got a project.....

**[ヴィトン](#389 "2013-05-22 14:09:23"):** There is significantly surprise this kind of simply just released sorts are listed below: uggs estimates boots and shoes mayfair shoes or boots girls java Highkoo Microsof corporation 5450 fight-style exceptional. The artist material moisture from the feet, maintain it cold and dry. Regardless of the items your first option is, UGG Classic Short you will get in the UGG boot.

