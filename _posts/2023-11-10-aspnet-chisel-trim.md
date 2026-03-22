---
title: "ASP chisel and trim"
categories:
  - Learning
tags:
  - Open-source
  - Devops
---

Excited about [dotnetconf](https://www.dotnetconf.net/) this week? How about this: ASPNET runs on Linux and containers (for 7+ years). By default 217MB 🤔 using Ubuntu for compatibility. Want smaller? Learn about chisel and trim! Now you are at 40MB! 😍 You bet I am excited! Hat tip to Rich Lander and [his container workshop](https://github.com/richlander/container-workshop)

```
dotnet publish -p:PublishProfile=DefaultContainer
-p:ContainerFamily=jammy-chiseled -p:PublishTrimmed=true --sc
```

![Terminal showing dotnet publish with chiseled container and docker images comparing sizes from 40MB chiseled-trimmed to 217MB standard](../assets/images/2023-11-10-aspnet-chisel-trim.jpg)

[Announcement](https://devblogs.microsoft.com/dotnet/announcing-dotnet-chiseled-containers/)

Thanks for reading! :-)
