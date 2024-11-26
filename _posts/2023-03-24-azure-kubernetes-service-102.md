---
title: "Azure Kubernetes Service 102"
categories:
  - Learning
tags:
  - Kubernetes
---

This post follows [a previous article](../azure-kubernetes-service-introduction/) on creating an Azure Kubernetes Service cluster.

After the initial creation is complete, you want to do a few things to set up for success:

First familiarize yourself with the Azure portal view of your cluster. I think Azure users should work with the command-line more, but in this case I make an exception. The Azure portal shows Kubernetes objects visually to help less experienced users, and the portal shows features that are important or new.

The first thing is to [enable monitoring](https://learn.microsoft.com/azure/aks/monitor-aks) so you can see what is going on in the cluster. Azure Monitor is a platform service that makes this very easy. You can also choose to go with Grafana and Prometheus. Azure managed Grafana is generally available. Azure managed Prometheus is in preview. You can enable monitoring in the az aks create command using --enable-addons monitoring. For simplicity I have not mentioned it there. 

Next you want to deploy an application. You can do that manually using kubectl or even automated after a CI/CD build of the application. AKS also offers [GitOps](https://learn.microsoft.com/azure/azure-arc/kubernetes/tutorial-use-gitops-flux2), where you point to a repository with yaml files and the cluster regularly checks whether that configuration is the same as the currently active one. 

Lastly I always enable [Azure Active Directory authentication](https://learn.microsoft.com/azure/aks/managed-azure-ad) on AKS. This means that a user who wants to interact with the cluster, first has to authenticate against Azure AD, and then authorization either in Azure AD or AKS is applied. As you can imagine, this drastically improves security for bad actors.

![img](../assets/images/2023-03-17-azure-kubernetes-service-102.png)

Thanks for reading! :-)
