---
title: Работа с API
description: Използвайте API и разберете ограниченията.
ms.date: 12/04/2020
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 966db1a22e7dece1bcd89733880bce059151157f
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267511"
---
# <a name="work-with-customer-insights-apis"></a>Работа с приложни програмни интерфейси (API) на Customer Insights

Dynamics 365 Customer Insights предоставя API за изграждане на ваши собствени приложения, базирани на вашите данни в Customer Insights.

> [!IMPORTANT]
> Подробности за тези API са изброени в [Справка за API на Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Те включват допълнителна информация за операции, параметри и отговори.

Тази статия ви насочва към достъп до приложните програмни интерфейси (API) на Customer Insights, създаване на регистрация на Azure App и ви помага да започнете с наличните клиентски библиотеки.

## <a name="get-started-trying-the-customer-insights-apis"></a>Започнете да изпробвате API на Customer Insights

1. [Влезте](https://home.ci.ai.dynamics.com) в Customer Insights. Ако все още нямате абонамент, [регистрирайте се за пробна версия на Customer Insights](https://aka.ms/tryci).

1. За да активирате приложните програмни интерфейси (API) в средата на Customer Insights, отидете на **Администратор** > **Разрешения**. За това ще са ви необходими администраторски разрешения.

1. Отидете на раздел **API** и изберете бутона **Активиране**.    
   Активирането на API създава първичен и вторичен абонаментен ключ за вашия екземпляр, който се използва в заявките за API. Можете да регенерирате клавишите, като изберете **Регенериране на първичен** или **Регенерирайте вторичен** на **Администратор** > **Разрешения** > **API**.

   :::image type="content" source="media/enable-apis.gif" alt-text="Активиране на API на Customer Insights":::

1. Изберете **Разгледайте нашите API**, за да изпробвате API.

1. Изберете операция на API и изберете **Изпробване**.

1. В страничния прозорец задайте стойността в падащо меню **Разрешение** на **Имплицитно**. Заглавката `Authorization` се получава с добавен маркер на носител. Вашият абонаментен ключ ще бъде попълнен автоматично.
  
1. По желание добавете всички необходими параметри на заявката.

1. Превъртете до дъното на страничния прозорец и изберете **Изпрати**.

HTTP отговорът скоро ще се появи по-долу.

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>Създайте нова регистрация на приложение в портала на Azure

Тези стъпки ви помагат да започнете да използвате API на Customer Insights в приложение на Azure, като използвате делегирани разрешения. Уверете се, че първо сте завършили [Секцията Начало](#get-started-trying-the-customer-insights-apis).

1. Влезте в [Портал на Azure](https://portal.azure.com) с акаунта, който има достъп до данните на Customer Insights.

1. Вляво изберете **Регистрации на приложения**.

1. Изберете **Нова регистрация** предоставете име на приложение и изберете типа на акаунта.
   Като опция добавете URL адрес за пренасочване. http://localhost е достатъчно за разработване на приложение на вашия локален компютър.

1. На новата си регистрация на приложение отидете на **Разрешения за API**.

1. Изберете **Добавете разрешение** и изберете **Customer Insights** в страничния прозорец.

1. За **Тип разрешение**, изберете **Делегирани разрешения** и изберете **user_impersonation** разрешение.

1. Изберете **Добавяне на разрешения**. Ако имате нужда от достъп до API, без потребител да влезе, прегледайте [Разрешения за приложение между сървъри](#server-to-server-application-permissions) раздел.

1. Изберете **Дайте съгласието на администратора за...**, за да завършите регистрацията на приложението.

Можете да използвате Приложение/ИД на клиент за регистрацията на това приложение с библиотеката за удостоверяване на Microsoft (MSAL), за да получите токен на носител, който да изпратите с вашата заявка до API.

За повече информация относно MSAL вижте [Преглед на библиотеката за удостоверяване на Microsoft (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview).

За повече информация относно регистрацията на приложения в Azure вижте [Новият опит за регистрация на приложения на портала Azure](https://docs.microsoft.com/azure/active-directory/develop/app-registration-portal-training-guide).

За информация относно използването на API на нашите клиентски библиотеки вижте [Клиентски библиотеки на Customer Insights](#customer-insights-client-libraries).

### <a name="server-to-server-application-permissions"></a>Разрешения за приложение между сървъри

[Разделът за регистрация на приложение](#create-a-new-app-registration-in-the-azure-portal) описва как да регистрирате приложение, което изисква потребител да влезе за удостоверяване. Научете как да създадете регистрация на приложение, което не се нуждае от взаимодействие с потребителя и може да се стартира на сървър.

1. В регистрацията на вашето приложение в портала на Azure отидете на **Разрешения за API**.

1. Изберете **Добавете разрешение** и изберете **Customer Insights** в страничния прозорец.

1. За **Тип разрешение**, изберете **Разрешения на приложение** и изберете разрешение **CustomerInsights.Api.All**.

1. Изберете **Добавяне на разрешения**.

1. За да дадете съгласието на администратора за това приложение, трябва да добавите Принципал на услугата.

   1. Инсталирайте модула PowerShell на Azure Active Directory (AD): `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`
   1. Свързване към акаунта си в AD: `Connect-AzureAD -TenantId <your tenant id>`. Можете да намерите ИД на клиента си **Общ преглед** > **Azure Active Directory**.
   1. Изпълнете следната команда, за да добавите Принципал на услугата на Azure AD:`New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"` Параметърът AppId се отнася до приложението API на Customer Insights.

   :::image type="content" source="media/azureAD-service-principal.png" alt-text="Пример за принципал на услуга":::

1. Върнете се на **Разрешения за API** за регистрацията на приложението ви.

1. Изберете **Дайте съгласието на администратора за...**, за да завършите регистрацията на приложението.

1. В заключение трябва да добавим името на регистрацията на приложението като потребител в Customer Insights.    
   Отворете Customer Insights, отидете на **Администратор** > **Разрешения** и изберете **Добавяне на потребител**.

1. Потърсете името на регистрацията на вашето приложение, изберете го от резултатите от търсенето и изберете **Запазете**.

## <a name="customer-insights-client-libraries"></a>Клиентски библиотеки на Customer Insights

Този раздел ви помага да започнете да използвате клиентските библиотеки, налични за API на Customer Insights.

### <a name="c-nuget"></a>C# NuGet

Научете как да започнете да използвате клиентските библиотеки на C# от NuGet.org. За повече информация относно NuGet пакет, вижте [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/). Понастоящем този пакет е насочен към рамките netstandard2.0 и netcoreapp2.0.

#### <a name="add-the-c-client-library-to-a-c-project"></a>Добавете клиентската библиотека на C# към проект на C#

1. Във Visual Studio отворете **Мениджър на пакети на NuGet** за вашия проект.

1. Търсете **Microsoft.Dynamics.CustomerInsights.Api**.

1. Изберете **Инсталирай**, за да добавите пакета към проекта.
   Като алтернатива изпълнете тази команда в **Конзола на Package Manager на NuGet**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Добавяне на пакет на NuGet към проект на Visual Studio":::

#### <a name="use-the-c-client-library"></a>Използвайте клиентската библиотека на C#

1. Използвайте [Библиотека за удостоверяване на Microsoft (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview), за да получите `AccessToken`, като използвате съществуващата си [Регистрация в приложението Azure](#create-a-new-app-registration-in-the-azure-portal).

1. След успешно удостоверяване и придобиване на маркер, конструирайте нов или използвайте съществуващ `HttpClient` с допълнителен **DefaultRequestHeaders "Authorization"** с настройка **<access token> на преносител** и **Ocp-Apim-Subscription-Key**, зададени на [**абонаментен ключ** от средата на Customer Insights](#get-started-trying-the-customer-insights-apis).    
   Нулирайте заглавието **Разрешение**, когато е подходящо. Например, когато токенът изтече.

1. Подайте този `HttpClient` в конструкцията на клиента на `CustomerInsights`.

   :::image type="content" source="media/httpclient-sample.png" alt-text="Пример за httpclient":::

1. Осъществявайте обаждания от клиента към „методите за разширение“, например `GetAllInstancesAsync`. Ако има достъп до основния `Microsoft.Rest.HttpOperationResponse` е за предпочитане, използвайте например „методите на http съобщение“ `GetAllInstancesWithHttpMessagesAsync`.

1. Отговорът вероятно ще бъде от тип `object`, тъй като методът може да върне множество типове (например `IList<InstanceInfo>` и `ApiErrorResult`). За да проверите типа на връщане, можете безопасно да прехвърлите обектите в типовете отговори, посочени в [Страница с подробности за API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) за тази операция.    
   Ако е необходима повече информация за заявката, използвайте **http методи за съобщения** за достъп до суровия обект на отговор.


[!INCLUDE[footer-include](../includes/footer-banner.md)]