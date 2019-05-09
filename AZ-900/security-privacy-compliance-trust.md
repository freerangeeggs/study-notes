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

### Role-Based Access Control (RBAC)

Allow users and applications only access to the relevant resources and resource groups. Do this by creating roles and assigning roles to users; then you adjust the resource to only let specific roles have access.

- [[Microsoft Learn] Secure resources with role-based access control](https://docs.microsoft.com/en-us/learn/modules/control-and-organize-with-azure-resource-manager/5-role-based-access)

### Resource Locks

Lock down a resource to stop accidental changes/deletions.

> Resource locks can set to either Delete or Read-only. Delete will allow all operations against the resource but block the ability to delete it. Read-only will only allow read activities to be performed against it, blocking any modification or deletion of the resource. Resource locks can be applied to subscriptions, resource groups, and to individual resources, and are inherited when applied at higher levels.

Locks can be added from the settings navigation on any resource blade.

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