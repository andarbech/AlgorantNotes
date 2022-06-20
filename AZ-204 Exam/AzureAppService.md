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

