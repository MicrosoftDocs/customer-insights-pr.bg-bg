---
title: Обогатяване с помощта на HERE Technologies за обогатяване от трети страни
description: Обща информация за обогатяването чрез HERE Technologies на трети страни.
ms.date: 12/10/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 8e8d6bfea4e0df54682501f60759c24c893444af
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597728"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a>Обогатяване на потребителски профили с HERE Technologies (преглед)

HERE Technologies е компания за платформи за местоположение, която предоставя данни и услуги, ориентирани към местоположението. С услугите за обогатяване на данни от HERE Technologies можете да изградите по-точно разбиране на местоположението на вашите клиенти с нормализиране на адреса, извличане на географска ширина и дължина и др.

## <a name="prerequisites"></a>Предварителни изисквания

За да конфигурирате обогатявания на HERE Technologies, трябва да са изпълнени следните предпоставки:

- Трябва да имате активен абонамент за HERE Technologies. За да получите абонамент, можете да се [регистрирайте се тук](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) или [да се свържете с HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) директно. [Научете повече за обогатяване на местоположението на HERE Technologies.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- Имате ключа за API на HERE Technologies.

- Имате разрешения за [Администратор](permissions.md#administrator).

## <a name="configuration"></a>Конфигурация

1. Отидете в **Данни** > **Допълване**.

1. Изберете **Обогати данните ми** в плочката на HERE Technologies.

   > [!div class="mx-imgBorder"]
   > ![Плочка на HERE Technologies](media/HERE-tile.png "Плочка на HERE Technologies")

1. Въведете активен **API ключ на HERE Technologies**. Прегледайте и дайте своето съгласие за **Поверителност и съответствие на данните**, като изберете отметката **Приемам**. 

1. Потвърдете и двата входа, като изберете **Свързване с HERE**.

1.  Изберете **Добавяне на данни** и изберете **набора от данни на клиент**, който искате да обогатите с данни за местоположение от HERE Technologies. Можете да изберете **Клиент** обект, за да обогатите всичките си клиентски профили или да изберете сегментен обект, за да обогатите само клиентски профили, съдържащи се в този сегмент.

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Снимка на екрана при избора на набор от данни за клиенти.":::

1. Изберете дали искате да присвоите полета на основния и/или вторичния адрес. Можете да посочите картографиране на полета и за двата адреса (например домашен и бизнес адрес) и да обогатите профилите и за двата адреса поотделно. Изберете **Напред**.

1. Определете кои полета от унифицираните ви профили трябва да се използват за търсене на съвпадащи данни за местоположението от HERE Technologies. Полетата **Улица 1** и **Пощенски код** са задължителни за избрания основен и/или вторичен адрес. За по-висока точност на съвпадението могат да се добавят повече полета.

   > [!div class="mx-imgBorder"]
   > ![Страница за конфигуриране на обогатяване на HERE Technologies](media/enrichment-HERE-configuration.png "Страница за конфигуриране на обогатяване на HERE Technologies")

1. Изберете **Приложи**, за да завършите нанасянето на полето.

## <a name="enrichment-results"></a>Резултати от допълването

За да започнете процеса на допълване, изберете **Стартиране** от командната лента. Можете също така да оставите системата да стартира допълването автоматично като част от [планирано обновяване](system.md#schedule-tab). Времето за обработка ще зависи от размера на вашите клиентски данни и времето за реакция на API от HERE Technologies.

След като процесът на допълване завърши, можете да прегледате току-що допълнените данни за потребителски профили в **Моите допълвания**. Освен това ще намерите часа на последната актуализация и броя на допълнените профили.

Можете да получите достъп до подробен изглед на всеки допълнен профил, като изберете **Преглед на допълнените данни**.

## <a name="next-steps"></a>Следващи стъпки

Надградете допълнените клиентски данни. Създайте [сегменти](segments.md), [мерки](measures.md) и дори [експортирайте данните](export-destinations.md), за да доставите персонализирано изживяване на клиентите си.

## <a name="data-privacy-and-compliance"></a>Поверителност и съответствие на данните

Когато активирате Dynamics 365 Customer Insights, за да предавате данни на HERE Technologies, разрешавате прехвърляне на данни извън границата за съответствие за Dynamics 365 Customer Insights, включително потенциално чувствителни данни като Лични данни. Microsoft ще прехвърли такива данни по ваше указание, но вие носите отговорност да гарантирате, че HERE Technologies отговаря на всички задължения за поверителност или сигурност, които може да имате. За информация посетете [Декларация за поверителност Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Вашият администратор на Dynamics 365 Customer Insights да премахнете това обогатяване по всяко време, за да прекратите използването на тази функционалност.


[!INCLUDE[footer-include](../includes/footer-banner.md)]