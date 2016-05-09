---
layout: post
title: A reason why Photoshop CS4 kicks ass
link: http://www.psyked.co.uk/a-reason-why-photoshop-cs4-kicks-ass/
author: psyked_james
description: 
post_id: 653
created: 2009/01/28 10:02:54
created_gmt: 2009/01/28 09:02:54
comment_status: open
post_name: a-reason-why-photoshop-cs4-kicks-ass
status: publish
post_type: post
---

# A reason why Photoshop CS4 kicks ass

Here's one reason why Photoshop CS4 kicks ass (here's something completely new). ![Content Aware Scale](http://uploads.psyked.co.uk/2009/01/contentawarescale.jpg) It's called "**Content-Aware Scale**".  Unlike the transform controls from previous iterations, this scaling mode is somehow aware of the contents of an image and can discern what elements you want to scale. So when you start scaling up or down, only the elements like the sky, water, background elements stretch and the people and buildings maintain their perspective and float around the scaling background.  Pretty cool huh? So here's an image I've grabbed from Google - a panorama of [Trakai Castle](http://en.wikipedia.org/wiki/Trakai_Island_Castle).  In the image below I've scaled it to 50% width - the top image is "Content-Aware Scale", and the bottom image is shrunk with the normal transform tools. ![Content Aware Scale - Example](http://uploads.psyked.co.uk/2009/01/contentawareexample.jpg) That took 30 seconds to do.  How long would you previously spend cleverly masking and cloning areas of the image by hand to do that? How cool is that - it's image transformation, just like in the movies.  Next we'll be enhancing perfect images of suspects from pixellated CCTV footage, just like in CSI.

## Comments

**[Paulius Uza](#532 "2009-01-28 10:59:50"):** Sorry for the off topic, but is this Trakai Castle in the picture? :)

**[James](#533 "2009-01-28 11:05:05"):** You know, I think it is - I grabbed the picture from Google Image search, but was never able to find it again to give some attribution! I'll change the 'some castle' bit in the post above.

**[lee](#534 "2009-01-28 17:55:36"):** Very coool James, but how does content-aware-scaling look in high-resolution? Any noticeable artifacts, blurs, etc?

**[James](#535 "2009-01-28 18:12:19"):** There's nothing obvious in terms of quality loss - I should mention that the screenshot above is pretty poor quality - I forgot to turn on antialiasing in my Photoshop preferences when I did that! I think there are limits to what it can do when you're scaling things up or down - my best guess is that it's working with convolution filters to pick out areas of high contrast and edges, and then scaling portions of the image as it goes. If your image has got a lot of large artefacts then it'll preserve them, but it does a pretty fine job of matching blurs around edges. The only thing I've picked up on is the scaling of shades and tones - in the image above you can notice that the sky colours have been squashed in the top picture - it's preserved the general texture, but with the sky colours being a very similar tone, it hasn't really picked up on the colour changes and dealt with those.

**[whatever](#536 "2009-01-29 10:44:04"):** Google "Seam Carving" if you'd like to know how it's done.

