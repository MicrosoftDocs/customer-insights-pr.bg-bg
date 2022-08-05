---
title: Power Automate конектор (предварителен преглед) | Документи на Microsoft
description: Създавайте потоци я Microsoft Power Automate от Dynamics 365 Customer Insights.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f87bd6db7143294a264813f6c5c7d7963f303628
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: bg-BG
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196105"
---
# <a name="power-automate-connector-preview"></a>Конектор на Power Automate (преглед)

Активирайте определени събития да възникват автоматично при промяна на данните и управлявайте по-сложни потоци директно в [Microsoft Power Automate](https://flow.microsoft.com/).

## <a name="known-limitations"></a>Известни ограничения

- Максимум 100 обаждания на 60 секунди. Използвайте [параметъра](/connectors/customerinsights/#get-items-from-an-entity) $skip, за да извикате API крайна точка няколко пъти.

## <a name="power-automate-triggers"></a>Активатори на Power Automate

Използвайте тригери за създаване на облачни потоци и автоматизиране на повтарящи се задачи, като известия или по-разширени действия. Използвайте тригери, когато:

- Неуспешна източник на данни обновяване.
- Опресняването на източник на данни успява.
- На сегмент се пресича праг. Активаторът е ограничен до преминаване над прага.
- Праг се пресича по бизнес мярка. Поддържат се само бизнес мерки без измерение. Активаторът е ограничен до преминаване над прага.
- Завърши пълно планирано обновяване. Този спусък не работи за ръчно стартирани опресняване.
- Обновяване на процеса на обединение е завършено.

[Конфигурирайте вашите активатори в Power Automate.](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a>Действия на Power Automate

Конекторът на Power Automate осигурява други действия освен наличните активатори. За повече информация моля вижте [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>Създаване на поток на Power Automate

1. Отидете на **Администратор** > **Връзки**.

1. В плочката **Power Automate**, изберете **Настройка**.

1. Конекторът на Customer Insights (преглед) в Power Automate се отваря. **Влезте** в Power Automate.

1. Изберете един от наличните задействания и добавете още стъпки към новия си поток. За повече информация вижте [Създаване на поток за облак в Power Automate](/power-automate/get-started-logic-flow).

Примери за използване на потоци: 
- Публикувайте съобщение до канал на Microsoft Teams, ако източник на данни опресняването не успее. 
- Изпратете имейл до собствениците на данни, когато е превишен праг за сегмент.

[!INCLUDE [footer-include](includes/footer-banner.md)]
