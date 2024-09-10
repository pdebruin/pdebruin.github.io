---
title: "WebAssembly with .NET"
categories:
  - Learning
tags:
  - Open-source
  - Devops
---

About 10 years ago, containers were the big change in application development and deployment. Since then, a lot has changed: technology has evolved, people have embraced, and Docker containers and Kubernetes clusters are everywhere.

[Webassembly (wasm)](https://webassembly.org/) seems to be appearing as the next big change. You could already create wasm apps with blazor. Now the .NET team have published a new wasi-experimental workload for dotnet, which allows you to play with this. As the name implies, this is all experimental, but a great development for the .NET ecosystem. Note that you also need wasmtime to run this. 

![img](../assets/images/2023-12-08-webassembly-dotnet.png)

https://devblogs.microsoft.com/dotnet/extending-web-assembly-to-the-cloud/

If you are interested in wasm developments, also check out the [spin](https://github.com/fermyon/spin) project. 

Thanks for reading! :-)
