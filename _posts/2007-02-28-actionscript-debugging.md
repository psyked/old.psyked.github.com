---
layout: post
title: ActionScript Debugging
link: http://www.psyked.co.uk/node41/
author: psyked_james
description: 
post_id: 43
created: 2007/02/28 17:43:42
created_gmt: 2007/02/28 16:43:42
comment_status: open
post_name: node41
status: publish
post_type: post
---

This is a simple little segment of code that i find very useful to work my way through flash files. It basically lists 
all the properties (which includes direct children) of the target movieclip. Here's a few implementations... 

(Set n beforehand with something like var n = my_mc) `for(var i in n){ trace(i+" : "+n[i]); };` and that's it in a 
nutshell. Your output will be something like this; `property : value` Ok, so thats not a very good example, but try it 
and you'll see. Here's a function-based version for you... 

    traceProperties = function(movieclip){ 
        n = movieclip; 
        for(i in n){ 
            trace(i+" : "+n[i]); 
        } 
    }

and its Actionscript 2.0 sibling... 

    function traceProperties(n:Object):Void{ 
        for(var i in n){ 
            trace(i+" : "+n[i]); 
        } 
    }
