---
title: Експортиране на сегменти в Sendinblue (преглед)
description: Научете как да конфигурирате връзката и да експортирате в Sendinblue.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 816a3b242fadaa5a75db878adf0a76baf638e41c
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: bg-BG
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196933"
---
# <a name="export-segments-to-sendinblue-preview"></a>Експортиране на сегменти в Sendinblue (преглед)

Експортирайте сегментите на унифицирани клиентски профили, за да генерирате кампании, да извършвате маркетинг по имейл и да използвате конкретни групи клиенти със Sendinblue.

## <a name="prerequisites"></a>Предварителни изисквания

- [Sendinblue акаунт](https://www.sendinblue.com/) и съответните администраторски идентификационни данни.
- [API ключ sendinBlue](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key).
- Съществуващи списъци в Sendinblue и съответните идентификатори.
- [Конфигурирани сегменти](segments.md).
- Единните клиентски профили в експортираните сегменти съдържат поле, представляващо имейл адрес.

## <a name="known-limitations"></a>Известни ограничения

- До 1 милион клиентски профила за износ в Sendinblue, което може да отнеме до 90 минути, за да завършите. Броят на клиентските профили, които можете да експортирате в Sendinblue, зависи от вашия договор с Sendinblue.
- Само сегменти.

## <a name="set-up-connection-to-sendinblue"></a>Настройване на връзка с Sendinblue

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Отидете на **Администратор** > **Връзки**.

1. Изберете **Добавяне на връзка** и изберете **Sendinblue**.

1. Въведете разпознаваемо име за връзката в полето **Показвано име**. Показваното име и типът описват тази връзка. Препоръчваме да изберете име, което обяснява целта на връзката.

1. Изберете кой може да използва тази връзка. По подразбиране това са само администратори. За повече информация вижте [Разрешаване на сътрудници да използват връзка за експортиране](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Въведете вашия **API ключ** SendinBlue.

1. Прегледайте поверителността на [данните и съответствието](connections.md#data-privacy-and-compliance) и изберете **Съгласен** съм.

1. Изберете **Свързване**, за да инициализирате връзката.

1. Изберете **Добавете себе си като потребител за експортиране** и предоставете вашите идентификационни данни на Customer Insights.

1. Изберете **Записване**, за да завършите връзката.

## <a name="configure-an-export"></a>Конфигуриране на експортиране

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Отидете на **Данни** > **Експортиране**.

1. Изберете **Добавяне на експортиране**.

1. В **Връзка за експортиране** поле, изберете връзка от раздела Sendinblue. Свържете се с администратор, ако няма налична връзка.

1. Въведете име за експортирането.

1. Въведете вашия **ИД** на списък Sendinblue.

1. В **Съвпадение на данните** раздел, в **Имейл** поле, изберете полето, което представлява имейл адреса на клиента.

1. По желание експортирайте **собствено име**, **фамилно име** и **Телефон**, за да създадете по-персонализирани имейли. Изберете **Добавяне на атрибут** за нанасяне на тези полета.

1. Изберете сегментите, които искате да експортирате.

1. Изберете **Записване**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
