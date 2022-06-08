---
title: Експортирайте данните от Customer Insights в Google Ads
description: Научете как да конфигурирате връзката и да експортирате в Google Ads.
ms.date: 03/31/2022
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 3e0eb91be97d69a999e90708d29c572f0055527e
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: bg-BG
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642291"
---
# <a name="export-segments-to-google-ads-preview"></a>Експортиране на сегменти в Google Ads (преглед)

Експортирайте сегменти от унифицирани клиентски профили в списък с аудитории на Google Ads и ги използвайте за реклама в Google Търсене, Gmail, YouTube и Google Display Network. 


## <a name="prerequisites-for-connection"></a>Предварителни изисквания за връзка

-   Имате [Акаунт в Google Ads](https://ads.google.com/) и съответните идентификационни данни на администратора.
-   Изпълнявате изискванията на [правилата за съвпадение на клиенти](https://support.google.com/adspolicy/answer/6299717).
-   Изпълнявате изискванията на [размерите на списъка за повторен маркетинг](https://support.google.com/google-ads/answer/7558048).
-   Имате [конфигурирани сегменти](segments.md).
-   Единните профили на клиенти в експортираните сегменти съдържат полета, представляващи имейл адрес, телефон, ИД на мобилен рекламодател, ИД на потребител към трето лице или адрес.

## <a name="known-limitations"></a>Известни ограничения

- Експортирането в Google Ads е ограничено до сегменти.
- Експортирането на сегменти с общо 1 милион потребителски профила може да отнеме до 30 минути поради ограничения от страна на доставчика. 
- Съответствието в Google Ads може да отнеме до 48 часа.

## <a name="set-up-connection-to-google-ads"></a>Настройване на връзка с Google Ads

1. Отидете на **Администратор** > **Връзки**.

1. Изберете **Добавяне на връзка** и изберете **Google Ads** за конфигуриране на връзката.

1. Въведете разпознаваемо име за връзката в полето **Показвано име**. Показваното име и типът описват тази връзка. Препоръчваме да изберете име, което обяснява целта на връзката.

1. Изберете кой може да използва тази връзка. Ако не предприемете нищо, по подразбиране ще е Администратори. За повече информация вижте [Разрешаване на сътрудници да използват връзка за експортиране](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Въведете своя **[ИД на клиента в Google Ads](https://support.google.com/google-ads/answer/1704344)**.

1. Изберете **Приемам**, за да потвърдите **Поверителност на данните и съответствие**.

1. Изберете **Удостоверете с Google Ads** и предоставете вашите идентификационни данни на Google Ads.

1. Изберете **Добавете себе си като потребител за експортиране** и предоставете вашите идентификационни данни на Customer Insights.

1. Изберете **Записване**, за да завършите връзката. 

## <a name="configure-an-export"></a>Конфигуриране на експортиране

Можете да конфигурирате това експортиране, ако имате достъп до връзка от този тип. За повече информация вижте [Разрешения, необходими за конфигуриране на експортиране](export-destinations.md#set-up-a-new-export).

1. Отидете на **Данни** > **Експортиране**.

1. За да създадете ново експортиране, изберете **Добавяне на местоназначение**.

1. В полето **Връзка за експортиране** изберете връзка от секцията Google Ads. Ако не виждате името на този раздел, тогава няма налични връзки от този тип.

1. Ако искате да създадете нова аудитория, оставете полето ИД на Google Аудитория празно. Автоматично ще създадем нова аудитория в профила Ви в Google Ads и ще използваме името на експортирания сегмент. Ако искате да актуализирате съществуваща аудитория в Google Ads, въведете идентификационния си [номер на аудиторията в Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)

1. В секцията Съвпадение на **данни** изберете едно или повече полета с данни, които да експортирате, и изберете полето, което представлява съответните полета с данни в "Статистика за клиенти".

1. Изберете сегментите, които искате да експортирате. 

Запазването на експортиране не го изпълнява незабавно.

Експортирането се изпълнява с всяко [планирано обновяване](system.md#schedule-tab). 

Може също [да експортирате данни при поискване](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Поверителност и съответствие на данните

Когато активирате Dynamics 365 Customer Insights, за да предавате данни на Google Ads, разрешавате прехвърляне на данни извън границата за съответствие за Dynamics 365 Customer Insights, включително потенциално чувствителни данни като Лични данни. Microsoft ще прехвърли такива данни по ваше указание, но вие носите отговорност да гарантирате, че Google Ads отговаря на всички задължения за поверителност или сигурност, които може да имате. За информация посетете [Декларация за поверителност Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Вашият администратор на Dynamics 365 Customer Insights да премахнете това местоназначение за експортиране по всяко време, за да прекратите използването на тази функционалност.


[!INCLUDE [footer-include](includes/footer-banner.md)]