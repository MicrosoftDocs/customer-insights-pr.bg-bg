---
title: Обогатяване на фирмените профили с Dun & Bradstreet (предварителен преглед)
description: Обща информация за обогатяването на трета страна на Dun & Bradstreet.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 71b35e4295e19c13edadc6548ac79715555e8183
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: bg-BG
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196013"
---
# <a name="enrich-company-profiles-with-dun--bradstreet-preview"></a>Обогатяване на фирмените профили с Dun & Bradstreet (предварителен преглед)

Dun & Bradstreet предоставя търговски данни, анализи и прозрения за бизнеса. Тя дава възможност на фирмите да допълнят своите данни за клиенти с унифицирани потребителски профили. Обогатяванията включват атрибути като DUNS номер, размер на фирмата, местоположение, индустрия и др.

## <a name="prerequisites"></a>Предварителни изисквания

- Активен [лиценз за Дън & Брадстрийт](https://www.dnb.com/marketing/media/give-your-data-a-boost.html?source=microsoft_audience_insights).
- [Единни профили](customer-profiles.md) на клиенти за фирми.
- Създаден е проект [на Дън & Брадстрийт](#set-up-your-dun--bradstreet-project).
- Връзка с Dun & bradstreet [е](connections.md) [конфигурирана](#configure-a-connection-for-dun--bradstreet) от администратор.

## <a name="set-up-your-dun--bradstreet-project"></a>Настройване на вашия проект "Дън и Брадстрийт"

Като лицензиран потребител на Dun & Bradstreet можете да настроите проект в [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights).

1. влезте в [Дън & Брадстрейт Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights). За да извлечете идентификационни данни, [възстановете паролата](https://sso.dnb.com/signin/forgot-password?lead_source=microsoft_audienceinsights) си.

1. Изтеглете [нашия файл](https://c360devenrichment.blob.core.windows.net/mapping/DnBCIdatamapping.csv) с шаблони за CSV, който ще се използва за съпоставяне на полетата "Аналитични данни за клиенти" в съответните полета "Дън и Брадстрийт".

1. Качете файла в стъпката **Качване на данни** от опита за създаване на проект Dun & bradstreet.

1. Изберете хоризонталните точки под съответния **източник** в новосъздадения проект Dun & bradstreet, за да видите наличните опции.

   :::image type="content" source="media/enrichment-dnb-dots.png" alt-text="Екранна снимка на точки в проект на Дън & Брадстрейт.":::

1. Изберете **Получаване на S3 подробности**. Съхранявайте тази информация на безопасно място. Ще ви трябва, за да [настроите връзката за обогатяването](#configure-a-connection-for-dun--bradstreet) в Customer Insights.

   :::image type="content" source="media/enrichment-dnb-s3info.png" alt-text="Екранна снимка на селекцията на s3 информация в проект на Dun & Bradstreet.":::

## <a name="configure-a-connection-for-dun--bradstreet"></a>Конфигуриране на връзка за Dun & bradstreet

Трябва да сте [администратор](permissions.md#admin) в Customer Insights и да имате идентификационните данни от Dun & Bradstreet Connect.

1. Изберете **Добавяне на връзка** при конфигуриране на обогатяване или отидете **на Администраторски** > **връзки** и изберете **Настройване** на плочката Dun & Bradstreet.

1. Въведете име за връзката.

1. Предоставете валидни идентификационни данни на Dun & Bradstreet и подробности за *проекта Dun & Bradstreet Регион, Път на падаща папка и Име* на папка Капка. Получавате [тази информация](#set-up-your-dun--bradstreet-project) от проекта Дън & Брадстрийт.

1. Прегледайте и дайте съгласието си за [Поверителност и съответствие на данните](#data-privacy-and-compliance) като изберете **съгласен съм**.

1. Изберете **Проверка** за проверка на конфигурацията и след това изберете **Запиши**.

   :::image type="content" source="media/enrichment-dnb-connection.png" alt-text="Страница за конфигуриране на връзката Dun & Bradstreet.":::

### <a name="data-privacy-and-compliance"></a>Поверителност и съответствие на данните

Когато разрешите Dynamics 365 Customer Insights да предавате данни на Dun & Bradstreet, вие разрешавате предаване на данни извън границата на съответствие за Dynamics 365 Customer Insights, включително потенциално чувствителни данни като Лични данни. Microsoft ще прехвърли такива данни по Ваша инструкция, но вие носите отговорност да гарантирате, че Dun & Bradstreet отговаря на всички задължения за поверителност или защита, които може да имате. За информация посетете [Декларация за поверителност Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Вашият администратор на Dynamics 365 Customer Insights да премахнете това обогатяване по всяко време, за да прекратите използването на тази функционалност.

## <a name="supported-countries-or-regions"></a>Поддържани държави или региони

В момента подкрепяме следните опции за държава/регион: Канада (английски) или Съединени американски щати (английски).

## <a name="configure-the-enrichment"></a>Конфигуриране на допълването

1. Отидете в раздела **Данни** > **Допълване** и изберете раздела **Откриване**.

1. Изберете **Обогатяване на данните** ми за данните **на Компанията за плочката** Dun & Bradstreet.

   :::image type="content" source="media/enrichment-dnb-tile.png" alt-text="Екранна снимка на плочката Дън & Брадстрийт.":::

1. Прегледайте обзора и след това изберете **Напред**.

1. Изберете връзката и потвърдете. Свържете се с администратор, ако няма налична връзка.

1. Изберете **Напред**.

1. Изберете набора **от данни на** Клиента и изберете профила или сегмента, които искате да обогатите с фирмени данни от Dun & Bradstreet. Обектът *"Клиент* " обогатява всичките Ви профили на клиенти, докато даден сегмент обогатява само профилите на клиентите, съдържащи се в този сегмент.

1. Дефинирайте кой тип полета от вашите единни профили да използвате за съответстващи фирмени данни от Dun & bradstreet. Изисква се поне едно от полетата **Име и адрес**, **Телефон** или **Имейл**.

1. Избор на **Напред**

1. Нанесете полетата си на фирмените данни от Дън & Брадстрийт. Изисква се или **DUNS номер**, или **Име на фирма** и **Държава** полета.

      :::image type="content" source="media/enrichment-dnb-mapping.png" alt-text="Панел за съпоставяне на полета &quot;Дън & Брадстрийт&quot;.":::

1. Изберете **Напред**, за да завършите съпоставянето на полета.

1. Предоставете **Име** за обогатяването и името **на** обекта "Изход".

1. Изберете **Записване на допълването**, след като прегледате избора си.

1. Изберете **Изпълнение**, за да стартирате процеса на обогатяване или близо, за да се върнете към **страницата "Обогатявания** ".

## <a name="view-enrichment-results"></a>Преглед на резултатите от обогатяването

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

## <a name="next-steps"></a>Следващи стъпки

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](includes/footer-banner.md)]
