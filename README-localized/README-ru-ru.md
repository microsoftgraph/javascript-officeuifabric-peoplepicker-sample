---
page_type: sample
products:
- office-365
- ms-graph
languages:
- javascript
- html
description: "В этом примере показано, как вносить в компонент Office UI Fabric JS PeoplePicker данные, полученные из Microsoft Graph."
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
# Пример Microsoft Graph Office UI Fabric JS PeoplePicker

## Содержание

* [Введение](#introduction)
* [Предварительные требования](#prerequisites)
* [Регистрация приложения](#register-the-application)
* [Запустите пример](#run-the-sample)
* [Вопросы и комментарии](#questions-and-comments)
* [Участие](#contributing)
* [Дополнительные ресурсы](#additional-resources)

## Введение

В этом примере показано, как заполнить компонент [Office UI Fabric JS PeoplePicker ](https://github.com/OfficeDev/office-ui-fabric-js/blob/master/ghdocs/components/PeoplePicker.md) данными, полученными из Microsoft Graph. Для работы с данными, возвращаемыми Microsoft Graph, используется [Microsoft Graph JavaScript SDK](https://github.com/microsoftgraph/msgraph-sdk-javascript). Это один HTML-файл, который содержит все элементы HTML и JavaScript, необходимые для создания компонента PeoplePicker и запроса данных Microsoft Graph.

## Предварительные требования

Для этого примера требуются приведенные ниже компоненты.  

  * [Office UI Fabric JS](https://github.com/OfficeDev/office-ui-fabric-js)
  * [Microsoft Graph JavaScript SDK](https://github.com/microsoftgraph/msgraph-sdk-javascript)
  * Веб-сервер для размещения HTML-файла. Нужно, чтобы этот сервер поддерживал запросы SSL.
  * [Рабочая или учебная учетная запись](https://dev.office.com/devprogram) Майкрософт. В этом примере используется запрос на получение 4 основных контактов для текущего пользователя. Этот запрос сработает только в случае с рабочей или учебной учетной записью.
  
1. Перейдите на страницу [регистрации приложений портала Azure](https://go.microsoft.com/fwlink/?linkid=2083908). 
1. Выберите **Новая регистрация**. 
1. После появления страницы **Регистрация приложения** введите сведения для регистрации приложения: 
    - В разделе **Имя** введите осмысленное название приложения, которое будут видеть его пользователи, например,`People Picker`. 
    - В разделе **Поддерживаемые типы учетных записей** выберите **Учетные записи в любом каталоге организации**. 
 1. В разделе "Перенаправления URI" выберите в раскрывающемся меню вкладку "Интернет" и введите размещенный URL-адрес, например, "https://localhost/PeoplePicker.html". 
1. Выберите **Зарегистрировать**, чтобы создать приложение. 
1. На странице **Обзор** приложения найдите значение **Идентификатор приложения (клиент)** и запишите его, чтобы использовать его позже. Это значение потребуется вам для настройки PeoplePicker.html 
1. В списке страниц приложения выберите **Манифест** и: 
    - В редакторе манифеста присвойте свойству ``allowPublicClient`` значение **true**. 
    - Нажмите **Сохранить** в панели над редактором манифеста. 
1. В списке страниц приложения выберите **Разрешения API** 
    - Нажмите кнопку **Добавить разрешение** и 
    - Убедитесь, что выбрана вкладка **Интерфейсы API Microsoft** 
    - В разделе *Часто используемые интерфейсы API Microsoft* щелкните **Microsoft Graph** 
    - Убедитесь, что в разделе **Делегированные разрешения** выбраны правильные разрешения. **User.Read**,**Mail.Send**, **User.ReadBasic.All**,**People.Read** **People.Read.All** При необходимости используйте поле поиска. 
    - Нажмите кнопку **Добавить разрешения** 

## Запустите пример

1. Откройте файл PeoplePicker.html в любом текстовом редакторе или в интегрированной среде разработки (IDE). Найдите указанные ниже строки и внесите в них соответствующие значения — идентификатор приложения, полученный при регистрации приложения в`clientId` и (*https://your host/PeoplePicker.html*) — в`redirectUrl`.

<pre>
    var clientId = "your application Id here";
</pre>

2. Скопируйте или клонируйте [Microsoft Graph JavaScript SDK](https://github.com/microsoftgraph/msgraph-sdk-javascript) и убедитесь в том, что эта ссылка на файл SDK правильно указана в файле PeoplePicker.html.
    <pre>
    &lt;!-- Microsoft Graph JavaScript SDK --&gt;
    &lt;script type="text/javascript" src="msgraph-sdk-javascript/lib/graph-js-sdk-web.js"&gt;&lt;/script&gt;
    </pre>
3. Скопируйте или клонируйте репозиторий[Office UI Fabric JS](https://github.com/OfficeDev/office-ui-fabric-js) и убедитесь в том, что эти ссылки на основные файлы структуры пользовательского интерфейса Office правильно указаны в файле PeoplePicker.html.
    <pre>
    &lt;!-- Fabric core --&gt;
    &lt;link rel="stylesheet" href="fabric.min.css"&gt;
    &lt;link rel="stylesheet" href="fabric.components.min.css"&gt;
    &lt;script src="fabric.min.js"&gt;&lt;/script&gt;
    </pre>
4. Скопируйте файл PeoplePicker.html в корневой каталог своего веб-узла.

5. Перейдите по ссылке *https://your host/PeoplePicker.html* в своем браузере (Chrome или Firefox).

6. Воспользуйтесь кнопкой *Войти*, чтобы войти с помощью рабочей или учебной учетной записи, и предоставьте необходимые разрешения.

7. Нажмите кнопку *Заполнить средство выбора*, чтобы заполнить компонент PeoplePicker сведениями о контактах текущего пользователя.


## Вопросы и комментарии

Мы будем рады узнать ваше мнение об этом примере. Вы можете отправлять нам свои вопросы и предложения на вкладке [Issues](https://github.com/microsoftgraph/javascript-officeuifabric-peoplepicker-sample/issues) (Проблемы) этого репозитория.

Ваш отзыв важен для нас. Для связи с нами используйте сайт [Stack Overflow](https://stackoverflow.com/questions/tagged/microsoftgraph). Помечайте свои вопросы тегом \[MicrosoftGraph].

## Участие ##

Если вы хотите добавить код в этот пример, просмотрите статью [CONTRIBUTING.md](CONTRIBUTING.md).

Этот проект соответствует [Правилам поведения разработчиков открытого кода Майкрософт](https://opensource.microsoft.com/codeofconduct/). Дополнительные сведения см. в разделе [Часто задаваемые вопросы о правилах поведения](https://opensource.microsoft.com/codeofconduct/faq/). Если у вас возникли вопросы или замечания, напишите нам по адресу [opencode@microsoft.com](mailto:opencode@microsoft.com).

## Дополнительные ресурсы

- [Другие примеры кода для Microsoft Graph](https://github.com/microsoftgraph?utf8=%E2%9C%93&q=sample)
- [Общие сведения о Microsoft Graph](https://graph.microsoft.io)

## Авторские права
(c) Корпорация Майкрософт (Microsoft Corporation), 2019. Все права защищены.
