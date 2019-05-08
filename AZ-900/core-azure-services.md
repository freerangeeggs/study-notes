# Understand core Azure services (30-35%)

## Core Azure architectural components

**Regions** are azure data centres in a localised area. There may be more than one data centre in a region.
For example, *Australia East* is located somewhere in Sydney, Australia; *Australia Southeast* is somewhere in Melbourne, Australia.
There are special regions for certain governments (like USA and Australia) and countries (like China).

[[Microsoft Learn] Datacenters and Regions in Azure](https://docs.microsoft.com/en-us/learn/modules/explore-azure-infrastructure/2-azure-datacenter-locations)

**Geographies** Are areas of the globe that contains many Azure regions, but are geopolitically specific (like APAC or Europe)

[[Microsoft Learn] Geographies](https://docs.microsoft.com/en-us/learn/modules/)explore-azure-infrastructure/3-geographies

**Availability Zones** are physically separate datacentres within an Azure region. They are completely independant of each other and designed to add fault-tolerant redundancies to your apps. You can choose to use Availability Zones when setting up specific services in Azure (like VMs, Disks, Load Balancers, and SQL Databases).

[[Microsoft Learn ] Availability Zones](https://docs.microsoft.com/en-us/learn/modules/explore-azure-infrastructure/4-availability-zones)

**Region Pairs** Are the grouping of two regions within the same aeography but far enough away to ensure they will not be taken down by the same disaster.

[[Microsoft Learn] Region Pairs](https://docs.microsoft.com/en-us/learn/modules/explore-azure-infrastructure/5-region-pairs)

**Resource Groups** are containers that hold related resources for an Azure solution. The resource group can include all the resources for the solution, or only those resources that you want to manage as a group. All resources must be in a resource group and a resource can only be a member of a single resource group. Resources can be moved between resource groups at any time. Resource groups can't be nested. Before any resource can be provisioned, you need a resource group for it to be placed in.

[[Microsoft Learn] Principles of resource groups](https://docs.microsoft.com/en-us/learn/modules/control-and-organize-with-azure-resource-manager/2-principles-of-resource-groups)

The **Azure Resource manager** is the core service APIS for accessing/ managing Azure services. The Portal, Powershell commandlets, and CLI all use the Azure Resource Manager.

You can deploy scripts to the Resource manager to roll-out a bunch of resources at once, unlike the portal where you can only deploy one resource at a time.

[[Microsoft Docs] Azure Resource Manager](https://docs.microsoft.com/en-us/azure/azure-resource-manager/resource-group-overview)

## Core products available in Azure

### Products available for Compute

[[Microsoft Learn] Core Cloud Services - Azure compute options](https://docs.microsoft.com/en-us/learn/modules/intro-to-azure-compute/)

> Azure compute is an on-demand computing service for running cloud-based applications. It provides computing resources like multi-core processors and supercomputers via virtual machines and containers. It also provides serverless computing to run apps without requiring infrastructure setup or configuration.

#### Virtual Machines

[[Microsoft Learn] Explore Azure Virtual Machines](https://docs.microsoft.com/en-us/learn/modules/intro-to-azure-compute/3-virtual-machines)

> **Virtual machines**, or VMs, are software emulations of physical computers. They include a virtual processor, memory, storage, and networking resources. They host an operating system (OS), and you're able to install and run software just like a physical computer. And by using a remote desktop client, you can use and control the virtual machine as if you were sitting in front of it.

##### Availability Sets

> An availability set is a logical grouping of two or more VMs that help keep your application available during planned or unplanned maintenance.

This is when you add have more than one VM running over different fault domains and update domains to allow for VM availability when there are scheduled or unscheduled maintenance, or when the VM Operating System needs an update.

Availability sets are free, but the VMS are not. If you want at least one VM available at any time, you will be paing for at least two VMs.

#### Virtual Machine Scale Sets

> Azure Virtual Machine Scale Sets let you create and manage a group of identical, load balanced VMs.

If you were to use scale sets, this would be for extremely high availability, big data processing, in an environment you need to configure/control.

**Azure Batch** is more insane than this, where it can scale thousands of VMS to batch-process work and then shut them down when done.

#### App Service

> This platform as a service (PaaS) allows you to focus on the website and API logic while Azure takes care of the infrastructure to run and scale your web applications.

With this, you are not focusing on VM or Application Updates, but just the implementation, configuration, and scaling of apps. You say how performant you want to be (and pay for it), Azure sorts out the finer details.

#### Serverless

Serverless is next-level PaaS, you don't even need to worry about scaling or performance. You just worry about what it is going to do (i.e. the logic), not how it is going to do it (i.e. the infrastructure or scaling). You pay for what is used, when nothing is happing, you aint paying.

With Azure, you have two options here:

- Functions
- Logic Apps

**Functions** are code based and have many triggers (like HTTP calls, blobs, tables or queues, and more). You write what you want to happen and it will happen when triggered.

**Logic Apps** are more power user friendly as they have a graphical interface with connectors. The connectors either are triggers to start a Logic App, or perform a function once triggered. Data is passed between connectors within a running App.

Functions run a function, Logic Apps run a workflow.

### Products available for Networking such as Virtual Network, Load Balancer, VPN Gateway, Application Gateway and Content Delivery Network

### Products available for Storage such as Blob Storage, Disk Storage, File Storage, and Archive Storage

### Products available for Databases such as CosmosDB, Azure SQL Database, Azure Database Migration service, and Azure SQL Data Warehouse

### The Azure Marketplace and its usage scenarios

## Solutions available on Azure

- describe Internet of Things (IoT) and products that are available for IoT on Azure such as IoT Fundamentals, IoT Hub and IoT Central
- describe Big Data and Analytics and products that are available for Big Data and Analytics such as SQL Data Warehouse, HDInsight and Data Lake Analytics
- describe Artificial Intelligence (AI) and products that are available for AI such as Azure Machine Learning Service and Studio
- describe Serverless computing and Azure products that are available for serverless computing such as Azure Functions, Logic Apps and App grid
- describe the benefits and outcomes of using Azure solutions

## Azure management tools

- [[Microsoft Learn] Azure Management Options](https://docs.microsoft.com/en-us/learn/modules/tour-azure-portal/2-azure-management)
- [[Microsoft Learn] Navigate the Portal](https://docs.microsoft.com/en-us/learn/modules/tour-azure-portal/3-navigate-the-portal)

The [Azure Portal](https://portal.azure.com) is a graphical, web-based app allowing you to create and manage Azure resources.

The [Azure PowerShell module](https://docs.microsoft.com/en-us/powershell/azure/new-azureps-module-az?view=azps-2.0.0) and [Azure CLI](https://github.com/Azure/azure-cli) allows you to create and manage your azure resources on the command line. These are best used for deployments and repetitive tasks.

[Azure Cloud Shell](https://shell.azure.com/) allows you to run Azure CLI or PowerShell commands against a subscription without needing to install anything. It also has a pre-installed [suite of tools](https://docs.microsoft.com/en-us/azure/cloud-shell/features#tools) to help you work.

The [Azure Mobile App](https://aka.ms/azuremobileapp/) gives limited management of azure servies, but keeps getting better. Also have the Cloud Shell built in.

### Azure Advisor

- [[Microsoft Docs] Introduction to Azure Advisor](https://docs.microsoft.com/en-us/azure/advisor/advisor-overview)

> Azure Advisor is a personalized cloud consultant that helps you follow best practices to optimize your Azure deployments. It analyzes your resource configuration and usage telemetry. It then recommends solutions to help improve the performance, security, and high availability of your resources while looking for opportunities to reduce your overall Azure spend.

> Azure Advisor is a free service built into Azure that provides recommendations on **high availability**, **security**, **performance**, and **cost**. Advisor analyzes your deployed services and looks for ways to improve your environment across those four areas.

Advisor tells you things that you can do to improve security and performance

![](https://docs.microsoft.com/en-us/learn/modules/predict-costs-and-optimize-spending/media/3-advisor-recommendations.png)

Clicking through the recommendations will tell you why they recommend the change, what to change it on, and why. It may group a single change on to multiple services you have configured in Azure.