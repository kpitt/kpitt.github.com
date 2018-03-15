---
comments: true
date: 2006-07-18T17:03:43Z
categories: [ Blog ]
title: ScribbishWP Sidebar Bug in IE
wordpress_id: 15
---

Some ScribbishWP users have reported problems with the sidebar in Internet Explorer. When the site is viewed in other browsers such as Firefox or Safari everything looks fine, but in IE the sidebar disappears to the bottom of the page below the content. The problem doesn't occur on all ScribbishWP sites, so what causes the problem and what can you do about it?


### The Problem

Surprise, surprise! The problem is actually a bug in the way Internet Explorer implements CSS. It is sometimes referred to as the "Expanding Box" problem, and it is triggered when one of the elements in the content area or the sidebar exceeds the column width defined in the stylesheet, You can get all the gory details of the bug at [**Position is Everything**](http://www.positioniseverything.net/explorer/expandingboxbug.html). Internet Explorer 6.0 made a number of improvements in the handling of the CSS box model, but this particular bug still persists.

In ScribbishWP, the content area and sidebar are assigned fixed widths in the stylesheet. This is partly for stylistic reasons and partly due to technical constraints of the current CSS standards. The positioning of the content area and sidebar into side-by-side columns depends on these fixed widths.

When Internet Explorer expands the width of one of these columns, the columns will no longer fit side-by-side so the sidebar gets pushed down below the content area. This happens most often with images and `<pre>` blocks, but it's possible in other cases also. Firefox and Safari, on the other hand, will limit the displayed width of the contained elements, and add a horizontal scrollbar below the element if necessary to allow the remainder of the element to be viewed.


### The Workarounds

Yes, I said _workarounds_ and not _solutions_. There are a variety of CSS hiding techniques and other browser-compatibility tricks, and some may wonder why I don't use those to "fix" the problem in ScribbishWP. There are several modifications that can be made to the CSS styling to prevent the sidebar from shifting to the bottom, but they all involve tradeoffs, so I'm leaving it up to individual authors to decide what is best for their site.

Here are several options that you might try if you want to avoid the problem on your site.


#### Adjust Your Content

Adjusting your content to fit within the size limits of the theme is really the only way to ensure that all visitors to your site receive basically the same experience. ScribbishWP defines a content area width of 500px and a sidebar width of 200px. If you can keep your content within these limits then you won't have a problem.

You should always scale your images appropriately for the available space. `<pre>` blocks can be a little trickier because adjusting the formatting to make it narrower may affect the meaning. It is also impossible to control the exact size of the fonts on different systems, so leave a little breathing room if you can.


#### Adjust the Column Widths

If you can't quite fit your content to the default column widths, you might want to adjust the widths. The column widths in ScribbishWP are controlled by three elements in the `style.css` file: **#content**, **#sidebar**, and **#container**. #content and #sidebar should be self-explanatory. The width of #container is the total width of #content and #sidebar, plus an extra 40px for the border between the two columns. For the default widths, this is 500px + 200px + 40px = 740px.

Just be aware that the default widths in ScribbishWP are already hitting close to the limit of what can be viewed on an 800x600 screen without horizontal scrolling. If you increase the widths by much then users may need higher resolution displays to view your site properly.


#### Set Fixed Element Widths

Internet Explorer won't honor the fixed widths of the containing column elements, but it _will_ honor a specific width assigned to the element itself. Assigning a specific width to an element will force IE to display scrollbars for the element if it exceeds the specified width.

Unfortunately, IE doesn't take quite the same approach as the other browsers when adding the scrollbars. Internet Explorer covers up part of the content by adding the scrollbars inside the current display area of the element instead of increasing the display height and adding the horizontal scrollbar below the element like Firefox and Safari. You may need to make extra room in the block by adding an empty line or two at the bottom, especially for single-line blocks, but that empty line will be seen as extra blank space in all other browsers.

You'll need to consider lots of variables when determining the correct width for a particular element. For example, the `<pre>` element in ScribbishWP uses 10px of padding, so the element width needs to be set to 490px instead of 500px. There is actually another 10px of padding on the right side, but it is not part of the visible portion of the element when the element is truncated so it isn't included in the calculation. If an element is nested inside a list then you'll need to reduce the width even further to account for the bullet margin.


#### Enable Line Breaking

You can force IE to add line breaks to normally "unbreakable" text by adding the following IE-specific CSS attribute:

    word-wrap: break-word;

This will, of course, mess up the careful formatting of your text without even giving you the control that you would have had by adjusting the content yourself. Non-IE browsers will ignore this non-standard attribute, though, so it should only affect the rendering on IE.


#### Hide the Overflow

You can ensure that your beautiful layout will never be compromised by telling IE to hide any content that overflows the boundaries of the content area. On the #content element in `style.css`, add the following CSS attribute:

    overflow: hidden;

This will cause IE to simply chop off any content that doesn't fit within the column. The drawback is that IE won't add any scrollbars or anything, The content is just gone, so the IE user will never see it.  Firefox and Safari still seem to display correctly because the element widths have already been adjusted before determining if there is any overflow.
