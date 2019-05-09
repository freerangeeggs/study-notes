# Understand cloud concepts (15-20%)

## Describe the benefits and considerations of using cloud services

### Terms

- https://docs.microsoft.com/en-au/learn/modules/principles-cloud-computing/3-benefits-of-cloud-computing

**High Availability**

**Scalability** is the increasing or decreasing the resources and services used based on the demand or workload at any given time.
You can "Scale-up" to add resources to an existing server (vertical scaling), or "Scale-out" to add additional servers (horizontal scaling).

**Elasticity** is automatic scalability

**Agility**

**Fault Tolerance** Backup and replication incase hardware dies, as well as hardware redundancies to allow the quick switching to the redundant hardware when something does die.

**Disaster Recovery** is an element of fault tolerance, and is the steps taken to ensure a natural or human disaster won't affect services. This is through redundances in separate locations (backup sites).

### Economies of scale

- https://docs.microsoft.com/en-au/learn/modules/principles-cloud-computing/3b-economies-of-scale

Costco can sell you an apple for much less than you local grocer, as they can buy more at a lower cost and on-sell the discount.

Cloud providers can sell you compute at a much lower cost than buying a server, as they have a lot more servers and can on-sell only a fraction of the server at a smaller cost.

### Capital Expenditure (CapEx) and Operational Expenditure (OpEx)

- https://docs.microsoft.com/en-au/learn/modules/principles-cloud-computing/3c-capex-vs-opex

**CapEx** is the purchasing of an asset to own, in full, and depreciating value over time. The Balance sheet will show this as an asset contributing to the companies value.

**OpEx** is the spending on a product or service as you use it. This does not contribute to the companies value.

Purchasing capital (like a server) often takes long and you generally need to purchase more than currently required, leaving unused/wasted resources until the time is required to use it. Leasing capital allows you to only pay for what you need at the time.

### Consumption-based model

You pay for what you use, after you have used it. No different to paying for power or water.
Azure has a "Pay-as-you-go" plan, which is precisely that.

## Describe the differences between Infrastructure-as-a-Service (IaaS), Platform-as-a-Service (PaaS) and Software-as-a-Service (SaaS)

- https://docs.microsoft.com/en-au/learn/modules/principles-cloud-computing/5-types-of-cloud-services

### Infrastructure-as-a-Service (IaaS)

Vendor manages the hardware (including virtualization), you manage the OS and applications. This includes all updates. Similar to an On-Premises VM.

### Platform-as-a-Service (PaaS)

Vendor manages the hardware (including virtualization) and OS, you manage the applications (including updates) and data storage. Examples are Azure App Services (Like web apps) and Azure SQL. OS security and patching is not your problem

### Software-as-a-Service (SaaS)

Vendor manages the hardware (including virtualization) and OS, applications, data storage, and all the updates to those. You just use the software. Office 365 is a SaaS service.

### Differences between the three different service types

This is down to management, who is responsible for what. The below graphic is useful for ths.

![Image describing the differences between cloud models](https://docs.microsoft.com/en-au/learn/modules/principles-cloud-computing/media/5-layer-diagram.png)

## Describe the differences between Public, Private and Hybrid cloud models

- https://docs.microsoft.com/en-au/learn/modules/principles-cloud-computing/4-cloud-deployment-models

### Public cloud

All hardware is at the cloud providers place, and the cloud provider deals with the hardware and software services provided. Hardware is shared among clients, and the cloud provider determines where the data is stored.

A good example is using SharePoint Online only.

This uses a OpEx model.

### Private cloud

It's like a public cloud, but it is at your place. You manage the purchasing, upgrades, and everything else regarding the hardware and software services on that cloud. Governments love this as they in charge of their data.

This would be where you use SharePoint On-premises only.

This is a more CapEx model.

### Hybrid cloud

You use some cloud at you place, and some cloud at their place.

This would be SharePoint Online as well as SharePoint On-premises.

Guess what, it is both CapEx and OpEx.

### Differences between the three different cloud models

## Further Reading

- [[Microsoft Learn] Cloud Concepts - Principles of cloud computing](https://docs.microsoft.com/en-au/learn/modules/principles-cloud-computing/index)