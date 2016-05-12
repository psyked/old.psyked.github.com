---
layout: post
title: Link&#58; POSTing XML data, without using HTTPService
link: http://www.psyked.co.uk/link-posting-xml-data-without-using-httpservice/
author: psyked_james
description: 
post_id: 911
created: 2009/06/21 18:32:49
created_gmt: 2009/06/21 17:32:49
comment_status: open
post_name: link-posting-xml-data-without-using-httpservice
status: publish
post_type: post
---

# Link: POSTing XML data, without using HTTPService

_[This came up a while ago, but I thought I'd promote the link I found that solved my woes.]_ The situation: I'm trying to interact with a REST API, via Flex and AIR.  Now, I know that the HTTPService class exists in Flex to make it really quick and easy to send and recieve data, but the downside of the HTTPService class is that it assumes a little top much.  It assumes for example, that any data you're trying to send comes in a name/value pair - which my data doesn't. The REST webservice I'm using requires raw XML data, but the HTTPService class doesn't do that. The solution?  Well, there's only one - don't use the HTTPService class, and code everything yourself.  Thankfully, this link I found tells you exactly how to do that, along with examples. <http://tacfug.org/blog/index.cfm/2007/3/26/Flex--Posting-XML-without-using-mxhttpservice->

## Comments

**[Wai Lam](#642 "2009-06-22 04:52:31"):** You can try post raw xml as text by. var request:HTTPService = new HTTPService(); request.method = "post"; request.resultFormat = "text"; request.contentType = "text/xml"; request.request = xml.toString(); request.send(); Also work with json by setting. request.contentType = "application/json"; request.request = JSON.encode(data);

**[James](#643 "2009-06-22 08:14:30"):** Thanks Wai - that looks like a good solution too.

**[Logan](#644 "2009-06-22 12:15:18"):** We use HTTPService for some of our XML POSTs to our RESTful web service. It seems to work fine for us. ` somevalue anothervalue `

**[Logan](#645 "2009-06-22 12:17:33"):** Oops, it ate my code: http://pastie.org/520067

**[Hydrolyze](#646 "2009-10-16 02:20:56"):** Just wanted to say hello all. This is my first post. I came to learn a lot here.

**[trertance](#647 "2009-11-09 15:06:12"):** Hello. My PC worked slowly, many errors. Help me, please to fix buggs on my computer. I used Windows XP. With best regards, trertance

**[Gosytholons](#648 "2013-05-04 22:51:45"):** Вы помните скандал, разгоревшийся прошлым летом? Тогда обладатель "Золотого тигра" Роттердамского кинофестиваля, вполне себе выдающийся фильм "Клип" сербского режиссера Майи Милош не получил прокатное удостоверение: запретительный документ был подписан рукой Ивана Демидова. Босс музобозовского человека в черных очках Владимир Мединский публично ругал "Клип" последними словами, что не помешало петербургскому фестивалю "Послание к человеку" пригласить Милош в жюри, правда, без "Клипа" (незадолго до этого показанного во внеконкурсной программе ММКФ). Все нормальные СМИ, и мы в том числе, откликнулись на эту возмутительную ситуацию и написали, что в цивилизованном мире ситуацию с откровенными фильмами решают возрастные ограничения. Это было за считаные недели до начала развернувшейся в России оргии с этими самыми ограничениями — вы не могли не обратить внимание на аршинные цифры "16+" и "18+", украшающие сегодня все афиши (включая совсем абсурдные надписи "Детям старше 18 лет" — тут на ум не приходит ничего, кроме анекдота: "Вовочка, но он же мальчик! — Ничего себе мальчик, 23 года!"). Исходя из этого, в России лицам допризывного возраста нельзя смотреть, слушать и читать ничего. Французская малышня хохочет — в отличие от чиновников Минкульта. Предполагаю, что они схватились за сердце и возопили: "Порнография!" Нет, никто напрямую не требовал вырезать эпизод, но фильму — на все сто детскому — решили дать ограничение. Да, "18+". Что, само собой, было равносильно прокатной смерти. В итоге компания "Вольга" с разрешения Алена Шаба вырезала веселого пса. Я вот думаю, может, надо с такой квазицензурой бороться, используя закон о защите прав потребителей? Вы купили билет и, если хронометраж фильма, показанного в кинотеатре, отличается от официального (его легко найти в сети, хотя бы на сайте imdb.com), можете требовать деньги назад. Должен быть выход. Раз уж нам так "повезло", что культурой в стране заведуют люди с менталитетом персонажа из песни Высоцкого: "Был в балете — мужики девок лапают!"

**[how to make money](#649 "2014-01-15 19:18:30"):** Spectacular internet site. A lot of helpful info right here. I will be giving it to a few associates ans also sharing around delectable. And naturally, thanks with your effort!

