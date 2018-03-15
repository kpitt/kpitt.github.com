---
comments: true
date: 2014-09-20T00:00:00Z
external-url: null
categories: [ Programming, Applications ]
title: PowerShell Mode for Zed
---

There's a new crop of programmer's text editors out there written with
JavaScript and Web browser technology, and they've been getting a lot of buzz.
I've been playing around a bit with several of them, and I'm intrigued by
[Zed][zed].  Zed steps a bit outside the traditional box and tries to bring a
simplified approach to code editing with minimalist UI and reduced command
complexity.  It also features an excellent remote editing mode, and it feels
like it takes cross-platform compatibility more to heart than some of the
other options.

I've recently been doing some PowerShell scripting at work.  You don't really
need a full-fledged IDE for PowerShell, so I decided to see if I could set up
Zed for script editing.  There's no PowerShell mode included and I couldn't
find any existing extensions, but Zed is based on the [Ace][ace] editor
component and it turns out that Ace already has PowerShell support.  With
just a few lines of JSON configuration, I was able to create a Zed PowerShell
mode for `.ps1` script files.  Thanks to the hidden functionality already
provided by Zed and Ace, you get not just syntax highlighting but also code
folding and autocompletion.

Installing the PowerShell mode is extremely simple using the Zed Package
Manager.  Just run the `Tools:Zpm:Install` command and enter
`gh:kpitt/zed-powershell-mode` for the URI.  You can access the
[source on GitHub][gh_psmode] if you would like to comment or contribute.

[zed]:       http://zedapp.org/
[ace]:       http://ace.c9.io/
[gh_psmode]: https://github.com/kpitt/zed-powershell-mode
