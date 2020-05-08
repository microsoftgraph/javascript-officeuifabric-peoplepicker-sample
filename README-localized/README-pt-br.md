---
page_type: sample
products:
- office-365
- ms-graph
languages:
- javascript
- html
description: "Este exemplo demonstra como preencher um componente JS PeoplePicker do Office UI Fabric com dados recuperados do Microsoft Graph."
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
# Exemplo de JS PeoplePicker do Microsoft Graph Office UI Fabric

## Sumário

* [Introdução](#introduction)
* [Pré-requisitos](#prerequisites)
* [Registrar o aplicativo](#register-the-application)
* [Executar o exemplo](#run-the-sample)
* [Perguntas e comentários](#questions-and-comments)
* [Colaboração](#contributing)
* [Recursos adicionais](#additional-resources)

## Introdução

Este exemplo demonstra como preencher um [componente JS PeoplePicker do Office UI Fabric](https://github.com/OfficeDev/office-ui-fabric-js/blob/master/ghdocs/components/PeoplePicker.md) com dados recuperados do Microsoft Graph. O exemplo usa o [SDK de JavaScript do Microsoft Graph](https://github.com/microsoftgraph/msgraph-sdk-javascript) para trabalhar com dados retornados pelo Microsoft Graph. Ele é formado por um único arquivo HTML contendo todas as HTML e JavaScript necessários para criar um componente PeoplePicker e solicitar os dados do Microsoft Graph.

## Pré-requisitos

Esse exemplo requer o seguinte:  

  * [Office UI Fabric JS](https://github.com/OfficeDev/office-ui-fabric-js)
  * [SDK de JavaScript do Microsoft Graph](https://github.com/microsoftgraph/msgraph-sdk-javascript)
  * Um servidor Web para hospedar o arquivo HTML. Este servidor deve dar suporte a solicitações SSL.
  * Uma [conta corporativas ou de estudante](https://dev.office.com/devprogram) Microsoft. Este exemplo baseia uma solicitação para obter os quatro principais contatos do usuário atual. Esta solicitação só funcionará com uma conta corporativa ou de estudante.
  
1. Navegue até a página [Portal do Azure - Registros de aplicativo](https://go.microsoft.com/fwlink/?linkid=2083908). 
1. Selecione **Novo registro**. 
1. Quando a página **Registrar um aplicativo** for exibida, insira as informações de registro do aplicativo: 
    - Na seção **Nome**, insira um nome de aplicativo relevante que será exibido aos usuários do aplicativo, por exemplo, `People Picker`. 
    - Na seção **Tipos de conta com suporte**, selecione **Contas em qualquer diretório organizacional**. 
 1. Em URI de redirecionamento, defina a primeira lista suspensa para a Web e defina o valor como a URL hospedada, por exemplo, "https://localhost/PeoplePicker.html" 
1. Selecione **Registrar** para criar o aplicativo. 
1. Na página **Visão geral** do aplicativo, encontre o valor de **ID do aplicativo (cliente)** e registre-o para usar mais tarde. Será necessário para configurar o PeoplePicker.html 
1. Na lista de páginas do aplicativo, selecione **Manifesto** e: 
    - No editor de manifesto, defina a propriedade ``allowPublicClient`` como **true** 
    - Selecione **Salvar** na barra acima do editor de manifesto. 
1. Na lista de páginas do aplicativo, selecione **Permissões de API**. 
    - Clique no botão **Adicionar uma permissão** e, em seguida, 
    - Certifique-se de que a guia **APIs da Microsoft** esteja selecionada 
    - Na seção *APIs mais usadas da Microsoft*, clique em **Microsoft Graph** 
    - Na seção **Permissões delegadas**, verifique se as permissões corretas estão marcadas: **User.Read**,**Mail.Send**, **User.ReadBasic.All**,**People.Read** **People.Read.All** Use a caixa de pesquisa, se necessário. 
    - Selecione o botão **Adicionar permissão** 

## Executar o exemplo

1. Abra o arquivo PeoplePicker. html em qualquer editor de texto ou IDE. Localize essas linhas e preencha-as com os valores correspondentes para `clientId` (a ID do aplicativo que você obteve ao registrar o aplicativo) e `redirectUrl` (*https://your host/PeoplePicker.html*).

<pre>
    var clientId = "your application Id here";
</pre>

2. Copie ou clone o [SDK de JavaScript do Microsoft Graph](https://github.com/microsoftgraph/msgraph-sdk-javascript) e verifique se esse link para o arquivo do SDK está correto no seu arquivo PeoplePicker.html.
    <pre>
    &lt;!-- Microsoft Graph JavaScript SDK --&gt;
    &lt;script type="text/javascript" src="msgraph-sdk-javascript/lib/graph-js-sdk-web.js"&gt;&lt;/script&gt;
    </pre>
3. Copie ou clone o repositório [JS do Office UI Fabric](https://github.com/OfficeDev/office-ui-fabric-js) e verifique se estes links para os principais arquivos do Office UI Fabric estão corretos em seu arquivo PeoplePicker.html.
    <pre>
    &lt;!-- Fabric core --&gt;
    &lt;link rel="stylesheet" href="fabric.min.css"&gt;
    &lt;link rel="stylesheet" href="fabric.components.min.css"&gt;
    &lt;script src="fabric.min.js"&gt;&lt;/script&gt;
    </pre>
4. Copie o arquivo PeoplePicker.html para o diretório raiz do seu host da Web.

5. No navegador (Chrome ou Firefox) navegue até *https://your host/PeoplePicker.html*.

6. Selecione o botão *Logon* para entrar com conta corporativa ou de estudante, e conceda as permissões solicitadas.

7. Selecione o botão *Preencher Seletor* para preencher o componente PeoplePicker com informações sobre os contatos do usuário atual.


## Perguntas e comentários

Gostaríamos de saber sua opinião sobre este exemplo. Você pode enviar perguntas e sugestões na seção [Problemas](https://github.com/microsoftgraph/javascript-officeuifabric-peoplepicker-sample/issues) deste repositório.

Seus comentários são importantes para nós. Junte-se a nós na página do [Stack Overflow](https://stackoverflow.com/questions/tagged/microsoftgraph). Marque suas perguntas com \[MicrosoftGraph].

## Colaboração ##

Se quiser contribuir para esse exemplo, confira [CONTRIBUTING.MD](CONTRIBUTING.md).

Este projeto adotou o [Código de Conduta Open-Source da Microsoft](https://opensource.microsoft.com/codeofconduct/). Para saber mais, confira as [Perguntas frequentes sobre o Código de Conduta](https://opensource.microsoft.com/codeofconduct/faq/) ou contate pelo [opencode@microsoft.com](mailto:opencode@microsoft.com) se tiver outras dúvidas ou comentários.

## Recursos adicionais

- [Outros exemplos do Microsoft Graph](https://github.com/microsoftgraph?utf8=%E2%9C%93&q=sample)
- [Visão geral do Microsoft Graph](https://graph.microsoft.io)

## Direitos autorais
Copyright (c) 2019 Microsoft. Todos os direitos reservados.
