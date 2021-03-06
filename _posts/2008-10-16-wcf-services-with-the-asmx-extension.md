---
comments: true
date: 2008-10-16 10:07:55
layout: post
slug: wcf-services-with-the-asmx-extension
title: WCF Services with the .asmx extension
wordpress_id: 28
tags:
- .NET
- Internet
- Programming
---

When creating a new Windows Communication Foundation web service, the default extension is .svc. This can be a problem if you want to migrate an existing .NET web service where clients may have hard-coded the .asmx extension. The following article from MSDN Blogs shows how to configure a WCF web service that uses the .asmx extension:

[Wenlong Dong's Blog : How to use .asmx extension to handle WCF requests?](http://blogs.msdn.com/wenlong/archive/2007/09/18/how-to-use-asmx-extension-to-handle-wcf-requests.aspx)
