---
title: Експортирайте данните от Customer Insights в Google Ads
description: Научете как да конфигурирате връзката с Google Ads.
ms.date: 11/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ba7c82e643ea0dc1897e0954e78646932cafffa3
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268949"
---
# <a name="connector-for-google-ads-preview"></a>Конектор за Google Ads (преглед)

Експортирайте сегменти на унифицирани клиентски профили в списъци с аудитории на Google Ads и ги използвайте за рекламиране в Google Search, Gmail, YouTube и Google Display Network. 

## <a name="prerequisites"></a>Предварителни изисквания

-   Имате [Акаунт в Google Ads](https://ads.google.com/) и съответните идентификационни данни на администратора.
-   В Google Ads има съществуващи аудитории и съответните идентификатори. За повече информация вижте [аудитории на Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).
-   Имате [конфигурирани сегменти](segments.md)
-   Единните клиентски профили в експортираните сегменти съдържат полета, представляващи имейл адрес, собствено име и фамилно име

## <a name="connect-to-google-ads"></a>Свързване с Google Ads

1. Отидете на **Администратор** > **Експортиране на дестинации**.

1. Под **Google Ads** изберете **Настройка**.

1. Въведете разпознаваемо име за местоназначението за експортиране в полето **Показвано име**.

1. Въведете своя **[ИД на клиента в Google Ads](https://support.google.com/google-ads/answer/1704344)**.

1. Въведете своя **[Одобрен от Google Ads маркер за програмисти](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.

1. Изберете **Приемам**, за да потвърдите **Поверителност на данните и съответствие**.

1. Въведете своя **[ИД на аудиторията на Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** и изберете **Свързване** за инициализиране на връзката с Google Ads.

1. Изберете **Удостоверете с Google Ads** и предоставете вашите идентификационни данни на Google Ads.

1. Изберете **Добавете себе си като потребител за експортиране** и предоставете вашите идентификационни данни на Customer Insights.

   :::image type="content" source="media/export-segments-googleads.PNG" alt-text="Експортиране на екранна снимка за връзка с Google Ads":::

1. Изберете **Напред**, за да конфигурирате експортирането.

## <a name="configure-the-connector"></a>Конфигуриране на конектор

1. В секцията **Съвпадение на данни** в полето **Имейл** изберете полето във вашия унифициран потребителски профил, което представлява имейл адреса на клиента. Повторете същите стъпки за полетата **Собствено име** и **фамилно име**.

1. Изберете сегментите, които искате да експортирате. Можете да експортирате до 1 милион потребителски профила общо в Google Ads.

1. Изберете **Записване**.

## <a name="export-the-data"></a>Експортиране на данните

Можете да [експортирате данни при поискване](export-destinations.md). Експортирането също ще се изпълнява с всяко [планирано обновяване](system.md#schedule-tab). В Google Ads вече можете да намерите своите сегменти под [Аудитории на Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en/).

## <a name="known-limitations"></a>Известни ограничения

- До 1 милион профила на износ към Google Ads.
- Експортирането в Google Ads е ограничено до сегменти.
- Експортирането на сегменти с общо 1 милион профила може да отнеме до 5 минути поради ограничения от страна на доставчика. 
- Съответствието в Google Ads може да отнеме до 48 часа.

## <a name="data-privacy-and-compliance"></a>Поверителност и съответствие на данните

Когато активирате Dynamics 365 Customer Insights, за да предавате данни на Google Ads, разрешавате прехвърляне на данни извън границата за съответствие за Dynamics 365 Customer Insights, включително потенциално чувствителни данни като Лични данни. Microsoft ще прехвърли такива данни по ваше указание, но вие носите отговорност да гарантирате, че Google Ads отговаря на всички задължения за поверителност или сигурност, които може да имате. За информация посетете [Декларация за поверителност Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Вашият администратор на Dynamics 365 Customer Insights да премахнете това местоназначение за експортиране по всяко време, за да прекратите използването на тази функционалност.


[!INCLUDE[footer-include](../includes/footer-banner.md)]