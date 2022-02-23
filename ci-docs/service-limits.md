---
title: Ограничения на услугите в Dynamics 365 Customer Insights
description: Разберете ограниченията и ограниченията.
ms.date: 09/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: eb25e050b8aa768e6e1d8d4c5adce6095cccc346
ms.sourcegitcommit: 31a9b531dacd3a6465b3030c704ff5c085b7e122
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 11/10/2021
ms.locfileid: "7815891"
---
# <a name="service-limits-in-customer-insights-capabilities"></a>Ограничения за услуги във възможностите на Customer Insights

Тази статия описва вградените ограничения на услугата Customer Insights, които са предназначени да гарантират надеждността и стабилността на услугата. Всички искания за промени могат да бъдат направени чрез [форума за идеи](https://go.microsoft.com/fwlink/?linkid=2074172). 

## <a name="audience-insights"></a>Аналитични данни за аудиторията

### <a name="service-limits-in-dynamics-365-customer-insights-audience-insights-capability"></a>Ограничения на услугата в Dynamics 365 Customer Insights възможност за прозрения на аудиторията

| Област  | Ограничения  | Бележки |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Сегменти, мерки и прогнози | 300  | Общият брой на [сегментите](audience-insights/segments.md), [мерките и](audience-insights/measures.md)[прогнозите](audience-insights/predictions.md), комбинирани, не може да надвишава 300.  |
| Взаимоотношения | 20 нива на дълбочина на релации в пътищата на обекти. | При създаването на [сегменти](audience-insights/segments.md) или [мерки](audience-insights/measures.md) с помощта на интерфейса на конструктора пътищата на обектите могат да имат до 20 прехода на релации между началния обект и целевия обект.  |


## <a name="engagement-insights"></a>Аналитични данни за ангажираност

### <a name="workspace-and-event-quotas"></a>Работно пространство и квоти за събития

Статистика за ангажираността е силно мащабируемо приложение, което може да поддържа милиони събития в секунда. По време на публичен визуализация събитията имат праг на силата на звука. Има и ограничение за броя на работните пространства в организацията.

### <a name="engagement-insights-limits"></a>Ограничения на Аналитични данни за ангажираността

- Максимален обем на събитие на работно пространство = 100 събития в секунда

- Максимален брой работни пространства на организация = 100

Когато събитията надхвърлят прага, това може да доведе до загуба на данни в отчетите въз основа на тези събития. Можете да се [свържете с поддръжката](https://go.microsoft.com/fwlink/?linkid=2145734) да поискате увеличаване на обема, преди да надвишите лимитите. Ще работим с вас, за да определим вашата нужда от увеличаване на обема и да подкрепим вашата заявка.


[!INCLUDE[footer-include](includes/footer-banner.md)]
