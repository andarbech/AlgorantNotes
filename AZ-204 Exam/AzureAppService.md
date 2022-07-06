# Azure App Service
## Definition
Azure App Service is an HTTP-Based Service for hosting web applications, REST APIs, and mobile backends. Allow develop in diferents  languague like, .NET,.NET core,
java, Ruby, Node.js, PHP or Pytho. Apps run and scale in Windows and Linux enviroments.

### Key Concepts
- scale depending on the usage of the web.
- Continuos integration and deployment with Azure DevOps, GitHub, Bitbucket, FTP, or a local.
- Deployment slots using the Azure portal or command-line tools and you can create a enviroment where you can push code to test on Azure.
- can host web apps natively on Linux. it can also run Linux custom containers
    * You can retrieve the current list by using the command in CloudShell
    ```
    #Bash
    az webapp list-runtimes --os-type linux
    ```
    * Limitations
        * App Service on Linux is not sopported pricing tier.
        * You can't mix Windows and Linux Apps in the same App Service Plan.
#### Azure Service Plans
- An App service plan defines a set of compute resources for a web app to run. One or more apps can be configured to run on the same computing resources. Azure Funtion also too.
- When you created an App Service plan in certain  region a set of compute resources is created for that plan in that region. 
- Each plan defines:
    * Region
    * Number od VM instaces
    * Size of VM instances (Small, Medium, Large)
    * Pricing tier (Free, Shared, Basic, Standard, Premium, PremiumV2, PremiumV3, Isolated)
        * The pricing tier of an App determines what features yu get and how much you pay for the plan.
            * **Shared compute:** both **Free** and **Shared**  share the resource pools
            * **Dedicated Computed:** the **Basic, Standar, Premium, PremiumV2** and **PremiumV3** tiers run App on dedicated Azure VMs.
# Deploy to App Service
- Azure soport automated deployment directly from several sources:
    * **Azure DevOps:** you can can push your code to Azure DevOps, build in the cloud, run the test, genreta release from the code and finally, puesh your code to an Azure Web App.
    * **GitHub:**  Azure support automated 
    * **Bitbucket:** you can configure and automated deployment  with Bitbucket.
- There are few options that can use to manually push your code to Azure:
    * **Git:** App Service web apps feature a Git URL tat you can add as a remote repository. Pushing to the remote repository will deploy your app.
    * **CLI:** ```webapp up``` is a feature of the ```az``` command-line inferfase  that packages  your app and deploys it. Unlike other  deployment methods ``az webapp up `` can create a new Appservice  web app for if you haven't alrady created one.
    * **ZIP Deploy:**  Use ```curl``or a similar HTTP utility to send a ZIP of your aplication files to App service
    * **FTP/S:** FTP or FTPS is a traditional way of pushing your code to manuy hosting enviroments, Including App Service.
- Whennever possible, use deployment slots when deploying a new production build. When using a  Standar App service Plan Tier or better, you can deploy your app to a staging enviroment and then swap your staging and production slots.
# Authentication and authorization in App Service.
- Azure App service provides built-in auth support. so youy can sign in users and acces data by writting minimal or no code in your web app, API, and mobile back end, and also Azure Functions.
- Many frameworks are bundled with security features, and you can use them if you like. If you need more flexibility than App service provide, you can also write your own utilities.
- Azure App Service allows you to integrate a variety of auth capabilities into your web app or API without implementing them yourself.
- App Service uses federated identity, in which a third-party identity provider manages the user identities and authentication flow for you. The following identity providers are available by default:
    * Microsoft Identity Platform [web](https://docs.microsoft.com/en-us/azure/app-service/configure-authentication-provider-aad)
    * Facebook [web](https://docs.microsoft.com/en-us/azure/app-service/configure-authentication-provider-facebook)
    * Google [web](https://docs.microsoft.com/en-us/azure/app-service/configure-authentication-provider-google)
    * Twitter [web](https://docs.microsoft.com/en-us/azure/app-service/configure-authentication-provider-twitter)
    * Any Open Connect provider [web](https://docs.microsoft.com/en-us/azure/app-service/configure-authentication-provider-openid-connect)
## How it works
- The authentication and authorization module runs in the same sandbox as your application. When it's enable incoming HTTP rquest passes through if before being handled by your aplication code. Services>
    * Authenticates users with the specified provider
    * Validates, stores, and refresh tokens
    * Injects indetity information into the request headers
## Auth flow
- **without provider SDK:** The App delegate federated sign-in to App service. This is typically the cxases with the browser app, which can present the provider's login page to the user. The server code manages the sing-in process, so it is called server-directed flow or server flow.
- **with provider SDK:** The app signs users in to the provider manually and then submitsthe authentication token to App Services for validation. This is typically the case with browser-less apps, which can't present  the provider's sing-in page to the user. The aplicatin code manages the sing-in process, so it is also called __client-directed flow__ or __client flow__ . this applies to REST API's, Azure Funtions, JavaScript browser clients, and native mobile app. 
# Authorization behavior
- **Allow unauthenticated requests:** This option defers authorization of unauthenticated traffic to your application code. For authenticated requests, App Service also passes along authentication information in the HTTP headers.
- **Require authentication:** This option will reject any unauthenticated traffic to your application. This rejection can be a redirect action to one of the configured identity providers. In these cases, a browser client is redirected to ```/.auth/login/<provider> ```for the provider you choose. If the anonymous request comes from a native mobile app, the returned response is an __HTTP 401 Unauthorized__
# Multi-tenant App Service networking features
- inbound feature: App-assigned address, Access restrictions, Service endpoints, Privates endpoints
- outbound feature: Hybrid Connections, Gateway-required virtual network integration, Virtual network integration.
- Examples:
    * Support IP-based SSL needs for your app	==>  App-assigned address
    * Support unshared dedicated inbound address for your app ==>	App-assigned address
    * Restrict access to your app from a set of well-defined addresses ==>	Access restrictions
