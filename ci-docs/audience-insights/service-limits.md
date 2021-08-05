---
title: Лимити за обслужване
description: Разберете ограниченията и ограниченията.
ms.date: 07/08/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 81253332cbea3110c0b3804db3a4d03b514f92d4
ms.sourcegitcommit: 9a99e48e96dfb3d895db428f37c30ae55eea66b7
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 07/14/2021
ms.locfileid: "6604356"
---
# <a name="service-limits-in-dynamics-365-customer-insights-audience-insights-capability"></a>Ограничения на услугата в Аналитични данни за аудитория на Dynamics 365 Customer Insights

Тази статия описва вградените ограничения на услугата Customer Insights, които са предназначени да гарантират надеждността и стабилността на услугата. Всички искания за промени могат да бъдат направени чрез [форума за идеи](https://go.microsoft.com/fwlink/?linkid=2074172). 
 
| Област  | Ограничения  | Бележки |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Сегменти и мерки | 100 сегмента или мерки. | Общият брой на активните [сегменти](segments.md) и [мерки](measures.md) комбинирано не може да надвишава 100.  |
| Релации | 20 нива на дълбочина на релации в пътищата на обекти. | При създаването на [сегменти](segments.md) или [мерки](measures.md) с помощта на интерфейса на конструктора пътищата на обектите могат да имат до 20 прехода на релации между началния обект и целевия обект.  |


[!INCLUDE[footer-include](../includes/footer-banner.md)]