---
title: Сегменти в Аналитични данни за аудиторията
description: Преглед на сегментите и как да ги създавате и управлявате.
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 6cb7bd62bf0f61e6dc5811b20e5011e4a086c743
ms.sourcegitcommit: 84283d523a891298fca8aaf629d9f9ab2a1bc067
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 05/27/2021
ms.locfileid: "6111374"
---
# <a name="segments-overview"></a><span data-ttu-id="f643d-103">Общ преглед на сегментите</span><span class="sxs-lookup"><span data-stu-id="f643d-103">Segments overview</span></span>

<span data-ttu-id="f643d-104">Сегментите ви позволяват да групирате клиентите си въз основа на демографски, транзакционни или поведенчески атрибути.</span><span class="sxs-lookup"><span data-stu-id="f643d-104">Segments let you group your customers based on demographic, transactional, or behavioral attributes.</span></span> <span data-ttu-id="f643d-105">Можете да използвате сегменти за насочване на промоционални кампании, търговски дейности и действия за поддръжка на клиенти за постигане на вашите бизнес цели.</span><span class="sxs-lookup"><span data-stu-id="f643d-105">You can use segments to target promotional campaigns, sales activities, and customer support actions to achieve your business goals.</span></span>

<span data-ttu-id="f643d-106">Клиентските профили, които съответстват на филтрите на дефиниция на сегмент, се наричат *членове* на сегмент.</span><span class="sxs-lookup"><span data-stu-id="f643d-106">Customer profiles that match the filters of a segment definition are referred as *members* of a segment.</span></span> <span data-ttu-id="f643d-107">Някои [лимити за обслужване](service-limits.md) се прилагат.</span><span class="sxs-lookup"><span data-stu-id="f643d-107">Some [service limits](service-limits.md) apply.</span></span>

## <a name="create-a-new-segment"></a><span data-ttu-id="f643d-108">Създаване на нов сегмент</span><span class="sxs-lookup"><span data-stu-id="f643d-108">Create a new segment</span></span>

<span data-ttu-id="f643d-109">Има няколко начина за създаване на нов сегмент:</span><span class="sxs-lookup"><span data-stu-id="f643d-109">There are multiple ways to create a new segment:</span></span> 

- <span data-ttu-id="f643d-110">Сложен сегмент с конструктор на сегменти: [Празен сегмент](segment-builder.md#create-a-new-segment)</span><span class="sxs-lookup"><span data-stu-id="f643d-110">Complex segment with segment builder: [Blank segment](segment-builder.md#create-a-new-segment)</span></span>
- <span data-ttu-id="f643d-111">Прости сегменти с един оператор: [Бърз сегмент](segment-builder.md#quick-segments)</span><span class="sxs-lookup"><span data-stu-id="f643d-111">Simple segments with one operator: [Quick segment](segment-builder.md#quick-segments)</span></span>
- <span data-ttu-id="f643d-112">Начин на изкуствен интелект за намиране на подобни клиенти: [Подобни клиенти](find-similar-customer-segments.md)</span><span class="sxs-lookup"><span data-stu-id="f643d-112">AI-powered way to find similar customers: [Similar Customers](find-similar-customer-segments.md)</span></span>
- <span data-ttu-id="f643d-113">Предложения с изкуствен интелект въз основа на мерки или атрибути: [Предложени сегменти за подобряване на мерките](suggested-segments.md)</span><span class="sxs-lookup"><span data-stu-id="f643d-113">AI-powered suggestions based on measures or attributes: [Suggested segments to improve measures](suggested-segments.md)</span></span>
- <span data-ttu-id="f643d-114">Предложения въз основа на дейности: [Предложени сегменти въз основа на активността на клиентите](suggested-segments-activity.md)</span><span class="sxs-lookup"><span data-stu-id="f643d-114">Suggestions based on activities: [Suggested segments based on customer activity](suggested-segments-activity.md)</span></span>

## <a name="manage-existing-segments"></a><span data-ttu-id="f643d-115">Управление на съществуващи сегменти</span><span class="sxs-lookup"><span data-stu-id="f643d-115">Manage existing segments</span></span>

<span data-ttu-id="f643d-116">Отидете на **Сегменти** страница, за да видите всичките си запазени сегменти и да ги управлявате.</span><span class="sxs-lookup"><span data-stu-id="f643d-116">Go to the **Segments** page, to view all your saved segments and manage them.</span></span>

<span data-ttu-id="f643d-117">Всеки сегмент е представен от ред, който включва допълнителна информация за сегмента.</span><span class="sxs-lookup"><span data-stu-id="f643d-117">Each segment is represented by a row that includes additional information about the segment.</span></span>

:::image type="content" source="media/segments-selected-segment.png" alt-text="Избран сегмент с падащ списък с опции и налични опции.":::

<span data-ttu-id="f643d-119">Следното действие е достъпно, когато изберете сегмент:</span><span class="sxs-lookup"><span data-stu-id="f643d-119">The following action are available when you select a segment:</span></span>

- <span data-ttu-id="f643d-120">**Прегледайте** подробностите за сегмента, включително тенденцията за броя на членовете, преглед на членовете на сегмента.</span><span class="sxs-lookup"><span data-stu-id="f643d-120">**View** the segment details, including member count trend a preview of segment members.</span></span>
- <span data-ttu-id="f643d-121">**Редактирайте** сегмента, за да промените свойствата.</span><span class="sxs-lookup"><span data-stu-id="f643d-121">**Edit** the segment to change its properties.</span></span>
- <span data-ttu-id="f643d-122">**Създайте дубликат** на сегмент.</span><span class="sxs-lookup"><span data-stu-id="f643d-122">**Create duplicate** of a segment.</span></span> <span data-ttu-id="f643d-123">Можете да изберете да редактирате свойствата му веднага или просто да запазите дубликата.</span><span class="sxs-lookup"><span data-stu-id="f643d-123">You can choose to edit its properties right away or simply save the duplicate.</span></span>
- <span data-ttu-id="f643d-124">**Обновете** сегмента, за да включва най-новите данни.</span><span class="sxs-lookup"><span data-stu-id="f643d-124">**Refresh** the segment to include the latest data.</span></span>
- <span data-ttu-id="f643d-125">**Активирайте** или **деактивирайте** сегмента.</span><span class="sxs-lookup"><span data-stu-id="f643d-125">**Activate** or **Deactivate** the segment.</span></span> <span data-ttu-id="f643d-126">Сегментите имат две възможни състояния – активно или неактивно.</span><span class="sxs-lookup"><span data-stu-id="f643d-126">Segments have two possible states - active or inactive.</span></span> <span data-ttu-id="f643d-127">Тези състояния са полезни при редактиране на сегмент.</span><span class="sxs-lookup"><span data-stu-id="f643d-127">These states come in handy when editing a segment.</span></span> <span data-ttu-id="f643d-128">За неактивни сегменти дефиницията на сегмента съществува, но все още не съдържа клиенти.</span><span class="sxs-lookup"><span data-stu-id="f643d-128">For inactive segments, the segment definition exists but it doesn't contain any customers yet.</span></span> <span data-ttu-id="f643d-129">Когато активирате сегмент, състоянието му се променя от „неактивно“ на „активно“ и той започва да търси клиенти, които съответстват на дефиницията на сегмента.</span><span class="sxs-lookup"><span data-stu-id="f643d-129">When you activate a segment, its state changes from 'inactive' to 'active" and it starts looking for customers that match the segment definition.</span></span> <span data-ttu-id="f643d-130">Ако е конфигурирано [планирано обновяване](system.md#schedule-tab), неактивните сегменти имат **Състояние**, посочено като **Пропуснато**, което показва, че дори не е бил направен опит за обновяване.</span><span class="sxs-lookup"><span data-stu-id="f643d-130">If a [scheduled refresh](system.md#schedule-tab) is configured, inactive segments have the **Status** listed as **Skipped**, indicating that a refresh wasn't even attempted.</span></span> <span data-ttu-id="f643d-131">Когато се активира неактивен сегмент, той ще се обнови и ще бъде включен в планираните обновявания.</span><span class="sxs-lookup"><span data-stu-id="f643d-131">When an inactive segment is activated, it will refresh and will be included in scheduled refreshes.</span></span>
  <span data-ttu-id="f643d-132">Като алтернатива можете да използвате функционалността **Планиране по-късно** в падащия списък **Активиране/деактивиране**, за да посочите бъдеща дата и час за активиране и деактивиране на определен сегмент.</span><span class="sxs-lookup"><span data-stu-id="f643d-132">Alternatively, you can use the **Schedule later** functionality in the **Activate/Deactivate** dropdown to specify a future date and time for activation and deactivation of a particular segment.</span></span>
- <span data-ttu-id="f643d-133">**Преименувайте** сегмента.</span><span class="sxs-lookup"><span data-stu-id="f643d-133">**Rename** the segment.</span></span>
- <span data-ttu-id="f643d-134">**Изтеглете** списъка с членове като .CSV файл.</span><span class="sxs-lookup"><span data-stu-id="f643d-134">**Download** the list of members as a .CSV file.</span></span>
- <span data-ttu-id="f643d-135">**Управление на експортирането** да видите сегмента, свързан с износа, и да ги управлявате.</span><span class="sxs-lookup"><span data-stu-id="f643d-135">**Manage exports** to see exports related segment and manage them.</span></span> [<span data-ttu-id="f643d-136">Научете повече за експортиранията.</span><span class="sxs-lookup"><span data-stu-id="f643d-136">Learn more about exports.</span></span>](export-destinations.md)
- <span data-ttu-id="f643d-137">**Изтриване** на сегмента.</span><span class="sxs-lookup"><span data-stu-id="f643d-137">**Delete** the segment.</span></span>

## <a name="refresh-segments"></a><span data-ttu-id="f643d-138">Обновяване на сегменти</span><span class="sxs-lookup"><span data-stu-id="f643d-138">Refresh segments</span></span>

<span data-ttu-id="f643d-139">Можете да опресните всички сегменти наведнъж, като изберете **Обновяване на всички** на страницата **Сегменти**, или можете да опресните един или няколко сегмента, когато ги изберете и изберете **Обновяване** от опциите.</span><span class="sxs-lookup"><span data-stu-id="f643d-139">You can refresh all segments at once by selecting **Refresh all** on the **Segments** page or you can refresh one or multiple segments when you select them and choose **Refresh** in from the options.</span></span> <span data-ttu-id="f643d-140">Освен това можете да конфигурирате повтарящо се обновяване в **Администриране** > **Система** > **График**.</span><span class="sxs-lookup"><span data-stu-id="f643d-140">Alternatively, you can configure a recurring refresh on **Admin** > **System** > **Schedule**.</span></span>

> [!TIP]
> <span data-ttu-id="f643d-141">Съществуват [шест вида статус](system.md#status-types) на задачите/процесите.</span><span class="sxs-lookup"><span data-stu-id="f643d-141">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="f643d-142">Освен това повечето процеси [зависят от други процеси надолу по веригата](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="f643d-142">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="f643d-143">Можете да изберете състоянието на процес, за да видите подробности за напредъка на цялата задача.</span><span class="sxs-lookup"><span data-stu-id="f643d-143">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="f643d-144">След като изберете **Вижте подробности** за една от задачите на заданието, ще намерите допълнителна информация: време за обработка, дата на последната обработка и всички грешки и предупреждения, свързани със задачата.</span><span class="sxs-lookup"><span data-stu-id="f643d-144">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="export-segments"></a><span data-ttu-id="f643d-145">Експортиране на сегменти</span><span class="sxs-lookup"><span data-stu-id="f643d-145">Export segments</span></span>

<span data-ttu-id="f643d-146">Можете да експортирате сегмент от страницата със сегменти или от [страница за експортиране](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="f643d-146">You can export a segment from the segments page or the [exports page](export-destinations.md).</span></span> 

1. <span data-ttu-id="f643d-147">Отидете на страницата **Сегменти**.</span><span class="sxs-lookup"><span data-stu-id="f643d-147">Go to the **Segments** page.</span></span>

1. <span data-ttu-id="f643d-148">Изберете **Показване на още [...]** за сегмента, който искате да експортирате.</span><span class="sxs-lookup"><span data-stu-id="f643d-148">Select **Show more [...]** for the segment you want to export.</span></span>

1. <span data-ttu-id="f643d-149">Изберете **Управление на експортиранията** от падащия списък с действия.</span><span class="sxs-lookup"><span data-stu-id="f643d-149">Select **Manage exports** from the actions drop-down list.</span></span>

1. <span data-ttu-id="f643d-150">Отваря се страницата **Експортирания (преглед) за сегмент**.</span><span class="sxs-lookup"><span data-stu-id="f643d-150">The page **Exports (preview) for segment** opens.</span></span> <span data-ttu-id="f643d-151">Можете да видите всички конфигурирани експорти, групирани по експорти, които съдържат текущия сегмент или не го съдържат.</span><span class="sxs-lookup"><span data-stu-id="f643d-151">You can see all configured exports grouped by by exports that contain the current segment or don't contain it.</span></span>

   1. <span data-ttu-id="f643d-152">За да добавите избрания сегмент към експорт, изберете експорта в списъка и изберете **Добавяне на сегмент**.</span><span class="sxs-lookup"><span data-stu-id="f643d-152">To add the selected segment to an export, select the export in the list and select **Add segment**.</span></span>

   1. <span data-ttu-id="f643d-153">За да създадете нов експорт с избрания сегмент, изберете **Добавете експортиране**.</span><span class="sxs-lookup"><span data-stu-id="f643d-153">To create a new export with the selected segment, select **Add export**.</span></span> <span data-ttu-id="f643d-154">За повече информация относно създаването на износ вж [Настройте ново експортиране](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="f643d-154">For more information about creating exports, see [Set up a new export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="f643d-155">Изберете **обратно** за да се върнете на главната страница за сегменти.</span><span class="sxs-lookup"><span data-stu-id="f643d-155">Select **Back** to return to the main page for segments.</span></span>

## <a name="view-processing-history-and-segment-members"></a><span data-ttu-id="f643d-156">Преглед на хронологията на обработката и членовете на сегмента</span><span class="sxs-lookup"><span data-stu-id="f643d-156">View processing history and segment members</span></span>

<span data-ttu-id="f643d-157">Можете да видите консолидирани данни за даден сегмент, като прегледате подробностите за него.</span><span class="sxs-lookup"><span data-stu-id="f643d-157">You can see consolidated data about a segment by reviewing its details.</span></span>

<span data-ttu-id="f643d-158">На страницата **Сегменти** изберете сегмента, който искате да прегледате.</span><span class="sxs-lookup"><span data-stu-id="f643d-158">On the **Segments** page, select the segment you want to review.</span></span>

<span data-ttu-id="f643d-159">Горната част на страницата включва графика на тенденциите, която визуализира промените в броя членове.</span><span class="sxs-lookup"><span data-stu-id="f643d-159">The upper part of the page includes a trend graph that visualizes changes in member count.</span></span> <span data-ttu-id="f643d-160">Задръжте курсора на мишката над точките от данни, за да видите броя членове за определена дата.</span><span class="sxs-lookup"><span data-stu-id="f643d-160">Hover over data points to see the member count on a specific date.</span></span>

<span data-ttu-id="f643d-161">Можете да актуализирате продължителността на визуализацията.</span><span class="sxs-lookup"><span data-stu-id="f643d-161">You can update the time frame of the visualization.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="f643d-162">![Времеви диапазон на сегмент](media/segment-time-range.png "Времеви диапазон на сегмент")</span><span class="sxs-lookup"><span data-stu-id="f643d-162">![Segment time range](media/segment-time-range.png "Segment time range")</span></span>

<span data-ttu-id="f643d-163">Долната част съдържа списък на членовете на сегмента.</span><span class="sxs-lookup"><span data-stu-id="f643d-163">The lower part contains a list of the segment members.</span></span>

> [!NOTE]
> <span data-ttu-id="f643d-164">Полетата, които се появяват в този списък, се основават на атрибутите на обектите на сегмента.</span><span class="sxs-lookup"><span data-stu-id="f643d-164">Fields that appear in this list are based on the attributes of your segment's entities.</span></span>
>
><span data-ttu-id="f643d-165">Списъкът е преглед на съпоставените членове на сегмента и показва първите 100 записа на сегмента, за да можете бързо да го оцените и да прегледате дефинициите му, ако е необходимо.</span><span class="sxs-lookup"><span data-stu-id="f643d-165">The list is a preview of the matching segment members and shows the first 100 records of your segment so that you can quickly evaluate it and review its definitions if needed.</span></span> <span data-ttu-id="f643d-166">За да видите всички съвпадащи записи, трябва да [експортирате сегмента](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="f643d-166">To see all matching records, you need to [export the segment](export-destinations.md).</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)] 
