---
title: Експортирайте данните от Customer Insights в DotDigital
description: Научете как да конфигурирате връзката и да експортирате в DotDigital.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f63a0f5f5f93e96681a88fd758381c012a404f43
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: bg-BG
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642062"
---
# <a name="export-segments-to-dotdigital-preview"></a>Експортиране на сегменти в DotDigital (преглед)

Експортирайте сегменти от унифицирани клиентски профили в адресните книги на DotDigital и ги използвайте за кампании, маркетинг по имейл и за изграждане на клиентски сегменти с DotDigital. 

## <a name="prerequisites-for-a-connection"></a>Предварителни изисквания за връзка

-   Имате [DotDigital акаунт](https://dotdigital.com/) и създавате [Потребител на API](https://support.dotdigital.com/hc/articles/115001718730-How-do-I-create-an-API-user). За да създадете връзка, ще трябва да използвате идентификационните данни на потребителя на API
-   В Google Ads има съществуващи адресни книги в DotDigital и съответните идентификатори. Идентификаторът може да бъде намерен в URL адреса, когато изберете и отворите адресна книга. За повече информация вижте [Адресни книги на DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).
-   Конфигурирали [сте сегменти](segments.md) в "Аналитични данни за клиенти".
-   Единните клиентски профили в експортираните сегменти съдържат поле, представляващо имейл адрес.

## <a name="known-limitations"></a>Известни ограничения

- До 1 милион потребителски профила на износ за DotDigital.
- Експортирането в DotDigital е ограничено до сегменти.
- Експортирането на сегменти с общо 1 милион потребителски профила може да отнеме до 3 часа поради ограничения от страна на доставчика. 
- Броят на потребителските профили, които можете да експортирате в DotDigital, зависи и е ограничен от вашия договор с DotDigital.

## <a name="set-up-connection-to-dotdigital"></a>Настройване на връзка с DotDigital

1. Отидете на **Администратор** > **Връзки**.

1. Изберете **Добавяне на връзка** и изберете **DotDigital** за конфигуриране на връзката.

1. Въведете разпознаваемо име за връзката в полето **Показвано име**. Показваното име и типът описват тази връзка. Препоръчваме да изберете име, което обяснява целта на връзката.

1. Изберете кой може да използва тази връзка. Ако не предприемете нищо, по подразбиране ще е Администратори. За повече информация вижте [Разрешаване на сътрудници да използват връзка за експортиране](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Въведете **потребителско име и парола за DotDigital API**. 

1. Въведете своя **[Идентификатор на адресната книга на DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.

1. Изберете **Приемам**, за да потвърдите **Поверителност на данните и съответствие**.

1. Изберете **Свържете** за инициализиране на връзката с DotDigital.

1. Изберете **Добавете себе си като потребител за експортиране** и предоставете вашите идентификационни данни на Customer Insights.

1. Изберете **Записване**, за да завършите връзката. 

## <a name="configure-an-export"></a>Конфигуриране на експортиране

Можете да конфигурирате това експортиране, ако имате достъп до връзка от този тип. За повече информация вижте [Разрешения, необходими за конфигуриране на експортиране](export-destinations.md#set-up-a-new-export).

1. Отидете на **Данни** > **Експортиране**.

1. За да създадете ново експортиране, изберете **Добавяне на местоназначение**.

1. В полето **Връзка за експортиране** изберете връзка от секцията DotDigital. Ако не виждате името на тази секция, няма достъпни за вас връзки от този тип.


1. В **Съвпадение на данните** раздел, в **Имейл** поле, изберете полето, което представлява имейл адреса на клиента. Повторете същите стъпки за други незадължителни полета, като например **собствено име**, **фамилно име**, **Пълно име**, **Пол** и **Пощенски код**.

1. Изберете сегментите, които искате да експортирате. Можете да експортирате до 1 милион потребителски профила общо в DotDigital.

1. Изберете **Записване**.

Запазването на експортиране не го изпълнява незабавно.

Експортирането се изпълнява с всяко [планирано обновяване](system.md#schedule-tab). Може също [да експортирате данни при поискване](export-destinations.md#run-exports-on-demand). 
 
В DotDigital вече можете да намерите своите сегменти в [адресни книги в DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).


## <a name="data-privacy-and-compliance"></a>Поверителност и съответствие на данните

Когато активирате Dynamics 365 Customer Insights, за да предавате данни на DotDigital, разрешавате прехвърляне на данни извън границата за съответствие за Dynamics 365 Customer Insights, включително потенциално чувствителни данни като Лични данни. Microsoft ще прехвърли такива данни по ваше указание, но вие носите отговорност да гарантирате, че DotDigital отговаря на всички задължения за поверителност или сигурност, които може да имате. За информация посетете [Декларация за поверителност Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Вашият администратор на Dynamics 365 Customer Insights да премахнете това местоназначение за експортиране по всяко време, за да прекратите използването на тази функционалност.


[!INCLUDE [footer-include](includes/footer-banner.md)]