AIR-ChromeWindowBlur-ANE
========================

A native extension for Adobe AIR for Mac/OSX development that uses Core Graphics to enhance window SystemChrome option with blur/alpha effects
Extension is compiled with XCode 5.1.1 and deployment target is set at 10.8+

What this ANE (Native Extension) Does?
======================================

Since a lot of folks love to build mobile and desktop applications with Adobe AIR, I found that System Chrome option lacks transparency and if you want transparance you have to invest quite a bit of time to write Native Window controls in AS3 and you end up with an app that doesn't look as native without the System Chrome (traditional system caption bar). 

With the upcoming arrival of OSX Yosemite, I'm sure a lot of AS3 developers will want their Mac apps to look similar to the native look of the OS, so I created a native extension that overrides some of the properties of AIR Framework and allows Custom Chrome to act as standard System Chrome but with cool visual blurring and transparency effect using Core Graphics API.

How to use it?
===============

I tried to allow developers as much freedom as possible and included options for transparency amount, the blur amount and even the color of the background window to play with.

You just need to get the ANE from this repo, link it with your project and off you go. 

FLASH CC/2014 LINKING:

1. Go to Actionscript 3 setting where you would normally include the SWC files.
2. Hit + and point to the location where you placed the ANE to link it.


FLASH BUILDER:

1. Open Project Properties
2. Go to Actionscript Build Path
3. Add SWC file
4. Change the file type to .ANE in the dialog box
5. Locate the ANE and add it.

NOTE: Adobe recommends Link Type for the attached ANEs to be of external type not Merged Into Code.


Example Usage:
===============

Since we are extending Custom Chrome functionality from AIR framework that doesn't have title bar, I've given you the ability to specify custom title.

```
import com.bozzified.extensions.NativeWinBlur;

// create instance for AIR window Core Graphics awesomeness
var win:NativeWinBlur = new NativeWinBlur();

// set window attributes - always goes before enableWindowBlur()
// ARGUMENTS TO PASS
// hasWindowTitle:Boolean=true, windowTitle:String="", maximizable:Boolean=true, minimizable:Boolean=true, closable:Boolean=true, resizable:Boolean=true
win.setWindowAttributes(true, "Core Graphics AIR Chrome Window Blurred", false, true, true, false);

// set effect properties 
// ARGUMENTS TO PASS
// alpha:Number=0.5, blurAmount:uint=50, red:uint=0, green:uint=0, blue:uint=0 
win.enableWindowBlur(0.4, 30, 255, 255, 255);

```



