---
title: "AKS free tier"
categories:
  - Learning
tags:
  - cloud-native
  - kubernetes
  - AKS
---

Last week the [free tier](https://techcommunity.microsoft.com/t5/apps-on-azure-blog/azure-kubernetes-service-free-tier-and-standard-tier/ba-p/3731432?wt.mc_id=pdebruin_content_blog_cnl_csasci) for [Azure Kubernetes Service](https://learn.microsoft.com/azure/aks/intro-kubernetes?wt.mc_id=pdebruin_content_blog_cnl_csasci) was announced. That is not as clear as I would like it to be.

Kubernetes and other container management technologies consist of [various components](https://kubernetes.io/docs/concepts/overview/components/). Most importantly for cost are the manager nodes and worker nodes. These are relevant because commercial vendors may charge a license fee for all nodes. With most this would add three machines with licenses per cluster. And in the cloud you pay as you go for compute, storage and network capacity, so that can be another cost item. This really starts to add up. So one optimization Azure, and some others, did, was to design their managed service so the managers were out of the customers control, including maintenance and cost, and could be optimized for multiple tenants.

![img](../assets/images/2023-02-03-azure-kubernetes-service-free-tier.png)

Side step: If you have never deployed a Kubernetes cluster manually, you should definitely do it once using [this step by step guide](https://github.com/ivanfioravanti/kubernetes-the-hard-way-on-azure). And then throw it away to never do it again. :-) That process will teach you a lot about Kubernetes and you will appreciate managed Kubernetes services even more.

When AKS started, and even before with Azure Container Service, AKS itself was for free. This is great for anyone wanting to experiment. And since Azure SLAs are financially backed, meaning you may get money back when the service doesn't behave as described, there also wasn't an SLA for AKS. This was a problem for enterprises. Remember, you still paid for compute, storage and network of the worker nodes, which are virtual machines or VM scale sets with SLA. So even if the control plane of the masters would be down, the deployed workloads continued to run. Eventually a paid option for AKS was created where customer pay in return for [an optional uptime SLA](https://techcommunity.microsoft.com/t5/apps-on-azure-blog/aks-introduces-uptime-sla/ba-p/1350832) for the managed control plane. This change to free and standard make the choice more explicit.

So did anything else change? Well the AKS product group are very active and open. [Lots of excitement happening](https://github.com/Azure/AKS/projects/1).

When you are considering AKS for production use, look at [the baseline architecture](https://learn.microsoft.com/azure/architecture/reference-architectures/containers/aks/baseline-aks) for AKS as a starting point.

To read more about cost management, check out [this post](https://blog.pdebruin.org/cost-management/).

Thanks for reading! :-)
