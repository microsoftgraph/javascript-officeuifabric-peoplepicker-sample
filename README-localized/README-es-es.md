---
page_type: sample
products:
- office-365
- ms-graph
languages:
- javascript
- html
description: "Este ejemplo muestra cómo rellenar un componente Selector de usuarios de Office UI Fabric JS con datos extraídos de Microsoft Graph"
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
# Ejemplo de Selector de usuarios de Microsoft Graph Office UI Fabric JS

## Tabla de contenido

* [Introducción](#introduction)
* [Requisitos previos](#prerequisites)
* [Registrar la aplicación](#register-the-application)
* [Ejecutar el ejemplo](#run-the-sample)
* [Preguntas y comentarios](#questions-and-comments)
* [Colaboradores](#contributing)
* [Recursos adicionales](#additional-resources)

## Introducción

Este ejemplo muestra cómo rellenar un componente [Selector de usuarios para JS de Office UI Fabric](https://github.com/OfficeDev/office-ui-fabric-js/blob/master/ghdocs/components/PeoplePicker.md) con datos recuperados de Microsoft Graph. Usa el [SDK del JavaScript de Microsoft Graph](https://github.com/microsoftgraph/msgraph-sdk-javascript) para trabajar con los datos devueltos por Microsoft Graph. Consta de un único archivo HTML que contiene todo el HTML y JavaScript necesarios para crear un componente Selector de usuarios y solicitar los datos de Microsoft Graph.

## Requisitos previos

Este ejemplo necesita lo siguiente:  

  * [Office UI Fabric JS](https://github.com/OfficeDev/office-ui-fabric-js)
  * [SDK de JavaScript para Graph](https://github.com/microsoftgraph/msgraph-sdk-javascript)
  * Un servidor web para hospedar el archivo HTML. Este servidor debe admitir las solicitudes SSL.
  * Una cuenta [educativa o profesional de Microsoft](https://dev.office.com/devprogram). Este ejemplo se basa en una solicitud para obtener los 4 contactos principales del usuario actual. Esta solicitud solo funcionará con una cuenta profesional o educativa.
  
1. Vaya a la página [Azure Portal: registros de aplicaciones](https://go.microsoft.com/fwlink/?linkid=2083908). 
1. Seleccione **Nuevo registro**. 
1. Cuando aparezca la **página Registrar una aplicación**, escriba la información de registro de la aplicación: 
    - En la sección **Nombre**, escriba un nombre significativo para la aplicación, que se mostrará a los usuarios de la aplicación, por ejemplo `Selector de usuarios` . 
    - En la sección **Tipos de cuentas compatibles**, seleccione **Cuentas de cualquier directorio de la organización**. 
 1. En URL de redirección, seleccione en la primera lista desplegable "web" y como valor establezca la dirección URL hospedada, por ejemplo, "https://hostlocal/SelectorDeUsuarios.html". 
1. Seleccione **Registrar** para crear la aplicación. 
1. En la página **Información general** de la aplicación, busque el valor **Id. de la aplicación (cliente)** y guárdelo para más tarde. Lo necesitará para configurar el archivo SelectorDeUsuarios.html. 
1. En la lista de páginas de la aplicación, seleccione **Manifiesto** y haga lo siguiente: 
    - En el editor de manifiestos, establezca la propiedad ``allowPublicClient`` como **true**. 
    - Seleccione **Guardar** en la barra situada sobre el editor de manifiestos. 
1. En la lista de páginas de la aplicación, seleccione **Permisos de API**. 
    - Haga clic en el botón **Agregar un permiso**. 
    - Asegúrese de que la pestaña **API de Microsoft** está seleccionada. 
    - En la sección *API de Microsoft más usadas*, haga clic en **Microsoft Graph**. 
    - En la sección **Permisos delegados**, asegúrese de que los permisos adecuados estén marcados: **User.Read**,**Mail.Send**, **User.ReadBasic.All**,**People.Read** y **People.Read.All**. Use el cuadro de búsqueda si lo necesita. 
    - Seleccione el botón **Agregar permisos**. 

## Ejecutar el ejemplo

1. Abra el archivo SelectorDeUsuarios.html en cualquier editor de texto o IDE. Busque estas líneas y rellénelas con los valores correspondientes para `clientId` (el identificador de la aplicación que obtuvo al registrar la aplicación) y `redirectUrl` (*https://su host/SelectorDeUsuarios.html*).

<pre>
    var clientId = "su ID. de aplicación va aquí";
</pre>

2. Copie o clone el [SDK de JavaScript para Microsoft Graph](https://github.com/microsoftgraph/msgraph-sdk-javascript) y asegúrese de que este vínculo al archivo del SDK sea correcto en el archivo SelectorDeUsuarios.html.
    <pre>
    &lt;!-- Microsoft Graph JavaScript SDK --&gt;
    &lt;script type="text/javascript" src="msgraph-sdk-javascript/lib/graph-js-sdk-web.js"&gt;&lt;/script&gt;
    </pre>
3. Copie o clone el [repositorio de Office UI Fabric JS](https://github.com/OfficeDev/office-ui-fabric-js) y asegúrese de que estos vínculos a los archivos de Office UI Fabric básicos sean correctos en el archivo SelectorDeUsuarios.html.
    <pre>
    &lt;!-- Fabric core --&gt;
    &lt;link rel="stylesheet" href="fabric.min.css"&gt;
    &lt;link rel="stylesheet" href="fabric.components.min.css"&gt;
    &lt;script src="fabric.min.js"&gt;&lt;/script&gt;
    </pre>
4. Copie el archivo SelectorDeUsuarios.html en el directorio raíz del host de web.

5. En el navegador (Chrome o Firefox), vaya a *https://su host/SelectorDeUsuarios.html*.

6. Seleccione el botón *Iniciar sesión* para iniciar sesión con su cuenta profesional o educativa y otorgue los permisos solicitados.

7. Seleccione el botón *Rellenar del selector* para rellenar el componente Selector de usuarios con información sobre los contactos del usuario actual.


## Preguntas y comentarios

Nos encantaría recibir sus comentarios sobre este ejemplo. Puede enviarnos sus preguntas y sugerencias a través de la sección [Problemas](https://github.com/microsoftgraph/javascript-officeuifabric-peoplepicker-sample/issues) de este repositorio.

Su opinión es importante para nosotros. Conecte con nosotros en [Stack Overflow](https://stackoverflow.com/questions/tagged/microsoftgraph). Etiquete sus preguntas con \[MicrosoftGraph].

## Colaboradores ##

Si quiere hacer su aportación a este ejemplo, vea [CONTRIBUTING.md](CONTRIBUTING.md).

Este proyecto ha adoptado el [Código de conducta de código abierto de Microsoft](https://opensource.microsoft.com/codeofconduct/). Para obtener más información, consulte [Preguntas frecuentes sobre el Código de conducta](https://opensource.microsoft.com/codeofconduct/faq/) o póngase en contacto a través de [opencode@microsoft.com](mailto:opencode@microsoft.com) si tiene otras preguntas o comentarios.

## Recursos adicionales

- [Otros ejemplos de código de Microsoft Graph](https://github.com/microsoftgraph?utf8=%E2%9C%93&q=sample)
- [Información general de Microsoft Graph](https://graph.microsoft.io)

## Derechos de autor
Copyright (c) 2019 Microsoft. Todos los derechos reservados.
