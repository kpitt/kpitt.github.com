---
layout: post
title: "Replacing the TextMate 2 Icon"
date: 2013-10-02 21:05
comments: false
external-url: 
categories: [Mac, Applications]
---

The application icon for Textmate 2 is a bright, pink flower.  Maybe they just want to avoid confusion with the commercial version during the alpha phase, but it does look a little unprofessional next to the other icons in dock. Fortunately, it's an easy fix.  Here's how to do it:

1. [Download][tm_download] and extract the 1.5 version of TextMate.
2. `Ctrl-Click` the application and select **Show Package Contents**.
3. Browse to the `Contents > Resources` folder and copy the `TextMate.icns` file.
4. Now select **Show Package Contents** on the TextMate 2.0 application and go to the `Content > Resources` folder there.
5. Rename the original `TextMate.icns` file to `TextMate.icns.backup`, then paste in the `TextMate.icns` file from TextMate 1.5.

You now have a copy of TextMate 2.0 that uses the old TextMate 1.5 icon.  If TextMate is running, you'll need to quit and restart it for the change to take effect.  You may also continue to see the old application icon cached in Finder until you log out and back in.

There are a few minor limitations.  There are no hi-res Retina versions of the icon, and this only replaces the application icon so the pink flower will still make an occasional appearance in other areas such as the document icons.  Most importantly, the icon file will get replaced whenever you update the application so you'll need to repeat this procedure after each update.

[tm_download]: http://macromates.com/download
