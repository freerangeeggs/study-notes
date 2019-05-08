# Understand Azure pricing and support (25-30%)

## Understand Azure subscriptions

- [[Microsoft Learn] Azure accounts and subscriptions](https://docs.microsoft.com/en-us/learn/modules/create-an-azure-account/2-azure-accounts-and-subscriptions)
- [[Microsoft Learn] Using multiple Azure subscriptions](https://docs.microsoft.com/en-us/learn/modules/create-an-azure-account/3-multiple-subscriptions)
- [[Microsoft Docs] Azure subscription and service limits, quotas, and constraints](https://docs.microsoft.com/en-us/azure/azure-subscription-service-limits)

An *Azure subscription* is a logical container used to provision resources in Microsoft Azure. It holds the details of all your resources. It is good to consider user access when creating subscriptions, and have one or more subscriptions per team and per deployment environment.

> "The subscription is a strong boundary of security, billing, and environment segmentation."
>
> Jeffrey Palermo, CODE Magazine, Jan/Feb 2019

Subscription pricing has a free option, but most use pay as you go  (consumption model), there are also Enterprise agreements which have assurances of use by the customer, allowing a reduced cost. There are also subscriptions for students and Visual Studio subscribers that are PAYG but with monthly credits.

## Understand planning and management of costs

### Options for purchasing Azure products and services

There are different ways to pay for your subscription:

- **Enterprise** - Agree on an annual spend, get cheaper rates because of it.
- **Web direct** - Pay at the standard rates.
- **Cloud Solution Provider** - A MS partner that on-sells to a customer.

No matter what agreement you have, you pay for what you use.

- [[Microsoft Learn] Purchasing Azure products and services](https://docs.microsoft.com/en-us/learn/modules/predict-costs-and-optimize-spending/1a-purchasing-products)

### Options around Azure Free account

> The Azure free account includes $200 credit to spend for the first 30 days of sign up, free access to our most popular Azure products for 12 months, and access to more than 25 products that are always free.

- [Azure Free Account FAQ](https://azure.microsoft.com/en-us/free/free-account-faq/)

### Factors affecting costs

- [[Microsoft Learn] Factors affecting costs](https://docs.microsoft.com/en-us/learn/modules/predict-costs-and-optimize-spending/1b-factors-affecting-cost)

#### Resource types

All the resources are metered, and the type of resource defines what is metered. Data traffic is metered on outbound traffic, compute is metered on VMs, I/O is metered on storage.

#### Services

Everything on Azure has a different cost, and there are other vendor-created services that may attract external costs as well.

#### Locations

> Azure has datacenters all over the world. Usage costs vary between locations that offer particular Azure products, services, and resources based on popularity, demand, and local infrastructure costs.

#### Ingress and egress traffic

Data that leaves Azure to the rest of the world is charged, data from the rest of the world to the Azure data centre is not charged. The cost is dependant of the Billing Zone it leaves from.

### Zones for billing purposes

A Billing Zone is different to an Availability Zone, and is a geographic grouping of regions to determine pricing.

### Pricing calculator

> The Azure pricing calculator is a free web-based tool that allows you to input Azure services and modify properties and options of the services. It outputs the costs per service and total cost for the full estimate.

In the *Products* tab on [the calculator](https://azure.microsoft.com/pricing/calculator/) you are first asked what azure services you want to use, clicking on one adds it to a list further down. Once done with all the services, you then fill out the options for each service. For some things there are a bunch of options that can greatly affect the cost (like Azure SQL, which by default is around $2500/month but changing to a DTU plan will get it down to about $7).

You can save an estimate for viewing later (Need to be logged-in with your Azure account), or export to Excel.

- [[Microsoft Learn] Estimate costs with the Azure pricing calculator](https://docs.microsoft.com/en-us/learn/modules/predict-costs-and-optimize-spending/2-estimate-costs-with-the-azure-pricing-calculator)
- [Azure Pricing Calculator](https://azure.microsoft.com/pricing/calculator/)

### Total Cost of Ownership (TCO) calculator

Compares you on-prem environment costs to what it will cost in Azure
You put in the details of your servers (including VMS), networking, storage, and databases, adjust the $ value that azure assumes it will cost for you, and they will tell youhow much you will save over 5 years.

- [[Microsoft Learn] Estimate the Total Cost of Ownership with the Azure TCO calculator](https://docs.microsoft.com/en-us/learn/modules/predict-costs-and-optimize-spending/3a-total-cost-of-ownership)
- [[Azure] Total Cost of Ownership Calculator](https://azure.microsoft.com/en-us/pricing/tco/)

### Best practices for minimizing Azure costs

- [[Microsoft Learn] Save on infrastructure costs](https://docs.microsoft.com/en-us/learn/modules/predict-costs-and-optimize-spending/4-save-on-infrastructure-costs)
- [[Microsoft Docs] Ways to monitor your costs when using Azure services](https://docs.microsoft.com/en-us/azure/billing/billing-getting-started#ways-to-monitor-your-costs-when-using-azure-services)

The biggest cost generally is in Compute, and therefore VMs. Azure suggests the following.

- Use Azure credits (only available on specific subscriptions)
- Use spending limits (only available on subscriptions with credits)
- Use reserved instances (pay in full for 1 or 3 years at a much reduced rate)
- Choose low-cost locations and regions (be careful of egress traffic though, that does cost)
- Research available cost-saving offers
- Right-size underutilized virtual machines (drop VM sizes if they aren't being fully utilised)
- Deallocate virtual machines in off hours (Turn it off when you leave work/aren't using it)
- Delete unused virtual machines (just because it aint physical, doesn't mean it aint there)
- Migrate to PaaS or SaaS services (Azure SQL in DTU billing is way cheaper than an idle VM with SQL server running on it.)
- Pick the right OS (Linux is cheaper than Windows)
- Azure Hybrid Benefit for Windows Server or SQL Server (if you bring your own licence, you pay less)
- Use Dev/Test subscription offers

#### Performing cost analysis

See Azure Cost Management below

#### Spending limits and quotas

Azure subscriptions that have credits (like ones for Visual Studio Subscribers) also have a spending limit to the value of those credits attached. When that limit is reached, all services are stopped and you are informed by email. On the beginning of the next month, when the subscription gets its new allotment of credit, the services are turned back on.

#### Using tags to identify cost owners

Any resource gan be given tags. These can help categorise the resources anyway you want and multiple tags can be assigned. You can then use Cost Analysis to filter by tag

- [[Microsoft Learn] Use tagging to organize resources](https://docs.microsoft.com/en-us/learn/modules/control-and-organize-with-azure-resource-manager/3-use-tagging-to-organize-resources)

#### Azure reservations

You can reserve VMs in Azure (called [Reserved Instances](https://azure.microsoft.com/en-us/pricing/reserved-vm-instances/)) and pay less. You need to reserve for one or three years and pay in full up-front. Azure claims that you can save up to 72% and even more using [Hybrid Benefit](https://azure.microsoft.com/en-us/pricing/hybrid-benefit/).

#### Azure Advisor

- [[Microsoft Learn] Predict and optimize with Cost Management and Azure Advisor](https://docs.microsoft.com/en-us/learn/modules/predict-costs-and-optimize-spending/3-predict-and-optimize-with-cost-management-and-advisor)

> Azure Advisor is a free service built into Azure that provides recommendations on **high availability**, **security**, **performance**, and **cost**. Advisor analyzes your deployed services and looks for ways to improve your environment across those four areas.

Advisor tells you things that you can do to improve security and performance

![](https://docs.microsoft.com/en-us/learn/modules/predict-costs-and-optimize-spending/media/3-advisor-recommendations.png)

Clicking through the recommendations will tell you why they recommend the change, what to change it on, and why. It may group a single change on to multiple services you have configured in Azure.

### Azure Cost Management

> Azure Cost Management is another free, built-in Azure tool that can be used to gain greater insights into where your cloud money is going. You can see historical breakdowns of what services you are spending your money on and how it is tracking against budgets that you have set. You can set budgets, schedule reports, and analyze your cost areas.

![](https://docs.microsoft.com/en-us/learn/modules/predict-costs-and-optimize-spending/media/3-cost-management.png)

Microsoft also bought Cloudyn to do advanced cost analysis, but that is being overridden by Cost Management, in fact, you cannot create a Cloudyn account any more.

## Understand the support options available with Azure

- [[Microsoft Learn] Azure support options](https://docs.microsoft.com/en-us/learn/modules/create-an-azure-account/6-support-options)
- [[Azure] Support Plans](https://azure.microsoft.com/en-au/support/plans/)

### Available Support Plans

- Developer
- Standard
- Professional Direct
- Premier

### How to open a support ticket

- [[Microsoft Docs] How to create an Azure support request](https://docs.microsoft.com/en-us/azure/azure-supportability/how-to-create-azure-support-request)

### Support channels outside of support plan channels

This is what you get when you don't have a support plan:

- Billing and subscription support (via [Azure Portal](https://portal.azure.com))
- [Azure products and services documentation](https://azure.microsoft.com/en-au/services/)
- [Online self-help documentation](https://docs.microsoft.com/en-us/azure/)
- [Whitepapers](https://azure.microsoft.com/en-us/resources/whitepapers/)
- [Community support forums](https://azure.microsoft.com/en-us/support/community/)
- [Microsoft Developer Network (MSDN) Forums](https://social.msdn.microsoft.com/Forums/home?category=windowsazureplatform)
- [Stack Overflow](https://stackoverflow.com/questions/tagged/azure/)
- [Server Fault](https://serverfault.com/questions/tagged/azure)
- [Azure Feedback Forums](https://feedback.azure.com/forums/34192--general-feedback)
- [Twitter](https://twitter.com/azuresupport)

### Knowledge Center

- [[Azure] Knowledge Center](https://azure.microsoft.com/en-us/resources/knowledge-center/)

A Q&A style database for how to do things in Azure, including Azure DevOps. Kinda like a massive FAQ.

## Azure Service Level Agreements (SLAs)

- [[Microsoft Learn] Service Level Agreements for Azure](https://docs.microsoft.com/en-us/learn/modules/explore-azure-infrastructure/6-service-level-agreements)

A **Service Level Agreement** (SLA) is an agreement and promise of a series of standards and practices a vendor adheres to with a customer. These are generally around performance and uptime, as well as what happens if the SLA is not met. In the case of Azure, a percentage credit is given to the customer.

SLAs are not available for products on the Free or Shared tiers, and all others can be gathered from the [Azure Support site](https://azure.microsoft.com/en-us/support/legal/sla/).

## Service lifecycles in Azure

- [[Microsoft Learn] Access public and private preview features](https://docs.microsoft.com/en-us/learn/modules/tour-azure-portal/8-preview-features)

**Private Preview** is when an Azure feature is available to *specific* Azure customers for evaluation purposes. This is typically by invite only and issued directly by the product team responsible for the feature or service.

**Public Preview** is when an Azure feature is available to all Azure customers for evaluation purposes.

**General Availability (GA)** is when a feature has been evaluated and tested successfully, it might then be released to customers as part of Azure's default product set.

### How to access Preview features

They are available in the portal, just click on *All Resources* and filter on `Preview`.
You can also look at the [Azure Updates Page](https://azure.microsoft.com/en-us/updates/?status=inpreview) in the *In Preview* tab.

### Monitor feature updates

You can do that from the [Azure Updates Page](https://azure.microsoft.com/en-us/updates/), it has an RSS link you can subscribe to.