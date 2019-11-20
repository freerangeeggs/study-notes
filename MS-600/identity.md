# Implement Microsoft Identity

## Register an Application

### Determine the supported account type

- [[Microsoft Learn] Account types in Microsoft Identity](https://docs.microsoft.com/en-us/learn/modules/getting-started-identity/4-different-account-types)

Three options here:

- **Accounts in this organizational directory only**: The app is registered for a single tenant only.
- **Accounts in any organizational directory**: The app is registered for any AAD tenant account (A.K.A. Work and School Accounts), but not for Microsoft Accounts (A.K.A. Personal accounts). This would be used by B2B applications.
- **Accounts in any organizational directory and personal Microsoft accounts**: B2B and B2C, this is multi-tenant as well as personal accounts.

### Select authentication and client credentials for app type and authentication flow

- [[Microsoft Docs] Authentication flows](https://docs.microsoft.com/en-us/azure/active-directory/develop/msal-authentication-flows)

**[Implicit Flow](https://docs.microsoft.com/en-us/azure/active-directory/develop/v2-oauth2-implicit-grant-flow)** is useful for SPAs, where there is no back-end. The user can authenticate and recieve id and access tokens. As it is not good practice to publicly expose a refresh token, none is provided on Implicit Flow. You can use MSAL to do a silent login request after the initial token has expired.

**[Auth Code Flow](https://docs.microsoft.com/en-us/azure/active-directory/develop/v2-oauth2-auth-code-flow)** is useful for scenarios where we can securely hold on to a refresh token, like on a Web app or Desktop App. The user is prompted to sign-in, and when successful an auth code is returned to the application. This can be used once (and once only) to get an access token and refresh token. Once the access token expires the refresh token can be used to get another access token without the user needing to sign-in again.

**[On-behalf-of Flow](https://docs.microsoft.com/en-us/azure/active-directory/develop/v2-oauth2-on-behalf-of-flow)** is when a backend service or web API needs to talk to another service or web API as if it was you. It will recieve a request from the application with an access token, and request a new access token to use when calling the additional service/API.

**[Client credentials Flow](https://docs.microsoft.com/en-us/azure/active-directory/develop/v2-oauth2-client-creds-grant-flow)** is auth without a user, ore more specifically when a service needs to authenticate to another service or API as the application and not a user. Auth is done without a UI (as there is no user), but instead will use the a client secret and password to connect, you can also use a client certificate for extra security.

**[Device Code Flow](https://docs.microsoft.com/en-us/azure/active-directory/develop/v2-oauth2-device-code)**  is useful for scenarios where a user needs to sign in but you cannot open a login prompt, such as IoT devices or on a command line application. The user is told to browse to a url, and enter a code that corresponds with the auth request; they then will need to log in and authorise the application.

**Integrated Windows Authentication** can be used in federated auth scenarios, where the user is created in Active Directory, but backed by AzureAD. An application with Integrated auth can get a token with no user interaction.

**[Resource Owner Password Credentials Flow](https://docs.microsoft.com/en-us/azure/active-directory/develop/v2-oauth-ropc)** is requesting a token by sending a username and password as part of the auth request call. This is a flow that requires no user interaction but will get an access token with user-level permissions.

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

