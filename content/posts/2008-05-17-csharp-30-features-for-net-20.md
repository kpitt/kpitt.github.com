---
comments: true
date: 2008-05-17T17:24:37Z
slug: csharp-30-features-for-net-20
categories:
- .NET
- Programming
title: C# 3.0 Features for .NET 2.0
wordpress_id: 24
---

When discussing the new features in Visual Studio 2008, [LINQ](http://msdn.microsoft.com/en-us/library/bb308959.aspx) gets most of the press. However, LINQ only works if you are targeting the .NET 3.5 Framework. Another new feature of Visual Studio 2008 is the ability to choose which Framework version to target, and sometimes you just don't have the luxury of upgrading all your users to the latest Framework. Fortunately several of the new language features in C# 3.0 don't require library support, so here are some useful enhancements that work just fine when targeting the .NET 2.0 Framework.

  * [Lambda Expressions](http://msdn.microsoft.com/en-us/library/bb397687.aspx) (more via [Eric White](http://blogs.msdn.com/ericwhite/pages/Lambda-Expressions.aspx) and [Scott Guthrie](http://weblogs.asp.net/scottgu/archive/2007/04/08/new-orcas-language-feature-lambda-expressions.aspx))
  * [Auto-Implemented Properties](http://msdn.microsoft.com/en-us/library/bb384054.aspx) (more via [Scott Guthrie](http://weblogs.asp.net/scottgu/archive/2007/03/08/new-c-orcas-language-features-automatic-properties-object-initializers-and-collection-initializers.aspx) and [Dan Wahlin](http://weblogs.asp.net/dwahlin/archive/2007/12/04/c-3-0-features-automatic-properties.aspx))
  * [Object and Collection Initializers](http://msdn.microsoft.com/en-us/library/bb384062.aspx) (more via [Dan Wahlin](http://weblogs.asp.net/dwahlin/archive/2007/09/09/c-3-0-features-object-initializers.aspx) and [developer.com](http://www.developer.com/net/csharp/article.php/3607421))
  * [Implicitly Typed Local Variables](http://msdn.microsoft.com/en-us/library/bb384061.aspx) (more via [Scott Guthrie](http://weblogs.asp.net/scottgu/archive/2007/05/15/new-orcas-language-feature-anonymous-types.aspx))
  * <del>[Extension Methods](http://msdn.microsoft.com/en-us/library/bb383977.aspx) (more via [developer.com](http://www.developer.com/net/csharp/article.php/3592216) and [Scott Guthrie](http://weblogs.asp.net/scottgu/archive/2007/03/13/new-orcas-language-feature-extension-methods.aspx))</del>  
    **Update:** It turns out that the compiler attaches an attribute to extension methods that is not defined in the .NET 2.0 library, so extension methods can only be used with .NET 3.5 after all.
