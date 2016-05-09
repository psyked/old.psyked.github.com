---
layout: post
title: A (rather crude) FQL syntax pretty-printer.
link: http://www.psyked.co.uk/a-rather-crude-fql-syntax-pretty-printer/
author: psyked_james
description: 
post_id: 1311
created: 2011/06/14 21:08:34
created_gmt: 2011/06/14 20:08:34
comment_status: open
post_name: a-rather-crude-fql-syntax-pretty-printer
status: publish
post_type: post
---

# A (rather crude) FQL syntax pretty-printer.

I've been working with [FQL](https://developers.facebook.com/docs/reference/fql/) \- Facebooks' SQL-like syntax - and I wanted a way to nicely format FQL queries, just as its possible to format JSON data. For example, I wanted a query like this one: 
    
    
    "SELECT uid,name,birthday,birthday_date FROM user WHERE uid
    IN ( SELECT uid2 FROM friend WHERE uid1 = me() ) ORDER BY
    birthday_date ASC"

To look more like this one: 
    
    
    "SELECT uid,name,birthday,birthday_date
        FROM user
        WHERE uid
        IN (
            SELECT uid2
                FROM friend
                WHERE uid1 = me()
        )
        ORDER BY birthday_date ASC"

Apparently, there's not much out there for formatting SQL syntax data, so I thought I'd make one myself. It's not perfect, but it works good enough for now - maybe I'll have a chance to improve it further in future. The code itself is stored on GitHub, and its Gist looks like this: