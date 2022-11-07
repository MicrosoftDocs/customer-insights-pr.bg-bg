---
title: Експортиране на сегменти в DotDigital (преглед)
description: Научете как да конфигурирате връзката и да експортирате в DotDigital.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8f3e3378dce9177c6645b91140884ae135540243
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: bg-BG
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724973"
---
# <a name="export-segments-to-dotdigital-preview"></a>Експортиране на сегменти в DotDigital (преглед)

Експортирайте сегменти от унифицирани клиентски профили в адресните книги на DotDigital и ги използвайте за кампании, маркетинг по имейл и за изграждане на клиентски сегменти с DotDigital.

## <a name="prerequisites"></a>Предварителни изисквания

- DotDigital [акаунт](https://dotdigital.com/) и потребител на [API](https://support.dotdigital.com/hc/articles/115001718730-How-do-I-create-an-API-user).
- DotDigital ID от нова [или съществуваща адресна](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book) книга в DotDigital. Идентификаторът може да бъде намерен в URL адреса, когато изберете и отворите адресна книга.
- [Конфигурирани сегменти](segments.md) в "Прозрения за клиентите".
- Единните клиентски профили в експортираните сегменти съдържат поле, представляващо имейл адрес.

## <a name="known-limitations"></a>Известни ограничения

- Частна връзка в комбинация с Bring your own storage (BYOS) не се поддържа.
- До 1 милион клиентски профила на експорт в DotDigital, което може да отнеме до три часа, за да завърши поради ограничения от страна на доставчика. Броят на клиентските профили, които можете да експортирате в DotDigital, зависи от договора ви с DotDigital.
- Само сегменти.

## <a name="set-up-connection-to-dotdigital"></a>Настройване на връзка с DotDigital

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Отидете на **Администратор** > **Връзки**.

1. Изберете Добавяне **на връзка** и изберете **DotDigital**.

1. Въведете разпознаваемо име за връзката в полето **Показвано име**. Показваното име и типът описват тази връзка. Препоръчваме да изберете име, което обяснява целта на връзката.

1. Изберете кой може да използва тази връзка. По подразбиране това са само администратори. За повече информация вижте [Разрешаване на сътрудници да използват връзка за експортиране](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Въведете **потребителско име и парола за DotDigital API**.

1. Въведете вашия **DotDigital адрес книга ID**.

1. Прегледайте поверителността и съответствието на [данните и изберете](connections.md#data-privacy-and-compliance) Съгласен съм **.**

1. Изберете **Свързване**, за да инициализирате връзката.

1. Изберете **Добавете себе си като потребител за експортиране** и предоставете вашите идентификационни данни на Customer Insights.

1. Изберете **Записване**, за да завършите връзката.

## <a name="configure-an-export"></a>Конфигуриране на експортиране

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Отидете на **Данни** > **Експортиране**.

1. Изберете Добавяне **на експортиране**.

1. В полето **Връзка за експортиране** изберете връзка от секцията DotDigital. Свържете се с администратор, ако няма налична връзка.

1. Въведете име за експортирането.

1. В **Съвпадение на данните** раздел, в **Имейл** поле, изберете полето, което представлява имейл адреса на клиента.

1. По желание експортирайте **собствено име**, фамилно име **, трите имена**, **·** **пола** и **пощенския код.**

1. Изберете сегментите, които искате да експортирате.

1. Изберете **Записване**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

В DotDigital намерете сегментите си в адресните книги [на](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book) DotDigital.

[!INCLUDE [footer-include](includes/footer-banner.md)]
