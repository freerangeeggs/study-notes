# Understand core Azure services (30-35%)

## Core Azure architectural components

**Regions** are azure data centres in a localised area. There may be more than one data centre in a region.
For example, *Australia East* is located somewhere in Sydney, Australia; *Australia Southeast* is somewhere in Melbourne, Australia.
There are special regions for certain governments (like USA and Australia) and countries (like China).

- [[Microsoft Learn] Datacenters and Regions in Azure](https://docs.microsoft.com/en-us/learn/modules/explore-azure-infrastructure/2-azure-datacenter-locations)

**Geographies** Are areas of the globe that contains many Azure regions, but are geopolitically specific (like APAC or Europe)

- [[Microsoft Learn] Geographies](https://docs.microsoft.com/en-us/learn/modules/)explore-azure-infrastructure/3-geographies

**Availability Zones** are physically separate datacentres within an Azure region. They are completely independant of each other and designed to add fault-tolerant redundancies to your apps. You can choose to use Availability Zones when setting up specific services in Azure (like VMs, Disks, Load Balancers, and SQL Databases).

- [[Microsoft Learn ] Availability Zones](https://docs.microsoft.com/en-us/learn/modules/explore-azure-infrastructure/4-availability-zones)

**Region Pairs** Are the grouping of two regions within the same aeography but far enough away to ensure they will not be taken down by the same disaster.

- [[Microsoft Learn] Region Pairs](https://docs.microsoft.com/en-us/learn/modules/explore-azure-infrastructure/5-region-pairs)

**Resource Groups** are containers that hold related resources for an Azure solution. The resource group can include all the resources for the solution, or only those resources that you want to manage as a group. All resources must be in a resource group and a resource can only be a member of a single resource group. Resources can be moved between resource groups at any time. Resource groups can't be nested. Before any resource can be provisioned, you need a resource group for it to be placed in.

- [[Microsoft Learn] Principles of resource groups](https://docs.microsoft.com/en-us/learn/modules/control-and-organize-with-azure-resource-manager/2-principles-of-resource-groups)

The **Azure Resource manager** is the core service APIS for accessing/ managing Azure services. The Portal, Powershell commandlets, and CLI all use the Azure Resource Manager.

You can deploy scripts to the Resource manager to roll-out a bunch of resources at once, unlike the portal where you can only deploy one resource at a time.

- [[Microsoft Docs] Azure Resource Manager](https://docs.microsoft.com/en-us/azure/azure-resource-manager/resource-group-overview)

## Core products available in Azure

### Products available for Compute

- [[Microsoft Learn] Core Cloud Services - Azure compute options](https://docs.microsoft.com/en-us/learn/modules/intro-to-azure-compute/)

> Azure compute is an on-demand computing service for running cloud-based applications. It provides computing resources like multi-core processors and supercomputers via virtual machines and containers. It also provides serverless computing to run apps without requiring infrastructure setup or configuration.

#### Virtual Machines

- [[Microsoft Learn] Explore Azure Virtual Machines](https://docs.microsoft.com/en-us/learn/modules/intro-to-azure-compute/3-virtual-machines)

> **Virtual machines**, or VMs, are software emulations of physical computers. They include a virtual processor, memory, storage, and networking resources. They host an operating system (OS), and you're able to install and run software just like a physical computer. And by using a remote desktop client, you can use and control the virtual machine as if you were sitting in front of it.

##### Availability Sets

> An availability set is a logical grouping of two or more VMs that help keep your application available during planned or unplanned maintenance.

This is when you add have more than one VM running over different fault domains and update domains to allow for VM availability when there are scheduled or unscheduled maintenance, or when the VM Operating System needs an update.

Availability sets are free, but the VMS are not. If you want at least one VM available at any time, you will be paying for at least two VMs.

#### Virtual Machine Scale Sets

> Azure Virtual Machine Scale Sets let you create and manage a group of identical, load balanced VMs.

If you were to use scale sets, this would be for extremely high availability, big data processing, in an environment you need to configure/control.

**Azure Batch** is more insane than this, where it can scale thousands of VMS to batch-process work and then shut them down when done.

#### App Service

> This platform as a service (PaaS) allows you to focus on the website and API logic while Azure takes care of the infrastructure to run and scale your web applications.

With this, you are not focusing on VM or Application Updates, but just the implementation, configuration, and scaling of apps. You say how performant you want to be (and pay for it), Azure sorts out the finer details.

#### Serverless

Serverless is next-level PaaS, you don't even need to worry about scaling or performance. You just worry about what it is going to do (i.e. the logic), not how it is going to do it (i.e. the infrastructure or scaling). You pay for what is used, when nothing is happing, you aren't paying.

With Azure, you have two options here:

- Functions
- Logic Apps

**Functions** are code based and have many triggers (like HTTP calls, blobs, tables or queues, and more). You write what you want to happen and it will happen when triggered.

**Logic Apps** are more power user friendly as they have a graphical interface with connectors. The connectors either are triggers to start a Logic App, or perform a function once triggered. Data is passed between connectors within a running App.

Functions run a function, Logic Apps run a workflow.

### Products available for Networking such as Virtual Network, Load Balancer, VPN Gateway, Application Gateway and Content Delivery Network

#### Virtual Network

- [[Microsoft Learn] Deploy your site to Azure](https://docs.microsoft.com/en-us/learn/modules/intro-to-azure-networking/2-deploy-to-azure)

> A *virtual network* is a logically isolated network on Azure.
>
> A virtual network allows Azure resources to securely communicate with each other, the internet, and on-premises networks. A virtual network is scoped to a single region; however, multiple virtual networks from different regions can be connected together using virtual network peering.

You can use expose a VM to a public IP, and separate other VMs by subnet to isolate them from the outside world.

#### Network Security Group (NSG)

> A network security group, or NSG, allows or denies inbound network traffic to your Azure resources. Think of a network security group as a cloud-level firewall for your network.

#### Load Balancer

- [[Microsoft Learn] Scale with Azure Load Balancer](https://docs.microsoft.com/en-us/learn/modules/intro-to-azure-networking/3-scale-load-balancer)

> A *load balancer* distributes traffic evenly among each system in a pool. A load balancer can help you achieve both high availability and resiliency.

Rather than having one VM processing requests, you can have multiple sitting behind a load balancer, which will redirect traffic to the VMs that are responsive. The load balancer now holds the public IP so users are still just pointing to the same spot.

#### VPN Gateway

- [[Microsoft Docs] Azure VPN Gateway](https://docs.microsoft.com/en-us/azure/vpn-gateway/)

VPN Gateway allows your on-premises environment to connect to a Virtual Network in Azure.

#### Application Gateway

- [[Microsoft Docs] Application Gateway](https://docs.microsoft.com/en-us/azure/application-gateway/)

> If all your traffic is HTTP, a potentially better option is to use Azure Application Gateway. Application Gateway is a load balancer designed for web applications. It uses Azure Load Balancer at the transport level (TCP) and applies sophisticated URL-based routing rules to support several advanced scenarios.

This is an application-level load balancer and allows for more intelligent routing (like URL path) and a Web Application Firewall.

#### Traffic Manager

> Traffic Manager uses the DNS server that's closest to the user to direct user traffic to a globally distributed endpoint.

If your servers are in many different geographic regions, Traffic manager will use DNS to point the user to the server with the lowest latency (i.e. the fastest).

#### Content Delivery Network (CDN)

> A content delivery network (CDN) is a distributed network of servers that can efficiently deliver web content to users. It is a way to get content to users in their local region to minimize latency.

Azure CDN will get what is in Azure Storage, and place it in hundreds of Points of Presence (PoPs) around the world. This minimises the distance and therefore time for the user to get the files needed. This is great for the fast loading of static content (like images and Single-Page Applications).

### Products available for Storage such as Blob Storage, Disk Storage, File Storage, and Archive Storage

- [[Microsoft Learn] Core Cloud Services - Azure data storage options](https://docs.microsoft.com/en-us/learn/modules/intro-to-data-in-azure)

#### Blob Storage

> Azure Blob Storage is unstructured, meaning that there are no restrictions on the kinds of data it can hold. Blobs are highly scalable and apps work with blobs in much the same way as they would work with files on a disk, such as reading and writing data. Blob Storage can manage thousands of simultaneous uploads, massive amounts of video data, constantly growing log files, and can be reached from anywhere with an internet connection.

Blob storage is where you store your files. There is no directory structure like you are used to on you Operating system, instead the file name defines the *directory path*. i.e. If you wanted a file to look like it is in a folder, you put it in a `foldername/filename.extension` format.

#### Azure Data Lake Storage Gen2

- [[Microsoft Learn] Introduction to Azure Data Lake storage](https://docs.microsoft.com/en-us/learn/modules/introduction-to-azure-data-lake-storage/)

> The Data Lake feature allows you to perform analytics on your data usage and prepare reports. Data Lake is a large repository that stores both structured and unstructured data.

#### Azure Files

> Azure Files offers fully managed file shares in the cloud that are accessible via the industry standard Server Message Block (SMB) protocol. Azure file shares can be mounted concurrently by cloud or on-premises deployments of Windows, Linux, and macOS.

Think of Azure Files like a mapped drive for the cloud.

#### Azure Queue

> Azure Queue storage is a service for storing large numbers of messages that can be accessed from anywhere in the world.

Queue storage is FIFO messaging, Apps or services put a message on the queue, and a receiving app or  service (like an Azure Function) takes the message off the queue and does something with it.

#### Disk Storage

> Disk storage provides disks for virtual machines, applications, and other services to access and use as they need, similar to how they would in on-premises scenarios. Disk storage allows data to be persistently stored and accessed from an attached virtual hard disk.

Disk storage is essentially a way to store virtual hard disks (.vhd files) for a VM to read from. the storage method is optimised to support the large binary format of a .vhd file.

#### Storage Tiers

These come in three different types; hot, cool, and archive.

**Hot** tier is for frequently accessed files; it is cheap to access the files but the cost to store is higher than other tiers. **Cool** tier is for files not so often accessed; it is cheaper to store the files but cost a little more to access than the hot tier. **Archive** is a more extreme version of cool, it is very cheap to store, but access costs more than cool and has some latency.

### Products available for Databases such as CosmosDB, Azure SQL Database, Azure Database Migration service, and Azure SQL Data Warehouse

- [[Microsoft Learn] How Azure data storage can meet your business storage needs](https://docs.microsoft.com/en-us/learn/modules/intro-to-data-in-azure/3-how-azure-storage-meets-your-business-storage-needs)

#### Azure SQL Database

> Azure SQL Database is a relational database as a service (DaaS) based on the latest stable version of the Microsoft SQL Server database engine. SQL Database is a high-performance, reliable, fully managed and secure database.

Azure SQL allows you to use SQL server without the need for implementing and managing a VM. Depending on the plan, economies of scale allows the price point to be very low but can blow out depending on quantity of data and number of transactions.

#### CosmosDB

> Azure Cosmos DB is a globally distributed database service. It supports schema-less data that lets you build highly responsive and Always On applications to support constantly changing data. You can use this feature to store data that is updated and maintained by users around the world.

CosmosDB can have multiple primary databases, and is quickly replicated worldwide with guaranteed single-digit millisecond response times. This is a lot more expensive than Azure Storage tables or Azure SQL DTU plans.

#### Azure Database Migration service

- [[Microsoft Docs] Azure Database Migration Service](https://docs.microsoft.com/en-us/azure/dms/)

> Azure Database Migration Service enables seamless migrations from multiple database sources to Azure Data platforms with minimal downtime. The service uses the Data Migration Assistant to generate assessment reports that provide recommendations to guide you through the changes required prior to performing a migration. When you're ready to begin the migration process, the Azure Database Migration Service performs all of the required steps.

#### Azure SQL Data Warehouse

- [[Microsoft Docs] SQL Data Warehouse](https://docs.microsoft.com/en-us/azure/sql-data-warehouse/)

> SQL Data Warehouse is a cloud-based Enterprise Data Warehouse (EDW) that leverages Massively Parallel Processing (MPP) to quickly run complex queries across petabytes of data. Use SQL Data Warehouse as a key component of a big data solution.

### The Azure Marketplace and its usage scenarios

- [Azure Marketplace](https://azuremarketplace.microsoft.com/en-us/marketplace/)

The Azure Marketplace allows Cloud Service Providers (CSPs) to sell their products and services through Azure. This could be utilising existing Azure services and adding their functionality on top, then on-selling to the customer.

## Solutions available on Azure

-[[Microsoft Learn] Microsoft Azure IoT strategy and solutions](https://docs.microsoft.com/en-us/learn/modules/azure-iot-strategy-and-solutions/index)

### Internet of Things (IoT) and products that are available for IoT on Azure such as IoT Fundamentals, IoT Hub and IoT Central

- [[Microsoft Learn] Azure IoT services](https://docs.microsoft.com/en-us/learn/modules/azure-iot-strategy-and-solutions/4-azure-iot-services)

### Big Data and Analytics and products that are available for Big Data and Analytics such as SQL Data Warehouse, HDInsight and Data Lake Analytics

#### SQL Data Warehouse

See above

#### HDInsight

### Artificial Intelligence (AI) and products that are available for AI such as Azure Machine Learning Service and Studio

### Serverless computing and Azure products that are available for serverless computing such as Azure Functions, Logic Apps and App grid

### Benefits and outcomes of using Azure solutions

## Azure management tools

- [[Microsoft Learn] Azure Management Options](https://docs.microsoft.com/en-us/learn/modules/tour-azure-portal/2-azure-management)
- [[Microsoft Learn] Navigate the Portal](https://docs.microsoft.com/en-us/learn/modules/tour-azure-portal/3-navigate-the-portal)

The [Azure Portal](https://portal.azure.com) is a graphical, web-based app allowing you to create and manage Azure resources.

The [Azure PowerShell module](https://docs.microsoft.com/en-us/powershell/azure/new-azureps-module-az?view=azps-2.0.0) and [Azure CLI](https://github.com/Azure/azure-cli) allows you to create and manage your azure resources on the command line. These are best used for deployments and repetitive tasks.

[Azure Cloud Shell](https://shell.azure.com/) allows you to run Azure CLI or PowerShell commands against a subscription without needing to install anything. It also has a pre-installed [suite of tools](https://docs.microsoft.com/en-us/azure/cloud-shell/features#tools) to help you work.

The [Azure Mobile App](https://aka.ms/azuremobileapp/) gives limited management of azure services, but keeps getting better. Also have the Cloud Shell built in.

### Azure Advisor

- [[Microsoft Docs] Introduction to Azure Advisor](https://docs.microsoft.com/en-us/azure/advisor/advisor-overview)

> Azure Advisor is a personalized cloud consultant that helps you follow best practices to optimize your Azure deployments. It analyzes your resource configuration and usage telemetry. It then recommends solutions to help improve the performance, security, and high availability of your resources while looking for opportunities to reduce your overall Azure spend.
>
> Azure Advisor is a free service built into Azure that provides recommendations on **high availability**, **security**, **performance**, and **cost**. Advisor analyzes your deployed services and looks for ways to improve your environment across those four areas.

Advisor tells you things that you can do to improve security and performance

![An example of Azure Advisor](https://docs.microsoft.com/en-us/learn/modules/predict-costs-and-optimize-spending/media/3-advisor-recommendations.png)

Clicking through the recommendations will tell you why they recommend the change, what to change it on, and why. It may group a single change on to multiple services you have configured in Azure.