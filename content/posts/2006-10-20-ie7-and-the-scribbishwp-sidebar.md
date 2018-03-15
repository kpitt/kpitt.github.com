---
comments: true
date: 2006-10-20T14:40:11Z
tags:
- Blog
title: IE7 and the ScribbishWP Sidebar
wordpress_id: 18
---

After a lengthy beta cycle, Internet Explorer 7 has finally been released. Microsoft claims that IE7 has significantly better CSS compatibility than previous releases, so how does that impact the sidebar "bug" in ScribbishWP? You'll be happy to know that IE7 does in fact fix the overflow problem that caused the sidebar to shift to the bottom of the page. Unfortunately, IE7 still puts the scrollbars inside the existing content space, but it's a whole lot better than having to play games with specific elements in your content to prevent IE from barfing.

On a related note: Jeffrey Hardy, the creator of the original Scribbish theme, recently introduced an updated style targeted at a minimum display resolution of 1024x768 (see [I no longer care about 800x600](http://quotedprintable.com/articles/2006/10/11/i-no-longer-care-about-800x600)). Requiring a higher screen resolution allows a wider area for content, which reduces the likelyhood of hitting the overflow issue in the first place. Hopefully I'll have some time soon to add the wider style as an option in ScribbishWP.
