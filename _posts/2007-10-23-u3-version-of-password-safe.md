---
comments: true
date: 2007-10-23 17:19:30
layout: post
slug: u3-version-of-password-safe
title: U3 version of Password Safe
wordpress_id: 22
tags:
- Applications
---

I recently purchased a [U3](http://www.u3.com/)-enabled flash drive. I've been using [Password Safe](http://passwordsafe.sourceforge.net/) (originally from Bruce Schneier's [Counterpane Labs](http://www.counterpane.com/), now a SourceForge project) for some time now to store my passwords, and it seemed like a perfect application to have on a flash drive. I was shocked when I discovered that they wanted $9.95 for the [U3 version](http://software.u3.com/Product_Details.aspx?productId=294&Selection=7) of a free utility!

Well, the [U3 Developer Kit](http://www.u3.com/developers/deploymentkit_sc.aspx) is available for a free registration and Password Safe is Open Source, so I decided to see if I could build my own U3 version. It turned out to be easier than I thought. The standard binary distribution of Password Safe already includes all of the necessary U3 support. I just followed the U3 packaging guidelines along with some pathnames gleaned from the Password Safe source to lay out the U3 package. I then used the U3 tools to generate the manifest file and configure the various actions. I even wrote a little device install utility as an [NSIS](http://nsis.sourceforge.net/) script to make sure the default data directory gets created when installing to the flash drive.

I'm hereby making available the final result under the same [Artistic License](http://www.opensource.org/licenses/artistic-license.php) terms as Password Safe itself. This is based on the 3.10 version of Password Safe, but I will attempt to provide updates whenever I happen to notice a new release of the original binaries. Feel free to [email me](mailto:kenny.pitt@gmail.com) if you have any feedback. I simply ask that you remember I had nothing to do with the original Password Safe program, only the packaging.

  * [U3 Installer](http://download.pittcrew.net/projects/U3/pwsafe/pwsafe-u3-3.10-installer.exe)
  * [Source](http://download.pittcrew.net/projects/U3/pwsafe/pwsafe-u3-3.10-src.zip)  
    The source ZIP contains just the source files for the U3 packaging. You'll need to obtain the program binaries from Password Safe and the `U3Action.exe` from the U3 Developer Tools, then place the files according to the directory listing in `package_dir.txt`. You can also get the U3P2EXE tool from the U3 site to build the executable installer package.
