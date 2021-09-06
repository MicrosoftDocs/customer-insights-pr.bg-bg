---
title: Експортирайте данни за Customer Insights в Sendinblue
description: Научете как да конфигурирате връзката и да експортирате в Sendinblue.
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 58ca0ae5ad4a3a291f4336984d14fefb23a58ab3
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314577"
---
# <a name="export-segments-to-sendinblue-preview"></a>Експортиране на сегменти в Sendinblue (преглед)

Експортирайте сегментите на унифицирани клиентски профили, за да генерирате кампании, да извършвате маркетинг по имейл и да използвате конкретни групи клиенти със Sendinblue.

## <a name="prerequisites-for-connection"></a>Предварителни изисквания за връзка

-   Имате [Акаунт в Sendinblue](https://www.sendinblue.com/) и съответните идентификационни данни на администратора.
-   В Sendinblue има съществуващи списъци и съответните идентификатори.
-   Имате [конфигурирани сегменти](segments.md).
-   Единните клиентски профили в експортираните сегменти съдържат поле, представляващо имейл адрес.

## <a name="known-limitations"></a>Известни ограничения

- До 1 милион профила на износ към Sendinblue.
- Експортирането в Sendinblue е ограничено до сегменти.
- Експортирането на сегменти с общо 1 милион профила може да отнеме до 90 минути. 
- Броят на профилите, които можете да експортирате в Sendinblue, зависи и е ограничен от вашия договор със Sendinblue.

## <a name="set-up-connection-to-sendinblue"></a>Настройване на връзка с Sendinblue

1. Отидете на **Администратор** > **Връзки**.

1. Изберете **Добавете връзка** и изберете **Sendinblue** за конфигуриране на връзката.

1. Въведете разпознаваемо име за връзката в полето **Показвано име**. Показваното име и типът описват тази връзка. Препоръчваме да изберете име, което обяснява целта на връзката.

1. Изберете кой може да използва тази връзка. По подразбиране това са само администратори. За повече информация вижте [Разрешаване на сътрудници да използват връзка за експортиране](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Въведете своя **[API ключ на SendinBlue](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.

1. Изберете **съгласен съм** за да потвърдите **Поверителност и съответствие на данните** и изберете **Свържете** за инициализиране на връзката към Sendinblue.

1. Изберете **Добавете себе си като потребител за експортиране** и предоставете вашите идентификационни данни на Customer Insights.

1. Изберете **Записване**, за да завършите връзката.

## <a name="configure-an-export"></a>Конфигуриране на експортиране

Можете да конфигурирате това експортиране, ако имате достъп до връзка от този тип. За повече информация вижте [Разрешения, необходими за конфигуриране на експортиране](export-destinations.md#set-up-a-new-export).

1. Отидете на **Данни** > **Експортиране**.

1. За да създадете ново експортиране, изберете **Добавяне на местоназначение**.

1. В **Връзка за експортиране** поле, изберете връзка от раздела Sendinblue. Ако не виждате името на тази секция, няма достъпни за вас връзки от този тип.

1. Въведете своя **ИД на списък на Sendinblue** 

1. В секцията **Съвпадение на данни** в полето **Имейл** изберете полето във вашия унифициран потребителски профил, което представлява имейл адреса на клиента. 

1. По желание можете да експортирате **собствено име**, **фамилно име** и **Телефон** за създаване на по-персонализирани имейли. Изберете **Добавяне на атрибут** за нанасяне на тези полета.

1. Изберете сегментите, които искате да експортирате. 

1. Изберете **Записване**.

Запазването на експортиране не го изпълнява незабавно.

Експортирането се изпълнява с всяко [планирано обновяване](system.md#schedule-tab). Може също [да експортирате данни при поискване](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Поверителност и съответствие на данните

Когато активирате Dynamics 365 Customer Insights за предаване на данни на Sendinblue, разрешавате прехвърляне на данни извън границата за съответствие за Dynamics 365 Customer Insights, включително потенциално чувствителни данни като Лични данни. Microsoft ще прехвърли такива данни по ваше указание, но вие сте отговорни за това Sendinblue отговаря на всички задължения за поверителност или сигурност, които може да имате. За информация посетете [Декларация за поверителност Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Вашият администратор на Dynamics 365 Customer Insights да премахнете това местоназначение за експортиране по всяко време, за да прекратите използването на тази функционалност.


[!INCLUDE[footer-include](../includes/footer-banner.md)]