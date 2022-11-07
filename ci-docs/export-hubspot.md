---
title: Експортиране на данни от прозрения за клиенти в HubSpot
description: Научете как да конфигурирате връзката и да експортирате в HubSpot.
ms.date: 09/23/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b34f1d54fa499f6c6b80fa547a8aaf61af3b35a1
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: bg-BG
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725341"
---
# <a name="export-segments-to-hubspot-preview"></a>Експортиране на сегменти в HubSpot (предварителен преглед)

Експортирайте сегменти от унифицирани клиентски профили в HubSpot и ги използвайте за имейл маркетинг.

## <a name="prerequisites-for-a-connection"></a>Предварителни изисквания за връзка

- Акаунт [в](https://www.hubspot.com/) HubSpot и съответните идентификационни данни на администратора.
- [API ключ](https://knowledge.hubspot.com/Integrations/How-do-I-get-my-HubSpot-API-key) от HubSpot.
- [Конфигурирани сегменти](segments.md) в "Прозрения за клиентите".

## <a name="known-limitations"></a>Известни ограничения

- Частна връзка в комбинация с Bring your own storage (BYOS) не се поддържа.
- До 100 000 клиентски профила на експорт в HubSpot, което може да отнеме до 15 минути. Броят на клиентските профили, които можете да експортирате в HubSpot, зависи и е ограничен от договора ви с HubSpot.
- Само сегменти.

## <a name="set-up-connection-to-hubspot"></a>Настройване на връзка към HubSpot

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Отидете на **Администратор** > **Връзки**.

1. Изберете Добавяне **на връзка** и изберете **HubSpot**, за да конфигурирате връзката.

1. Въведете разпознаваемо име за връзката в полето **Показвано име**. Показваното име и типът описват тази връзка. Препоръчваме да изберете име, което обяснява целта на връзката.

1. Изберете кой може да използва тази връзка. Ако не предприемете нищо, по подразбиране ще е Администратори. За повече информация вижте [Разрешаване на сътрудници да използват връзка за експортиране](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Въведете идентификационните си данни за HubSpot, когато бъдете подканени.

1. Прегледайте поверителността и съответствието на [данните и изберете](connections.md#data-privacy-and-compliance) Съгласен съм **.**

1. Изберете **Свързване**, за да инициализирате връзката с HubSpot.

1. Изберете **Добавете себе си като потребител за експортиране** и предоставете вашите идентификационни данни на Customer Insights.

1. Изберете **Записване**, за да завършите връзката.

## <a name="configure-an-export"></a>Конфигуриране на експортиране

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Отидете на **Данни** > **Експортиране**.

1. За да създадете ново експортиране, изберете **Добавяне на експортиране**.

1. В **полето Връзка за експортиране** изберете връзка от секцията HubSpot. Ако не виждате името на тази секция, няма достъпни за вас връзки от този тип.

1. В **Съвпадение на данните** раздел, в **Имейл** поле, изберете полето, което представлява имейл адреса на клиента. Повторете същите стъпки за други полета по избор.

1. Изберете сегментите, които искате да експортирате.

1. Изберете **Записване**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
