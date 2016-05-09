---
layout: post
title: Having trouble with workspaces in Appcelerator Titanium?
link: http://www.psyked.co.uk/having-trouble-with-workspaces-in-appcelerator-titanium/
author: psyked_james
description: 
post_id: 1352
created: 2011/07/19 10:05:51
created_gmt: 2011/07/19 09:05:51
comment_status: open
post_name: having-trouble-with-workspaces-in-appcelerator-titanium
status: publish
post_type: post
---

# Having trouble with workspaces in Appcelerator Titanium?

So I was having some trouble with corrupted workspaces in Appcelerator Titanium. Every time I launched the application it would try opening this corrupt workspace, and now offer any options for selecting a different one. The solution? In the end, I just had to resort to deleting the entire `.metadata` folder of the Workspace. Nuclear option maybe, but it worked, and the Titanium Studio was at least able to open for long enough for me to change or rebuild the workspace.

## Comments

**[DS905](#882 "2012-01-04 00:36:16"):** Delete the file %WORKSPACE_PATH%/.metadata/.plugins/org.eclipse.core.resources/.snap, and restart Studio

**[James](#883 "2012-01-05 10:16:44"):** @DS905 - Sounds like a good suggestion, thanks!

