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

 

