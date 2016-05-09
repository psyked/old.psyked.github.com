---
layout: post
title: "getURL doesn't work!"
link: http://www.psyked.co.uk/geturl-doesnt-work/
author: psyked_james
description: 
post_id: 125
created: 2007/10/01 13:47:17
created_gmt: 2007/10/01 12:47:17
comment_status: open
post_name: geturl-doesnt-work
status: publish
post_type: post
---

# "getURL doesn't work!"

Ever used **getURL();** for loading new pages in Flash? That's how you load a new page. Obvious, huh? In 97% of situations it works fine. The other 3% it doesn't* I've had a rough ride with getURL unexplicably not functioning. Turns out that it works if you omit target parameter of the function call, it works. Remember that next time you get stuck... * Please note, statistics are made up on the spot.

## Comments

**[pall zoltan](#216 "2007-12-27 17:37:02"):** i've had the same problem, and for a reason or another, getURL wouldn't work so i had to move my code form the .as file onto the button itself... i've seen people having problems with this even in flash 5... i was using flash cs3, publishing FP9, AS2

**[Rob](#217 "2010-02-16 15:23:23"):** What is: 'omit target parameter'? How do you set this? Example?

**[pallzoltan](#218 "2010-02-16 15:26:54"):** it means that you write getURL('http://www.google.com/'); instead of getURL('http://www.google.com/', '_blank');

**[Alam](#219 "2011-10-05 04:43:34"):** i had same problem. alls.on(release){ //Replace URL with your own URL, or customized actions. getURL("http://www.filmsemestamendukung.com/index.php", _blank); }; // or alls.onRelease{ //Replace URL with your own URL, or customized actions. getURL("http://www.filmsemestamendukung.com/index.php", _blank); }; also wont work.

**[tenda](#220 "2013-11-26 07:16:52"):** The easiest fix is to specify AllowScriptAccess="always" in the HTML page. So the html embed code should read something like:

