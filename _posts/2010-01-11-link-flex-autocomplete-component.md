---
layout: post
title: Link: Flex AutoComplete component
link: http://www.psyked.co.uk/link-flex-autocomplete-component/
author: psyked_james
description: 
post_id: 1111
created: 2010/01/11 15:07:20
created_gmt: 2010/01/11 14:07:20
comment_status: open
post_name: link-flex-autocomplete-component
status: publish
post_type: post
---

# Link: Flex AutoComplete component

If you're ever looking for an autocompletion component in the Flex framework, I'd strongly suggest you check this one out: <http://hillelcoren.com/flex-autocomplete/> Quite simply it's awesome, it's fully featured and packs a helluva lot of options into such a small package. I swapped an old ComoBox component for it just now, and it worked fantastically with no additional configuration. Check out the demo for it here: <http://web.me.com/hillelcoren/Site/Demo.html>

## Comments

**[Jeffry Houser](#767 "2010-01-11 15:26:25"):** If you're looking for a Flex AutoComplete that comes with support, you can check out ours at: http://www.flextras.com/?event=ProductHome&productID=10 It is based on the Combobox so, is a slightly different take than Hillel's.

**[Tink](#768 "2010-01-11 16:03:56"):** We also have one of these as the hillelcoren one was too complex for our needs. http://www.tink.ws/blog/filtercombobox/

**[James](#769 "2010-01-11 17:03:21"):** Thanks guys, I'll check both of those out also - there's another couple of situations where a ComboBox-based solution would be more suitable.

**[Jeffry Houser](#770 "2010-01-11 17:10:02"):** Let me know if we can answer any questions that you have. Ours can easily revert to an AutoCompete TextInput by just removing the down arrow via a property (I believe downArrowVisible ). If you're dealing with large data sets, but don't want to load the data all at once, we support the pinging of a database, and replacing the dataProvider after each call. As always, we'd welcome any feedback that you'd have.

**[Tink](#771 "2010-01-11 18:23:06"):** In the same wat, setting 'arrowButtonWidth' to 0 would make ours look like a TextInput. Personally I recommend access to a DB through a command and storing the data in a model, then bind the FilterComboBox to the data.

**[Jeffry Houser](#772 "2010-01-11 18:48:32"):** Tink, Not sure if that last comment was directed at me or not; but just to be clear; there is nothing about our AutoCompleteComboBox that prevents that approach, even if you are using our "RemoteData" option or not. I believe that encapsulation is important to the long-term maintainability of a code base; and encapsulating the data access functionality seems like a no brainer.

**[Tink](#773 "2010-01-12 10:51:11"):** It was aimed at you as a diss mate, was just commenting on how I would recommend managing data and serverside calls (i.e. I wouldn't do this from inside view components).

**[Tink](#774 "2010-01-12 13:17:44"):** LOL "wasn't"

**[Jeffry Houser](#775 "2010-01-12 14:05:45"):** Tink; In that case I agree completely.

**[James](#776 "2010-01-12 15:37:37"):** Thanks for the comments guys, got a bit tense there! In the end I actually ended up using Tink's FilterComboBox component - the original one was great but the multiple selection stuff was throwing a spanner in the works.

**[Jeffry Houser](#777 "2010-01-12 15:54:47"):** James, I you took a look at the Flextras AutoCompleteComboBox; I'd welcome any feedback. Feel free to contact me privately if that is your preference.

