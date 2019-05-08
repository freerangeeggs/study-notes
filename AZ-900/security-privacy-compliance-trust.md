# Understand security, privacy, compliance, and trust (25-30%)

## Understand securing network connectivity in Azure

- describe Azure Firewall
- describe Azure DDoS Protection
- describe Network Security Group (NSG)
- choose an appropriate Azure security solution

## Describe core Azure Identity services

- understand the difference between authentication and authorization
- describe Azure Active Directory
- describe Azure Multi-Factor Authentication

## Describe security tools and features of Azure

- describe Azure Security
- understand Azure Security center usage scenarios
- describe Key Vault
- describe Azure Information Protection (AIP)
- describe Azure Advanced Threat Protection (ATP)

## Azure governance methodologies

### Azure Policies

> Azure Policy is a service you can use to create, assign, and manage policies. These policies apply and enforce rules that your resources need to follow. These policies can enforce these rules when resources are created, and can be evaluated against existing resources to give visibility into compliance.

- [[Microsoft Learn] Use policies to enforce standards](https://docs.microsoft.com/en-us/learn/modules/control-and-organize-with-azure-resource-manager/4-use-policies-to-enforce-standards)

### Initiatives

### Role-Based Access Control (RBAC)

Allow users and applications only access to the relevant resources and resource groups. Do this by creating roles and assigning roles to users; then you adjust the resource to only let specific roles have access.

- [[Microsoft Learn] Secure resources with role-based access control](https://docs.microsoft.com/en-us/learn/modules/control-and-organize-with-azure-resource-manager/5-role-based-access)

### Resource Locks

Lock down a resource to stop accidental changes/deletions.

> Resource locks can set to either Delete or Read-only. Delete will allow all operations against the resource but block the ability to delete it. Read-only will only allow read activities to be performed against it, blocking any modification or deletion of the resource. Resource locks can be applied to subscriptions, resource groups, and to individual resources, and are inherited when applied at higher levels.

Locks can be added from the settings navigation on any resouce blade.

- [[Microsoft Learn] Use resource locks to protect resources](https://docs.microsoft.com/en-us/learn/modules/control-and-organize-with-azure-resource-manager/6-use-resource-locks-to-protect-resources)

### Azure Advisor security assistance

## Understand monitoring and reporting options in Azure

- describe Azure Monitor
- describe Azure Service Health
- understand the use cases and benefits of Azure Monitor and Azure Service Health

## Understand privacy, compliance and data protection standards in Azure

- understand industry compliance terms such as GDPR, ISO and NIST
- understand the Microsoft Privacy Statement
- describe the Trust center
- describe the Service Trust Portal
- describe Compliance Manager
- determine if Azure is compliant for a business need
- understand Azure Government services
- understand Azure Germany services