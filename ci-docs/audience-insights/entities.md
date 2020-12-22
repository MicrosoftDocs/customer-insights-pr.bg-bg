---
title: Обекти и набори от данни
description: Преглед на данните на страницата „Обекти“.
ms.date: 04/16/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: e3f41c0424b2cd756d72ae6af9d5225ebba92628
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405077"
---
# <a name="entities-in-audience-insights"></a><span data-ttu-id="b0cbb-103">Обекти в Аналитични данни за аудитория</span><span class="sxs-lookup"><span data-stu-id="b0cbb-103">Entities in audience insights</span></span>

<span data-ttu-id="b0cbb-104">След [конфигуриране на източниците на данни](data-sources.md) отидете в страницата **Обекти**, за да оцените качеството на приетите данни.</span><span class="sxs-lookup"><span data-stu-id="b0cbb-104">After [configuring your data sources](data-sources.md), go to the **Entities** page to evaluate the quality of the ingested data.</span></span> <span data-ttu-id="b0cbb-105">Обектите се считат за набори от данни.</span><span class="sxs-lookup"><span data-stu-id="b0cbb-105">Entities are considered datasets.</span></span> <span data-ttu-id="b0cbb-106">Множество възможности на Dynamics 365 Customer Insights са изградени около тези обекти.</span><span class="sxs-lookup"><span data-stu-id="b0cbb-106">Multiple capabilities of Dynamics 365 Customer Insights are built around these entities.</span></span> <span data-ttu-id="b0cbb-107">Внимателният преглед може да помогне да потвърдите производителността на тези възможности.</span><span class="sxs-lookup"><span data-stu-id="b0cbb-107">Reviewing them closely can help you validate the output of those capabilities.</span></span>

<span data-ttu-id="b0cbb-108">Страницата **Обекти** показва обекти и включва няколко колони:</span><span class="sxs-lookup"><span data-stu-id="b0cbb-108">The **Entities** page lists entities and includes several columns:</span></span>

- <span data-ttu-id="b0cbb-109">**Име:** Името на обекта на данни.</span><span class="sxs-lookup"><span data-stu-id="b0cbb-109">**Name**: The name of your data entity.</span></span> <span data-ttu-id="b0cbb-110">Ако видите предупредителен символ до името на обекта, това означава, че данните за този обект не са заредени успешно.</span><span class="sxs-lookup"><span data-stu-id="b0cbb-110">If you see a warning symbol next to an entity name, it means that the data for that entity didn't load successfully.</span></span>
- <span data-ttu-id="b0cbb-111">**Източник**: Типът източник на данни, приети в обекта</span><span class="sxs-lookup"><span data-stu-id="b0cbb-111">**Source**: The type of data source that ingested the entity</span></span>
- <span data-ttu-id="b0cbb-112">**Създаден от**: Името на човека, създал обекта</span><span class="sxs-lookup"><span data-stu-id="b0cbb-112">**Created by**: Name of the person who created the entity</span></span>
- <span data-ttu-id="b0cbb-113">**Създаден**: Дата и час на създаване на обекта</span><span class="sxs-lookup"><span data-stu-id="b0cbb-113">**Created**: Date and time of the entity creation</span></span>
- <span data-ttu-id="b0cbb-114">**Актуализиран от**: Името на човека, актуализирал обекта</span><span class="sxs-lookup"><span data-stu-id="b0cbb-114">**Updated by**: Name of the person who updated the entity</span></span>
- <span data-ttu-id="b0cbb-115">**Последна актуализация**: Дата и час на последната актуализация на обекта</span><span class="sxs-lookup"><span data-stu-id="b0cbb-115">**Last updated**: Date and time of the last update of the entity</span></span>
- <span data-ttu-id="b0cbb-116">**Последно обновяване**: Дата и час на последното обновяване на данните</span><span class="sxs-lookup"><span data-stu-id="b0cbb-116">**Last refresh**: Date and time of the last data refresh</span></span>

## <a name="exploring-a-specific-entitys-data"></a><span data-ttu-id="b0cbb-117">Разглеждане на данните на конкретен обект</span><span class="sxs-lookup"><span data-stu-id="b0cbb-117">Exploring a specific entity's data</span></span>

<span data-ttu-id="b0cbb-118">Изберете обект, за да изследвате различните полета и записи, включени в този обект.</span><span class="sxs-lookup"><span data-stu-id="b0cbb-118">Select an entity to explore the different fields and records included within that entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b0cbb-119">![Избор на обект](media/data-manager-entities-data.png "Избор на обект")</span><span class="sxs-lookup"><span data-stu-id="b0cbb-119">![Select an entity](media/data-manager-entities-data.png "Select an entity")</span></span>

- <span data-ttu-id="b0cbb-120">Разделът **Данни** е избран по подразбиране и показва таблица, в която са изброени подробности за отделни записи на обекта.</span><span class="sxs-lookup"><span data-stu-id="b0cbb-120">The **Data** tab is selected by default and shows a table listing details about individual records of the entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b0cbb-121">![Таблица „Полета”](media/data-manager-entities-fields.PNG "Таблица „Полета”")</span><span class="sxs-lookup"><span data-stu-id="b0cbb-121">![Fields table](media/data-manager-entities-fields.PNG "Fields table")</span></span>

- <span data-ttu-id="b0cbb-122">Разделът **Полета** показва таблица за преглед на подробности за избрания обект, като имена на полета, типове данни и типове.</span><span class="sxs-lookup"><span data-stu-id="b0cbb-122">The **Fields** tab shows a table to review details for the selected entity, such as field names, data types, and types.</span></span> <span data-ttu-id="b0cbb-123">Колоната **Тип** показва свързаните типове на Common Data Model, които или са автоматично идентифицирани от системата, или [ръчно нанесени](map-entities.md) от потребителите.</span><span class="sxs-lookup"><span data-stu-id="b0cbb-123">The **Type** column shows Common Data Model associated types, which are either auto-identified by the system or [manually mapped](map-entities.md) by users.</span></span> <span data-ttu-id="b0cbb-124">Това са семантични типове, които могат да се различават от типовете данни на атрибутите – например полето *Имейл* по-долу има тип данни *Текст*, но неговият (семантичен) тип на Common Data Model може да бъде *Имейл* или *EmailAddress*.</span><span class="sxs-lookup"><span data-stu-id="b0cbb-124">These are semantic types that can differ from the attributes' data types—for example, the field *Email* below has a data type *Text* but its (semantic) Common Data Model type might be *Email* or *EmailAddress*.</span></span>

> [!NOTE]
> <span data-ttu-id="b0cbb-125">И двете таблици показват само пример за данните на обекта.</span><span class="sxs-lookup"><span data-stu-id="b0cbb-125">Both tables show only a sample of your entity's data.</span></span> <span data-ttu-id="b0cbb-126">За да прегледате пълния набор от данни, отидете на страницата **Източници на данни**, изберете обект, изберете **Редактиране**, след което прегледайте данните на обекта с редактора на Power Query, както е обяснено в [Източници на данни](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="b0cbb-126">To view the full data set, go to the **Data sources** page, select an entity, select **Edit**, and then view this entity's data with the Power Query editor as explained in [Data sources](data-sources.md).</span></span>

<span data-ttu-id="b0cbb-127">За да научите повече за данните, приети в обекта, колоната **Обобщение** ви предоставя някои важни характеристики на данните, като например празни, липсващи стойности, уникални стойности, брой и разпределения, приложими за вашите данни.</span><span class="sxs-lookup"><span data-stu-id="b0cbb-127">To learn more about the data ingested in the entity, the **Summary** column provides you with some important characteristics of the data, such as nulls, missing values, unique values, counts, and distributions, as applicable to your data.</span></span>

<span data-ttu-id="b0cbb-128">Изберете иконата на диаграмата, за да видите обобщението на данните.</span><span class="sxs-lookup"><span data-stu-id="b0cbb-128">Select the chart icon to see the summary of the data.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b0cbb-129">![Символ за обобщение](media/data-manager-entities-summary.png "Таблица за обобщение на данни")</span><span class="sxs-lookup"><span data-stu-id="b0cbb-129">![Summary symbol](media/data-manager-entities-summary.png "Data summary table")</span></span>

### <a name="next-step"></a><span data-ttu-id="b0cbb-130">Следваща стъпка</span><span class="sxs-lookup"><span data-stu-id="b0cbb-130">Next step</span></span>

<span data-ttu-id="b0cbb-131">Вижте темата [Унифициране](data-unification.md), за да научите как да *нанасяте*, *съпоставяте* и *обединявате* приетите данни.</span><span class="sxs-lookup"><span data-stu-id="b0cbb-131">See the [Unify](data-unification.md) topic to learn how to *map*, *match*, and *merge* the ingested data.</span></span>
