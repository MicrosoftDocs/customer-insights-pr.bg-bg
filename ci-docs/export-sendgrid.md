---
title: Експортиране на сегменти в SendGrid (преглед)
description: Научете как да конфигурирате връзката и да експортирате в SendGrid.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 855e77055eeb24a2c6cff0d45cd23edf93cc0581
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: bg-BG
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724835"
---
# <a name="export-segments-to-sendgrid-preview"></a>Експортиране на сегменти в SendGrid (преглед)

Експортирайте сегменти от унифицирани клиентски профили в списъци с контакти на SendGrid и ги използвайте за кампании и маркетинг по имейл в SendGrid.

## <a name="prerequisites"></a>Предварителни изисквания

- Акаунт в [SendGrid](https://sendgrid.com/) и съответните идентификационни данни на администратор.
- [Съществуващи списъци с контакти в SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts) и съответните ИД.
- Ключ за API на [SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).
- [Конфигурирани сегменти](segments.md) в "Прозрения за клиентите".
- Единните клиентски профили в експортираните сегменти съдържат поле, представляващо имейл адрес.

## <a name="known-limitations"></a>Известни ограничения

- Частна връзка в комбинация с Bring your own storage (BYOS) не се поддържа.
- Общо до 100 000 клиентски профила в SendGrid, което може да отнеме до няколко часа. Броят на клиентските профили, които можете да експортирате в SendGrid, зависи от договора ви със SendGrid.
- Само сегменти.

## <a name="set-up-connection-to-sendgrid"></a>Настройване на връзка към SendGrid

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Отидете на **Администратор** > **Връзки**.

1. Изберете Добавяне **на връзка** и изберете **SendGrid**.

1. Въведете разпознаваемо име за връзката в полето **Показвано име**. Показваното име и типът описват тази връзка. Препоръчваме да изберете име, което обяснява целта на връзката.

1. Изберете кой може да използва тази връзка. По подразбиране това са само администратори. За повече информация вижте [Разрешаване на сътрудници да използват връзка за експортиране](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Въведете вашия **SendGrid API ключ**.

1. Прегледайте поверителността и съответствието на [данните и изберете](connections.md#data-privacy-and-compliance) Съгласен съм **.**

1. Изберете **Свързване**, за да инициализирате връзката.

1. Изберете **Добавете себе си като потребител за експортиране** и предоставете вашите идентификационни данни на Customer Insights.

1. Изберете **Записване**, за да завършите връзката.

## <a name="configure-an-export"></a>Конфигуриране на експортиране

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Отидете на **Данни** > **Експортиране**.

1. Изберете Добавяне **на експортиране**.

1. В полето **Връзка за експортиране** изберете връзка от секцията SendGrid. Свържете се с администратор, ако няма налична връзка.

1. Въведете име за експортирането.

1. Въведете вашия **ИД** на списък SendGrid.

1. В **Съвпадение на данните** раздел, в **Имейл** поле, изберете полето, което представлява имейл адреса на клиента.

1. По желание изберете полета като **собствено име, фамилно име**, Страна/регион **, Щат**, **·** **Град** **и** Пощенски код.**·**

1. Изберете сегментите, които искате да експортирате, следвайки известните ограничения.

1. Изберете **Записване**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
