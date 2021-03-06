# Understand security, privacy, compliance, and trust (25-30%)

## Understand securing network connectivity in Azure

### Describe Azure Firewall

### Describe Azure DDoS Protection

### Describe Network Security Group (NSG)

### Choose an appropriate Azure security solution

## Describe core Azure Identity services

### Understand the difference between authentication and authorization

### Describe Azure Active Directory

### Describe Azure Multi-Factor Authentication

## Describe security tools and features of Azure

- [[Microsoft Learn] Get tips from Azure Security Center](https://docs.microsoft.com/en-us/learn/modules/intro-to-security-in-azure/2a-azure-security-center)

### Describe Azure Security

### Understand Azure Security center usage scenarios

### Describe Key Vault

### Describe Azure Information Protection (AIP)

### Describe Azure Advanced Threat Protection (ATP)

## Azure governance methodologies

### Azure Policies

- [[Microsoft Learn] Use policies to enforce standards](https://docs.microsoft.com/en-us/learn/modules/control-and-organize-with-azure-resource-manager/4-use-policies-to-enforce-standards)
- [[Microsoft Learn] Apply and monitor infrastructure standards with Azure Policy](https://docs.microsoft.com/en-us/learn/modules/intro-to-governance/index)

> Azure Policy is a service you can use to create, assign, and manage policies. These policies apply and enforce rules that your resources need to follow. These policies can enforce these rules when resources are created, and can be evaluated against existing resources to give visibility into compliance.

### Initiatives

- [[Microsoft Learn] Organize policy with initiatives](https://docs.microsoft.com/en-us/learn/modules/intro-to-governance/3-initiatives)

> Initiatives work alongside policies in Azure Policy. An initiative definition is a set or group of policy definitions to help track your compliance state for a larger goal. Even if you have a single policy, we recommend using initiatives if you anticipate increasing the number of policies over time.

Initiatives are a logical grouping of Policies, so you can assign an initiative and achieve the same result as individually assigning a bunch of policies.

### Role-Based Access Control (RBAC)

Allow users and applications only access to the relevant resources and resource groups. Do this by creating roles and assigning roles to users; then you adjust the resource to only let specific roles have access.

- [[Microsoft Learn] Secure resources with role-based access control](https://docs.microsoft.com/en-us/learn/modules/control-and-organize-with-azure-resource-manager/5-role-based-access)

#### Management Groups

- [[Microsoft Learn] Enterprise governance management](https://docs.microsoft.com/en-us/learn/modules/intro-to-governance/4-management-groups)

> Azure Management Groups are containers for managing access, policies, and compliance across multiple Azure subscriptions. Management groups allow you to order your Azure resources hierarchically into collections, which provide a further level of classification that is above the level of subscriptions.

Management Groups are control over subscriptions. Allows roles to flow to the subscriptions that are part of the Management Group.

### Resource Locks

Lock down a resource to stop accidental changes/deletions.

> Resource locks can set to either Delete or Read-only. Delete will allow all operations against the resource but block the ability to delete it. Read-only will only allow read activities to be performed against it, blocking any modification or deletion of the resource. Resource locks can be applied to subscriptions, resource groups, and to individual resources, and are inherited when applied at higher levels.

Locks can be added from the settings navigation on any resource blade.

- [[Microsoft Learn] Use resource locks to protect resources](https://docs.microsoft.com/en-us/learn/modules/control-and-organize-with-azure-resource-manager/6-use-resource-locks-to-protect-resources)

### Azure Advisor security assistance

## Monitoring and reporting options in Azure

- [[Microsoft Learn] Monitor your service health](Monitor your service health)

### Azure Monitor

> **Azure Monitor** maximizes the availability and performance of your applications by delivering a comprehensive solution for collecting, analyzing, and acting on telemetry from your cloud and on-premises environments. It helps you understand how your applications are performing and proactively identifies issues affecting them and the resources they depend on.

It's analysis and reporting on services in Azure. For example you can see how much CPU/memory a WebApp uses over a period of time.

### Azure Service Health

> Azure Service Health is a suite of experiences that provide personalized guidance and support when issues with Azure services affect you. It can notify you, help you understand the impact of issues, and keep you updated as the issue is resolved. Azure Service Health can also help you prepare for planned maintenance and changes that could affect the availability of your resources.

Azure Service Health provides up-to-date status information about the health of Azure services; in three parts:

- Azure Status provides a global view of the health state of Azure services.
- Service Health provides you with a customizable dashboard that tracks the state of your Azure services in the regions where you use them.
- Resource Health helps you diagnose and obtain support when an Azure service issue affects your resources.

### understand the use cases and benefits of Azure Monitor and Azure Service Health

Azure Monitor is about the status of your resources, Azure Service Health is about the status of Azure's resources.

## Understand privacy, compliance and data protection standards in Azure

- [[Microsoft Learn] Explore your service compliance with Compliance Manager](https://docs.microsoft.com/en-us/learn/modules/intro-to-governance/6-azure-compliance)

### Industry compliance terms such as GDPR, ISO and NIST

- **ISO**
- **SOC**
- **NIST**
- **FedRAMP**
- **GDPR**

### The Microsoft Privacy Statement

> The Microsoft privacy statement explains what personal data Microsoft processes, how Microsoft processes it, and for what purposes.
>
> The statement applies to the interactions Microsoft has with you and Microsoft products such as Microsoft services, websites, apps, software, servers, and devices. It is intended to provide openness and honesty about how Microsoft deals with personal data in its products and services.

### Trust center

> Trust Center is a website resource containing information and details about how Microsoft implements and supports security, privacy, compliance, and transparency in all Microsoft cloud products and services. The Trust Center is an important part of the Microsoft Trusted Cloud Initiative, and provides support and resources for the legal and compliance community.

### Service Trust Portal

> The Service Trust Portal (STP) hosts the Compliance Manager service, and is the Microsoft public site for publishing audit reports and other compliance-related information relevant to Microsoft’s cloud services. STP users can download audit reports produced by external auditors and gain insight from Microsoft-authored reports that provide details on how Microsoft builds and operates its cloud services.

### Compliance Manager

> Compliance Manager is a workflow-based risk assessment dashboard within the Trust Portal that enables you to track, assign, and verify your organization's regulatory compliance activities related to Microsoft professional services and Microsoft cloud services such as Office 365, Dynamics 365, and Azure.

Compliance Manager gives you a risk assessment of your environments based on actions taken by you and by Microsoft.

![Example of Compliance Manager](https://docs.microsoft.com/en-us/learn/modules/intro-to-governance/media/6-compliancemanager.png)

### Determine if Azure is compliant for a business need

### Azure Government

### Azure Germany

Only availble to those in the EU or European Free Trade Association (EFTA). Strictly follows Germanl data security and soverignty laws. Has it's own Azure Portal so the whole service is not open to audit from the US.
