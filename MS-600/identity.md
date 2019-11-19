# Implement Microsoft Identity

## Register an Application

### Determine the supported account type

- [[Microsoft Learn] Account types in Microsoft Identity]
(https://docs.microsoft.com/en-us/learn/modules/getting-started-identity/4-different-account-types)
Three options here:

- **Accounts in this organizational directory only**: The app is registered for a single tenant only.
- **Accounts in any organizational directory**: The app is registered for any AAD tenant account (A.K.A. Work and School Accounts), but not for Microsoft Accounts (A.K.A. Personal accounts). This would be used by B2B applications.
- **Accounts in any organizational directory and personal Microsoft accounts**: B2B and B2C, this is multi-tenant as well as personal accounts.

### Select authentication and client credentials for app type and authentication flow



### Define app roles

App roles are specified in the app manifest, like so:

```json
"appRoles": [
  {
    "allowedMemberTypes": [
      "User"
    ],
    "description": "Creators can create Surveys",
    "displayName": "SurveyCreator",
    "id": "1b4f816e-5eaf-48b9-8613-7923830595ad",
    "isEnabled": true,
    "value": "SurveyCreator"
  },
  {
    "allowedMemberTypes": [
      "User"
    ],
    "description": "Administrators can manage the Surveys in their tenant",
    "displayName": "SurveyAdmin",
    "id": "c20e145e-5459-4a6c-a074-b942bbd4cfe1",
    "isEnabled": true,
    "value": "SurveyAdmin"
  }
],
```

These roles are specific to the app only, and are not transferred. An Azure admin can assign users to each role within the app. If the tenant has AzureAD Premium, the admin can assign security groups.

## Implement Authentication

### Configure Microsoft Authentication Library (MSAL JS) for endpoint and token cache
### Plan and configure scopes for dynamic or static permission
### Use the MSAL JS login method


## Configure Permissions to Consume an API

### Configure Delegated permissions for the app
### Configure Application permissions for the app
### Identify admin consent requirements


## Implement Authorization to Consume an API

### Configure incremental consent scopes
### Call MSAL JS using AquireTokenSilent/AquireToken pattern


## Implement Authorization in an API

### Validate Access Token
### Configure effective permissions for delegated scopes
### Implement app permissions using roles
### Use a delegated access token to call a Microsoft API


## Create a Service to Access Microsoft Graph

### Configure client credentials using a certificate
### Configure Application permissions for the app
### Acquire an access token for Microsoft Graph using an application permission and client credential certificate
### Acquire an access token using the client secret

