---
title: "Startup Microsoft Entra"
categories:
  - Learning
tags:
  - Devops
---

In previous posts I described ways to get started with Azure, and walked through the steps required to create an Azure subscription. Since identity is considered to be the new control plane, let's start with what that looks like in Azure. 

[Microsoft Entra](https://entra.microsoft.com) is the identity service for Azure, and for other cloud services like [Microsoft 365](https://www.microsoft365.com/). Entra also provides much more, but identity management is the most important now that you have an Azure subscription. 

There are a couple of things you want to take care of:
* [Enable multi-factor authentication](https://learn.microsoft.com/entra/identity/authentication/tutorial-enable-azure-mfa?wt.mc_id=pdebruin_content_blog_cnl_csasci)
* [Create another global administrator](https://learn.microsoft.com/entra/identity/role-based-access-control/manage-roles-portal?wt.mc_id=pdebruin_content_blog_cnl_csasci)

Then you can explore Azure or M365 or Entra, depending on your interest. Even if you don't care much about identity, I think it is good to be aware of the functionality of Entra including protection, governance, verified id, and permissions management. 

![img](../assets/images/2024-07-19-startup-microsoft-entra.png)

Thanks for reading! :-)
