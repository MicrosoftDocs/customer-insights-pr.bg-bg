---
title: Схема на обекти на Customer Insights в Common Data Model
description: Работа с обекти в Common Data Model.
ms.date: 08/13/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 2cdbe11a1c0cc5d65434fb2ae3a3f38c18f31cf4
ms.sourcegitcommit: 3807202283dd116a30f900a163d8141db621e5a8
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 01/28/2022
ms.locfileid: "8046478"
---
# <a name="entity-schemas-in-common-data-model"></a>Схеми на обекти в Common Data Model



[Common Data Model](/common-data-model/) е декларативна спецификация и дефиниция на стандартни обекти, които представляват често използвани понятия и дейности в бизнеса и приложенията за производителност. Този модел се разширява и до данни за наблюдение и аналитични данни. Common Data Model предоставя добре дефинирани, модулни и разширяващи се бизнес обекти - като акаунт, бизнес единица, случай, контакт, потенциален клиент, възможност и продукт, както и взаимодействия с доставчици, работници и клиенти, като дейности и услуги споразумения на ниво. Всеки може да надгради и разшири дефинициите на Common Data Model, за да улови допълнителни идеи, специфични за бизнеса.

Това е споделен модел на данни, който позволява на приложенията и интеграторите на данни да си сътрудничат по-лесно, като предоставя унифицирано определение на данните. Общият модел на данни включва богата система от метаданни със стандартни обекти, релации, йерархии, черти и други. Произхожда от приложенията на Dynamics 365 и е с отворен достъп до GitHub с над 260 стандартни обекта. Голяма система от вътрешни и външни партньори допринасят със специфични за индустрията концепции към Common Data Model.

Множество системи и платформи прилагат Common Data Model днес, включително потоците от данни на Power BI и услугите за данни на Azure. Вече се поддържа в Microsoft Dataverse, Dynamics 365, Power Apps, Power BI и предстоящите услуги за данни на Azure, като пряко добавя стойност към [инициативата за отворени данни](https://www.microsoft.com/open-data-initiative).

## <a name="customer-insights-entity-schemas"></a>Схеми на обекти на Customer Insights

За да установим 360-градусов изглед на клиента и да направим достъпни модели на Customer Insights в Common Data Model за разширяемост, публикувахме следните схеми на субектите:

| Обект | Описание |
|---------|---------|
|[CustomerActivity](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customeractivity) | Дейност, извършвана от потребител, която има наблюдателна стойност за бизнеса. |
|[CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile) | Лице или организация, които са извършвали или имат потенциал да се занимават с бизнес дейности. |
|[MeasureDefinition](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/measuredefinition) | Дефиниция на KPI, разделена на нула или повече измерения (например активни потребители на месец, обща изразходвана сума по клиент, средна цена на придобиване на клиента) |
|[Сегмент](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segment) | Определя група членове с общи черти. |
|[SegmentMembership](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segmentmembership) | Членове, участващи в даден сегмент. |

За повече информация вижте документацията за [Схеми на обекти на Customer Insights в Common Data Model](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/overview).

## <a name="view-entities-using-the-common-data-model-entity-navigator"></a>Преглед на обекти, които използват навигатора на обекти на Common Data Model

Можете да видите обекти в [Навигатор на обекти на Common Data Model](https://microsoft.github.io/CDM/). Изберете обект от секцията на приложението Insights, за да получите списъка с обекти на Customer Insights и техните определения.
> [!div class="mx-imgBorder"]
> ![Навигатор на обект на CDM, който показва обекта CustomerActivity.](media/CDM-entity-navigator.png "Навигатор на обект на CDM, който показва обекта CustomerActivity")


[!INCLUDE[footer-include](../includes/footer-banner.md)]
