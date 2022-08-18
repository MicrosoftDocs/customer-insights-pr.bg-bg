---
title: Обогатяване на клиентските профили с HERE Technologies (предварителен преглед)
description: Обща информация за обогатяването чрез HERE Technologies на трети страни.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 86a070342193dd7afda38823d90f4bd28c8b862e
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: MT
ms.contentlocale: bg-BG
ms.lasthandoff: 08/08/2022
ms.locfileid: "9237845"
---
# <a name="enrich-customer-profiles-with-here-technologies-preview"></a>Обогатяване на клиентските профили с HERE Technologies (предварителен преглед)

HERE Technologies е компания за платформи за местоположение, която предоставя данни и услуги, ориентирани към местоположението. Услугите за обогатяване на данни на HERE Technologies подобряват прецизността на информацията за местоположението за вашите клиенти. Той осигурява нормализиране на адресите, извличане на географска ширина и дължина и др.

## <a name="prerequisites"></a>Предварителни изисквания

- Активен абонамент за HERE Technologies. За да получите абонамент, [регистрирайте се тук](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) или [се свържете директно с HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you). [Научете повече за обогатяване на местоположението на HERE Technologies.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- A HERE [връзка](connections.md) е [конфигуриран](#configure-the-connection-for-here-technologies) от администратор.

## <a name="configure-the-connection-for-here-technologies"></a>Конфигуриране на връзката за HERE Technologies

Трябва да сте [администратор](permissions.md#admin) в "Аналитични данни за клиенти" и да имате активен aPI ключ here Technologies.

1. Изберете **Добавяне на връзка** при конфигуриране на обогатяване или отидете **на Администраторски** > **връзки** и изберете **Настройване** на плочката ТУК Технологии.

1. Въведете име за връзката и валиден aPI ключ ЗА ТЕХНОЛОГИИ ТУК.

1. Прегледайте поверителността на [данните и съответствието](connections.md#data-privacy-and-compliance) и изберете **Съгласен** съм.

1. Изберете **Проверка** за проверка на конфигурацията и след това изберете **Запиши**.

   :::image type="content" source="media/enrichment-HERE-connection.png" alt-text="Страница за конфигуриране на връзка на HERE Technologies.":::

## <a name="configure-the-enrichment"></a>Конфигуриране на допълването

1. Отидете в раздела **Данни** > **Допълване** и изберете раздела **Откриване**.

1. Изберете **Обогатяване на данните ми** за плочката **Местоположение** от HERE Technologies.

   :::image type="content" source="media/HERE-tile.png" alt-text="Плочка на HERE Technologies.":::

1. Прегледайте обзора и след това изберете **Напред**.

1. Изберете връзката. Свържете се с администратор, ако няма налична връзка.

1. Изберете **Напред**.

1. Изберете набора **от данни на** Клиента и изберете профила или сегмента, който искате да обогатите с данни от HERE Technologies. Обектът *"Клиент* " обогатява всичките Ви профили на клиенти, докато даден сегмент обогатява само профилите на клиентите, съдържащи се в този сегмент.

1. Дефинирайте кой тип полета от вашите единни профили да използвате за съвпадение: основния и/или вторичния адрес. Можете да посочите съпоставяне на поле за двата адреса и да допълните профилите за двата адреса поотделно. Например за домашен адрес и бизнес адрес. Изберете **Напред**.

1. Нанесете полетата си към данните от HERE Technologies. Полетата **Улица 1** и **Пощенски код** са задължителни за избрания основен и/или вторичен адрес. За по-висока точност на съвпадение добавете още полета.

1. Изберете **Напред**, за да завършите съпоставянето на полета.

1. Предоставете **Име** за обогатяването и името **на** обекта "Изход".

1. Изберете **Записване на допълването**, след като прегледате избора си.

1. Изберете **Изпълнение**, за да стартирате процеса на обогатяване или близо, за да се върнете към **страницата "Обогатявания** ".

## <a name="view-enrichment-results"></a>Преглед на резултатите от обогатяването

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

**Броят на клиентите, обогатени по поле**, осигурява пробиване в покритието на всяко обогатено поле.

## <a name="next-steps"></a>Следващи стъпки

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
