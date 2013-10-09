---
comments: true
date: 2009-01-23 15:24:08
layout: post
slug: visual-studio-2008-database-edition-and-sql-server-2008
title: Visual Studio 2008 Database Edition and SQL Server 2008
wordpress_id: 29
tags:
- .NET
- Programming
- Visual Studio
---

I recently went through the unfortunate demise of the primary disk on my main development machine, so I had to rebuild my dev environment from scratch. I have a test server running SQL Server 2005, so I decided to install SQL Server 2008 on my dev machine for compatibility testing. Imagine my frustration when I tried to load up my database project in Visual Studio 2008 and was told that I needed a local instance of SQL Server 2005!

Fortunately, Microsoft has a [new GDR release of Database Edition](http://blogs.msdn.com/gertd/archive/2008/11/25/visual-studio-team-system-2008-database-edition-gdr-rtm.aspx) that adds support for SQL Server 2008. Unfortunately, this isn't just a service pack, it's more like a product upgrade. An upgrade of your database project is required, and the project will no longer be usable by other developers on the team if they haven't upgraded to the GDR release also. Oh well, I guess you can't have everything.
