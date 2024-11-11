---
title: "Resiliency"
categories:
  - Learning
tags:
  - DevOps
---

Quality in terms of reliability and resiliency is getting attention lately. For the past decade, I have worked with customers to create solutions in the public cloud. And there are many differences with on-premise if that is what you know, or just many things to be aware of if you have always used public cloud: the cloud provider's physical consists of datacenters grouped in availability zones and regions, your solution uses a number of cloud services, and you may have created some custom configuration or code to connect it all. 

Service level agreements sound great but the reality is that when your solution is unavailable for users, you don't want to ask for your money back; you want to get the solution back up and running. 

So, should your code contain retry logic? Probably. 
Should you use availability zones? Likely.
Should you use secondary regions, or even hosting options at other organizations? Maybe.
And automation? And fire drills? And, and, and?
It depends! :-)

First, you should make sure that you have the expertise in your team to understand the variables. Next you should write down requirements that indicate what is important, what downtime is allowed, what budget is available, etc. Yes, like proper architecture. 

[Azure reliability documentation](https://learn.microsoft.com/azure/reliability/overview?wt.mc_id=pdebruin_content_blog_cnl_csasci)

[Azure well architected framework](https://learn.microsoft.com/azure/well-architected/reliability/principles?wt.mc_id=pdebruin_content_blog_cnl_csasci)

[Azure blog on resiliency](https://azure.microsoft.com/blog/?s=resiliency&wt.mc_id=pdebruin_content_blog_cnl_csasci)

![img](../assets/images/2024-11-08-resiliency.jpg)

And you should engage in conversations with your cloud provider, because your voice is the strongest to shape roadmaps. Remember how Azure started with paired regions and without availability zones? And how it took time to get Azure Advisor? Keep providing feedback, through direct person to person communication, or [Azure feedback](https://feedback.azure.com/?wt.mc_id=pdebruin_content_blog_cnl_csasci), or Learn Q&A (https://learn.microsoft.com/answers//tags/133/azure?wt.mc_id=pdebruin_content_blog_cnl_csasci)

Thanks for reading! :-)
