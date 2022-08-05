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
ms.openlocfilehash: 3c04fc26dc690cf32b45913257e82b9a0f617185
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: bg-BG
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196289"
---
# <a name="export-segments-to-campaign-monitor-preview"></a>Експортиране на сегменти в Campaign Monitor (преглед)

Експортирайте сегменти от унифицирани клиентски профили в Campaign Monitor и ги използвайте за маркетингови дейности.

## <a name="prerequisites"></a>Предварителни изисквания

- Профил [в Campaign Monitor](https://www.campaignmonitor.com/) и съответните идентификационни данни на администратор.
- ИД [на списък с монитори на кампанията](https://www.campaignmonitor.com/api/getting-started/#your-list-id).
- [Генериран API ключ](https://www.campaignmonitor.com/api/getting-started/) от **Настройки на** профила в Монитор на кампанията, за да получите ИД на aPI списъка.
- [Конфигурирани сегменти](segments.md) в "Аналитични данни за клиенти".
- Единните клиентски профили в експортираните сегменти съдържат поле, представляващо имейл адрес.

## <a name="known-limitations"></a>Известни ограничения

- До 1 милион клиентски профила на експортиране в Campaign Monitor, което може да отнеме до 20 минути, за да завършите. Броят на клиентските профили, които можете да експортирате в Campaign Monitor, зависи от договора Ви с Campaign Monitor.
- Само сегменти.

## <a name="set-up-connection-to-campaign-monitor"></a>Задаване на връзка с Campaign Monitor

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Отидете на **Администратор** > **Връзки**.

1. Изберете **Добавяне на връзка** и изберете **Монитор** на кампанията.

1. Въведете разпознаваемо име за връзката в полето **Показвано име**. Показваното име и типът описват тази връзка. Препоръчваме да изберете име, което обяснява целта на връзката.

1. Изберете кой може да използва тази връзка. По подразбиране това са само администратори. За повече информация вижте [Разрешаване на сътрудници да използват връзка за експортиране](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Прегледайте поверителността на [данните и съответствието](connections.md#data-privacy-and-compliance) и изберете **Съгласен** съм.

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

1. Въведете ИД **на списъка си** с монитори на кампанията.

1. В **Съвпадение на данните** раздел, в **Имейл** поле, изберете полето, което представлява имейл адреса на клиента. Необходимо е да експортирате сегменти в Campaign Monitor.

1. Изберете сегментите, които искате да експортирате.

1. Изберете **Записване**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
