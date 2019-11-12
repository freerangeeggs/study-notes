# Extend Office

[[Microsoft Learn] Understand Office Add-ins fundamentals](https://docs.microsoft.com/en-us/learn/modules/understand-office-add-ins-fundamentals/)

## Understand fundamental components and types of Office Add-ins

### Task pane and Content Office Add-ins

Task pane add-ins appear as a side-bar in the Office application
Content addins are elements you can place inside an Excel spreadsheet or PowerPoint presentation, as part of the content. 

### Dialogs

Dispays a non-modal dialog in a new window, to perform a function that doesn't work within the context of the add-in itself. for example; you could havea task pane add-in running a SPA that you need to sign in to a separate service, You could use the dialog to sign-in without redirecting your task pane window away from your SPA. This saves complicated routing and state management.

### Custom functions

Only available in excel, these allow you to create new cell functions (like `MAX()`, `MIN()`, etc...)
Only available on desktop applications in Windows or Mac, and Excel Online (in the browser)
Also need to be connected to an )365 subscription)

### Add-in commands

A UI entry-point to the add-in, typically a ribbon button in your Office application but will appear as a menu option in Outlook Mobile or Outlook Web Access.

Runs either some custom JavaScript or opens a taskpane add-in. Content add-ins are not supported and OneNote only supports add-in commans on the browser version.

### The Office Add-ins manifest

Defines what your add-in does. Are there ad-in commands and what do they do? What icon do you want to set? ID, name, visiblilty, etc...

The manifest can be [side-loaded](https://docs.microsoft.com/en-us/office/dev/add-ins/testing/sideload-office-add-ins-for-testing) into your account or added to your organization via [centralized deployment](https://docs.microsoft.com/en-us/office/dev/add-ins/publish/centralized-deployment).

## Understand Office JS APIs

- understand the Office Add-in programming model
- understand Office Add-in developer tools
- understand the capabilities of the Excel Javascript API
- understand the capabilities of the Outlook JavaScript API
- understand the capabilities of the Word JavaScript API
- understand the capabilities of the PowerPoint JavaScript API
- understand the capabilities of custom functions

## Understand customization of Add-ins

- understand the options of persisting state and settings
- understand Office UI Fabric in Office Add-ins
- understand when to use Microsoft Graph in Office Add-ins
- understand authorization when using Microsoft Graph in Office Add-ins

## Understand testing, debugging, and deployment options

- select deployment options based on requirements
- understand testing and debugging concepts for Office Add-ins

## Understand actionable messages

- understand the features of actionable messages with an adaptive card
- understand the scenarios for refreshing an actionable message