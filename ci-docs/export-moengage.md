---
title: Експортиране на сегменти към MoEngage
description: Научете как да конфигурирате връзката и да експортирате в MoEngage.
ms.date: 07/26/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: df38e9e88a9c116252fba26983b5f3711b46f051
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: bg-BG
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725249"
---
# <a name="export-segments-to-moengage-preview"></a>Експортиране на сегменти към MoEngage (предварителен преглед)

Експортирайте сегменти от унифицирани клиентски профили в MoEngage и ги използвайте за имейл маркетинг в MoEngage.

## <a name="prerequisites-for-a-connection"></a>Предварителни изисквания за връзка

- [MoEngage акаунт](https://www.moengage.com/) и съответните идентификационни данни на администратора.
- MoEngage API ключ от Настройки > API в MoEngage.
- [Конфигурирани сегменти](segments.md) в "Прозрения за клиентите".

## <a name="known-limitations"></a>Известни ограничения

- Частна връзка в комбинация с Bring your own storage (BYOS) не се поддържа.
- До 100 000 клиентски профила на експорт към MoEngage, което може да отнеме до 15 минути. Броят на клиентските профили, които можете да експортирате в MoEngage зависи от договора ви с MoEngage.
- Само сегменти.

## <a name="set-up-connection-to-moengage"></a>Настройване на връзка с MoEngage

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Отидете на **Администратор** > **Връзки**.

1. Изберете Добавяне **на връзка** и изберете **MoEngage** за конфигуриране на връзката.

1. Въведете разпознаваемо име за връзката в полето **Показвано име**. Показваното име и типът описват тази връзка. Препоръчваме да изберете име, което обяснява целта на връзката.

1. Изберете кой може да използва тази връзка. Ако не предприемете нищо, по подразбиране ще е Администратори. За повече информация вижте [Разрешаване на сътрудници да използват връзка за експортиране](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Въведете вашия [MoEngage Data API ID и API ключ](https://developers.moengage.com/hc/articles/4404674776724-Overview#:~:text=Navigate%20to%20Settings%20%3E%20APIs%20%3E%20DATA,ID%20Password%20%2D%20DATA%20API%20KEY).

1. Прегледайте поверителността и съответствието на [данните и изберете](connections.md#data-privacy-and-compliance) Съгласен съм **.**

1. Изберете **Свързване**, за да инициализирате връзката с MoEngage.

1. Изберете **Добавете себе си като потребител за експортиране** и предоставете вашите идентификационни данни на Customer Insights.

1. Изберете **Записване**, за да завършите връзката.

## <a name="configure-an-export"></a>Конфигуриране на експортиране

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Отидете на **Данни** > **Експортиране**.

1. За да създадете ново експортиране, изберете **Добавяне на експортиране**.

1. В **полето Връзка за експортиране** изберете връзка от секцията MoEngage. Ако не виждате името на тази секция, няма достъпни за вас връзки от този тип.

1. В **Съвпадение на данните** раздел, в **Имейл** поле, изберете полето, което представлява имейл адреса на клиента. Повторете същите стъпки за други полета по избор.

1. Изберете сегментите, които искате да експортирате. Ще създадем един или повече сегменти със същото име като избраните сегменти в MoEngage под Сегменти по избор на **сегменти** > **·**.

1. Изберете **Записване**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
