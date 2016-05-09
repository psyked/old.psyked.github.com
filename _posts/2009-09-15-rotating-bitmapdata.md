---
layout: post
title: Rotating BitmapData with Actionscript 3
link: http://www.psyked.co.uk/rotating-bitmapdata/
author: psyked_james
description: 
post_id: 942
created: 2009/09/15 22:00:07
created_gmt: 2009/09/15 21:00:07
comment_status: open
post_name: rotating-bitmapdata
status: publish
post_type: post
---

# Rotating BitmapData with Actionscript 3

Here's a little snippet - rotating BitmapData (through 90 degrees) with Actionscript 3. [sourcecode language="javascript"] var matrix:Matrix = new Matrix(); matrix.translate(-bmd.width / 2, -bmd.height / 2); matrix.rotate(90 * (Math.PI / 180)); matrix.translate(bmd.height / 2, bmd.width / 2); var matriximage:BitmapData = new BitmapData(bmd.height, bmd.width, false, 0x00000000); matriximage.draw(bmd, matrix); [/sourcecode] The code above can rotate an images BitmapData, using a Matrix to transform the image when you draw the data.  It's only really designed to rotate the image in 90 degree increments though - so be aware of that. How it actually works is to create a new Matrix object, offset the source BitmapData's width and height (so the rotation goes from the center of the bitmap), rotate the BitmapData, move the BitmapData again (to undo the previous offset), create a new BitmapData object to draw the rotated BitmapData into, and finally draw the source BitmapData with our newly created Matrix. Simple.

## Comments

**[Konstantin](#673 "2010-09-12 09:51:55"):** Wow, thanks a lot. That's exactly what I was looking for :)

**[Teo](#674 "2010-12-26 23:20:21"):** +1))

**[gray_hare](#675 "2011-02-23 21:13:22"):** You're not actually rotating BitmapData here as the tittle suggests. You're just telling BitmapData object how pixels have to be drawn and this is not the same.

**[James](#676 "2011-02-24 01:13:06"):** **gray_hare** \- Isn't the end result the same though? It's not like this is a filter that's being applied, we input one bitmapdata object, and get another, rotated version of the bitmapdata.

**[karl](#677 "2011-05-09 09:14:16"):** thnx, you helped me out here..

**[Eric](#678 "2011-07-31 16:25:21"):** gray_hare - Actually he is rotating the bitmapdata when he's drawing it into the new bitmap, and the new bitmap has a "new Matrix" which is a non rotated matrix. Also there is a better way to do this. Use this for 90 degree rotation: var matrix = new Matrix(0, -1, 1, 0, 0, bmd.height / 2); Use this for 180 degree rotation: var matrix = new Matrix(0, -1, -1, 0, bmd.width / 2, bmd.height / 2); Use this for 270 degree rotation: var matrix = new Matrix(0, 1, -1, 0, bmd.width / 2, 0); This is a lot faster and accurate.

**[WORMSS](#680 "2012-04-11 16:06:10"):** Shouldn't it be: Use this for 90 degree rotation: var matrix = new Matrix(0, -1, 1, 0, 0, bmd.width);

**[Paul](#681 "2012-07-16 21:39:27"):** The code to rotate is EXACTLY what I need but not sure how to incflude it in the Class below. Its a basic camera Class for AIR for Android. Takes good pictures but the saveImage function saves the image to cameraroll except that its lying at 90 degrees relative to the image onscreen. Was hoping to somehow add the rotation code before save. Any help would be appreciated. Thanks Paul package { import flash.display.BitmapData; import flash.display.Sprite; import flash.display.Stage; import flash.display.StageAlign; import flash.display.StageScaleMode; import flash.events.TouchEvent; import flash.media.Camera; import flash.media.CameraRoll; import flash.media.Video; import flash.ui.Multitouch; import flash.ui.MultitouchInputMode; import flash.geom.Matrix; [SWF(backgroundColor="#000000", frameRate="24")] public class MobileAS3ExamplesCamera extends Sprite { private var video:Video; private var videoHolder:Sprite; private var camera:Camera; private var capture:BitmapData; private var cameraRoll:CameraRoll; public function MobileAS3ExamplesCamera() { super(); stage.scaleMode = StageScaleMode.NO_SCALE; stage.align = StageAlign.TOP_LEFT; setupVideo(); setupCamera(); registerListeners(); } protected function setupVideo():void { videoHolder = new Sprite(); videoHolder.x = stage.stageWidth/2; videoHolder.y = stage.stageHeight/2; video = new Video(480, 360); videoHolder.addChild(video); video.x = -180; video.y = -240; //videoHolder.rotation = 90; addChild(videoHolder); } protected function setupCamera():void { camera = Camera.getCamera(); camera.setMode(480, 360, 24); video.attachCamera(camera); } protected function registerListeners():void { Multitouch.inputMode = MultitouchInputMode.TOUCH_POINT; stage.addEventListener(TouchEvent.TOUCH_TAP, saveImage); } protected function saveImage(e:TouchEvent):void { capture = new BitmapData(480, 360); capture.draw(video); cameraRoll = new CameraRoll(); cameraRoll.addBitmapData(capture); } } }

**[male escort service florida](#682 "2013-12-20 15:40:26"):** Thanks for finally writing about > Rotating BitmapData with Actionscript 3 | Psyked < Liked it!

