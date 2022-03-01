---
title: Ограничения за обслужване в Dynamics 365 Customer Insights
description: Разберете ограниченията и ограниченията.
ms.date: 09/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: eba7871faf304d5945191b5b9bc215243b4f8a05
ms.sourcegitcommit: 5704002484cdf85ebbcf4e7e4fd12470fd8e259f
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 09/08/2021
ms.locfileid: "7483643"
---
# <a name="service-limits-in-customer-insights-capabilities"></a>Ограничения за услуги във възможностите на Customer Insights

Тази статия описва вградените ограничения на услугата Customer Insights, които са предназначени да гарантират надеждността и стабилността на услугата. Всички искания за промени могат да бъдат направени чрез [форума за идеи](https://go.microsoft.com/fwlink/?linkid=2074172). 

## <a name="audience-insights"></a>Аналитични данни за аудиторията

### <a name="service-limits-in-dynamics-365-customer-insights-audience-insights-capability"></a>Ограничения на услугата в Аналитични данни за аудитория на Dynamics 365 Customer Insights

| Област  | Ограничения  | Бележки |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Сегменти и мерки | 100 сегмента или мерки. | Общият брой на активните [сегменти](audience-insights/segments.md) и [мерки](audience-insights/measures.md) комбинирано не може да надвишава 100.  |
| Релации | 20 нива на дълбочина на релации в пътищата на обекти. | При създаването на [сегменти](audience-insights/segments.md) или [мерки](audience-insights/measures.md) с помощта на интерфейса на конструктора пътищата на обектите могат да имат до 20 прехода на релации между началния обект и целевия обект.  |


## <a name="engagement-insights"></a>Аналитични данни за ангажираност

### <a name="workspace-and-event-quotas"></a>Работно пространство и квоти за събития

Статистика за ангажираността е силно мащабируемо приложение, което може да поддържа милиони събития в секунда. По време на публичен визуализация събитията имат праг на силата на звука. Има и ограничение за броя на работните пространства в организацията.

### <a name="engagement-insights-limits"></a>Ограничения на Аналитични данни за ангажираността

- Максимален обем на събитие на работно пространство = 100 събития в секунда

- Максимален брой работни пространства на организация = 100

Когато събитията надхвърлят прага, това може да доведе до загуба на данни в отчетите въз основа на тези събития. Можете да се [свържете с поддръжката](https://go.microsoft.com/fwlink/?linkid=2145734) да поискате увеличаване на обема, преди да надвишите лимитите. Ще работим с вас, за да определим вашата нужда от увеличаване на обема и да подкрепим вашата заявка.


[!INCLUDE[footer-include](includes/footer-banner.md)]