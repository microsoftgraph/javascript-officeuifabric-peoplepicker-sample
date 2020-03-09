---
page_type: sample
products:
- office-365
- ms-graph
languages:
- javascript
- html
description: "このサンプルは、Office UI Fabric JS PeoplePicker コンポーネントに Microsoft Graph から取得したデータを取り込む方法を示しています。"
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
# Microsoft Graph Office UI Fabric JS PeoplePicker サンプル

## 目次

* [はじめに](#introduction)
* [前提条件](#prerequisites)
* [アプリケーションの登録](#register-the-application)
* [サンプルの実行](#run-the-sample)
* [質問とコメント](#questions-and-comments)
* [投稿](#contributing)
* [その他のリソース](#additional-resources)

## 概要

このサンプルは、[Office UI Fabric JS PeoplePicker コンポーネント](https://github.com/OfficeDev/office-ui-fabric-js/blob/master/ghdocs/components/PeoplePicker.md)に、Microsoft Graph から取得したデータを取り込む方法を示しています。[Microsoft Graph JavaScript SDK](https://github.com/microsoftgraph/msgraph-sdk-javascript) を使用して、Microsoft Graph が返すデータを操作します。PeoplePicker コンポーネントを作成して、Microsoft Graph データを要求するために必要な HTML と Javascript のすべてを含む 1 つの HTML ファイルが含まれています。

## 前提条件

このサンプルを実行するには次のものが必要です。  

  * [Office UI Fabric JS](https://github.com/OfficeDev/office-ui-fabric-js)
  * [Microsoft Graph JavaScript SDK](https://github.com/microsoftgraph/msgraph-sdk-javascript)
  * HTML ファイルをホストする Web サーバー。このサーバーは SSL 要求をサポートする必要があります。
  * Microsoft の[職場または学校のアカウント](https://dev.office.com/devprogram)。このサンプルでは、現在のユーザーの上位 4 件の連絡先を取得する要求を使用します。この要求は、職場または学校のアカウントでのみ機能します。
  
1. [Azure portal の [アプリの登録]](https://go.microsoft.com/fwlink/?linkid=2083908) ページに移動します。 
1. [**新規登録**] を選択します。 
1. [**アプリケーションの登録ページ**] が表示されたら、以下のアプリケーションの登録情報を入力します。 
    - **[名前]** セクションに、アプリのユーザーに表示されるわかりやすいアプリケーション名を入力します (例: `People Picker`)。 
    - [**サポート対象のアカウントの種類**] セクションで、[**任意の組織ディレクトリのアカウント**] を選択します。 
 1. [リダイレクト URI] で、最初のドロップダウン リストを [Web] に設定し、ホストする URL (例: 'https://localhost/PeoplePicker.html') に値を設定します 
1. [**登録**] を選択して、アプリケーションを作成します。 
1. アプリの [**概要**] ページで、[**Application (client) ID**] (アプリケーション (クライアント) ID) の値を確認し、後で使用するために記録します。PeoplePicker.html を校正するために必要です 
1. アプリのページの一覧から [**マニフェスト**] を選択します。 
    - マニフェスト エディターで ``allowPublicClient`` プロパティを **true** に設定します。 
    - マニフェスト エディターの上のバーの [**保存**] を選択します。 
1. アプリのページの一覧から [**API のアクセス許可**] を選択します。 
    - [**アクセス許可の追加]**] ボタンをクリックします 
    - [**Microsoft API**] タブが選択されていることを確認します 
    - [*一般的に使用される Microsoft API*] セクションで、[**Microsoft Graph**] をクリックします 
    - [**委任されたアクセス許可**] セクションで、適切なアクセス許可がチェックされていることを確認します。[**User.Read**]、[**Mail.Send**]、[**User.ReadBasic.All**]、[**People.Read**]、[**People.Read.All**] (必要に応じて検索ボックスを使用します)。 
    - [**アクセス許可の追加**] ボタンを選択します 

## サンプルの実行

1. 任意のテキスト エディターまたは IDE で PeoplePicker.htm ファイルを開きます。これらの行を検索し、`clientId` (アプリを登録したときに取得したアプリケーション ID) および `redirectUrl` (*https://your host/PeoplePicker.html*) に対応する値を入力します。

<pre>
    var clientId = "ここにアプリケーション ID を入力します";
</pre>

2. [Microsoft Graph JavaScript SDK](https://github.com/microsoftgraph/msgraph-sdk-javascript) をコピーまたは複製し、PeoplePicker.html ファイル内の SDK ファイルに対するこのリンクが正しいことを確認します。
    <pre>
    &lt;!-- Microsoft Graph JavaScript SDK --&gt;
    &lt;script type="text/javascript" src="msgraph-sdk-javascript/lib/graph-js-sdk-web.js"&gt;&lt;/script&gt;
    </pre>
3. [Office UI Fabric JS](https://github.com/OfficeDev/office-ui-fabric-js) repo をコピーまたは複製し、PeoplePicker.html ファイル内のコア Office UI Fabric に対するこれらのリンクが正しいことを確認します。
    <pre>
    &lt;!-- Fabric core --&gt;
    &lt;link rel="stylesheet" href="fabric.min.css"&gt;
    &lt;link rel="stylesheet" href="fabric.components.min.css"&gt;
    &lt;script src="fabric.min.js"&gt;&lt;/script&gt;
    </pre>
4. PeoplePicker.html ファイルを Web ホストのルート ディレクトリにコピーします。

5. ブラウザー (Chrome または Firefox) で、*https://your host/PeoplePicker.html* に移動します。

6. [*ログイン*] ボタンを選択し、職場または学校のアカウントでログインし、要求されたアクセス許可を付与します。

7. [*ピッカーの入力]* ボタンを選択して、PeoplePicker コンポーネントに現在のユーザーの連絡先に関する情報を 入力します。


## 質問とコメント

このサンプルに関するフィードバックをお寄せください。質問や提案につきましては、このリポジトリの「[問題](https://github.com/microsoftgraph/javascript-officeuifabric-peoplepicker-sample/issues)」セクションで送信できます。

お客様からのフィードバックを重視しています。[スタック オーバーフロー](https://stackoverflow.com/questions/tagged/microsoftgraph)でご連絡ください。ご質問には [MicrosoftGraph] のタグを付けてください。

## 投稿 ##

このサンプルに投稿する場合は、[CONTRIBUTING.md](CONTRIBUTING.md) を参照してください。

このプロジェクトでは、[Microsoft Open Source Code of Conduct (Microsoft オープン ソース倫理規定)](https://opensource.microsoft.com/codeofconduct/) が採用されています。詳細については、「[Code of Conduct の FAQ (倫理規定の FAQ)](https://opensource.microsoft.com/codeofconduct/faq/)」を参照してください。また、その他の質問やコメントがあれば、[opencode@microsoft.com](mailto:opencode@microsoft.com) までお問い合わせください。

## その他のリソース

- [Microsoft Graph の他のサンプル](https://github.com/microsoftgraph?utf8=%E2%9C%93&q=sample)
- [Microsoft Graph の概要](https://graph.microsoft.io)

## 著作権
Copyright (c) 2019 Microsoft.All rights reserved.
