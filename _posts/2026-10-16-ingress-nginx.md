---
title: "Ingress NGINX: time to migrate"
description: "Upstream maintenance of Ingress NGINX has ended and AKS security patch support for the application routing add-on with NGINX runs through November 2026. Time to move to Gateway API."
categories:
  - Learning
tags:
  - Kubernetes
---

Two weeks ago I joined the AKS team, and last week I was experimenting with visualizing pods per node. This week I worked on a real challenge: the retirement of Ingress NGINX. 

Awareness: Kubernetes SIG Network and the Security Response Committee announced the retirement of Ingress NGINX, and upstream maintenance ended in March 2026: no further releases, no bug fixes, and no fixes for security vulnerabilities that may be discovered. Microsoft provides support for critical security patches for the application routing add-on with NGINX through November 2026. Existing deployments keep working, so nothing tells you it is time to act. But an ingress controller sits at the edge of your cluster, and that is the last place you want unpatched software.

![Node view of the hostedpool system pool on AKS Automatic](/assets/images/2026-10-16-ingress-nginx.png)

Options: AKS aligns with upstream Kubernetes and uses Gateway API as the long-term standard for ingress and L7 traffic management. Whether you use the application routing add-on or the open-source controller, the targets are the same:

- The application routing Gateway API implementation
- Application Gateway for Containers, which supports both Ingress API and Gateway API
- For service mesh or advanced requirements, Gateway API ingress with the Istio service mesh add-on, which works without injecting sidecars into your workloads

Check the Gateway API limitations first if you rely on request header and body size limits, Lua scripts or rate limiting.

[Migrate from NGINX ingress to Gateway API](https://learn.microsoft.com/azure/aks/app-routing-nginx-to-gateway-api-migration)

[Application routing Gateway API implementation](https://learn.microsoft.com/azure/aks/app-routing-gateway-api)

[Application Gateway for Containers](https://learn.microsoft.com/azure/application-gateway/for-containers/overview)

[Gateway API ingress with Istio](https://learn.microsoft.com/azure/aks/istio-gateway-api)

Thanks for reading! :-)
