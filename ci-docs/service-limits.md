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
ms.openlocfilehash: 9bf8f03b785fb3035e3fc979a3304d4e98fd8d28
ms.sourcegitcommit: 1946d7af0bd2ca216885bec3c5c95009996d9a28
ms.translationtype: MT
ms.contentlocale: bg-BG
ms.lasthandoff: 02/25/2022
ms.locfileid: "8350394"
---
# <a name="service-limits-in-customer-insights-capabilities"></a>Ограничения за услуги във възможностите на Customer Insights

Тази статия описва вградените ограничения на услугата Customer Insights, които са предназначени да гарантират надеждността и стабилността на услугата. Всички искания за промени могат да бъдат направени чрез [форума за идеи](https://go.microsoft.com/fwlink/?linkid=2074172). 

## <a name="audience-insights"></a>Аналитични данни за аудиторията

| Област  | Ограничения  | Бележки |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Сегменти, мерки и прогнози | 300  | Общият брой на [комбинираните сегменти](audience-insights/segments.md)[,](audience-insights/measures.md) мерки и [прогнози](audience-insights/predictions.md) не може да надвишава 300.  |
| Взаимоотношения | 20 нива на дълбочина на релации в пътищата на обекти. | При създаването на [сегменти](audience-insights/segments.md) или [мерки](audience-insights/measures.md) с помощта на интерфейса на конструктора пътищата на обектите могат да имат до 20 прехода на релации между началния обект и целевия обект.  |

<!--
## Engagement insights

### Workspace and event quotas

Engagement insights is a highly scalable application that can support millions of events per second. During public preview, events have a volume threshold. There's also a limit to the number of workspaces in an organization.

### Engagement insights limits

- Maximum event volume per workspace  = 100 events per second

- Maximum number of workspaces per organization = 100

When events exceed the threshold, it can lead to loss of data in reports based on those events. You can [contact support](https://go.microsoft.com/fwlink/?linkid=2145734) to request a volume increase before you exceed limits. We'll work with you to determine your need for a volume increase and support your request.
-->

[!INCLUDE[footer-include](includes/footer-banner.md)]
