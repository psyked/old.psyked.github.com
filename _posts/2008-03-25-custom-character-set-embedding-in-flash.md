---
layout: post
title: Custom character-set embedding in Flash
link: http://www.psyked.co.uk/custom-character-set-embedding-in-flash/
author: psyked_james
description: 
post_id: 199
created: 2008/03/25 23:13:11
created_gmt: 2008/03/25 22:13:11
comment_status: open
post_name: custom-character-set-embedding-in-flash
status: publish
post_type: post
---

# Custom character-set embedding in Flash

You know those lovely font embedding options? Wouldn't it be great if you could make your own character sets? ![customfontembedding.jpg](http://uploads.psyked.co.uk/2008/03/customfontembedding.jpg) As great as the default options are (All, Uppercase, Lowercase, Numerals) the latter 3 combined don't contain all of the visible characters - and the 'All' option embeds thousands of other useless characters. So how about this?  If you are bored with Flash taking ages to publish because you have (rather lazily!) embeded the full Unicode font set (I really have no idea what embedding 39477 characters achieves, Verdana - in the Windows Character map on my PC - only lists 665 chars) then this is a little bit of code I knocked up this morning that might help (someone could turn it into a class pretty application if they want!) **What do you need to do?**

  1. Copy and paste the code below into frame 1 of an FLA.
  2. Change the code in **bold**. The variable 'myString' contains whatever characters you want to embed. In my example (which may be of use) I am embedding all the Verdana characters listed in the Windows Character Map. N.B. I have added a space at the start as this is an important character to embed! Note also that to embed a quotation mark you must write " and to embed an backslash you must write \\. You need to give your font set a name (in this example it is 'Dynamic Learning Character Set' but you can put whatever you want). This is what will appear in the list when you click the 'Embed...' button in Flash. Finally you need to specify a unique 'fontSetID'. Flash seems to have taken the numbers 1 - 20 and 9999(!?!) so you can pick any number you like other than those.
  3. Press CTRL+ENTER to test the FLA and copy the XML that is generated in the output window.
  4. Open the file: C:Program FilesMacromediaFlash 8enFirst RunFontEmbeddingUnicodeTable.xml...and paste in your XML to the top (just under the <fontEmbeddingTable> node)
  5. Save the UnicodeTable.xml file and restart Flash. You should now see that you can embed your custom font into your SWF. If you need to add other characters you can just repeat the above steps to update UnicodeTable.xml and then republish your SWF file.
This technique reduced my project publish time from 85 seconds to 22. 
    
    
    var myString:String = "** !"#$%&'()*+,-./0123456789:;<=>?@ABCDEFGHIJKLMNO
    
    PQRSTUVWXYZ[\]^_`abcdefghijklmnopqrstuvwxyz{|}~¡¢£¤¥¦§¨©ª«¬­®¯°±²³´µ¶·¸¹
    
    º»¼½¾¿ÀÁÂÃÄÅÆÇÈÉÊËÌÍÎÏÐÑÒÓÔÕÖ×ØÙÚÛÜÝÞßàáâãäåæçèéêëìíîïðñòóôõö÷øùúûüýþÿAa
    
    AaAaCcCcCcCcDdÐdEeEeEeEeEeGgGgGgGgHhHhIiIiIiIiIi??JjKk?LlLlLl??LlNnNnNn?
    
    ??OoOoOoŒœRrRrRrSsSsSsŠšTtTtTtUuUuUuUuUuUuWwYyŸZzZzŽž?ƒOoUu??????ˆ?¯??°?
    
    ˜?`´~??;?????????????G????T?????????S??F??O???????aß?de??????µ???p??st?f
    
    ????????????????????????????????????????????????????????????????????????
    
    ????????????????????????????????????????????????????????????????????????
    
    ??????????????????????????????????????????????????????–—?=‘’‚?“”„†‡•…‰'?
    
    ‹›??/n?£P?€?l?™?e???????-/·v8?˜?==????????**"
    
    
    var nameOfFontSet:String = "**My Character Set**"var fontSetID:Number = **50**
    
    generateCharSet( nameOfFontSet, fontSetID, myString);
    
    
    function generateCharSet (setName, setID, chars) {
    
       var outputXML:String = "<glyphRange name="" + setName + "" id="" +
    
    setID + "">n"
    
       var numberOfChars:Number = chars.length;
    
       for (var i:Number=0; i<=numberOfChars-1; i++) {
    
          var charCode:Number = chars.charCodeAt(i)
    
          var hexCode:String = convertTo4DigitHexValue(charCode.toString(16))
    
          outputXML += "t<range min="0x" + hexCode + "" max="0x" +
    
    hexCode + "" />n"
    
       }
    
       outputXML += "</glyphRange>"
    
       trace("outputXML:n" + outputXML);
    
    }
    
    
    function convertTo4DigitHexValue (hexValue:String):String {
    
       var hexLength:Number = hexValue.length;
    
       var numberOfLeadingZerosRequired:Number = 4 - hexLength;
    
       for (var i:Number=0; i<=numberOfLeadingZerosRequired-1; i++) {
    
          hexValue = "0" + hexValue;
    
       }
    
       return hexValue
    
    }

## Comments

**[John Priestley](#280 "2009-05-01 05:41:11"):** Hi James. This is a great and helpful post but I find it doesn't quiate address my need. I wonder if you can help? I'm trying to load the set of International Phonetic Alphabet characters, nearly all of which render quite nicely on my local machine (MacOS X), in any of various fonts including Arial, Lucida, Myriad Pro, as long as I don't embed the font. But many of them won't render in Windows. I tried your procedure as explained above, and it all appears to go as expected, but didn't change the way the font renders once I embed it. Do you have any suggestions as to what I should be reading to get deeper into this?

**[James](#281 "2009-05-01 09:17:23"):** @John - Have you tried using the 'All' character set with the International Phonetic Alphabet? It sounds like the reason you won't be seeing all of the custom characters in Windows, and the reason their appearance isn't so good is because the characters are not all embedded in the Flash movie. The information above deals with the font glyphs for the basic 600 or so characters that make up all of the Latin language variants - if the Phonetic Alphabets' characters are outside those bounds then the code listed above probably won't be embedding them properly. - So although it looks like it works, its not catering for the IPA font glyphs?

