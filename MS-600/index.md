# Exam MS-600: Building Applications and Solutions with Microsoft 365 Core Services

[[Microsoft Learning] Exam MS-600: Building Applications and Solutions with Microsoft 365 Core Services (beta)](https://docs.microsoft.com/en-us/learn/certifications/exams/ms-600)

## Skills Measured

### [Implement Microsoft Identity](./identity.md) (20-25%)

**Register an Application**

- determine the supported account type
- select authentication and client credentials for app type and authentication flow
- define app roles

**Implement Authentication**

- configure Microsoft Authentication Library (MSAL JS) for endpoint and token cache
- plan and configure scopes for dynamic or static permission
- use the MSAL JS login method

**Configure Permissions to Consume an API**

- configure Delegated permissions for the app
- configure Application permissions for the app
- identify admin consent requirements

**Implement Authorization to Consume an API**

- configure incremental consent scopes
- call MSAL JS using AquireTokenSilent/AquireToken pattern

**Implement Authorization in an API**

- validate Access Token
- configure effective permissions for delegated scopes
- implement app permissions using roles
- use a delegated access token to call a Microsoft API

**Create a Service to Access Microsoft Graph**

- configure client credentials using a certificate
- configure Application permissions for the app
- acquire an access token for Microsoft Graph using an application permission and client credential certificate
- acquire an access token using the client secret

### [Build Apps with Microsoft Graph](./ms-graph.md) (20-25%)

**Optimize Data Usage with query parameters**

- use $filter query parameter
- use $select query parameter
- order results using $orderby query parameter
- set page size of results using $skip and $top query parameters
- expand and retrieve resources using $expand query parameter
- retrieve the total count of matching resources using $count query parameter
- search for resources using $search query parameter
- determine the appropriate Microsoft Graph SDK to leverage

**Optimize network traffic**

- monitor for changes using change notifications
- combine multiple requests using $batch
- get changes using a delta query
- implement error 429 handler

**Access User data from Microsoft Graph**

- get the signed in users profile
- get a list of users in the organization
- get the users profile photo
- get the user object based on the users unique identifier
- get the users manager profile

**Access Files with Microsoft Graph**

- get the list of files in the signed in users OneDrive
- download a file from the signed in users OneDrive using file unique id
- download a file from a SharePoint Site using the relative path to the file
- get the list of files trending around the signed in user
- upload a large file to OneDrive
- get a user object from an owner list in a group and retrieve that user’s files

**Manage a group lifecycle on Microsoft Graph**

- get the information on a group by id
- get the list of members in a Group
- get the list of owners of a Group
- get the list of Groups where the signed in user is a member
- get the list of Groups where the signed in user is an owner
- provision a Group
- provision a Team with a Group
- delete a group

### [Extend and Customize SharePoint](./custom-sharepoint.md) (20-25%)

**Understand the components of a SharePoint Framework (SPFx) web part**

- identify the appropriate tool to create an SPFx Web Part project
- understand properties of client-side web parts
- understand Office UI Fabric in client-side web parts
- understand when to use an app page
- differentiate between app page and web part
- understand rendering framework options

**Understand SPFx extensions**

- identify the appropriate tool to create an SPFx Extension project
- understand page placeholders from Application Customizer
- understand the ListView Command Set extension
- understand the Field Customizer extension

**Understand the process to package and deploy an SPFx solution**

- understand the options for preparing a package for deployment
- understand the options for packaging a solution
- understand the requirements of tenant-scoped solution deployment
- understand the requirements of domain isolated web parts
- understand the options to deploy a solution

**Understand the consumption of Microsoft Graph**

- understand the purpose of the MSGraphClient object
- understand the methods for granting permissions to Microsoft Graph

**Understand the consumption of third party APIs secured with Azure AD from within SPFx**

- understand the purpose of the AadHttpClient object
- understand the methods for granting permissions to consume a third party API

**Understand Web Parts as Teams Tabs**

- understand the considerations for creating a SPFx Web Part to be a Teams Tab
- understand the options for deploying a SPFx Web Part as a Teams Tab

**Understand branding and theming in SharePoint**

- understand the options for SharePoint site theming
- understand the options for site designs and site scripts

### [Extend Teams](./teams.md) (15-20%)

**Understand the components of a Teams app**

- understand the purpose of a Teams app manifest
- understand App Studio functionality and features
- identify the components of an app package for Microsoft Teams
- understand the options for distributing a Teams app
- understand the benefits of using deep links
- understand task modules

**Understand webhooks in Microsoft Teams**

- understand when to use webhooks
- understand the limitations of webhooks
- understand the differences between incoming and outgoing webhooks

**Understand tabs in Microsoft Teams**

- understand when to use tabs
- understand the capabilities of personal tabs
- understand the capabilities of channel tabs
- understand the requirements for tabs for mobile clients

**Understand messaging extensions**

- understand when to use messaging extensions
- understand where messaging extensions can be invoked from
- understand search based messaging extensions
- choose the appropriate message extension command type based on requirements
- understand action-based messaging extensions with adaptive cards
- understand action-based messaging extensions with parameters

**Understand conversational bots**

- understand when to use conversational bots
- understand the scoping options for bots
- understand when to use a task module from a bot

### [Extend Office](./office.md) (15-20%)

**Understand fundamental components and types of Office Add-ins**

- understand task pane and Content Office Add-ins
- understand dialogs
- understand custom functions
- understand Add-in commands
- understand the purpose of Office Add-ins manifest

**Understand Office JS APIs**

- understand the Office Add-in programming model
- understand Office Add-in developer tools
- understand the capabilities of the Excel Javascript API
- understand the capabilities of the Outlook JavaScript API
- understand the capabilities of the Word JavaScript API
- understand the capabilities of the PowerPoint JavaScript API
- understand the capabilities of custom functions

**Understand customization of Add-ins**

- understand the options of persisting state and settings
- understand Office UI Fabric in Office Add-ins
- understand when to use Microsoft Graph in Office Add-ins
- understand authorization when using Microsoft Graph in Office Add-ins

**Understand testing, debugging, and deployment options**

- select deployment options based on requirements
- understand testing and debugging concepts for Office Add-ins

**Understand actionable messages**

- understand the features of actionable messages with an adaptive card
- understand the scenarios for refreshing an actionable message