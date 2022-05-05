---
title: Ограничения за обслужване в Dynamics 365 Customer Insights
description: Разберете ограниченията и ограниченията.
ms.date: 09/03/2021
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: e2e7fc3033c25646693831d4c4c800d84ae6d6da
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: bg-BG
ms.lasthandoff: 04/27/2022
ms.locfileid: "8641749"
---
# <a name="service-limits-in-customer-insights"></a>Ограничения на услугата в "Аналитични данни за клиенти"

Тази статия описва вградените ограничения на услугата Customer Insights, които са предназначени да гарантират надеждността и стабилността на услугата. Всички искания за промени могат да бъдат направени чрез [форума за идеи](https://go.microsoft.com/fwlink/?linkid=2074172). 

## <a name="customer-insights"></a>Customer Insights

| Област  | Ограничения  | Бележки |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Сегменти, мерки и прогнози | 300  | Общият брой на [комбинираните сегменти](segments.md)[,](measures.md) мерки и [прогнози](predictions.md) не може да надвишава 300.  |
| Взаимоотношения | 20 нива на дълбочина на релации в пътищата на обекти. | При създаването на [сегменти](segments.md) или [мерки](measures.md) с помощта на интерфейса на конструктора пътищата на обектите могат да имат до 20 прехода на релации между началния обект и целевия обект.  |


[!INCLUDE [footer-include](includes/footer-banner.md)]
