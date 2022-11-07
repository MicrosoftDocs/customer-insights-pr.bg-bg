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
ms.openlocfilehash: fc4ac34c1de096e25ba6c374fe17b1da6b2f745f
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: bg-BG
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724881"
---
# <a name="export-segments-to-sendinblue-preview"></a>Експортиране на сегменти в Sendinblue (преглед)

Експортирайте сегментите на унифицирани клиентски профили, за да генерирате кампании, да извършвате маркетинг по имейл и да използвате конкретни групи клиенти със Sendinblue.

## <a name="prerequisites"></a>Предварителни изисквания

- Акаунт [в](https://www.sendinblue.com/) Sendinblue и съответните идентификационни данни на администратора.
- Ключ за [API на SendinBlue](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key).
- Съществуващи списъци в Sendinblue и съответните идентификатори.
- [Конфигурирани сегменти](segments.md).
- Единните клиентски профили в експортираните сегменти съдържат поле, представляващо имейл адрес.

## <a name="known-limitations"></a>Известни ограничения

- Частна връзка в комбинация с Bring your own storage (BYOS) не се поддържа.
- До 1 милион клиентски профила на износ в Sendinblue, което може да отнеме до 90 минути. Броят на клиентските профили, които можете да експортирате в Sendinblue, зависи от договора ви със Sendinblue.
- Само сегменти.

## <a name="set-up-connection-to-sendinblue"></a>Настройване на връзка с Sendinblue

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Отидете на **Администратор** > **Връзки**.

1. Изберете Добавяне **на връзка** и изберете **Sendinblue**.

1. Въведете разпознаваемо име за връзката в полето **Показвано име**. Показваното име и типът описват тази връзка. Препоръчваме да изберете име, което обяснява целта на връзката.

1. Изберете кой може да използва тази връзка. По подразбиране това са само администратори. За повече информация вижте [Разрешаване на сътрудници да използват връзка за експортиране](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Въведете вашия **SendinBlue API ключ**.

1. Прегледайте поверителността и съответствието на [данните и изберете](connections.md#data-privacy-and-compliance) Съгласен съм **.**

1. Изберете **Свързване**, за да инициализирате връзката.

1. Изберете **Добавете себе си като потребител за експортиране** и предоставете вашите идентификационни данни на Customer Insights.

1. Изберете **Записване**, за да завършите връзката.

## <a name="configure-an-export"></a>Конфигуриране на експортиране

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Отидете на **Данни** > **Експортиране**.

1. Изберете Добавяне **на експортиране**.

1. В **Връзка за експортиране** поле, изберете връзка от раздела Sendinblue. Свържете се с администратор, ако няма налична връзка.

1. Въведете име за експортирането.

1. Въведете вашия **Sendinblue списък ID**.

1. В **Съвпадение на данните** раздел, в **Имейл** поле, изберете полето, което представлява имейл адреса на клиента.

1. По желание експортирайте **собствено име**, фамилно име **и** телефона **,** за да създадете по-персонализирани имейли. Изберете **Добавяне на атрибут** за нанасяне на тези полета.

1. Изберете сегментите, които искате да експортирате.

1. Изберете **Записване**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
