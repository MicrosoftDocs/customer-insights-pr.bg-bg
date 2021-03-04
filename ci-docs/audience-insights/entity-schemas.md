---
title: Схема на обекти на Customer Insights в Common Data Model
description: Работа с обекти в Common Data Model.
ms.date: 04/17/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 9e7a6e944d37d25f4c25846644278b39b3ddd08e
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269271"
---
# <a name="entity-schemas-in-common-data-model"></a>Схеми на обекти в Common Data Model

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

[Common Data Model](https://docs.microsoft.com/common-data-model/) е декларативна спецификация и дефиниция на стандартни обекти, които представляват често използвани понятия и дейности в бизнеса и приложенията за производителност. Този модел се разширява и до данни за наблюдение и аналитични данни. Common Data Model предоставя добре дефинирани, модулни и разширяващи се бизнес обекти - като акаунт, бизнес единица, случай, контакт, потенциален клиент, възможност и продукт, както и взаимодействия с доставчици, работници и клиенти, като дейности и услуги споразумения на ниво. Всеки може да надгради и разшири дефинициите на Common Data Model, за да улови допълнителни идеи, специфични за бизнеса.

Това е споделен модел на данни, който позволява на приложенията и интеграторите на данни да си сътрудничат по-лесно, като предоставя унифицирано определение на данните. Общият модел на данни включва богата система от метаданни със стандартни обекти, релации, йерархии, черти и други. Произхожда от приложенията на Dynamics 365 и е с отворен достъп до GitHub с над 260 стандартни обекта. Голяма система от вътрешни и външни партньори допринасят със специфични за индустрията концепции към Common Data Model.

Множество системи и платформи прилагат Common Data Model днес, включително Power BI потоци от данни и услуги за данни на Azure. Вече се поддържа в Common Data Service, Dynamics 365, Power Apps, Power BI и предстоящите услуги за данни на Azure, които директно добавят стойност към [инициативата за отворени данни](https://www.microsoft.com/open-data-initiative).

## <a name="customer-insights-entity-schemas"></a>Схеми на обекти на Customer Insights

За да установим 360-градусов изглед на клиента и да направим достъпни модели на Customer Insights в Common Data Model за разширяемост, публикувахме следните схеми на субектите:

| Обект | Описание |
|---------|---------|
|[CustomerActivity](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customeractivity) | Дейност, извършвана от потребител, която има наблюдателна стойност за бизнеса. |
|[CustomerProfile](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile) | Лице или организация, които са извършвали или имат потенциал да се занимават с бизнес дейности. |
|[MeasureDefinition](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/measuredefinition) | Дефиниция на KPI, разделена на нула или повече измерения (например активни потребители на месец, обща изразходвана сума по клиент, средна цена на придобиване на клиента) |
|[Сегмент](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segment) | Определя група членове с общи черти. |
|[SegmentMembership](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segmentmembership) | Членове, участващи в даден сегмент. |

За повече информация вижте документацията за [Схеми на обекти на Customer Insights в Common Data Model](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/overview).

## <a name="view-entities-using-the-common-data-model-entity-navigator"></a>Преглед на обекти, които използват навигатора на обекти на Common Data Model

Можете да видите обекти в [Навигатор на обекти на Common Data Model](https://microsoft.github.io/CDM/). Изберете бутона **Зареждане от GitHub!** и навигирайте до **foundationCommon** > **crmCommon** > **решения** > **customerInsights**, където ще намерите списък с обектите на Customer Insights и техните дефиниции.
> [!div class="mx-imgBorder"]
> ![Навигатор на обект на CDM, който показва обекта CustomerActivity](media/CDM-entity-navigator.png "Навигатор на обект на CDM, който показва обекта CustomerActivity")


[!INCLUDE[footer-include](../includes/footer-banner.md)]