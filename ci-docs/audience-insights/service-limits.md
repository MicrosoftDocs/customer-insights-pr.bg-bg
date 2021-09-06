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
ms.openlocfilehash: 2966f2ede1ddbe0245471771365cbf5b593be608764aa10ed28d962c52bb8067
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034851"
---
# <a name="service-limits-in-dynamics-365-customer-insights-audience-insights-capability"></a>Ограничения на услугата в Аналитични данни за аудитория на Dynamics 365 Customer Insights

Тази статия описва вградените ограничения на услугата Customer Insights, които са предназначени да гарантират надеждността и стабилността на услугата. Всички искания за промени могат да бъдат направени чрез [форума за идеи](https://go.microsoft.com/fwlink/?linkid=2074172). 
 
| Област  | Ограничения  | Бележки |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Сегменти и мерки | 100 сегмента или мерки. | Общият брой на активните [сегменти](segments.md) и [мерки](measures.md) комбинирано не може да надвишава 100.  |
| Релации | 20 нива на дълбочина на релации в пътищата на обекти. | При създаването на [сегменти](segments.md) или [мерки](measures.md) с помощта на интерфейса на конструктора пътищата на обектите могат да имат до 20 прехода на релации между началния обект и целевия обект.  |


[!INCLUDE[footer-include](../includes/footer-banner.md)]