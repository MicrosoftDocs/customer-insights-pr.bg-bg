---
title: Експортиране на сегменти в RollWorks (преглед)
description: Научете как да конфигурирате връзката и да експортирате в RollWorks.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d857bf5d11de86521c4a9d4fc665c020496d89d2
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: bg-BG
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725112"
---
# <a name="export-segments-to-rollworks-preview"></a>Експортиране на сегменти в RollWorks (преглед)

Експортирайте сегменти от унифицирани клиентски профили в RollWorks и ги използвайте за реклама.

## <a name="prerequisites"></a>Предварителни изисквания

- RollWorks [акаунт](https://www.rollworks.com/) и съответните идентификационни данни на администратора.
- ИД на рекламодател на [RollWorks](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).
- [Конфигурирани сегменти](segments.md) в "Прозрения за клиентите".
- Единните клиентски профили в експортираните сегменти съдържат поле, представляващо имейл адрес.

## <a name="known-limitations"></a>Известни ограничения

- Частна връзка в комбинация с Bring your own storage (BYOS) не се поддържа.
- До 250 000 клиентски профила на експорт в RollWorks, което може да отнеме до 10 минути. Броят на клиентските профили, които можете да експортирате в RollWorks, зависи от договора ви с RollWorks.
- Само сегменти.

## <a name="set-up-connection-to-rollworks"></a>Настройване на връзката с RollWorks

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Отидете на **Администратор** > **Връзки**.

1. Изберете Добавяне **на връзка** и изберете **RollWorks**.

1. Въведете разпознаваемо име за връзката в полето **Показвано име**. Показваното име и типът описват тази връзка. Препоръчваме да изберете име, което обяснява целта на връзката.

1. Изберете кой може да използва тази връзка.  По подразбиране това са само администратори. За повече информация вижте [Разрешаване на сътрудници да използват връзка за експортиране](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Прегледайте поверителността и съответствието на [данните и изберете](connections.md#data-privacy-and-compliance) Съгласен съм **.**

1. Изберете **Свързване**, за да инициализирате връзката.

1. Изберете **Удостоверяване с RollWorks** и предоставете администраторските си данни за RollWorks.

1. Изберете **Добавете себе си като потребител за експортиране** и предоставете вашите идентификационни данни на Customer Insights.

1. Изберете **Записване**, за да завършите връзката.

## <a name="configure-an-export"></a>Конфигуриране на експортиране

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Отидете на **Данни** > **Експортиране**.

1. Изберете Добавяне **на експортиране**.

1. В полето **Връзка за експортиране** изберете връзка от секцията RollWorks. Свържете се с администратор, ако няма налична връзка.

1. Въведете име за експортирането.

1. Въведете вашия **идентификационен номер** на рекламодател на RollWorks.

1. В **Съвпадение на данните** раздел, в **Имейл** поле, изберете полето, което представлява имейл адреса на клиента.

1. Изберете сегментите, които искате да експортирате.

1. Изберете **Записване**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
