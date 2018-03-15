---
comments: false
date: 2005-09-17T17:57:42Z
categories:
- Programming
title: Coolest New Technology at the PDC
wordpress_id: 7
---

OK, so [Visual Studio 2005](http://lab.msdn.microsoft.com/vs2005/default.aspx) and the .NET Framework 2.0 are scheduled to be released on November 7. There's a lot of cool stuff there, but we've known about that for quite a while and with the beta already in Go Live it hardly qualifies as "new" anymore. There's [Windows Vista](http://msdn.microsoft.com/windowsvista/) which includes some cool enhancements to the end-user experience and provides opportunities for developing some new types of OS add-ons, but it doesn't seem like a huge win for general development. There's "Avalon", now called Windows Presentation Foundation, which is great for UI developers and graphic designers, but I work more on the back-end stuff. "Indigo", now called Windows Communication Foundation, has some improvements to the development model for Web Services and some efficiency improvements if you're doing WCF to WCF and aren't concerned about interopability. Other than that, I don't see a lot of difference in the development effort required.

So what is the coolest new technology that Microsoft showed at the PDC? My vote goes to [LINQ](http://msdn.microsoft.com/library/en-us/dndotnet/html/linqprojectovw.asp), which stands for Language Integrated Query. I'm sure there will be lots of details written about LINQ in the near future, but in a nutshell LINQ allows you to write SQL-like queries in a consistent and type-safe way against .NET collections, SQL data sources, or XML documents. Syntax for the LINQ query language will be handled by the C# 3.0 compiler, but according to Microsoft's Anders Hejlsberg, LINQ will not require any changes to the .NET runtime. All the runtime features needed to implement LINQ are already part of the 2.0 Framework.

The LINQ query language is based on a function pattern that developers can implement for any object type to provide custom query support. Standard implementations are provided for IEnumerable<> collections, Microsoft SQL Server databases, and XML data. The function pattern approach also allows other .NET languages such as Delphi to develop their own query syntax that will support the LINQ functionality.

For SQL Server databases, LINQ provides new attributes that can be applied to class definitions to define an object-relational mapping, allowing the developer to view the SQL tables as objects and properties. The LINQ preview also contains a tool that will generate the mapping classes for an existing SQL Server schema. For XML, LINQ provides a new object model for XML data that is much simpler and easier to work with than the XML DOM model. In the PDC preview version, there is no way to create a strongly-typed object view of the XML data like there is for SQL, but I expect that a similar tool to generate classes based on an XML schema will be added eventually.

I think LINQ will be especially useful with collections and XML data where all the data manipulation has to be done in C# code already. The LINQ syntax is much simpler and easier to read than the code that is required today. For SQL databases, there will always be a place for stored procedures on the database server, but LINQ will provide an excellent alternative to building custom SQL query strings or writing hundreds of stored procs for all the different variations of simple SELECT queries. I'm looking forward to giving it a try.
