---
title: Работа с приложни програмни интерфейси (API) на Customer Insights
description: Използвайте API и разберете ограниченията.
ms.date: 08/31/2022
ms.reviewer: wimohabb
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
searchScope:
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: f499bff4a6ac07a88ff0f773b9cee77dc74989e8
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: MT
ms.contentlocale: bg-BG
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387327"
---
# <a name="work-with-customer-insights-apis"></a>Работа с приложни програмни интерфейси (API) на Customer Insights

Dynamics 365 Customer Insights предоставя API за изграждане на ваши собствени приложения въз основа на вашите данни в Customer Insights.

> [!IMPORTANT]
> Подробности за тези API са изброени в [Справка за API на Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Те включват допълнителна информация за операции, параметри и отговори.

Опитайте API на Customer Insights, създайте Регистрация на приложения на Azure и започнете с клиентски библиотеки.

## <a name="get-started-trying-the-customer-insights-apis"></a>Започнете да изпробвате API на Customer Insights

Активирайте API на Customer Insights и ги изпробвайте. Администраторът на Customer Insights трябва да разреши API достъп до "Аналитични данни за клиенти". След като достъпът е разрешен, всеки потребител може да използва API с абонаментния ключ.

1. [Влезте](https://home.ci.ai.dynamics.com) в Customer Insights. Ако все още нямате абонамент, [регистрирайте се за пробна версия на Customer Insights](https://aka.ms/tryci).

1. Отидете на **Защита на администратора** > **и** изберете раздела **API**.

1. Ако API достъпът до средата не е настроен, изберете **Разрешаване**.

   Активирането на API създава първичен и вторичен абонаментен ключ за вашия екземпляр, който се използва в заявките за API. За да регенерирате клавишите, изберете раздела Регенериране на **първичен** или **Регенериране на вторичен** в **раздела API**.

1. Изберете [**Разгледайте нашите API**](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances), за да изпробвате API-тата.

1. Потърсете и изберете API операция и изберете **Опитайте я**.

   :::image type="content" source="media/try-api.png" alt-text="Как да тествате API.":::

1. В страничния прозорец задайте стойността в **Разрешение** падащото меню до **имплицитно**. Заглавката `Authorization` се добавя с токен на носител. Вашият абонаментен ключ се попълва автоматично.
  
1. По желание добавете всички необходими параметри на заявката.

1. Превъртете до дъното на страничния прозорец и изберете **Изпрати**.

   HTTP отговорът показва в долната част на екрана.

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>Създайте нова регистрация на приложение в портала на Azure

Създайте нова [регистрация](/graph/auth-register-app-v2) на приложение, за да използвате API за аналитични данни за клиенти в приложение на Azure с помощта на делегирани разрешения.

1. Завършете секцията [Първи](#get-started-trying-the-customer-insights-apis) стъпки.

1. Влезте в [Портал на Azure](https://portal.azure.com) с акаунта, който има достъп до данните на Customer Insights.

1. Потърсете и след това изберете **регистрации на** приложения.

1. Изберете **Нова регистрация** предоставете име на приложение и изберете типа на акаунта.

   Като опция добавете URL адрес за пренасочване. http://localhost е достатъчно за разработване на приложение на вашия локален компютър.

1. Изберете **Регистриране**.

1. На новата си регистрация на приложение отидете на **Разрешения за API**.

1. Изберете **Добавяне на разрешение** и изберете **Dynamics 365 AI за аналитични данни** за клиенти в страничния екран.

1. За **Тип разрешение**, изберете **Делегирани разрешения** и след това изберете разрешение **user_impersonation**.

1. Изберете **Добавяне на разрешения**.

1. Изберете **Дайте съгласието на администратора за...**, за да завършите регистрацията на приложението.

1. За да получите достъп до API без влизане на потребител, отидете [на разрешения за](#server-to-server-application-permissions) приложение "Сървър към сървър".

Можете да използвате ИД на приложение/клиент за тази регистрация на приложение в библиотеката [за удостоверяване на Microsoft (MSAL),](/azure/active-directory/develop/msal-overview) за да получите маркер за приносител, който да изпратите с вашето искане до API.

<!-- :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

За информация относно използването на API в нашите клиентски библиотеки вижте [Клиентски библиотеки на Customer Insights](#customer-insights-client-libraries).

### <a name="server-to-server-application-permissions"></a>Разрешения за приложение между сървъри

Създайте регистрация на приложение, което не се нуждае от взаимодействие с потребителите и може да се изпълнява на сървър.

1. В регистрацията на вашето приложение в портала на Azure отидете на **Разрешения за API**.

1. Изберете **Добавяне на разрешение**.

1. Изберете **API, които моята организация използва** и изберете **AI на Dynamics 365 for Customer Insights** от списъка.

1. За **Тип разрешение**, изберете **разрешения на приложение** и след това изберете разрешение **CustomerInsights.Api.All**.

1. Изберете **Добавяне на разрешения**.

1. Върнете се на **Разрешения за API** за регистрацията на приложението ви.

1. Изберете **Дайте съгласието на администратора за...**, за да завършите регистрацията на приложението.

   <!--  :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

1. Добавете името на регистрацията на приложението като потребител в Customer Insights.

   1. Отворете "Аналитични данни за клиенти", отидете **на Защита на администратора** > **и** изберете **Добавяне на потребители**.

   1. Потърсете името на регистрацията на вашето приложение, изберете го от резултатите от търсенето и изберете **Запазете**.

## <a name="sample-queries"></a>Примерни заявки

За кратък списък с примерни заявки на OData за работа с API вижте [OData примери за](odata-examples.md) заявки.

## <a name="customer-insights-client-libraries"></a>Клиентски библиотеки на Customer Insights

Първи стъпки с помощта на клиентските библиотеки, налични за API-та на Customer Insights. Всички изходни кодове на библиотеката и примерни приложения могат да бъдат намерени в [Страница на GitHub за Customer Insights](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).

### <a name="c-nuget"></a>C# NuGet

Използвайте c# клиентски библиотеки от NuGet.org. В момента пакетът е насочен към netstandard2.0 и netcoreapp2.0 рамки. За повече информация относно NuGet пакета вижте [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).

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

1. Осъществявайте обаждания от клиента към „методите за разширение“, например `GetAllInstancesAsync`. Ако достъпът до базовия `Microsoft.Rest.HttpOperationResponse` инструмент е предпочитан, използвайте "методите на HTTP съобщението", например`GetAllInstancesWithHttpMessagesAsync`.

1. Отговорът вероятно `object` е тип, защото методът може да върне няколко типа (например `IList<InstanceInfo>`, и `ApiErrorResult`). За да проверите типа рекламация, използвайте обектите в типовете отговори, зададени на [страницата](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) с подробни данни за API за тази операция.

   Ако е необходима повече информация за заявката, използвайте **http методи за съобщения** за достъп до суровия обект на отговор.

### <a name="nodejs-package"></a>Пакет NodeJS

Използвайте клиентските библиотеки на NodeJS, достъпни чрез NPM: https://www.npmjs.com/package/@microsoft/customerinsights

### <a name="python-package"></a>Пакет на Python

Използвайте клиентските библиотеки на Python, достъпни чрез PyPi: https://pypi.org/project/customerinsights/

[!INCLUDE [footer-include](includes/footer-banner.md)]
