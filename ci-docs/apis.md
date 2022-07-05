---
title: Работа с приложни програмни интерфейси (API) на Customer Insights
description: Използвайте API и разберете ограниченията.
ms.date: 05/10/2021
ms.reviewer: wimohabb
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
searchScope:
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: 8e8bd590d3bba9dc7b1644b6ff42b9fc53237ca9
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: bg-BG
ms.lasthandoff: 06/29/2022
ms.locfileid: "9054051"
---
# <a name="work-with-customer-insights-apis"></a>Работа с приложни програмни интерфейси (API) на Customer Insights

Dynamics 365 Customer Insights предоставя API за изграждане на ваши собствени приложения въз основа на вашите данни в Customer Insights.

> [!IMPORTANT]
> Подробности за тези API са изброени в [Справка за API на Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Те включват допълнителна информация за операции, параметри и отговори.

Тази статия се описва как да получите достъп до API за аналитични данни за клиенти, да създадете регистрация на приложение в Azure и да започнете с клиентски библиотеки.

## <a name="get-started-trying-the-customer-insights-apis"></a>Започнете да изпробвате API на Customer Insights

1. [Влезте](https://home.ci.ai.dynamics.com) в Customer Insights. Ако все още нямате абонамент, [регистрирайте се за пробна версия на Customer Insights](https://aka.ms/tryci).

1. За да активирате API в средата си "Аналитични данни за клиенти", отидете **на Защита на администратора** > **·**. За това ще са ви необходими администраторски разрешения.

1. Отидете на раздел **API** и изберете бутона **Активиране**.    
 
   Активирането на API създава първичен и вторичен абонаментен ключ за вашия екземпляр, който се използва в заявките за API. Можете да регенерирате клавишите, като изберете началното **регенериране** или **Регенериране на** вторичното на API **за защита на** > **администратора** > **·**.

<!--  :::image type="content" source="media/enable-apis.gif" alt-text="Enable Customer Insights APIs."::: -->

1. Изберете **Разгледайте нашите API**, за да [изпробвате API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

1. Изберете операция на API и изберете **Изпробване**.

1. В страничния прозорец задайте стойността в **Разрешение** падащото меню до **имплицитно**. Заглавката `Authorization` се добавя с токен на носител. Вашият абонаментен ключ ще бъде попълнен автоматично.
  
1. По желание добавете всички необходими параметри на заявката.

1. Превъртете до дъното на страничния прозорец и изберете **Изпрати**.

HTTP отговорът скоро ще се появи по-долу.

<!--   :::image type="content" source="media/try-apis.gif" alt-text="How to test the APIs."::: -->

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>Създайте нова регистрация на приложение в портала на Azure

Тези стъпки ви помагат да започнете да използвате API на Customer Insights в приложение на Azure, като използвате делегирани разрешения. Не забравяйте да попълните [Начална секция](#get-started-trying-the-customer-insights-apis) първо.

1. Влезте в [Портал на Azure](https://portal.azure.com) с акаунта, който има достъп до данните на Customer Insights.

1. Вляво изберете **Регистрации на приложения**.

1. Изберете **Нова регистрация** предоставете име на приложение и изберете типа на акаунта.

   Като опция добавете URL адрес за пренасочване. http://localhost е достатъчно за разработване на приложение на вашия локален компютър.

1. На новата си регистрация на приложение отидете на **Разрешения за API**.

1. Изберете **Добавяне на разрешение** и изберете **Dynamics 365 AI за аналитични данни** за клиенти в страничния екран.

1. За **Тип разрешение**, изберете **Делегирани разрешения** и след това изберете разрешение **user_impersonation**.

1. Изберете **Добавяне на разрешения**. Ако имате нужда от достъп до API, без потребител да влезе, прегледайте [Разрешения за приложение между сървъри](#server-to-server-application-permissions) раздел.

1. Изберете **Дайте съгласието на администратора за...**, за да завършите регистрацията на приложението.

Можете да използвате Приложение/ИД на клиент за регистрацията на това приложение с библиотеката за удостоверяване на Microsoft (MSAL), за да получите токен на носител, който да изпратите с вашата заявка до API.

<!-- :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

За повече информация относно MSAL вижте [Преглед на библиотеката за удостоверяване на Microsoft (MSAL)](/azure/active-directory/develop/msal-overview).

За повече информация относно регистрацията на приложения в Azure вижте [Регистрирайте приложение](/graph/auth-register-app-v2).

За информация относно използването на API в нашите клиентски библиотеки вижте [Клиентски библиотеки на Customer Insights](#customer-insights-client-libraries).

### <a name="server-to-server-application-permissions"></a>Разрешения за приложение между сървъри

[Разделът за регистрация на приложение](#create-a-new-app-registration-in-the-azure-portal) описва как да регистрирате приложение, което изисква потребител да влезе за удостоверяване. Научете как да създадете регистрация на приложение, което не се нуждае от взаимодействие с потребителите и може да се изпълнява на сървър.

1. В регистрацията на вашето приложение в портала на Azure отидете на **Разрешения за API**.

1. Изберете **Добавяне на разрешение**. 

1. Изберете **API, които моята организация използва** и изберете **AI на Dynamics 365 for Customer Insights** от списъка. 

1. За **Тип разрешение**, изберете **разрешения на приложение** и след това изберете разрешение **CustomerInsights.Api.All**.

1. Изберете **Добавяне на разрешения**.

1. Върнете се на **Разрешения за API** за регистрацията на приложението ви.

1. Изберете **Дайте съгласието на администратора за...**, за да завършите регистрацията на приложението.

 <!--  :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

1. В заключение трябва да добавим името на регистрацията на приложението като потребител в Customer Insights.  
   
   Отворете "Аналитични данни за клиенти", отидете **на Защита на администратора** > **и** изберете **Добавяне на потребител**.

1. Потърсете името на регистрацията на вашето приложение, изберете го от резултатите от търсенето и изберете **Запазете**.

## <a name="sample-queries"></a>Примерни заявки

Съставихме кратък списък с примерни заявки на OData, за да работим с API: [OData примери](odata-examples.md) за заявки.

## <a name="customer-insights-client-libraries"></a>Клиентски библиотеки на Customer Insights

Този раздел ви помага да започнете да използвате клиентските библиотеки, налични за API на Customer Insights. Всички изходни кодове на библиотеката и примерни приложения могат да бъдат намерени в [Страница на GitHub за Customer Insights](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries). 

### <a name="c-nuget"></a>C# NuGet

Научете как да започнете да използвате клиентските библиотеки на C# от NuGet.org. За повече информация относно NuGet пакет, вижте [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/). Понастоящем този пакет е насочен към рамките netstandard2.0 и netcoreapp2.0.

#### <a name="add-the-c-client-library-to-a-c-project"></a>Добавете клиентската библиотека на C# към проект на C#

1. Във Visual Studio отворете **Мениджър на пакети на NuGet** за вашия проект.

1. Търсете **Microsoft.Dynamics.CustomerInsights.Api**.

1. Изберете **Инсталирай**, за да добавите пакета към проекта.
 
   Като алтернатива изпълнете тази команда в **Конзола на Package Manager на NuGet**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`

 <!--  :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Add NuGet package to Visual Studio project."::: -->

#### <a name="use-the-c-client-library"></a>Използвайте клиентската библиотека на C#

1. Използвайте [Библиотека за удостоверяване на Microsoft (MSAL)](/azure/active-directory/develop/msal-overview), за да получите `AccessToken`, като използвате съществуващата си [Регистрация в приложението Azure](#create-a-new-app-registration-in-the-azure-portal).

1. След успешно удостоверяване и придобиване на маркер, конструирайте нов или използвайте съществуващ `HttpClient` с DefaultRequestHeaders "Authorization"**, настроен** на Носителя "маркер за достъп"**и** Ocp-Apim-Subscription-Key **, настроени на абонаментния** ключ [**от вашата среда** Customer Insights](#get-started-trying-the-customer-insights-apis).   
 
   Нулирайте заглавието **Разрешение**, когато е подходящо. Например, когато токенът изтече.

1. Подайте този `HttpClient` в конструкцията на клиента на `CustomerInsights`.

<!--   :::image type="content" source="media/httpclient-sample.png" alt-text="Sample of httpclient."::: -->

1. Осъществявайте обаждания от клиента към „методите за разширение“, например `GetAllInstancesAsync`. Ако има достъп до основния `Microsoft.Rest.HttpOperationResponse` е за предпочитане, използвайте „методите на http съобщение“, например `GetAllInstancesWithHttpMessagesAsync`.

1. Отговорът вероятно ще бъде от тип `object`, тъй като методът може да върне множество типове (например `IList<InstanceInfo>` и `ApiErrorResult`). За да проверите типа рекламация, използвате обектите в типовете отговори, зададени на [страницата](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) с подробни данни за API за тази операция.    
   
   Ако е необходима повече информация за заявката, използвайте **http методи за съобщения** за достъп до суровия обект на отговор.

### <a name="nodejs-package"></a>Пакет NodeJS

Използвайте клиентските библиотеки на NodeJS, достъпни чрез NPM: https://www.npmjs.com/package/@microsoft/customerinsights

### <a name="python-package"></a>Пакет на Python

Използвайте клиентските библиотеки на Python, достъпни чрез PyPi: https://pypi.org/project/customerinsights/

[!INCLUDE [footer-include](includes/footer-banner.md)]
