---
layout: post
title: Corona SDK: Solving JSON decode error with UTF-8 files.
link: http://www.psyked.co.uk/corona-sdk-solving-json-decode-error-with-utf-8-files/
author: psyked_james
description: 
post_id: 1456
created: 2011/11/14 22:41:45
created_gmt: 2011/11/14 21:41:45
comment_status: open
post_name: corona-sdk-solving-json-decode-error-with-utf-8-files
status: publish
post_type: post
---

# Corona SDK: Solving JSON decode error with UTF-8 files.

While working with JSON-encoded data files, I had some problems getting the darn things to work.  Apart from an unhelpful error message, the Corona simulator gave me no clues as to what was wrong. Turned out that the problem was actually to do with the UTF-8 encoding. And in the end, what fixed it was changing the UTF-8 encoding to **"UTF-8 without BOM"** \- the default UTF-8 encoding just didn't cut it. ![](/wp-content/uploads/2011/11/corona-ribbon.png)