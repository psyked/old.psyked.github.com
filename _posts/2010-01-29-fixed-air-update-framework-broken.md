---
layout: post
title: Fixed: AIR update framework broken!
link: http://www.psyked.co.uk/fixed-air-update-framework-broken/
author: psyked_james
description: 
post_id: 1160
created: 2010/01/29 22:30:30
created_gmt: 2010/01/29 21:30:30
comment_status: open
post_name: fixed-air-update-framework-broken
status: publish
post_type: post
---

# Fixed: AIR update framework broken!

![](http://uploads.psyked.co.uk/2010/01/broken-air-update-framework.jpg) _Arrgh!_ All of a sudden the AIR Update Framework stops working.  No explanation, no errors; nothing. Where you'd expect to see your update notification popping up, you get a window just like the one above - no content, just the default Flex blue background colour. The problem is actually a pretty specific one, but it's not going to fix itself.  Using the Flex 3.5 SDK and the AIR Update Framework together causes this issue - obviously some part of the Flex SDK has changed between Flex 3.4 and 3.5, and no-one tested the framework before releasing it!  The issue is fixed in Flex 4 and doesn't occur in anything other than the 3.5 SDK - so upgrading / downgrading is one solution; or... 

### Hack a solution:

Kudos to **Richard Leggett** for this solution; you can add an event listener for the **StatusUpdateEvent.UPDATE_STATUS** event, which includes this code: [sourcecode language="javascript"] try { var loader:Object = NativeApplication.nativeApplication.openedWindows[1].stage.getChildAt(0); loader.content.application.visible = true; } catch(e:Error) { trace("Wait till Flex 4!"); } [/sourcecode] And this will get things back and working again. 

### More information:

[Read the official bug report in the bug management system.](http://bugs.adobe.com/jira/browse/SDK-24766?focusedCommentId=334246&page=com.atlassian.jira.plugin.system.issuetabpanels:comment-tabpanel#action_334246)

## Comments

**[sectore](#803 "2010-01-30 16:39:21"):** That's not really a fix, call it workaround ;) Fortunately Adobe has reopen SDK-24766 to review this bug these days: <https://bugs.adobe.com/jira/browse/SDK-24766> Hoping it will be fixed soon ;) -Jens

**[James](#804 "2010-01-30 22:32:06"):** Yep, not really a fantastic fix! The proper alternative to this workaround would be to fix the error properly - but that would mean making the fix in the source and recompiling the SWC files for the ApplicationUpdaterUI classes. Haven't had time to try that one out, but it would be great if someone could. The disadvantage to this hack seems to be that the window always opens & then closes - doesn't stay there for very long, but the opening is discernable. I guess this is also to do with the way that the interface has changed between SDKs.

**[sectore](#805 "2010-01-31 12:54:10"):** At [SDK-24766](http://bugs.adobe.com/jira/browse/SDK-24766) you will find an instruction by Horia Olaru to rebuild a applicationupdater_ui.swc. Unfortunally it did'nt work for me. The update framework is one of most important thing to build and deliver an AIR app. Personally I can't understand, why Adobe does such a miserable job on it. Because it is not the first time that the applicationupdater_ui is broken, check [SDK-22886](http://bugs.adobe.com/jira/browse/SDK-22886) or just search for ApplicationUpdater or ApplicationUpdaterUI at the bug base: <http://bugs.adobe.com/jira/> What is the end of the story? You have to build your own ApplicationUpdaterUI, as I did for Flex 4 some months ago: [Custom ApplicationUpdaterUI for using AIR Update Framework in Flex 4](http://www.websector.de/blog/2009/09/09/custom-applicationupdaterui-for-using-air-updater-framework-in-flex-4/) However, that cant be the right way ;) -Jens

**[James](#806 "2010-02-03 10:13:32"):** It seems this issue has now been _properly_ fixed by the Flex / AIR team, with the release of the Flex 3.5a SDK: http://blogs.adobe.com/air/2010/02/important_update_to_the_flex_3.html

