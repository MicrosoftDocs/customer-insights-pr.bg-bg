---
title: Разширени сценарии за web SDK
description: Разширени сценарии, които да вземете предвид, когато инструментирате уебсайта си със SDK.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 09/27/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 4c6646ecadbb604000d6c95b685cf6e420969a6d
ms.sourcegitcommit: f1e3cc51ea4cf68210eaf0210ad6e14b15ac4fe8
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 09/27/2021
ms.locfileid: "7558688"
---
# <a name="advanced-web-sdk-instrumentation"></a>Усъвършенствани инструменти за уеб SDK

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Тази статия ви води през напреднали сценарии, за да прецените кога да [осигурите инструменти за вашия уебсайт](instrument-website.md) с SDK на възможността за аналитични данни за ангажиране на Dynamics 365 Customer Insights.

## <a name="setting-user-details-for-your-event"></a>Задаване на потребителски подробности за вашето събитие

SDK ви позволява да дефинирате потребителска информация, която може да бъде изпратена с всяко събитие. Можете да посочите потребителски данни в свойство, наречено `user` (очакваните данни за това свойство са `IUser` обект), подобно на `src`, `name` и `cfg` в конфигурацията фрагмент от код.

`IUser` обектът съдържа следните свойства на низа:

- **localId**: Локалният идентификатор на потребителя.
- **authId**: Удостовереният потребителски идентификатор.
- **authType**: Типът на удостоверяване, използван за получаване на удостоверения потребителски идентификатор.
- **име**: Потребителското име.
- **имейл**: Имейл адресът на потребителя.

Следващият пример показва фрагмент от код, изпращащ потребителска информация. Когато виждате функции, предшествани от звездичка *, заменете функцията с вашата персонализирана реализация:

```
[…]
window, document
{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
    name:"myproject",
    cfg:{
      ingestionKey:<paste your ingestion key>",
      autoCapture:{
        view:true,
        click:true
      }
    },
    user:{
      authId: getLoggedInUserId()*,
      email: getLoggedInUserEmail()*,
      authType: "MSA",
      name: "John Doe"
    }
[…]
```

Можете също да посочите потребителска информация, като извикате `setUser(user: IUser)` API. Телеметрия, изпратена след обаждане до `setUser` API ще съдържа информация за потребителя.

## <a name="adding-custom-properties-for-each-event"></a>Добавяне на персонализирани свойства за всяко събитие

SDK ви позволява да указвате персонализирани свойства, които могат да бъдат изпратени с всяко събитие. Можете да посочите персонализираните свойства като обект, съдържащ двойки ключ-стойност (стойността може да бъде от тип `string | number | boolean`). Можете да добавите обекта в свойство, наречено `props`, подобен на`src`, `name` и `cfg` в конфигурацията фрагмент от код.

Следващият пример показва фрагмент от код, изпращащ персонализирани свойства:

```
[…]
window, document
{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
    name:"myproject",
    cfg:{
      ingestionKey:<paste your ingestion key>",
      autoCapture:{
        view:true,
        click:true
      }
    },
    props:{
      "key_name_string": "value",
      "key_name_number": 10,
      "key_name_bool": true
    }
[…]
```

Можете също да укажете персонализирани подробности индивидуално, като извикате `setProperty(name: string, value: string | number | boolean)` API.

## <a name="sending-custom-events"></a>Изпращане на персонализирани събития

Можете да използвате SDK за изпращане на персонализирани събития. Трябва да посочите име за събитието и свойства, които да бъдат изпратени заедно със събитието.

Следващият пример показва фрагмент от код, проследяващ персонализирано събитие. „ИМЕ“ е стойността в ключа `name` в конфигурацията фрагмент. Това е и името на променливата в обекта на прозореца, където се зарежда SDK.

```
window["NAME"].trackEvent({
    name: "event_name",
    properties: {
        "duration": 320,
        "name": "getting_started",
        "ad_shown": true
    }
});
```


[!INCLUDE[footer-include](../includes/footer-banner.md)]
