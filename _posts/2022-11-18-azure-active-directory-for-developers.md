---
title: "Azure Active Directory for developers"
categories:
  - Learning
tags:
  - Node
  - Identity
---

Azure Active Directory helps developers authenticate users in any app and any language. There are a few concepts you should know about.

Before you start developing with Azure Active Directory (AzureAD) it helps if you have global administrator access to an AzureAD instance. For instance, you may have access to a stand-alone Azure subscription through a trial or a [Visual Studio benefit](https://my.visualstudio.com/). Another way is to join the [Microsoft 365 developer program](https://developer.microsoft.com/microsoft-365/dev-program).

The most important thing to know about is application registrations. This is a way to let AzureAD know about the type of app, how it should authenticate, where it has access to, what should happen after authentication, etc. As you can see, [Authentication flows](https://learn.microsoft.com/azure/active-directory/develop/authentication-flows-app-scenarios) can become rather complex, and configuration should happen carefully to prevent losing time on debugging misconfiguration. The key is to start simple, make it work, and expand from there.

The good news is that there are [many samples](https://learn.microsoft.com/azure/active-directory/develop/sample-v2-code) that cover authentication flows. In this case we will work with a [sample Node web app](https://github.com/Azure-Samples/ms-identity-javascript-nodejs-tutorial/blob/main/1-Authentication/1-sign-in/README.md). Since we are starting simple, let's first focus on getting the sample to work, which should be easier than updating your own app with identity code and configuration from the sample.

The sample requires an app registration, which is how you get the **client ID**. It should be configured for authentication as web app with return url (http://localhost:4000/redirect) when developing locally. The app registration is created in your instance of Azure Active Directory, which has a **tenant ID**. You also want to create a **client secret**.

```azcli
az ad app create --display-name nodeweb --type spa --return-url http://localhost:4000/redirect
```