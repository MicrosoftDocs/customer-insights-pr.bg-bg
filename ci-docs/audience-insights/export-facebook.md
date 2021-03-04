---
title: Експортирайте данните от Customer Insights в Facebook Ads Manager
description: Научете как да конфигурирате връзката към Facebook Ads Manager.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c839f9dc7e403412c0e3d936392d45a43bc63545
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269961"
---
# <a name="connector-for-facebook-ads-manager-preview"></a>Конектор за Facebook Ads Manager (преглед)

Експортирайте сегменти от унифицирани потребителски профили във Facebook Ads Manager за създаване на кампании във Facebook и Instagram.

## <a name="prerequisites"></a>Предварителни изисквания

- Трябва да имате [**акаунт във Facebook Ad**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account), който включва [**акаунт във Facebook Business**](https://business.facebook.com/).
- Трябва да сте администратор на [**акаунта във Facebook Ad**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).

## <a name="connect-to-facebook-ads-manager"></a>Свързване към Facebook Ads Manager

1. Отидете на **Администратор** > **Експортиране на дестинации**.

1. Под **Facebook Ads Manager** изберете **Настройване**.

1. Въведете разпознаваемо име за местоназначението за експортиране в полето **Показвано име**.

1. Изберете **Продължаване с Facebook**, за да влезете във вашия акаунт във Facebook Ad.

1. Позволете разрешението **ads_management** след удостоверяване с Facebook.

1. Изберете **Акаунт във Facebook**, с който искате да работите.

1. Изберете **Съществуваща потребителска аудитория** от падащия списък или създайте **Нова потребителска аудитория**. За повече информация вижте [**Аудитории във Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).

1. Изберете **Приемам**, за да потвърдите **Поверителност на данните и съответствие**.

1. Изберете **Напред**, за да конфигурирате експортирането.

## <a name="configure-the-connector"></a>Конфигуриране на конектор

1. В **Избор на основно поле за идентификатор** изберете **Имейл**, **Име и адрес** или **Телефон** за изпращане до Facebook Ads Manager.

1. Нанесете съответните атрибути от обединения клиент за избрания идентификатор на ключ.
   > [СЪВЕТ] Най-добрите шансове за съвпадение се появяват, ако изберете **Имейл** като основен идентификатор. Добавянето на допълнителни идентификатори може да подобри съвпадението.

1. Изберете **Добавяне на атрибут**, за да съпоставите допълнителни атрибути, които да изпратите на Facebook Ads Manager. Атрибути от Facebook Ads Manager се съпоставят със следните лесни за разбиране имена: **FN** = **Собствено име**, **LN** = **Фамилно име**, **FI** = **Първи инициал**, **PHONE** = **Телефон**, **GEN** = **Пол**, **DOB** = **Дата на раждане**, **ST** = **Състояние**, **CT** = **Град**, **ZIP** = **Пощенски код**, **COUNTRY** = **Държава/регион**

1. Изберете сегментите, които искате да експортирате.

1. Изберете **Записване**.

## <a name="export-the-data"></a>Експортиране на данните

Можете да [експортирате данни при поискване](export-destinations.md). Експортирането също ще се изпълнява с всяко [планирано обновяване](system.md#schedule-tab).

## <a name="known-limitations"></a>Известни ограничения

- До 10 милиона клиентски профила на експортиране към Facebook Ads Manager 
- Експортирането в Facebook Ads Manager е ограничено до сегменти
- Експортирането на сегменти с общо 10 милион профила може да отнеме до 90 минути

## <a name="data-privacy-and-compliance"></a>Поверителност и съответствие на данните

Когато активирате Dynamics 365 Customer Insights, за да предавате данни на Facebook Ads Manager, разрешавате прехвърляне на данни извън границата за съответствие за Dynamics 365 Customer Insights, включително потенциално чувствителни данни като Лични данни. Microsoft ще прехвърли такива данни по ваше указание, но вие носите отговорност да гарантирате, че Facebook Ads отговаря на всички задължения за поверителност или сигурност, които може да имате. За информация посетете [Декларация за поверителност Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Вашият администратор на Dynamics 365 Customer Insights да премахнете това местоназначение за експортиране по всяко време, за да прекратите използването на тази функционалност.


[!INCLUDE[footer-include](../includes/footer-banner.md)]