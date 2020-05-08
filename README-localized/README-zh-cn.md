---
page_type: sample
products:
- office-365
- ms-graph
languages:
- javascript
- html
description: "本示例演示如何使用从 Microsoft Graph 检索的数据填充 Office UI Fabric JS PeoplePicker 组件。"
extensions:
  contentType: samples 
  technologies:
  - Microsoft Graph
  - Office Fabric UI
  - Office UI Fabric
  services:
  - Office 365
  createdDate: 12/6/2016 3:58:50 PM
---
# Microsoft Graph Office UI Fabric JS PeoplePicker 示例

## 目录

* [简介](#introduction)
* [先决条件](#prerequisites)
* [注册应用程序](#register-the-application)
* [运行示例](#run-the-sample)
* [问题和意见](#questions-and-comments)
* [参与](#contributing)
* [其他资源](#additional-resources)

## 简介

本示例演示如何使用从 Microsoft Graph 检索的数据填充 [Office UI Fabric JS PeoplePicker 组件](https://github.com/OfficeDev/office-ui-fabric-js/blob/master/ghdocs/components/PeoplePicker.md)。它使用 [Microsoft Graph JavaScript SDK](https://github.com/microsoftgraph/msgraph-sdk-javascript) 来处理 Microsoft Graph 返回的数据。示例中的单个 HTML 文件包含了创建 PeoplePicker 组件并请求 Microsoft Graph 数据所需的所有 HTML 和 Javascript。

## 先决条件

本示例要求如下：  

  * [Office UI Fabric JS](https://github.com/OfficeDev/office-ui-fabric-js)
  * [Microsoft Graph JavaScript SDK](https://github.com/microsoftgraph/msgraph-sdk-javascript)
  * 用于托管 HTML 文件的 Web 服务器。此服务器必须支持 SSL 请求。
  * Microsoft [工作或学校帐户](https://dev.office.com/devprogram)。本示例依靠请求获取当前用户的前 4 个联系人。此请求只能通过工作或学校帐户进行。
  
1. 导航到 [Azure 门户 -“应用注册”](https://go.microsoft.com/fwlink/?linkid=2083908)页面。 
1. 选择“**新注册**”。 
1. 出现“**注册应用程序**”页面后，输入应用程序的注册信息： 
    - 在“**名称**”部分，输入一个会显示给应用用户的有意义的应用程序名称，例如 `People Picker`。 
    - 在“**受支持的帐户类型**”部分，选择“**任何组织目录中的帐户**”。 
 1. 在“重定向 URI”下，将第一个下拉列表设置为“Web”，并将值设置为托管的 URL，例如“https://localhost/PeoplePicker.html” 
1. 选择“**注册**”以创建应用程序。 
1. 在应用的“**概述**”页面上，查找“**应用程序(客户端) ID**”值，记录下来以供稍后使用。你将需要使用该值来配置 PeoplePicker.html 
1. 在应用的页面列表中，选择“**清单**”，然后： 
    - 在清单编辑器中，将 ``allowPublicClient`` 属性设置为 **true** 
    - 在清单编辑器上方的栏中选择“**保存**”。 
1. 在应用的页面列表中，选择“**API 权限**” 
    - 单击“**添加权限”**按钮，然后， 
    - 确保已选中”**Microsoft API**”选项卡 
    - 在“*常用 Microsoft API*”部分，单击“**Microsoft Graph**” 
    - 在“**委派权限**”部分，确保已选中适当的权限：**User.Read**、**Mail.Send**、**User.ReadBasic.All**、**People.Read**、**People.Read.All**。必要时请使用搜索框。 
    - 选择“**添加权限**”按钮 

## 运行示例

1. 在任何文本编辑器或 IDE 中打开 PeoplePicker.html 文件。查找以下行，并为其填充相应的 `clientId` 值（注册应用时收到的应用程序 ID）和 `redirectUrl` 值 (*https://your host/PeoplePicker.html*)。

<pre>
    var clientId = "your application Id here";
</pre>

2. 复制或克隆 [Microsoft Graph JavaScript SDK](https://github.com/microsoftgraph/msgraph-sdk-javascript)，并确保 SDK 文件的以下链接在 PeoplePicker.html 文件中正确。
    <pre>
    &lt;!-- Microsoft Graph JavaScript SDK --&gt;
    &lt;script type="text/javascript" src="msgraph-sdk-javascript/lib/graph-js-sdk-web.js"&gt;&lt;/script&gt;
    </pre>
3. 复制或克隆 [Office UI Fabric JS](https://github.com/OfficeDev/office-ui-fabric-js) 存储库，并确保核心 Office UI Fabric 文件的以下链接在 PeoplePicker.html 文件中正确。
    <pre>
    &lt;!-- Fabric core --&gt;
    &lt;link rel="stylesheet" href="fabric.min.css"&gt;
    &lt;link rel="stylesheet" href="fabric.components.min.css"&gt;
    &lt;script src="fabric.min.js"&gt;&lt;/script&gt;
    </pre>
4. 将 PeoplePicker.html 文件复制到 Web 主机的根目录。

5. 在浏览器（Chrome 或 Firefox）中，导航到 *https://your host/PeoplePicker.html*。

6. 选择“*登录*”按钮以使用你的工作或学校帐户登录，并授予所请求的权限。

7. 选择“*填充选取器*”按钮以使用当前用户的联系人信息填充 PeoplePicker 组件。


## 问题和意见

我们乐意倾听你对本示例的反馈。你可以在该存储库中的[问题](https://github.com/microsoftgraph/javascript-officeuifabric-peoplepicker-sample/issues)部分将问题和建议发送给我们。

你的反馈对我们意义重大。请在 [Stack Overflow](https://stackoverflow.com/questions/tagged/microsoftgraph) 上与我们联系。请给你的问题添加 \[MicrosoftGraph] 标记。

## 参与 ##

如果想要参与本示例，请参阅 [CONTRIBUTING.md](CONTRIBUTING.md)。

此项目遵循 [Microsoft 开放源代码行为准则](https://opensource.microsoft.com/codeofconduct/)。有关详细信息，请参阅[行为准则常见问题解答](https://opensource.microsoft.com/codeofconduct/faq/)。如有其他任何问题或意见，也可联系 [opencode@microsoft.com](mailto:opencode@microsoft.com)。

## 其他资源

- [其他 Microsoft Graph 示例](https://github.com/microsoftgraph?utf8=%E2%9C%93&q=sample)
- [Microsoft Graph 概述](https://graph.microsoft.io)

## 版权信息
版权所有 (c) 2019 Microsoft。保留所有权利。
