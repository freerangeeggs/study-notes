# Extend Office

- [[Microsoft Learn] Understand Office Add-ins fundamentals](https://docs.microsoft.com/en-us/learn/modules/understand-office-add-ins-fundamentals/)

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

- [[Microsoft Learn] Understand Office Javascript APIs](https://docs.microsoft.com/en-us/learn/modules/understand-office-javascript-apis/)

### The Office Add-in programming model

Office proviced a JavaScript API that works as the interface between the Office App and your Add-in, there is a common API that is universal to all Office apps, and Host-specific APIs that deal with the specifics of an Office app (like picking a range in a spreadsheet, or the sender of an email).

Each piece of functionality is part of a [requirement set](https://docs.microsoft.com/en-us/office/dev/add-ins/develop/office-versions-and-requirement-sets), and you must check if an [office host supports a specific requirement set](https://docs.microsoft.com/en-us/office/dev/add-ins/overview/office-add-in-availability) if you want to use that functionality.

### Office Add-in developer tools

**Yeoman generator for Office Add-ins**

Scaffolds an add-in with manifest for Word, Excel, PowerPoint, Outlook, OneNote, or Project. This is front-end only and in you can choose from a selection of JavaScript Frameworks.

**Visual Studio**

Scaffolds an add-in for Word, Excel, PowerPoint or Outlook only. Creates an MVC app so is front and back-end capable.

**Script Lab**

An add-in available through [Appsource](https://appsource.microsoft.com/en-us/product/office/wa104380862) that can be used as a sandbox for testing out stuff in Word, Excel, or PowerPoint.

**Manifest validator**

Will read a manifest and tell you if anything is incorrect or where things should be filled out. 

### Excel Javascript API

- [[Microsoft Learn] Understand the capabilities of the Excel JavaScript API](https://docs.microsoft.com/en-us/learn/modules/understand-office-javascript-apis/4-understand-excel-javascript-api-capabilities)
- [[Microsoft Docs] Excel JavaScript API overview](https://docs.microsoft.com/en-us/office/dev/add-ins/reference/overview/excel-add-ins-reference-overview)

### Outlook JavaScript API

- [[Microsoft Learn] Understand the capabilities of the Outlook JavaScript API](https://docs.microsoft.com/en-us/learn/modules/understand-office-javascript-apis/5-understand-outlook-javascript-api-capabilities)
- [[Microsoft Docs] Outlook add-in APIs](https://docs.microsoft.com/en-us/outlook/add-ins/apis?context=office/dev/add-ins/context)

It is missing information on [task pane add-ins](https://docs.microsoft.com/en-us/outlook/add-ins/add-in-commands-for-outlook#launching-a-task-pane) though.

### Word JavaScript API

- [[Microsoft Learn] Understand the capabilities of the Word JavaScript API](https://docs.microsoft.com/en-us/learn/modules/understand-office-javascript-apis/6-understand-word-javascript-api-capabilities)
- [[Microsoft Docs] Word JavaScript API overview](https://docs.microsoft.com/en-us/office/dev/add-ins/reference/overview/word-add-ins-reference-overview)

### PowerPoint JavaScript API

- [[Microsoft Docs] JavaScript API for PowerPoint](https://docs.microsoft.com/en-us/office/dev/add-ins/reference/overview/powerpoint-add-ins-reference-overview)

### Custom functions

- [[Microsoft Learn] Understand the capabilities of custom functions](https://docs.microsoft.com/en-us/learn/modules/understand-office-javascript-apis/7-understand-custom-functions-capabilities)
- [[Microsoft Docs] Create custom functions in Excel](https://docs.microsoft.com/en-us/office/dev/add-ins/excel/custom-functions-overview)

This is in Excel only, and allows you to create a fucntion that can be referenced in a cell (like `VLOOKUP()`);
As it does not have nay visible elements, there referencing `Office.js` but instead a `custom-functions-runtime.js`.

When creating a custom function, JDoc comments are used to pass through the parameters for Excel to display to the user when they are using the function.

To communicate with an active taskpane add-in, you need to use a storage API. You also have access to a dialog API.

### Not mentioned but may be worthwhile

- [[Microsoft Docs] OneNote JavaScript API overview](https://docs.microsoft.com/en-us/office/dev/add-ins/reference/overview/onenote-add-ins-javascript-reference)
- [[Microsoft Docs] JavaScript API for Project](https://docs.microsoft.com/en-us/office/dev/add-ins/reference/overview/project-add-ins-reference-overview)
- [[Microsoft Docs] Visio JavaScript API overview](https://docs.microsoft.com/en-us/office/dev/add-ins/reference/overview/visio-javascript-reference-overview)

## Understand customization of Add-ins

- [[Microsoft Learn] Introduction to Office Add-ins customization](https://docs.microsoft.com/en-us/learn/modules/understand-office-add-ins-customization/1-introduction)

### Persisting state and settings

There are a few Office API objects (i.e. in the JavaScript API) that persisits data based on the Office App you are in and the context you want to work with.

Outlook has `RoamingSettings` and `CustomProperties`, which persist data to the user's mailbox and exchange item (email, appointment, etc...) respectively.

The others have a `Settings` object which persists data to the document/workbook/presentation, and Word and Excel have a `CustomXmlParts` that persists to a custom XML section of the document or workbook.

### Office UI Fabric in Office Add-ins

- [Office UI Fabric](https://developer.microsoft.com/en-us/fabric)

The fabric is a is baseline set of UI stylings and components that have an Office-style look and feel, although not required it can be useful.

It comes in two parts: `Fabric Core` which is the CSS stylings, colours, and iconography, and `Fabric components` which are a collection of React components (buttons, input components, panels, lalala...)

### When to use Microsoft Graph in Office Add-ins

Use when you want to access data from AzureAD, Office365, Windows 10, Enterprise Mobility, Dynamics 365. 

If you want to use the graph as part of your add-in, you will need to register the add-in as an AzureAD app, and provide consent scopes to what services you wish to use.

### Authorization when using Microsoft Graph in Office Add-ins

The user will need to be prompted to sign-in, AAD login prompts don't allow for iframes, which is what an add-in runs in, so you will need to use the dialog API to sign in and give consent to the scopes mentioned above.

After that your app will get an authorization token, which needs to be sent as part of the headers in any request to the Graph.

## Understand testing, debugging, and deployment options

### Select deployment options based on requirements



### Testing and debugging concepts for Office Add-ins



## Understand actionable messages

### Features of actionable messages with an adaptive card


### Scenarios for refreshing an actionable message


