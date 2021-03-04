---
title: Конектор на Power Automate | Microsoft Docs
description: Създавайте потоци в Microsoft Power Automate от Dynamics 365 Customer Insights.
ms.date: 01/20/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: fb1df4e9ab1f78300b8ec1f8dfdfbfbac0e71447
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268811"
---
# <a name="power-automate-connector-preview"></a>Конектор на Power Automate (преглед)

Активирайте определени събития да възникват автоматично при промяна на данните и управлявайте по-сложни потоци директно в [Power Automate](https://flow.microsoft.com/).

## <a name="power-automate-triggers"></a>Активатори на Power Automate

Използвайте тригери за създаване на облачни потоци и автоматизиране на повтарящи се задачи, като известия или по-разширени действия. 

- Задейства се при неуспешно обновяване на източник на данни. 
- Задейства се при успешно обновяване на източник на данни.
- Задейства се при преминаване на праг в сегмент. Активаторът е ограничен до преминаване над прага.
- Задейства се при преминаване на праг в бизнес метрика. Активаторът е ограничен до преминаване над прага.
- Задействайте, когато завърши пълно опресняване на (източници на данни, сегменти, мерки, ...).
- Задейства се, когато завърши опресняване на процеса на обединяване (карта, съвпадение, сливане).

[Конфигурирайте вашите активатори в Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).

## <a name="power-automate-actions"></a>Действия на Power Automate
Конекторът на Power Automate осигурява други действия освен наличните активатори. За повече информация моля вижте [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>Създаване на поток на Power Automate

1. В статията за аудиторията отидете на **Администратор** > **Експортиране на местоположения**.

1. В плочката **Power Automate**, изберете **Настройка**.

1. Конекторът на Customer Insights (преглед) в Power Automate се отваря. **Влезте** в Power Automate.

1. Изберете един от наличните задействания и добавете още стъпки към новия си поток. За повече информация вижте [Създаване на поток за облак в Power Automate](https://docs.microsoft.com/power-automate/get-started-logic-flow).

Примери за използване на потоци: 
- Публикувайте съобщение до канал на Microsoft Teams, ако източник на данни опресняването не успее. 
- Изпратете имейл до собствениците на данни, когато е превишен праг за сегмент.



[!INCLUDE[footer-include](../includes/footer-banner.md)]