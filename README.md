# Microsoft Graph Office UI Fabric JS PeoplePicker Sample

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

In addition, the sample uses the [Office JavaScript API Helpers](https://github.com/OfficeDev/office-js-helpers) for authentication. This helper library provides a way of authenticating users to the [v2 authentication endpoint](https://azure.microsoft.com/en-us/documentation/articles/active-directory-appmodel-v2-overview), which enables developers to write a single code flow that handles authentication for both work or school and personal accounts.

 > **Note** The authentication code the uses the Office Javascript API Helper for authentication currently works only with Chrome and Firefox browsers. This is due to a known open bug that is being tracked in [this issue](https://github.com/OfficeDev/office-js-helpers/issues/5). You can use other libraries, such as [HelloJS](http://adodson.com/hello.js/), to get an access token from the [v2 authentication endpoint](https://azure.microsoft.com/en-us/documentation/articles/active-directory-appmodel-v2-overview) that you can use to create a Microsoft Graph client with the Microsoft Graph Javascript SDK.


## Prerequisites

This sample requires the following:  

  * [Office UI Fabric JS](https://github.com/OfficeDev/office-ui-fabric-js)
  * [Microsoft Graph JavaScript SDK](https://github.com/microsoftgraph/msgraph-sdk-javascript)
  * A web server to host the HTML file. This server must support SSL requests.
  * A Microsoft [work or school account](https://dev.office.com/devprogram). This sample relies on a request to get the top 4 contacts for the current user. This request will work only with a work or school account.
  
## Register the application

1. Sign into the [Application Registration Portal](https://apps.dev.microsoft.com/) using either your personal or work or school account.

2. Choose **Add an app**.

3. Enter a name for the app, and choose **Create application**. 
    
   The registration page displays, listing the properties of your app.

4. Copy the Application Id. This is the unique identifier for your app. 

5. Under **Platforms**, choose **Add Platform**.

6. Choose **Web**.

7. Make sure the **Allow Implicit Flow** check box is selected, and enter *https://your host/PeoplePicker.html* as the Redirect URI. 

   The **Allow Implicit Flow** option enables the hybrid flow. During authentication, this enables the app to receive both sign-in info (the id_token) and artifacts (in this case, an authorization code) that the app can use to obtain an access token.

8. Choose **Save**.

## Run the sample

1. Open the PeoplePicker.html file in any text editor or IDE. Find these lines and populate them with the corresponding values for `clientId` (the application id you got when you registered the app) and `redirectUrl` (*https://your host/PeoplePicker.html*).

    <pre>
    var clientId = "your application Id here";
    var redirectUrl = "https://your host name here/PeoplePicker.html";
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
Copyright (c) 2016 Microsoft. All rights reserved.
