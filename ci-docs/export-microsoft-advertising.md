---
title: Експортиране на сегменти в Microsoft Advertising (преглед)
description: Научете как да конфигурирате връзката и да експортирате в Microsoft Advertising.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 44217e7823ffbe14d232b3e33de1b4ea6ed69dcf
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: bg-BG
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196519"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a>Експортиране на сегменти в Microsoft Advertising (преглед)

Експортирайте сегменти на Customer Insights в Microsoft Advertising, за да създадете аудитории за списъци с клиенти. Използвайте тези аудитории за рекламните си кампании.

## <a name="prerequisites"></a>Предварителни изисквания

- Акаунт [за](https://ads.microsoft.com/) рекламиране на Microsoft и съответните идентификационни данни на администратор.
- ИД на клиент за рекламиране на Microsoft и ИД на акаунт. Намерете ИД на клиент (`cid`) и ИД на акаунт (`aid`) в параметрите на URL адреса, когато сте влезли в Microsoft Advertising.
- Условията за ползване на "Списъци с клиенти" се приемат.
- [Конфигурирани сегменти](segments.md) в "Аналитични данни за клиенти".
- Единните клиентски профили в експортираните сегменти съдържат поле, представляващо имейл адрес.

## <a name="known-limitations"></a>Известни ограничения

- До 500 000 клиентски профила на експортиране в Microsoft Advertising, което може да отнеме до 10 минути.
- Само сегменти.

## <a name="set-up-connection-to-microsoft-advertising"></a>Настройване на връзка с Рекламиране на Microsoft

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Отидете на **Администратор** > **Връзки**.

1. Изберете **Добавяне на връзка** и изберете **Рекламиране на Microsoft**.

1. Въведете разпознаваемо име за връзката в полето **Показвано име**. Показваното име и типът описват тази връзка. Препоръчваме да изберете име, което обяснява целта на връзката.

1. Изберете кой може да използва тази връзка. По подразбиране са администратори. За повече информация вижте [Разрешаване на сътрудници да използват връзка за експортиране](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Въведете Идентификационния номер **на клиента за рекламиране на** Microsoft.

1. Прегледайте поверителността на [данните и съответствието](connections.md#data-privacy-and-compliance) и изберете **Съгласен** съм.

1. Изберете **Свързване**, за да инициализирате връзката.

1. Изберете **Удостоверяване с Microsoft Advertising** и предоставете администраторските си данни за Microsoft Advertising.

1. Изберете **Добавете себе си като потребител за експортиране** и предоставете вашите идентификационни данни на Customer Insights.

1. Изберете **Записване**, за да завършите връзката.

## <a name="configure-an-export"></a>Конфигуриране на експортиране

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Отидете на **Данни** > **Експортиране**.

1. Изберете **Добавяне на експортиране**.

1. В полето **Връзка за експортиране** изберете връзка от секцията Microsoft Advertising. Свържете се с администратор, ако няма налична връзка.

1. Въведете име за експортирането.

1. Изберете сегменти за експортиране. Аудиториите за съвпадение на клиенти в Microsoft Advertising се създават автоматично с името на сегментите, избрани за експортиране. Всеки сегмент ще доведе до отделна аудитория за списъци с клиенти.

1. Въведете своя **Идентификационен номер на клиент на Microsoft Advertising и идентификатор на акаунт**.

1. В **Съвпадение на данните** раздел, в **Имейл** поле, изберете полето с имейл адреса на клиента.

1. Изберете **Записване**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
