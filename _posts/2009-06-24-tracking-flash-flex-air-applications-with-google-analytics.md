---
layout: post
title: Tracking Flash / Flex / AIR applications with Google Analytics
link: http://www.psyked.co.uk/tracking-flash-flex-air-applications-with-google-analytics/
author: psyked_james
description: 
post_id: 916
created: 2009/06/24 09:45:31
created_gmt: 2009/06/24 08:45:31
comment_status: open
post_name: tracking-flash-flex-air-applications-with-google-analytics
status: publish
post_type: post
---

# Tracking Flash / Flex / AIR applications with Google Analytics

In case you weren't aware, a lot of the stuff you can do in a website you can also do in the Flash Player.  Prime example: Google Analytics tracking. Now for a simple Flash movie, you'd traditionally host the Flash file in an external website, and add the tracking to the HTML pages.  If you're doing something a little more different - or are obsessive about knowing how your users are interacting with the content - you might be interested to know that there is support for actionscript-initiated tracking, and that it's supported by Google themselves (a good sign). You can read all about the Google Analytics tracking component for Flash on the Google code website: <http://code.google.com/apis/analytics/docs/tracking/flashTrackingIntro.html> Where this really comes into its own is in AIR applications.  Flash / Flex tracking in a HTML website isn't really all that special - once you know the API a little, you can always use the ExternalInterface commands in the Flash Player to communicate with javascript functions on the host page, but that kind of option isn't usually available to a pure Flash-based AIR application.  Using the component effectively removes the need for the external javascript file, and means that your desktop AIR application can communicate freely with Google Analytics - enabling application tracking.  The code is no different whether its an online Flash webpage, or a desktop AIR application.

## Comments

**[venkat](#650 "2009-06-25 01:51:06"):** GA tracking is not supported for AIR applications. There is a note on the page that says. "Note: Currently, Flash tracking is available for any Flash content embedded in a web page. Tracking of data sent from Adobe Air, Shockwave, or via the Flash IDE (e.g. using Test Movie) is not supported at this time."

**[James](#651 "2009-06-25 08:18:44"):** @venkat - That may be so, but speaking from experience, it does actually still work. I'm working on a more in-depth 'how to' post, so stay tuned...

**[Luis Tello](#652 "2009-07-28 18:29:06"):** What did you use as a URL when you signed up GA. Did you use a proxy URL and then sent all your data over to it as it occurred on the Air App?

**[James](#653 "2009-07-28 19:46:26"):** I actually used just the url of this website (http://www.psyked.co.uk/) - it seems the URL is just used for validating the account - and there's no problems with the tracking.

**[Luis Tello](#654 "2009-07-28 20:45:45"):** Hey James, We got the account and pulled Google's code from ga.js and put it locally. We need to wait till 3:50pm EST, but are we missing anything else?

**[alchemist](#655 "2009-09-09 12:40:17"):** Here's a more detail example of Flex and Google Analytics hope it helps http://bytearray.brixtonjunkies.com/2009/08/20/flex-google-analytics-howto/

**[Paul Sanderson](#656 "2009-09-16 13:51:41"):** Hey guys if you want to track an Air Application you should look at http://www.airanalytics.net. We can tell you how many installs you have had, the number of uses etc... we can even keep tracking when your app is offline.... Air Analytics currently in private beta but we are looking for people to test out our system. So if you register I will activate you and you can have a bash with our system. Thanks Paul

