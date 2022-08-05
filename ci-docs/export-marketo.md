---
title: Експортиране на сегменти в Marketo (преглед)
description: Научете как да конфигурирате връзката и да експортирате в Marketo.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f57cdfbb24df8a8ffa1670b426d50dbba2c5f40f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: bg-BG
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195231"
---
# <a name="export-segments-to-marketo-preview"></a>Експортиране на сегменти в Marketo (преглед)

Експортирайте сегменти на унифицирани клиентски профили, за да генерирате кампании, да предоставяте маркетинг по имейл и да използвате конкретни групи клиенти с Marketo.

## <a name="prerequisites"></a>Предварителни изисквания

- [Акаунт](https://login.marketo.com/) в Marketo и съответните идентификационни данни на администратор.
- [ИД на клиент на Marketo, Тайна на клиента и REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/).
- [Съществуващи списъци в Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists) и съответните идентификатори.
- [Конфигурирани сегменти](segments.md).
- Единните клиентски профили в експортираните сегменти съдържат поле, представляващо имейл адрес.

## <a name="known-limitations"></a>Известни ограничения

- До 1 милион клиентски профила на износ за Marketo, което може да отнеме до 3 часа. Броят на клиентските профили, които можете да експортирате в Marketo, зависи от вашия договор с Marketo.
- Само сегменти.

## <a name="set-up-connection-to-marketo"></a>Настройване на връзка към Marketo

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Отидете на **Администратор** > **Връзки**.

1. Изберете **Добавяне на връзка** и изберете **Marketo**.

1. Въведете разпознаваемо име за връзката в полето **Показвано име**. Показваното име и типът описват тази връзка. Препоръчваме да изберете име, което обяснява целта на връзката.

1. Изберете кой може да използва тази връзка. По подразбиране това са само администратори. За повече информация вижте [Разрешаване на сътрудници да използват връзка за експортиране](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Въведете вашия **Marketo клиент ID, Клиент тайна и REST Крайна точка Hostname**. Името на хоста REST Endpoint е само името на хоста, без https://. Пример: xyz-abc-123.mktorest.com.

1. Прегледайте поверителността на [данните и съответствието](connections.md#data-privacy-and-compliance) и изберете **Съгласен** съм.

1. Изберете **Свързване**, за да инициализирате връзката.

1. Изберете **Добавете себе си като потребител за експортиране** и предоставете вашите идентификационни данни на Customer Insights.

1. Изберете **Записване**, за да завършите връзката.

## <a name="configure-an-export"></a>Конфигуриране на експортиране

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Отидете на **Данни** > **Експортиране**.

1. Изберете **Добавяне на експортиране**.

1. В полето **Връзка за експортиране** изберете връзка от секцията Marketo. Свържете се с администратор, ако няма налична връзка.

1. Въведете име за експортирането.

1. Въведете вашия **ИД** на списък Marketo. ИД на списъка е чисто цифрова стойност. Например, ако вашият Marketo списък ID е ST12345A7, премахнете знака преди и след цифрите и въведете *12345*.

1. В секцията Съвпадение на **данни** изберете поне едно поле, което представлява имейл адреса на клиента или ИД на Marketo на клиента.

1. По желание експортирайте **Собствено име**, **Фамилно име**, **Град**, **Щат** и **Страна/регион**, за да създадете по-персонализирани имейли. Изберете **Добавяне на атрибут** за нанасяне на тези полета.

1. Изберете сегментите, които искате да експортирате.

1. Изберете **Записване**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

В Marketo намерете сегментите си под [Marketo списъци](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).

[!INCLUDE [footer-include](includes/footer-banner.md)]
