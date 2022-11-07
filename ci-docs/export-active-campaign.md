---
title: Експортиране на сегменти в ActiveCampaign
description: Научете как да конфигурирате връзката и да експортирате в ActiveCampaign.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e62888a6d618fb1154890e607d8c23d3767d35f7
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: bg-BG
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725387"
---
# <a name="export-segments-to-activecampaign-preview"></a>Експортиране на сегменти в ActiveCampaign (преглед)

Експортирайте сегменти от унифицирани клиентски профили в ActiveCampaign и ги използвайте за маркетингови дейности.

## <a name="prerequisites"></a>Предварителни изисквания

- Акаунт за [ActiveCampaign](https://www.activecampaign.com/) и съответните идентификационни данни на администратор.
- ИД на списък на [активни кампании](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).
- API ключ [на](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key) ActiveCampaign и име на хост за крайна точка на REST.
- [Конфигурирани сегменти](segments.md) в "Прозрения за клиентите".
- Единните клиентски профили в експортираните сегменти съдържат поле, представляващо имейл адрес.

## <a name="known-limitations"></a>Известни ограничения

- Частна връзка в комбинация с Bring your own storage (BYOS) не се поддържа.
- До 1 милион клиентски профила на експорт в ActiveCampaign, което може да отнеме до 90 минути. Броят на потребителските профили, които можете да експортирате в ActiveCampaign, зависи и е ограничен от вашия договор с ActiveCampaign.
- Само сегменти.

## <a name="set-up-connection-to-activecampaign"></a>Настройване на връзка с ActiveCampaign

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Отидете на **Администратор** > **Връзки**.

1. Изберете Добавяне **на връзка** и изберете **Активна кампания**.

1. Въведете разпознаваемо име за връзката в полето **Показвано име**. Показваното име и типът описват тази връзка. Препоръчваме да изберете име, което обяснява целта на връзката.

1. Изберете кой може да използва тази връзка. По подразбиране това са само администратори. За повече информация вижте [Разрешаване на сътрудници да използват връзка за експортиране](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Въведете своя API ключ ActiveCampaign и име на хост REST Endpoint. Името на хоста REST Endpoint е само името на хоста, без https://.

1. Прегледайте поверителността и съответствието на [данните и изберете](connections.md#data-privacy-and-compliance) Съгласен съм **.**

1. Изберете **Свързване**, за да инициализирате връзката.

1. Изберете **Добавете себе си като потребител за експортиране** и предоставете вашите идентификационни данни на Customer Insights.

1. Изберете **Записване**, за да завършите връзката.

## <a name="configure-an-export"></a>Конфигуриране на експортиране

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Отидете на **Данни** > **Експортиране**.

1. Изберете Добавяне **на експортиране**.

1. В **Връзка за експортиране** поле, изберете връзка от раздела ActiveCampaign. Свържете се с администратор, ако няма налична връзка.

1. Въведете име за експортирането.

1. Въведете ИД **на списъка си** с активни кампании.

1. В **Съвпадение на данните** раздел, в **Имейл** поле, изберете полето, което представлява имейл адреса на клиента.

1. По желание експортирайте **собствено име**, фамилно име **и** телефона **,** за да създадете по-персонализирани имейли. Изберете **Добавяне на атрибут** за нанасяне на тези полета.

1. Изберете сегментите, които искате да експортирате.

1. Изберете **Записване**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
