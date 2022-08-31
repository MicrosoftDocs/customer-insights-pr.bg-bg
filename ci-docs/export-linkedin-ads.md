---
title: Експортиране на сегменти в LinkedIn Ads (преглед)
description: Научете как да конфигурирате връзката и да експортирате в LinkedIn Ads.
ms.date: 08/12/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 4c3928e05db0ebda262b4ad3e928ce85f70035b9
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: bg-BG
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304690"
---
# <a name="export-segments-to-linkedin-ads-preview"></a>Експортиране на сегменти в LinkedIn Ads (преглед)

Експортирайте сегменти от унифицирани клиентски профили в LinkedIn Ads, за да създадете съответстващи аудитории. Използвайте съответстващите аудитории за насочване към компания и насочване към контакти.

## <a name="prerequisites"></a>Предварителни изисквания

- Акаунт [LinkedIn Campaign Manager](https://business.linkedin.com/marketing-solutions/ads) и съответните администраторски идентификационни данни.
- Идентификационен [LinkedIn Campaign Manager номер на акаунт](https://www.linkedin.com/help/lms/answer/a424270).
- [Конфигурирани сегменти](segments.md) в "Аналитични данни за клиенти".
- Експортираните сегменти се нуждаят от поне едно конкретно поле в зависимост от това дали избирате [насочване към](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) контакт или [насочване към](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) компанията в LinkedIn. Възможните полета са изброени в стъпката **Данни съвпадение** при [конфигуриране на експортирането](#configure-an-export).

## <a name="known-limitations"></a>Известни ограничения

- До 100 000 клиентски профила за експортиране в Реклами на LinkedIn, което може да отнеме до 10 минути, за да завършите.
- Само сегменти. Даден сегмент трябва да съдържа най-малко 300 уникални профила.

## <a name="set-up-connection-to-linkedin-ads"></a>Настройване на връзка с реклами в LinkedIn

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Отидете на **Администратор** > **Връзки**.

1. Изберете **Добавяне на връзка** и изберете **Реклами на LinkedIn**.

1. Въведете разпознаваемо име за връзката в полето **Показвано име**. Показваното име и типът описват тази връзка. Препоръчваме да изберете име, което обяснява целта на връзката.

1. Изберете кой може да използва тази връзка. По подразбиране това са само администратори. За повече информация вижте [Разрешаване на сътрудници да използват връзка за експортиране](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Предоставете Идентификационен номер на профила си LinkedIn Campaign Manager.

1. Прегледайте поверителността на [данните и съответствието](connections.md#data-privacy-and-compliance) и изберете **Съгласен** съм.

1. Изберете **Свързване**, за да инициализирате връзката.

1. Изберете **Удостоверяване с LinkedIn** и предоставете администраторските си данни за LinkedIn Campaign Manager.

1. Изберете **Добавете себе си като потребител за експортиране** и предоставете вашите идентификационни данни на Customer Insights.

1. Изберете **Записване**, за да завършите връзката.

## <a name="configure-an-export"></a>Конфигуриране на експортиране

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Отидете на **Данни** > **Експортиране**.

1. Изберете **Добавяне на експортиране**.

1. В полето **Връзка за експортиране** изберете връзка от секцията LinkedIn Ads. Свържете се с администратор, ако няма налична връзка.

1. Въведете име за експортирането.

1. Изберете дали искате да експортирате данни в [насочване на контакти](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) или [насочване на компанията](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) в LinkedIn.

1. В **Съвпадение на данните** раздел, за насочване към контакти, изберете поне едно поле, което представлява имейл адреса на клиента, Apple Ad ID, Google Ad ID, Google User ID или първо и фамилно име. Ако изберете насочване към компания, изберете поне едно поле, което представлява име на фирма, имейл домейн, URL адрес на страницата в LinkedIn, символ на акции или уебсайт.

1. По желание добавете полета, за да дефинирате допълнително експортирането си. Изберете **Добавяне на атрибут** за нанасяне на тези полета.

1. Изберете сегментите, които искате да експортирате. Съвпадащите аудитории в LinkedIn Campaign Manager автоматично ще се създаде с името на сегментите, които сте избрали за експортиране. Всеки сегмент ще доведе до отделна съпоставена аудитория.

1. Изберете **Записване**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
