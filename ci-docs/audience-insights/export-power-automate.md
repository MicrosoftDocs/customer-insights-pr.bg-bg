---
title: Конектор на Power Automate | Microsoft Docs
description: Създавайте потоци в Microsoft Power Automate от Dynamics 365 Customer Insights.
ms.date: 08/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: ffe92414365b0b777691a4a2d585100e4fbea591
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405066"
---
# <a name="power-automate-connector-preview"></a>Конектор на Power Automate (преглед)

Активирайте определени събития да възникват автоматично при промяна на данните и управлявайте по-сложни потоци директно в [Power Automate](https://flow.microsoft.com/).

## <a name="power-automate-triggers"></a>Активатори на Power Automate

Можете да използвате различни активатори, които ви позволяват да създавате потоци, за да автоматизирате повтарящи се задачи, като например известия или по-разширени действия. 

- Задейства се при неуспешно обновяване на източник на данни. 
- Задейства се при успешно обновяване на източник на данни.
- Задейства се при преминаване на праг в сегмент. Активаторът е ограничен до преминаване над прага.
- Задейства се при преминаване на праг в бизнес метрика. Активаторът е ограничен до преминаване над прага.
- Задействайте, когато завърши пълно опресняване на (източници на данни, сегменти, мерки, ...).
- Задейства се, когато завърши опресняване на процеса на обединяване (карта, съвпадение, сливане).

[Конфигурирайте вашите активатори в Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).

## <a name="power-automate-actions"></a>Действия на Power Automate
Конекторът на Power Automate осигурява други действия освен наличните активатори. За повече информация моля вижте [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).

## <a name="create-a-power-automate-flow-in-audience-insights"></a>Създаване на поток на Power Automate в Аналитични данни за аудитория

1. В Аналитични данни за аудитория отидете на **Администратор** > **Система**.

1. В страницата **Система** изберете раздела **Състояние**.

1. В секцията **Източници на данни** изберете **Потоци** и изберете **Създаване на поток** от падащия списък.
   > [!div class="mx-imgBorder"]
   > ![Конектор на Power Automate, който показва действие за създаване на поток](media/power-automate-connector-create-flow.png "Конектор на Power Automate, който показва действие за създаване на поток")

1. В Power Automate изберете един от наличните активатори, за да създадете предпочитания поток. Ако създавате първия си поток, първо ви е нужно удостоверяване с конектора на Power Automate.
