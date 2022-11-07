---
title: Експортиране на сегменти в Campaign Monitor (преглед)
description: Научете как да конфигурирате връзката и да експортирате в Campaign Monitor.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 82303c7bcb269ee68419c9639ee743e13451f273
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: bg-BG
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724535"
---
# <a name="export-segments-to-campaign-monitor-preview"></a>Експортиране на сегменти в Campaign Monitor (преглед)

Експортирайте сегменти от унифицирани клиентски профили в Campaign Monitor и ги използвайте за маркетингови дейности.

## <a name="prerequisites"></a>Предварителни изисквания

- Акаунт за [наблюдение на кампании и съответните идентификационни данни на](https://www.campaignmonitor.com/) администратора.
- ИД на списък за наблюдение на [кампания](https://www.campaignmonitor.com/api/getting-started/#your-list-id).
- Генериран [API ключ](https://www.campaignmonitor.com/api/getting-started/) от **настройките** на профила в монитора на кампанията, за да получите идентификационния номер на списъка с API.
- [Конфигурирани сегменти](segments.md) в "Прозрения за клиентите".
- Единните клиентски профили в експортираните сегменти съдържат поле, представляващо имейл адрес.

## <a name="known-limitations"></a>Известни ограничения

- Частна връзка в комбинация с Bring your own storage (BYOS) не се поддържа.
- До 1 милион клиентски профила на експорт към Campaign Monitor, което може да отнеме до 20 минути. Броят на клиентските профили, които можете да експортирате в Campaign Monitor, зависи от договора Ви с Campaign Monitor.
- Само сегменти.

## <a name="set-up-connection-to-campaign-monitor"></a>Задаване на връзка с Campaign Monitor

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Отидете на **Администратор** > **Връзки**.

1. Изберете Добавяне **на връзка** и изберете **Монитор** на кампанията.

1. Въведете разпознаваемо име за връзката в полето **Показвано име**. Показваното име и типът описват тази връзка. Препоръчваме да изберете име, което обяснява целта на връзката.

1. Изберете кой може да използва тази връзка. По подразбиране това са само администратори. За повече информация вижте [Разрешаване на сътрудници да използват връзка за експортиране](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Прегледайте поверителността и съответствието на [данните и изберете](connections.md#data-privacy-and-compliance) Съгласен съм **.**

1. Изберете **Свързване** за инициализиране на връзката с Campaign Monitor.

1. Изберете **Удостоверяване с Campaign Monitor** и предоставете администраторските си данни за Campaign Monitor.

1. Изберете **Добавете себе си като потребител за експортиране** и предоставете вашите идентификационни данни на Customer Insights.

1. Изберете **Записване**, за да завършите връзката.

## <a name="configure-an-export"></a>Конфигуриране на експортиране

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Отидете на **Данни** > **Експортиране**.

1. За да създадете ново експортиране, изберете **Добавяне на експортиране**.

1. В полето **Връзка за експортиране** изберете връзка от секцията Campaign Monitor. Свържете се с администратор, ако няма налична връзка.

1. Въведете име за експортирането.

1. Въведете идентификационния номер **на списъка си за наблюдение на** кампании.

1. В **Съвпадение на данните** раздел, в **Имейл** поле, изберете полето, което представлява имейл адреса на клиента. Необходимо е да експортирате сегменти в Campaign Monitor.

1. Изберете сегментите, които искате да експортирате.

1. Изберете **Записване**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
