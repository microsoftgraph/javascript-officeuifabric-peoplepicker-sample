---
page_type: sample
products:
- office-365
- ms-graph
languages:
- javascript
- html
description: "Cet exemple explique la façon de remplir un composant PeoplePicker Office UI Fabric JS avec des données récupérées à partir de Microsoft Graph."
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
# Exemple PeoplePicker Office UI Fabric JS de Microsoft Graph Office

## Table des matières

* [Introduction](#introduction)
* [Conditions préalables](#prerequisites)
* [Inscription de l’application](#register-the-application)
* [Exécuter l’exemple](#run-the-sample)
* [Questions et commentaires](#questions-and-comments)
* [Contribution](#contributing)
* [Ressources supplémentaires](#additional-resources)

## Introduction

Cet exemple explique la façon de renseigner un [composant PeoplePicker Office UI Fabric JS](https://github.com/OfficeDev/office-ui-fabric-js/blob/master/ghdocs/components/PeoplePicker.md) avec les données récupérées de Microsoft Graph. Il utilise le [Kit de développement logiciel Microsoft Graph JavaScript SDK](https://github.com/microsoftgraph/msgraph-sdk-javascript) pour fonctionner avec les données renvoyées par Microsoft Graph. Il se compose d’un fichier HTML unique qui contient toutes les informations HTML et JavaScript nécessaires pour créer un composant PeoplePicker et demander les données Microsoft Graph.

## Conditions préalables

Cet exemple nécessite les éléments suivants :  

  * [Interface utilisateur Office Fabric JS](https://github.com/OfficeDev/office-ui-fabric-js)
  * [Kit de développement logiciel (SDK) JavaScript Microsoft Graph](https://github.com/microsoftgraph/msgraph-sdk-javascript)
  * Un serveur web pour héberger le fichier HTML. Ce serveur doit prendre en charge les demandes SSL.
  * Un [compte professionnel ou scolaire](https://dev.office.com/devprogram) Microsoft. Cet exemple s’appuie sur une demande pour obtenir les 4 principaux contacts de l’utilisateur actuel. Cette demande ne s'utilise qu’avec un compte professionnel ou scolaire.
  
1. Accédez à la page [Portail Azure – Inscriptions d’applications](https://go.microsoft.com/fwlink/?linkid=2083908). 
1. Sélectionnez **Nouvelle inscription**. 
1. Lorsque la **page Inscrire une application** s’affiche, saisissez les informations d’inscription de votre application : 
    - Dans la section **Nom**, saisissez un nom d’application cohérent qui s’affichera pour les utilisateurs de l’application, par exemple `People Picker`. 
    - Dans la section **Types de comptes pris en charge**, sélectionnez **Comptes dans un annuaire organisationnel**. 
 1. Sous l'URI de redirection, attribuez la valeur Web à la première liste déroulante, puis définissez la valeur de l’URL hébergée, par ex. « https://localhost/PeoplePicker.html » 
1. Sélectionnez **S’inscrire** pour créer l’application. 
1. Sur la page **Vue d’ensemble** de l’application, cherchez la valeur **ID d’application (client)** et conservez-la pour plus tard. Vous en aurez besoin pour configurer PeoplePicker.html 
1. Dans la liste des pages de l’application, sélectionnez **Manifeste**, puis : 
    - Dans l’éditeur de manifeste, attribuez la valeur **Vrai** à la propriété ``allowPublicClient`` 
    - Sélectionnez **Enregistrer** dans la barre au-dessus de l’éditeur de manifeste. 
1. Dans la liste des pages de l’application, sélectionnez **Permissions API**. 
    - Cliquez sur le bouton **Ajouter une autorisation** puis, 
    - Vérifiez que l'onglet **API Microsoft** est sélectionné 
    - Dans la section *API Microsoft couramment utilisées*, cliquez sur **Microsoft Graph** 
    - Dans la section **Autorisations déléguées**, assurez-vous que les autorisations appropriées sont vérifiées : **User.Read**,**Mail.Send**, **User.ReadBasic.All**,**People.Read** **People.Read.All** Utilisez la zone de recherche, le cas échéant. 
    - Cliquez sur le bouton **Ajouter des autorisations** 

## Exécuter l’exemple

1. Ouvrez le fichier PeoplePicker.html dans un éditeur de texte ou un IDE. Recherchez ces lignes et renseignez-les avec les valeurs correspondantes pour `clientId` (ID de l'application que vous avez obtenu lors de l’inscription de l’application) et `redirectUrl` (*https://your host/PeoplePicker.html*).

<pre>
    var clientId = « votre ID d’application ici » ;
</pre>

2. Copiez ou clonez le [Kit de développement logiciel (SDK) Microsoft Graph JavaScript](https://github.com/microsoftgraph/msgraph-sdk-javascript) et assurez-vous que ce lien vers le fichier SDK est correct dans votre fichier PeoplePicker.html.
    <pre>
    &lt;!-- Microsoft Graph JavaScript SDK --&gt;
    &lt;script type="text/javascript" src="msgraph-sdk-javascript/lib/graph-js-sdk-web.js"&gt;&lt;/script&gt;
    </pre>
3. Copiez ou clonez le référentiel [Office UI Fabric JS](https://github.com/OfficeDev/office-ui-fabric-js) et assurez-vous que ces liens vers les principaux fichiers Office UI Fabric sont corrects dans votre fichier PeoplePicker.html.
    <pre>
    &lt;!-- Fabric core --&gt;
    &lt;link rel="stylesheet" href="fabric.min.css"&gt;
    &lt;link rel="stylesheet" href="fabric.components.min.css"&gt;
    &lt;script src="fabric.min.js"&gt;&lt;/script&gt;
    </pre>
4. Copiez le fichier PeoplePicker.html dans le répertoire racine de votre hôte web.

5. Dans votre navigateur (Chrome ou Firefox), accédez à *https://your host/PeoplePicker.html*.

6. Sélectionnez le bouton de *Connexion* à votre compte professionnel ou scolaire, puis accordez les autorisations demandées.

7. Sélectionnez le bouton du *sélecteur Remplir* pour compléter le composant PeoplePicker avec les informations des contacts de l’utilisateur actuel.


## Questions et commentaires

Nous aimerions connaître votre opinion sur cet exemple. Vous pouvez nous faire part de vos questions et suggestions dans la rubrique [Problèmes](https://github.com/microsoftgraph/javascript-officeuifabric-peoplepicker-sample/issues) de ce référentiel.

Votre avis compte beaucoup pour nous. Communiquez avec nous sur [Stack Overflow](https://stackoverflow.com/questions/tagged/microsoftgraph). Posez vos questions avec la balise \[MicrosoftGraph].

## Contribution ##

Si vous souhaitez contribuer à cet exemple, voir [CONTRIBUTING.md](CONTRIBUTING.md).

Ce projet a adopté le [Code de conduite Open Source de Microsoft](https://opensource.microsoft.com/codeofconduct/). Pour en savoir plus, reportez-vous à la [FAQ relative au code de conduite](https://opensource.microsoft.com/codeofconduct/faq/) ou contactez [opencode@microsoft.com](mailto:opencode@microsoft.com) pour toute question ou tout commentaire.

## Ressources supplémentaires

- [Autres exemples Microsoft Graph](https://github.com/microsoftgraph?utf8=%E2%9C%93&q=sample)
- [Présentation de Microsoft Graph](https://graph.microsoft.io)

## Copyright
Copyright (c) 2019 Microsoft. Tous droits réservés.
