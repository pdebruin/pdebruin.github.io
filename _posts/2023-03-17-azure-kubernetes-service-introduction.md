---
title: "Azure Kubernetes Service introduction"
categories:
  - Learning
tags:
  - aks
  - kubernetes
---

In previous roles I used to work a lot with containers. Next month KubeCon is happening close to my home and I will be helping out at the booth and discussing everything Microsoft Learn and architecture center with attendees :-) In preparation I wanted to create some content on Azure Kubernetes Service, both for my own memory refresh as well as for your benefit. Note that you can use containers in other Azure services like AppService and Container Apps.

If you are interested in documentation, you could start with my [list of guidance](https://github.com/pdebruin/aks/blob/master/aks_guidance.md).

For completeness, check out these previous blog posts about [Windows Terminal](https://blog.pdebruin.org/accessing-azure-terminal/) and [AKS](https://blog.pdebruin.org/azure-kubernetes-service-free-tier/).

Before starting to work with Kubernetes, make sure to have a Linux command-line environment like

* Ubuntu installed on your device
* Windows Subsystem for Linux on your Windows device
* A Linux VM (in Azure)
* Azure cloud shell

There are some pros and cons to the above options. For instance, Azure cloud shell is very easy to start with: simply [browse](https://shell.azure.com) and you get a web-based environment with az and kubectl installed. However you are not a super user so you can't install things, and you can't use ```docker build``` to create a new container image. In your own environment you can be super user but you will have to install tools like:

az version
[](https://learn.microsoft.com/cli/azure/install-azure-cli-linux?pivots=script&wt.mc_id=pdebruin_content_blog_cnl_csasci)
```curl -L https://aka.ms/InstallAzureCli | bash```

kubectl
https://learn.microsoft.com/cli/azure/aks?view=azure-cli-latest#az-aks-install-cli?wt.mc_id=pdebruin_content_blog_cnl_csasci
az aks install-cli

![img](../assets/images/2023-03-17-azure-kubernetes-service-introduction.png)



Thanks for reading! :-)
