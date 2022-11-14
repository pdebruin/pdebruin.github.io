---
title: ".NET and Linux and containers"
categories:
  - Learning
tags:
  - DotNet
  - Linux
  - Containers
---

DotNet runs on Linux, MacOS and Windows. It also runs in containers. .NET 6.0 is the long-term support (3 years) version release last year. .NET 7.0 is the latest version with standard support (1 1/2 years).

![img](../assets/images/2022-11-11-dotnet-and-linux-and-containers.png)

[Watch the 10-minute walkthrough video](https://www.youtube.com/watch?v=mSi8nvwObXc)

There is a dotnet command-line tool that helps create new apps, or restore packages, or build and publish your app.

The default container image for .NET is larger than necessary. Use the .net alpine image to reduce the container image by half.

And once containerized, the .net app can run on any container hosting option including Azure Kubernetes Service, Azure Container Apps, or Azure App Service.

[ASP.NET sample using Alpine container image](https://github.com/pdebruin/asp7)

[Learn .NET](https://dotnet.microsoft.com/learn?wt.mc_id=pdebruin_content_blog_cnl_csasci).

[DotNetConf videos](https://www.youtube.com/c/dotNET/videos)