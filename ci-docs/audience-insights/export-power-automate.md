---
title: Конектор на Power Automate | Microsoft Docs
description: Създавайте потоци я Microsoft Power Automate от Dynamics 365 Customer Insights.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: dd90ef4576246b49d4a9c74005196ee9813a6744
ms.sourcegitcommit: d168a738a08adb8b4b2e410bdaa3716d7b63cc9b
ms.translationtype: MT
ms.contentlocale: bg-BG
ms.lasthandoff: 03/17/2022
ms.locfileid: "8455894"
---
# <a name="power-automate-connector-preview"></a>Конектор на Power Automate (преглед)

Активирайте определени събития да възникват автоматично при промяна на данните и управлявайте по-сложни потоци директно в [Power Automate](https://flow.microsoft.com/).

## <a name="known-limitations"></a>Известни ограничения

- Можете да направите максимум 100 обаждания на 60 секунди. Можете да се обадите на API крайна точка няколко пъти с помощта на параметъра $skip. [Научете повече за параметъра $skip](/connectors/customerinsights/#get-items-from-an-entity).

## <a name="power-automate-triggers"></a>Активатори на Power Automate

Използвайте тригери за създаване на облачни потоци и автоматизиране на повтарящи се задачи, като известия или по-разширени действия. 

- Задейства се при неуспешно обновяване на източник на данни. 
- Задейства се при успешно обновяване на източник на данни.
- Задейства се при преминаване на праг в сегмент. Активаторът е ограничен до преминаване над прага.
- Задейства се при преминаване на праг в бизнес метрика. Поддържат се само бизнес мерки без измерение. Активаторът е ограничен до преминаване над прага.
- Задействайте, когато завърши пълно опресняване на (източници на данни, сегменти, мерки, ...).
- Задейства се, когато завърши опресняване на процеса на обединяване (карта, съвпадение, сливане).

[Конфигурирайте вашите активатори в Power Automate.](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a>Действия на Power Automate

Конекторът на Power Automate осигурява други действия освен наличните активатори. За повече информация моля вижте [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>Създаване на поток на Power Automate

1. В статията за аудиторията отидете на **Администратор** > **Експортиране на местоположения**.

1. В плочката **Power Automate**, изберете **Настройка**.

1. Конекторът на Customer Insights (преглед) в Power Automate се отваря. **Влезте** в Power Automate.

1. Изберете един от наличните задействания и добавете още стъпки към новия си поток. За повече информация вижте [Създаване на поток за облак в Power Automate](/power-automate/get-started-logic-flow).

Примери за използване на потоци: 
- Публикувайте съобщение до канал на Microsoft Teams, ако източник на данни опресняването не успее. 
- Изпратете имейл до собствениците на данни, когато е превишен праг за сегмент.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
