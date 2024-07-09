---
title: "Azure Functions performance"
categories:
  - Learning
tags:
  - Devops
---

Two interesting blog posts on Azure Functions performance and scale:

🏎️ From 0 to 32000 requests per second in [7 seconds](https://techcommunity.microsoft.com/t5/apps-on-azure-blog/how-to-achieve-high-http-scale-with-azure-functions-flex/ba-p/4169736) and

🔥 Improving [cold start time](https://techcommunity.microsoft.com/t5/apps-on-azure-blog/our-latest-work-to-improve-azure-functions-cold-starts/ba-p/4164500)

![img](../assets/images/2024-06-21-functions-performance.jpg)

This is interesting, because the idea of serverless compute is very compelling, until you run into challenges. Obviously there isn't a machine running your code all-the-time, because that would be costly for either the customer and/or the cloud provider. The challenge then is, how do you make deployments and scaling "feel" like it is?

Thanks for reading! :-)
