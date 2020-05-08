# [ARCHIVED] Microsoft Graph Office UI Fabric JS PeoplePicker Sample


## IMPORTANT

**This project is being archived. As part of the archival process, we're closing all open issues and pull requests. For UI components designed to work with Microsoft Graph and React (as well as other web-based frameworks), see the [Microsoft Graph Toolkit](https://docs.microsoft.com/graph/toolkit/overview)**

**You can continue to use this sample "as-is", but it won't be maintained moving forward. We apologize for any inconvenience.**

## Table of contents

* [Introduction](#introduction)
* [Prerequisites](#prerequisites)
* [Register the application](#register-the-application)
* [Run the sample](#run-the-sample)
* [Questions and comments](#questions-and-comments)
* [Contributing](#contributing)
* [Additional resources](#additional-resources)

## Introduction

This sample demonstrates how to populate an [Office UI Fabric JS PeoplePicker component](https://github.com/OfficeDev/office-ui-fabric-js/blob/master/ghdocs/components/PeoplePicker.md) with data retrieved from Microsoft Graph. It uses the [Microsoft Graph JavaScript SDK](https://github.com/microsoftgraph/msgraph-sdk-javascript) to work with data returned by Microsoft Graph. It consists of a single HTML file that contains all of the HTML and Javascript required to create a PeoplePicker component and request the Microsoft Graph data.

## Prerequisites

This sample requires the following:  

  * [Office UI Fabric JS](https://github.com/OfficeDev/office-ui-fabric-js)
  * [Microsoft Graph JavaScript SDK](https://github.com/microsoftgraph/msgraph-sdk-javascript)
  * A web server to host the HTML file. This server must support SSL requests.
  * A Microsoft [work or school account](https://dev.office.com/devprogram). This sample relies on a request to get the top 4 contacts for the current user. This request will work only with a work or school account.
  
1. Navigate to the [Azure portal - App registrations](https://go.microsoft.com/fwlink/?linkid=2083908) page. 
1. Select **New registration**. 
1. When the **Register an application page** appears, enter your application's registration information: 
    - In the **Name** section, enter a meaningful application name that will be displayed to users of the app, for example `People Picker`. 
    - In the **Supported account types** section, select **Accounts in any organizational directory**. 
 1. Under Redirect URI, set the first drop-down to Web and set the value to your hosted url e.g. 'https://localhost/PeoplePicker.html' 
1. Select **Register** to create the application. 
1. On the app **Overview** page, find the **Application (client) ID** value and record it for later. You'll need it to configure the PeoplePicker.html 
1. In the list of pages for the app, select **Manifest**, and: 
    - In the manifest editor, set the ``allowPublicClient`` property to **true** 
    - Select **Save** in the bar above the manifest editor. 
1. In the list of pages for the app, select **API permissions** 
    - Click the **Add a permission** button and then, 
    - Ensure that the **Microsoft APIs** tab is selected 
    - In the *Commonly used Microsoft APIs* section, click on **Microsoft Graph** 
    - In the **Delegated permissions** section, ensure that the right permissions are checked: **User.Read**,**Mail.Send**, **User.ReadBasic.All**,**People.Read** **People.Read.All** Use the search box if necessary. 
    - Select the **Add permissions** button 

## Run the sample

1. Open the PeoplePicker.html file in any text editor or IDE. Find these lines and populate them with the corresponding values for `clientId` (the application id you got when you registered the app) and `redirectUrl` (*https://your host/PeoplePicker.html*).

<pre>
    var clientId = "your application Id here";
</pre>

2. Copy or clone the [Microsoft Graph JavaScript SDK](https://github.com/microsoftgraph/msgraph-sdk-javascript) and make sure that this link to the SDK file is correct in your PeoplePicker.html file.
    <pre>
    &lt;!-- Microsoft Graph JavaScript SDK --&gt;
    &lt;script type="text/javascript" src="msgraph-sdk-javascript/lib/graph-js-sdk-web.js"&gt;&lt;/script&gt;
    </pre>
3. Copy or clone the [Office UI Fabric JS](https://github.com/OfficeDev/office-ui-fabric-js) repo and make sure that these links to the core Office UI Fabric files are correct in your PeoplePicker.html file.
    <pre>
    &lt;!-- Fabric core --&gt;
    &lt;link rel="stylesheet" href="fabric.min.css"&gt;
    &lt;link rel="stylesheet" href="fabric.components.min.css"&gt;
    &lt;script src="fabric.min.js"&gt;&lt;/script&gt;
    </pre>
4. Copy the PeoplePicker.html file to the root directory of your web host.

5. In your browser (Chrome or Firefox) navigate to *https://your host/PeoplePicker.html*.

6. Select the *Login* button to sign in with your work or school account and grant the requested permissions.

7. Select the *Populate Picker* button to fill the PeoplePicker component with information about the current user's contacts.


## Questions and comments

We'd love to get your feedback about this sample. You can send us your questions and suggestions in the [Issues](https://github.com/microsoftgraph/javascript-officeuifabric-peoplepicker-sample/issues) section of this repository.

Your feedback is important to us. Connect with us on [Stack Overflow](https://stackoverflow.com/questions/tagged/microsoftgraph). Tag your questions with [MicrosoftGraph].

## Contributing ##

If you'd like to contribute to this sample, see [CONTRIBUTING.md](CONTRIBUTING.md).

This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/). For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.

## Additional resources

- [Other Microsoft Graph samples](https://github.com/microsoftgraph?utf8=%E2%9C%93&q=sample)
- [Microsoft Graph overview](https://graph.microsoft.io)

## Copyright
Copyright (c) 2019 Microsoft. All rights reserved.
