---
title: Създаване и редактиране на мерки
description: Определете мерки, свързани с клиентите, за анализ и отразяване на представянето в определени области на бизнеса.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 0e214a6eb66abd27f7292db3ce2c2a6e16a8ff33
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405109"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="e389d-103">Определяне и управление на мерки</span><span class="sxs-lookup"><span data-stu-id="e389d-103">Define and manage measures</span></span>

<span data-ttu-id="e389d-104">**Мерките** представляват водещи показатели на представянето (KPI), които отразяват представянето и състоянието на конкретни области на бизнеса.</span><span class="sxs-lookup"><span data-stu-id="e389d-104">**Measures** represent key performance indicators (KPIs) that reflect the performance and health of specific business areas.</span></span> <span data-ttu-id="e389d-105">Статистика за аудиторията предоставя интуитивно изживяване за изграждане на различни видове мерки, като се използва конструктор на заявки, който не изисква ръчно кодиране или валидиране на вашите мерки.</span><span class="sxs-lookup"><span data-stu-id="e389d-105">Audience insights provides an intuitive experience for building different types of measures, using a query builder that doesn't require you to code or validate your measures manually.</span></span> <span data-ttu-id="e389d-106">Можете да проследите бизнес мерките на страницата **Начало**, да прегледате мерките за конкретни клиенти на **Картата на клиент** и да използвате мерките за определяне на клиентските сегменти на страницата **Сегменти**.</span><span class="sxs-lookup"><span data-stu-id="e389d-106">You can track your business measures on the **Home** page, see measures for specific customers on the **Customer Card**, and use measures to define customer segments on the **Segments** page.</span></span>

## <a name="create-a-measure"></a><span data-ttu-id="e389d-107">Създаване на мярка</span><span class="sxs-lookup"><span data-stu-id="e389d-107">Create a measure</span></span>

<span data-ttu-id="e389d-108">Този раздел ви превежда през създаването на мярка от самото начало.</span><span class="sxs-lookup"><span data-stu-id="e389d-108">This section walks you through creating a measure from scratch.</span></span> <span data-ttu-id="e389d-109">Можете да създадете мерки с данни от няколко източника на данни, които са свързани чрез обект на клиент.</span><span class="sxs-lookup"><span data-stu-id="e389d-109">You can build measures with data from multiple data sources that are connected through the Customer entity.</span></span> <span data-ttu-id="e389d-110">Някои [лимити за обслужване](service-limits.md) се прилагат.</span><span class="sxs-lookup"><span data-stu-id="e389d-110">Some [service limits](service-limits.md) apply.</span></span>

1. <span data-ttu-id="e389d-111">В Аналитични данни за аудиторията отидете на **Мерки**.</span><span class="sxs-lookup"><span data-stu-id="e389d-111">In audience insights, go to **Measures**.</span></span>

2. <span data-ttu-id="e389d-112">Изберете **Нова мярка**.</span><span class="sxs-lookup"><span data-stu-id="e389d-112">Select **New measure**.</span></span>

3. <span data-ttu-id="e389d-113">Изберете мярката **Тип**:</span><span class="sxs-lookup"><span data-stu-id="e389d-113">Choose the measure **Type**:</span></span>

   - <span data-ttu-id="e389d-114">**Атрибут на клиент**: Единично поле за клиент, което отразява резултат, стойност или състояние за клиента.</span><span class="sxs-lookup"><span data-stu-id="e389d-114">**Customer attribute**: A single field per customer that reflects a score, value, or state for the customer.</span></span> <span data-ttu-id="e389d-115">Клиентските атрибути се създават като атрибути в нов обект, генериран от системата, наречен **Мярка на клиент**.</span><span class="sxs-lookup"><span data-stu-id="e389d-115">Customer attributes are created as attributes in a new system-generated entity called **Customer_Measure**.</span></span>

   - <span data-ttu-id="e389d-116">**Мярка на клиент**: Аналитични данни за поведението на клиента с разбивка по избрани измерения.</span><span class="sxs-lookup"><span data-stu-id="e389d-116">**Customer measure**: Insights on customer behavior with breakdown by selected dimensions.</span></span> <span data-ttu-id="e389d-117">За всяка мярка се генерира нов обект, евентуално с множество записи на клиент.</span><span class="sxs-lookup"><span data-stu-id="e389d-117">A new entity is generated for each measure, potentially with multiple records per customer.</span></span>

   - <span data-ttu-id="e389d-118">**Бизнес мярка**: Проследява бизнес представянето и състоянието на бизнеса.</span><span class="sxs-lookup"><span data-stu-id="e389d-118">**Business measure**: Tracks your business performance and health of the business.</span></span> <span data-ttu-id="e389d-119">Бизнес мерките могат да имат два различни резултата: цифров резултат, който се показва на страницата **Начало** или нов обект, който се намира на страницата **Обекти**.</span><span class="sxs-lookup"><span data-stu-id="e389d-119">Business measures can have two different outputs: a numeric output that shows on the **Home** page or a new entity that you find on the **Entities** page.</span></span>

4. <span data-ttu-id="e389d-120">Въведете **Име** и по избор **Показвано име**, след което изберете **Напред**.</span><span class="sxs-lookup"><span data-stu-id="e389d-120">Provide a **Name** and an optional **Display name**, then select **Next**.</span></span>

5. <span data-ttu-id="e389d-121">В секцията **Обекти** изберете първия обект от падащия списък.</span><span class="sxs-lookup"><span data-stu-id="e389d-121">In the **Entities** section, select the first entity from the drop-down list.</span></span> <span data-ttu-id="e389d-122">На този етап трябва да решите дали са необходими допълнителни обекти като част от дефиницията на мярката.</span><span class="sxs-lookup"><span data-stu-id="e389d-122">At this point, you should decide whether additional entities are needed as part of your measure definition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e389d-123">![Определение за мярка](media/measure-definition.png "Определение за мярка")</span><span class="sxs-lookup"><span data-stu-id="e389d-123">![Measure definition](media/measure-definition.png "Measure definition")</span></span>

   <span data-ttu-id="e389d-124">За да добавите още обекти, изберете **Добавяне на обект** и изберете обектите, които искате да използвате за мярката.</span><span class="sxs-lookup"><span data-stu-id="e389d-124">To add more entities, select **Add entity** and select entities you want to use for the measure.</span></span>

   > [!NOTE]
   > <span data-ttu-id="e389d-125">Може да изберете само обекти, които имат релация с първоначалния обект.</span><span class="sxs-lookup"><span data-stu-id="e389d-125">You can select only entities that have relationships to your starting entity.</span></span> <span data-ttu-id="e389d-126">За повече информация относно дефинирането на релации вижте [Релации](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="e389d-126">For more information about defining relationships, see [Relationships](relationships.md).</span></span>

6. <span data-ttu-id="e389d-127">По желание можете да конфигурирате променливи.</span><span class="sxs-lookup"><span data-stu-id="e389d-127">Optionally, you can configure variables.</span></span> <span data-ttu-id="e389d-128">В секцията **Променливи** изберете **Нова променлива**.</span><span class="sxs-lookup"><span data-stu-id="e389d-128">In the **Variables** section, select **New variable**.</span></span>

   <span data-ttu-id="e389d-129">Променливите са изчисления, които се правят на всеки от избраните от вас записи.</span><span class="sxs-lookup"><span data-stu-id="e389d-129">Variables are calculations that are made on each of your selected records.</span></span> <span data-ttu-id="e389d-130">Например сумиране на точки на продажба (POS) и онлайн продажби за всеки от записите на клиентите.</span><span class="sxs-lookup"><span data-stu-id="e389d-130">For example, summing point-of-sale (POS) and online sales for each of your customers' records.</span></span>

7. <span data-ttu-id="e389d-131">Посочете **Име** за променливата.</span><span class="sxs-lookup"><span data-stu-id="e389d-131">Provide a **Name** for the variable.</span></span>

8. <span data-ttu-id="e389d-132">В областта **Израз** изберете поле, с което да започнете изчислението си.</span><span class="sxs-lookup"><span data-stu-id="e389d-132">In the **Expression** area, choose a field to begin your calculation with.</span></span>

9. <span data-ttu-id="e389d-133">Въведете израз в областта **Израз**, докато избирате още полета, които да бъдат включени в изчислението.</span><span class="sxs-lookup"><span data-stu-id="e389d-133">Type an expression in the **Expression** area while choosing more fields to be included in your calculation.</span></span>

   > [!NOTE]
   > <span data-ttu-id="e389d-134">Понастоящем се поддържат само аритметични изрази.</span><span class="sxs-lookup"><span data-stu-id="e389d-134">Currently, only arithmetic expressions are supported.</span></span> <span data-ttu-id="e389d-135">Освен това изчислението на променливи не се поддържа за обекти от различни [пътища на обект](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="e389d-135">Additionally, variable calculation isn't supported for entities from different [entity paths](relationships.md).</span></span>

10. <span data-ttu-id="e389d-136">Изберете **Готово**.</span><span class="sxs-lookup"><span data-stu-id="e389d-136">Select **Done**.</span></span>

11. <span data-ttu-id="e389d-137">В секцията **Определение за мярка** ще дефинирате как избраните от вас обекти и изчислените променливи се обобщават в нов обект на мярка или атрибут.</span><span class="sxs-lookup"><span data-stu-id="e389d-137">In the **Measure definition** section, you'll define how your chosen entities and calculated variables are aggregated in a new measure entity or attribute.</span></span>

12. <span data-ttu-id="e389d-138">Изберете **Ново измерение**.</span><span class="sxs-lookup"><span data-stu-id="e389d-138">Select **New dimension**.</span></span> <span data-ttu-id="e389d-139">Можете да си представите измерението като функция за *групиране по*.</span><span class="sxs-lookup"><span data-stu-id="e389d-139">You can think of a dimension as a *group by* function.</span></span> <span data-ttu-id="e389d-140">Извеждането на данни на обекта или атрибута на мярката ще се групира по всички дефинирани измерения.</span><span class="sxs-lookup"><span data-stu-id="e389d-140">The data output of your Measure entity or attribute will be grouped by all of your defined dimensions.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="e389d-141">![Избор на цикъл на агрегиране](media/measures-businessreport-measure-definition2.png "Избор на цикъл на агрегиране")</span><span class="sxs-lookup"><span data-stu-id="e389d-141">![Choose aggregate cycle](media/measures-businessreport-measure-definition2.png "Choose aggregate cycle")</span></span>

    <span data-ttu-id="e389d-142">Изберете или въведете следната информация като част от дефиницията на измерението:</span><span class="sxs-lookup"><span data-stu-id="e389d-142">Select or enter the following information as part of your dimension's definition:</span></span>

    - <span data-ttu-id="e389d-143">**Обект**: Ако дефинирате обект на мярка, той трябва да включва поне един атрибут.</span><span class="sxs-lookup"><span data-stu-id="e389d-143">**Entity**: If you define a Measure entity, it should include at least one attribute.</span></span> <span data-ttu-id="e389d-144">Ако дефинирате атрибут на мярка, той ще включва само един атрибут по подразбиране.</span><span class="sxs-lookup"><span data-stu-id="e389d-144">If you define a Measure attribute, it will include only one attribute by default.</span></span> <span data-ttu-id="e389d-145">Този избор е свързан с избора на обекта, който включва този атрибут.</span><span class="sxs-lookup"><span data-stu-id="e389d-145">This selection is about choosing the entity that includes that attribute.</span></span>
    - <span data-ttu-id="e389d-146">**Поле**: Изберете конкретния атрибут, който ще бъде включен мярката или атрибута.</span><span class="sxs-lookup"><span data-stu-id="e389d-146">**Field**: Choose the specific attribute to be included either in your Measure entity or attribute.</span></span>
    - <span data-ttu-id="e389d-147">**Набор** : Изберете дали искате да агрегирате данни на ежедневна, ежемесечна или годишна база.</span><span class="sxs-lookup"><span data-stu-id="e389d-147">**Bucket**: Choose whether you want to aggregate data on a daily, monthly, or annual basis.</span></span> <span data-ttu-id="e389d-148">Това е задължителен избор само ако сте избрали атрибут от тип „Дата”.</span><span class="sxs-lookup"><span data-stu-id="e389d-148">It's a required selection only if you've selected a Date type attribute.</span></span>
    - <span data-ttu-id="e389d-149">**Като**: Определя името на новото поле.</span><span class="sxs-lookup"><span data-stu-id="e389d-149">**As**: Defines the name of your new field.</span></span>
    - <span data-ttu-id="e389d-150">**Показвано име** : Определя показваното име на полето.</span><span class="sxs-lookup"><span data-stu-id="e389d-150">**Display name**: Defines the display name of your field.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e389d-151">Бизнес мярката ще се запише като обект с едно число и ще се показва на страницата **Начало**, освен ако не добавите още измерения към мярката.</span><span class="sxs-lookup"><span data-stu-id="e389d-151">Your business measure will be saved as a single-number entity and will appear on the **Home** page unless you add more dimensions to your measure.</span></span> <span data-ttu-id="e389d-152">След добавяне на още измерения, мярката *няма* да се показва на страницата **Начало**.</span><span class="sxs-lookup"><span data-stu-id="e389d-152">After adding more dimensions, the measure will *not* show up on the **Home** page.</span></span>

13. <span data-ttu-id="e389d-153">По желание добавете функции за агрегиране.</span><span class="sxs-lookup"><span data-stu-id="e389d-153">Optionally, add aggregation functions.</span></span> <span data-ttu-id="e389d-154">Всяко агрегиране, което създавате, води до нова стойност в рамките на обекта на мярка или атрибут.</span><span class="sxs-lookup"><span data-stu-id="e389d-154">Any aggregation that you create results in a new value within your Measures entity or attribute.</span></span> <span data-ttu-id="e389d-155">Поддържаните функции за агрегиране са: **Мин.**, **Макс.**, **Средно**, **Средна стойност**, **Сбор**, **Уникален брой**, **Първо** (взема се първият запис на стойност на измерение) и **Последно** (взема се последният запис, добавен към стойност на измерение).</span><span class="sxs-lookup"><span data-stu-id="e389d-155">Supported aggregation functions are: **Min**, **Max**, **Average**, **Median**, **Sum**, **Count Unique**, **First** (takes the first record of a dimension value), and **Last** (takes the last record added to a dimension value).</span></span>

14. <span data-ttu-id="e389d-156">Изберете **Записване**, за да запишете промените на мярката.</span><span class="sxs-lookup"><span data-stu-id="e389d-156">Select **Save** to apply your changes to the measure.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="e389d-157">Управление на мерките</span><span class="sxs-lookup"><span data-stu-id="e389d-157">Manage your measures</span></span>

<span data-ttu-id="e389d-158">След като създадете поне една мярка, ще видите списък с мерки на страницата **Мерки**.</span><span class="sxs-lookup"><span data-stu-id="e389d-158">After creating at least one measure, you'll see a list of measures on the **Measures** page.</span></span>

<span data-ttu-id="e389d-159">Ще намерите информация за типа мярка, създателя, датата и часа на създаване, датата и часа на последното редактиране, състоянието (дали мярката е активна, неактивна или неуспешна) и датата и часа на последното обновяване.</span><span class="sxs-lookup"><span data-stu-id="e389d-159">You'll find information about the measure type, the creator, creation date and time, last edit date and time, status (whether the measure is active, inactive, or failed), and last refresh date and time.</span></span> <span data-ttu-id="e389d-160">Когато изберете мярка от списъка, можете да видите преглед на резултатите от нея.</span><span class="sxs-lookup"><span data-stu-id="e389d-160">When you select a measure from the list, you can see a preview of its output.</span></span>

<span data-ttu-id="e389d-161">За да обновите всичките си мерки едновременно, изберете **Обновяване на всички** без да избирате конкретна мярка.</span><span class="sxs-lookup"><span data-stu-id="e389d-161">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e389d-162">![Действия за управление на единични мерки](media/measure-actions.png "Действия за управление на единични мерки")</span><span class="sxs-lookup"><span data-stu-id="e389d-162">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="e389d-163">Друга възможност е да изберете мярка от списъка и да извършите едно от следните действия:</span><span class="sxs-lookup"><span data-stu-id="e389d-163">Alternatively, select a measure from the list and perform one of the following actions:</span></span>

- <span data-ttu-id="e389d-164">Изберете името на мярката, за да видите подробности за нея.</span><span class="sxs-lookup"><span data-stu-id="e389d-164">Select the measure name to see its details.</span></span>
- <span data-ttu-id="e389d-165">**Редактиране** на конфигурацията на мярката.</span><span class="sxs-lookup"><span data-stu-id="e389d-165">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="e389d-166">**Преименуване** на мярката.</span><span class="sxs-lookup"><span data-stu-id="e389d-166">**Rename** the measure.</span></span>
- <span data-ttu-id="e389d-167">**Изтриване** на мярката.</span><span class="sxs-lookup"><span data-stu-id="e389d-167">**Delete** the measure.</span></span>
- <span data-ttu-id="e389d-168">Изберете многоточието (...) и след това **Обновяване**, за да стартирате процеса на обновяване на мярката.</span><span class="sxs-lookup"><span data-stu-id="e389d-168">Select the ellipsis (...) and then **Refresh** to start the refresh process for the measure.</span></span>
- <span data-ttu-id="e389d-169">Изберете многоточието (...) и след това **Изтегляне**, за да получите .CSV файл на мярката.</span><span class="sxs-lookup"><span data-stu-id="e389d-169">Select the ellipsis (...) and then **Download** to get a .CSV file of the measure.</span></span>

> [!TIP]
> <span data-ttu-id="e389d-170">Съществуват [шест вида статус](system.md#status-types) на задачите/процесите.</span><span class="sxs-lookup"><span data-stu-id="e389d-170">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="e389d-171">Освен това повечето процеси [зависят от други процеси надолу по веригата](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="e389d-171">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="e389d-172">Можете да изберете състоянието на процес, за да видите подробности за напредъка на цялата задача.</span><span class="sxs-lookup"><span data-stu-id="e389d-172">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="e389d-173">След като изберете **Вижте подробности** за една от задачите на заданието, ще намерите допълнителна информация: време за обработка, дата на последната обработка и всички грешки и предупреждения, свързани със задачата.</span><span class="sxs-lookup"><span data-stu-id="e389d-173">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="e389d-174">Следваща стъпка</span><span class="sxs-lookup"><span data-stu-id="e389d-174">Next step</span></span>

<span data-ttu-id="e389d-175">Можете да използвате съществуващите мерки, за да създадете своя първи клиентски сегмент на страницата **Сегменти**.</span><span class="sxs-lookup"><span data-stu-id="e389d-175">You cam use existing measures to create your first customer segment on the **Segments** page.</span></span> <span data-ttu-id="e389d-176">За повече информация вижте [Сегменти](segments.md).</span><span class="sxs-lookup"><span data-stu-id="e389d-176">For more information, see [Segments](segments.md).</span></span>
