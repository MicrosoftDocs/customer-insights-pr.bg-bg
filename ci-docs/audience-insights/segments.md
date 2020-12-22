---
title: Създаване и управление на сегменти
description: Създайте сегменти с клиенти, за да ги групирате въз основа на различни атрибути.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: 6931110c2ae93cd2792d319aa5a34f0df3088552
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405118"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="63ac0-103">Създаване и управление на сегменти</span><span class="sxs-lookup"><span data-stu-id="63ac0-103">Create and manage segments</span></span>

<span data-ttu-id="63ac0-104">Сегментите ви позволяват да групирате клиентите си въз основа на демографски, транзакционни или поведенчески атрибути.</span><span class="sxs-lookup"><span data-stu-id="63ac0-104">Segments let you group your customers based on demographic, transactional, or behavioral attributes.</span></span> <span data-ttu-id="63ac0-105">Можете да използвате сегменти за насочване на промоционални кампании, търговски дейности и действия за поддръжка на клиенти за постигане на вашите бизнес цели.</span><span class="sxs-lookup"><span data-stu-id="63ac0-105">You can use segments to target promotional campaigns, sales activities, and customer support actions to achieve your business goals.</span></span>

<span data-ttu-id="63ac0-106">Можете да дефинирате сложни филтри за обекта на клиентския профил и свързаните с него обекти.</span><span class="sxs-lookup"><span data-stu-id="63ac0-106">You can define complex filters around the Customer Profile entity and its related entities.</span></span> <span data-ttu-id="63ac0-107">Всеки сегмент след обработка създава набор от клиентски записи, които можете да експортирате и да предприемете действия по тях.</span><span class="sxs-lookup"><span data-stu-id="63ac0-107">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="63ac0-108">Някои [лимити за обслужване](service-limits.md) се прилагат.</span><span class="sxs-lookup"><span data-stu-id="63ac0-108">Some [service limits](service-limits.md) apply.</span></span>

<span data-ttu-id="63ac0-109">Освен ако не е посочено друго, всички сегменти са **Динамични сегменти**, които се обновяват по периодичен график.</span><span class="sxs-lookup"><span data-stu-id="63ac0-109">Unless stated otherwise, all segments are **Dynamic segments**, which are refreshed on a recurring schedule.</span></span>

<span data-ttu-id="63ac0-110">Следващият пример илюстрира способността за сегментиране.</span><span class="sxs-lookup"><span data-stu-id="63ac0-110">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="63ac0-111">Определихме сегмент за клиенти, които са поръчали стоки за поне 500 долара през последните 90 дни *и* които са участвали в обаждане за обслужване на клиенти, което е ескалирало.</span><span class="sxs-lookup"><span data-stu-id="63ac0-111">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="63ac0-112">![Няколко групи](media/segmentation-group1-2.png "Няколко групи")</span><span class="sxs-lookup"><span data-stu-id="63ac0-112">![Multiple groups](media/segmentation-group1-2.png "Multiple groups")</span></span>

## <a name="create-a-new-segment"></a><span data-ttu-id="63ac0-113">Създаване на нов сегмент</span><span class="sxs-lookup"><span data-stu-id="63ac0-113">Create a new segment</span></span>

<span data-ttu-id="63ac0-114">Сегментите се управляват на страницата **Сегменти**.</span><span class="sxs-lookup"><span data-stu-id="63ac0-114">Segments are managed on the **Segments** page.</span></span>

1. <span data-ttu-id="63ac0-115">В Аналитични данни за аудитория отидете на страницата **Сегменти**.</span><span class="sxs-lookup"><span data-stu-id="63ac0-115">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="63ac0-116">Изберете **Нов** > **Празен сегмент**.</span><span class="sxs-lookup"><span data-stu-id="63ac0-116">Select **New** > **Blank segment**.</span></span>

3. <span data-ttu-id="63ac0-117">В прозореца **Нов сегмент** изберете тип на сегмент и въведете **Име**.</span><span class="sxs-lookup"><span data-stu-id="63ac0-117">In the **New segment** pane, choose a segment type and provide a **Name**.</span></span>

   <span data-ttu-id="63ac0-118">По избор въведете показвано име и описание, които да помогнат за идентифицирането на сегмента.</span><span class="sxs-lookup"><span data-stu-id="63ac0-118">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

4. <span data-ttu-id="63ac0-119">Изберете **Напред**, за да преминете към страницата **Конструктор на сегменти**, където ще определите група.</span><span class="sxs-lookup"><span data-stu-id="63ac0-119">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="63ac0-120">Групата представлява набор от клиенти.</span><span class="sxs-lookup"><span data-stu-id="63ac0-120">A group is a set of customers.</span></span>

5. <span data-ttu-id="63ac0-121">Изберете обекта, който включва атрибута, по който искате да сегментирате.</span><span class="sxs-lookup"><span data-stu-id="63ac0-121">Choose the entity that includes the attribute you want to segment by.</span></span>

6. <span data-ttu-id="63ac0-122">Изберете атрибута, по който да се сегментира.</span><span class="sxs-lookup"><span data-stu-id="63ac0-122">Choose the attribute to segment by.</span></span> <span data-ttu-id="63ac0-123">Този атрибут може да има един от четирите типа стойности: числова, низ, дата или булева.</span><span class="sxs-lookup"><span data-stu-id="63ac0-123">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

7. <span data-ttu-id="63ac0-124">Изберете оператор и стойност за избрания атрибут.</span><span class="sxs-lookup"><span data-stu-id="63ac0-124">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="63ac0-125">![Персонализиран филтър на група](media/customer-group-numbers.png "Филтър на група клиенти")</span><span class="sxs-lookup"><span data-stu-id="63ac0-125">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="63ac0-126">Номер</span><span class="sxs-lookup"><span data-stu-id="63ac0-126">Number</span></span> |<span data-ttu-id="63ac0-127">Дефиниция</span><span class="sxs-lookup"><span data-stu-id="63ac0-127">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="63ac0-128">1</span><span class="sxs-lookup"><span data-stu-id="63ac0-128">1</span></span>     |<span data-ttu-id="63ac0-129">Entity</span><span class="sxs-lookup"><span data-stu-id="63ac0-129">Entity</span></span>          |
   |<span data-ttu-id="63ac0-130">2</span><span class="sxs-lookup"><span data-stu-id="63ac0-130">2</span></span>     |<span data-ttu-id="63ac0-131">Атрибут</span><span class="sxs-lookup"><span data-stu-id="63ac0-131">Attribute</span></span>          |
   |<span data-ttu-id="63ac0-132">3</span><span class="sxs-lookup"><span data-stu-id="63ac0-132">3</span></span>    |<span data-ttu-id="63ac0-133">Оператор</span><span class="sxs-lookup"><span data-stu-id="63ac0-133">Operator</span></span>         |
   |<span data-ttu-id="63ac0-134">4</span><span class="sxs-lookup"><span data-stu-id="63ac0-134">4</span></span>    |<span data-ttu-id="63ac0-135">Стойност</span><span class="sxs-lookup"><span data-stu-id="63ac0-135">Value</span></span>         |

8. <span data-ttu-id="63ac0-136">Ако обекта е свързан с унифицирания обект на клиент чрез [релации](relationships.md), трябва да определите пътя на релацията, за да създадете валиден сегмент.</span><span class="sxs-lookup"><span data-stu-id="63ac0-136">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="63ac0-137">Добавяйте обектите от пътя на релацията, докато можете да изберете обекта **Клиент: CustomerInsights** от падащото меню.</span><span class="sxs-lookup"><span data-stu-id="63ac0-137">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="63ac0-138">След това изберете **Всички записи** за всяко състояние.</span><span class="sxs-lookup"><span data-stu-id="63ac0-138">Then, choose **All records** for each condition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="63ac0-139">![Път на релация по време на създаване на сегмент](media/segments-multiple-relationships.png "Път на релация по време на създаване на сегмент")</span><span class="sxs-lookup"><span data-stu-id="63ac0-139">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

9. <span data-ttu-id="63ac0-140">Изберете **Записване**, за да запишете сегмента.</span><span class="sxs-lookup"><span data-stu-id="63ac0-140">Select **Save** to save your segment.</span></span> <span data-ttu-id="63ac0-141">Сегментът ще бъде записан и обработен, ако всички изисквания са потвърдени.</span><span class="sxs-lookup"><span data-stu-id="63ac0-141">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="63ac0-142">В противен случай ще бъде записан като чернова.</span><span class="sxs-lookup"><span data-stu-id="63ac0-142">Otherwise, it will be saved as a draft.</span></span>

10. <span data-ttu-id="63ac0-143">Изберете **Обратно към сегментите**, за да се върна на страницата **Сегменти**.</span><span class="sxs-lookup"><span data-stu-id="63ac0-143">Select **Back to segments** to go back to the **Segments** page.</span></span>

## <a name="manage-existing-segments"></a><span data-ttu-id="63ac0-144">Управление на съществуващи сегменти</span><span class="sxs-lookup"><span data-stu-id="63ac0-144">Manage existing segments</span></span>

<span data-ttu-id="63ac0-145">На страницата **Сегменти** можете да видите всички записани сегменти и да ги управлявате.</span><span class="sxs-lookup"><span data-stu-id="63ac0-145">On the **Segments** page, you can view all your saved segments and manage them.</span></span>

<span data-ttu-id="63ac0-146">Всеки сегмент е представен от ред, който включва допълнителна информация за сегмента.</span><span class="sxs-lookup"><span data-stu-id="63ac0-146">Each segment is represented by a row that includes additional information about the segment.</span></span>

<span data-ttu-id="63ac0-147">Можете да сортирате сегментите в колона, като изберете заглавието на колоната.</span><span class="sxs-lookup"><span data-stu-id="63ac0-147">You can sort the segments in a column by selecting the column heading.</span></span>

<span data-ttu-id="63ac0-148">Използвайте полето **Търсене** в горния десен ъгъл, за да филтрирате сегментите.</span><span class="sxs-lookup"><span data-stu-id="63ac0-148">Use the **Search** box in the top-right corner to filter the segments.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="63ac0-149">![Опции за управление на съществуващ сегмент](media/segments-selected-segment.png "Опции за управление на съществуващ сегмент")</span><span class="sxs-lookup"><span data-stu-id="63ac0-149">![Options to manage an existing segment](media/segments-selected-segment.png "Options to manage an existing segment")</span></span>

<span data-ttu-id="63ac0-150">Следното действие е достъпно, когато изберете сегмент:</span><span class="sxs-lookup"><span data-stu-id="63ac0-150">The following action are available when you select a segment:</span></span>

- <span data-ttu-id="63ac0-151">**Прегледайте** подробностите за сегмента, включително тенденцията за броя на членовете, преглед на членовете на сегмента.</span><span class="sxs-lookup"><span data-stu-id="63ac0-151">**View** the segment details, including member count trend a preview of segment members.</span></span>
- <span data-ttu-id="63ac0-152">**Редактирайте** сегмента, за да промените свойствата.</span><span class="sxs-lookup"><span data-stu-id="63ac0-152">**Edit** the segment to change its properties.</span></span>
- <span data-ttu-id="63ac0-153">**Обновете** сегмента, за да включва най-новите данни.</span><span class="sxs-lookup"><span data-stu-id="63ac0-153">**Refresh** the segment to include the latest data.</span></span>
- <span data-ttu-id="63ac0-154">**Активирайте** или **деактивирайте** сегмента.</span><span class="sxs-lookup"><span data-stu-id="63ac0-154">**Activate** or **Deactivate** the segment.</span></span> <span data-ttu-id="63ac0-155">Сегментите имат две възможни състояния – активно или неактивно.</span><span class="sxs-lookup"><span data-stu-id="63ac0-155">Segments have two possible states - active or inactive.</span></span> <span data-ttu-id="63ac0-156">Тези състояния са полезни при редактиране на сегмент.</span><span class="sxs-lookup"><span data-stu-id="63ac0-156">These states come in handy when editing a segment.</span></span> <span data-ttu-id="63ac0-157">За неактивни сегменти дефиницията на сегмента съществува, но все още не съдържа клиенти.</span><span class="sxs-lookup"><span data-stu-id="63ac0-157">For inactive segments, the segment definition exists but it doesn't contain any customers yet.</span></span> <span data-ttu-id="63ac0-158">Когато активирате сегмент, състоянието му се променя от „неактивно“ на „активно“ и той започва да търси клиенти, които съответстват на дефиницията на сегмента.</span><span class="sxs-lookup"><span data-stu-id="63ac0-158">When you activate a segment, its state changes from 'inactive' to 'active" and it starts looking for customers that match the segment definition.</span></span> <span data-ttu-id="63ac0-159">Ако е конфигурирано [планирано обновяване](system.md#schedule-tab), неактивните сегменти имат **Състояние**, посочено като **Пропуснато**, което показва, че дори не е бил направен опит за обновяване.</span><span class="sxs-lookup"><span data-stu-id="63ac0-159">If a [scheduled refresh](system.md#schedule-tab) is configured, inactive segments have the **Status** listed as **Skipped**, indicating that a refresh wasn't even attempted.</span></span> <span data-ttu-id="63ac0-160">Когато се активира неактивен сегмент, той ще се обнови и ще бъде включен в планираните обновявания.</span><span class="sxs-lookup"><span data-stu-id="63ac0-160">When an inactive segment is activated, it will refresh and will be included in scheduled refreshes.</span></span>
  <span data-ttu-id="63ac0-161">Като алтернатива можете да използвате функционалността **Планиране по-късно** в падащия списък **Активиране/деактивиране**, за да посочите бъдеща дата и час за активиране и деактивиране на определен сегмент.</span><span class="sxs-lookup"><span data-stu-id="63ac0-161">Alternatively, you can use the **Schedule later** functionality in the **Activate/Deactivate** dropdown to specify a future date and time for activation and deactivation of a particular segment.</span></span>
- <span data-ttu-id="63ac0-162">**Преименувайте** сегмента.</span><span class="sxs-lookup"><span data-stu-id="63ac0-162">**Rename** the segment.</span></span>
- <span data-ttu-id="63ac0-163">**Изтеглете** списъка с членове като .CSV файл.</span><span class="sxs-lookup"><span data-stu-id="63ac0-163">**Download** the list of members as a .CSV file.</span></span>
- <span data-ttu-id="63ac0-164">Опцията **Добавяне към** изпраща списъка с идентификатори на клиенти в сегмента за обработка в друго приложение.</span><span class="sxs-lookup"><span data-stu-id="63ac0-164">**Add to** option sends the list of customer IDs in the segment for processing in another application.</span></span>
- <span data-ttu-id="63ac0-165">**Изтриване** на сегмента.</span><span class="sxs-lookup"><span data-stu-id="63ac0-165">**Delete** the segment.</span></span>

## <a name="refresh-segments"></a><span data-ttu-id="63ac0-166">Обновяване на сегменти</span><span class="sxs-lookup"><span data-stu-id="63ac0-166">Refresh segments</span></span>

<span data-ttu-id="63ac0-167">Можете да опресните всички сегменти наведнъж, като изберете **Обновяване на всички** на страницата **Сегменти**, или можете да опресните един или няколко сегмента, когато ги изберете и изберете **Обновяване** от опциите.</span><span class="sxs-lookup"><span data-stu-id="63ac0-167">You can refresh all segments at once by selecting **Refresh all** on the **Segments** page or you can refresh one or multiple segments when you select them and choose **Refresh** in from the options.</span></span> <span data-ttu-id="63ac0-168">Освен това можете да конфигурирате повтарящо се обновяване в **Администриране** > **Система** > **График**.</span><span class="sxs-lookup"><span data-stu-id="63ac0-168">Alternatively, you can configure a recurring refresh on **Admin** > **System** > **Schedule**.</span></span>

> [!TIP]
> <span data-ttu-id="63ac0-169">Съществуват [шест вида статус](system.md#status-types) на задачите/процесите.</span><span class="sxs-lookup"><span data-stu-id="63ac0-169">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="63ac0-170">Освен това повечето процеси [зависят от други процеси надолу по веригата](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="63ac0-170">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="63ac0-171">Можете да изберете състоянието на процес, за да видите подробности за напредъка на цялата задача.</span><span class="sxs-lookup"><span data-stu-id="63ac0-171">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="63ac0-172">След като изберете **Вижте подробности** за една от задачите на заданието, ще намерите допълнителна информация: време за обработка, дата на последната обработка и всички грешки и предупреждения, свързани със задачата.</span><span class="sxs-lookup"><span data-stu-id="63ac0-172">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="download-and-export-segments"></a><span data-ttu-id="63ac0-173">Изтегляне и експортиране на сегменти</span><span class="sxs-lookup"><span data-stu-id="63ac0-173">Download and export segments</span></span>

<span data-ttu-id="63ac0-174">Можете да изтеглите сегментите в CSV файл или да ги експортирате в Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="63ac0-174">You can download your segments to a CSV file or export them to Dynamics 365 Sales.</span></span>

### <a name="download-segments-to-a-csv-file"></a><span data-ttu-id="63ac0-175">Изтегляне на сегменти в CSV файл</span><span class="sxs-lookup"><span data-stu-id="63ac0-175">Download segments to a CSV file</span></span>

1. <span data-ttu-id="63ac0-176">В Аналитични данни за аудитория отидете на страницата **Сегменти**.</span><span class="sxs-lookup"><span data-stu-id="63ac0-176">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="63ac0-177">Изберете многоточието в определена плочка сегмент.</span><span class="sxs-lookup"><span data-stu-id="63ac0-177">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="63ac0-178">Изберете **Изтегляне като CSV** от падащия списък с действия.</span><span class="sxs-lookup"><span data-stu-id="63ac0-178">Select **Download as CSV** from the actions drop-down list.</span></span>

### <a name="export-segments-to-dynamics-365-sales"></a><span data-ttu-id="63ac0-179">Експортиране на сегменти в Dynamics 365 Sales</span><span class="sxs-lookup"><span data-stu-id="63ac0-179">Export segments to Dynamics 365 Sales</span></span>

<span data-ttu-id="63ac0-180">Преди да експортирате сегменти в Dynamics 365 Sales, администраторът трябва да [създаде местоназначение за експортиране](export-destinations.md) за Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="63ac0-180">Before exporting segments to Dynamics 365 Sales, an admin needs to [create the export destination](export-destinations.md) for Dynamics 365 Sales.</span></span>

1. <span data-ttu-id="63ac0-181">В Аналитични данни за аудитория отидете на страницата **Сегменти**.</span><span class="sxs-lookup"><span data-stu-id="63ac0-181">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="63ac0-182">Изберете многоточието в определена плочка сегмент.</span><span class="sxs-lookup"><span data-stu-id="63ac0-182">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="63ac0-183">Изберете **Добавяне към** от падащия списък с действия и изберете местоназначението за експортиране, в което искате да изпратите данните.</span><span class="sxs-lookup"><span data-stu-id="63ac0-183">Select **Add to** from the actions drop-down list and select the export destination you want to send the data to.</span></span>

## <a name="draft-mode-for-segments"></a><span data-ttu-id="63ac0-184">Режим на чернова за сегменти</span><span class="sxs-lookup"><span data-stu-id="63ac0-184">Draft mode for segments</span></span>

<span data-ttu-id="63ac0-185">Ако не са изпълнени всички изисквания за обработка на сегмент, можете да запишете сегмента като чернова и да получите достъп до него от страницата **Сегменти**.</span><span class="sxs-lookup"><span data-stu-id="63ac0-185">If not all requirements to process a segment are met, you can save the segment as a draft and access it from the **Segments** page.</span></span>

<span data-ttu-id="63ac0-186">Той ще се запише като неактивен сегмент и не може да се активира, докато не стане валиден.</span><span class="sxs-lookup"><span data-stu-id="63ac0-186">It will be saved as an inactive segment, and can't be activated it until it's valid.</span></span>

## <a name="add-more-conditions-to-a-group"></a><span data-ttu-id="63ac0-187">Добавяне на още условия към група</span><span class="sxs-lookup"><span data-stu-id="63ac0-187">Add more conditions to a group</span></span>

<span data-ttu-id="63ac0-188">За да добавите още условия към група, можете да използвате два логически оператора:</span><span class="sxs-lookup"><span data-stu-id="63ac0-188">To add more conditions to a group, you can use two logical operators:</span></span>

- <span data-ttu-id="63ac0-189">Оператор **И**: И двете условия трябва да бъдат изпълнени като част от процеса на сегментиране.</span><span class="sxs-lookup"><span data-stu-id="63ac0-189">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="63ac0-190">Тази опция е най-полезна, когато дефинирате условия за различни обекти.</span><span class="sxs-lookup"><span data-stu-id="63ac0-190">This option is most useful when you define conditions across different entities.</span></span>

- <span data-ttu-id="63ac0-191">Оператор **ИЛИ**: Едно от условията трябва да бъде изпълнено като част от процеса на сегментиране.</span><span class="sxs-lookup"><span data-stu-id="63ac0-191">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="63ac0-192">Тази опция е най-полезна, когато дефинирате няколко условия за един и същи обект.</span><span class="sxs-lookup"><span data-stu-id="63ac0-192">This option is most useful when you define multiple conditions for the same entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="63ac0-193">![Оператор ИЛИ, където трябва да бъде изпълнено едно от условията](media/segmentation-either-condition.png "Оператор ИЛИ, където трябва да бъде изпълнено едно от условията")</span><span class="sxs-lookup"><span data-stu-id="63ac0-193">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

<span data-ttu-id="63ac0-194">В момента е възможно да се вложи оператор **ИЛИ** под оператор **И**, но не и обратното.</span><span class="sxs-lookup"><span data-stu-id="63ac0-194">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

## <a name="combine-multiple-groups"></a><span data-ttu-id="63ac0-195">Комбиниране на няколко групи</span><span class="sxs-lookup"><span data-stu-id="63ac0-195">Combine multiple groups</span></span>

<span data-ttu-id="63ac0-196">Всяка група произвежда определен набор от клиенти.</span><span class="sxs-lookup"><span data-stu-id="63ac0-196">Each group produces a specific set of customers.</span></span> <span data-ttu-id="63ac0-197">Можете да комбинирате тези групи, за да включите клиентите, необходими за бизнес случая.</span><span class="sxs-lookup"><span data-stu-id="63ac0-197">You can combine these groups to include the customers required for your business case.</span></span>

1. <span data-ttu-id="63ac0-198">В статията за аудиторията отидете на страницата **Сегменти** и изберете сегмент.</span><span class="sxs-lookup"><span data-stu-id="63ac0-198">In audience insights, go to the **Segments** page and select a segment.</span></span>

2. <span data-ttu-id="63ac0-199">Изберете **Добавяне на група**.</span><span class="sxs-lookup"><span data-stu-id="63ac0-199">Select **Add Group**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="63ac0-200">![Добавяне на група за група клиенти](media/customer-group-add-group.png "Добавяне на група за група клиенти")</span><span class="sxs-lookup"><span data-stu-id="63ac0-200">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

3. <span data-ttu-id="63ac0-201">Изберете един от следните оператори: **Обединяване**, **Пресичане** или **Освен**.</span><span class="sxs-lookup"><span data-stu-id="63ac0-201">Select one of the following set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="63ac0-202">![Добавяне на обединяване за група клиенти](media/customer-group-union.png "Добавяне на обединяване за група клиенти")</span><span class="sxs-lookup"><span data-stu-id="63ac0-202">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   <span data-ttu-id="63ac0-203">Изберете зададен оператор, за да дефинирате нова група.</span><span class="sxs-lookup"><span data-stu-id="63ac0-203">Select a set operator to define a new group.</span></span> <span data-ttu-id="63ac0-204">Записване на различни групи за определяне на това какви данни се запазват:</span><span class="sxs-lookup"><span data-stu-id="63ac0-204">Save different groups to determine what data gets retained:</span></span>

   - <span data-ttu-id="63ac0-205">**Обединяването** съединява двете групи.</span><span class="sxs-lookup"><span data-stu-id="63ac0-205">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="63ac0-206">**Пресичането** припокрива двете групи.</span><span class="sxs-lookup"><span data-stu-id="63ac0-206">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="63ac0-207">Само данни, които *са често срещани* в двете групи, се задържат в единната група.</span><span class="sxs-lookup"><span data-stu-id="63ac0-207">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="63ac0-208">**Освен** комбинира двете групи.</span><span class="sxs-lookup"><span data-stu-id="63ac0-208">**Except** combines the two groups.</span></span> <span data-ttu-id="63ac0-209">Само данни в група А, които *не са често срещани* за данните в група B, се задържат.</span><span class="sxs-lookup"><span data-stu-id="63ac0-209">Only data in group A that *is not common* to data in group B is retained.</span></span>

## <a name="view-processing-history-and-segment-members"></a><span data-ttu-id="63ac0-210">Преглед на хронологията на обработката и членовете на сегмента</span><span class="sxs-lookup"><span data-stu-id="63ac0-210">View processing history and segment members</span></span>

<span data-ttu-id="63ac0-211">Можете да видите консолидирани данни за даден сегмент, като прегледате подробностите за него.</span><span class="sxs-lookup"><span data-stu-id="63ac0-211">You can see consolidated data about a segment by reviewing its details.</span></span>

<span data-ttu-id="63ac0-212">На страницата **Сегменти** изберете сегмента, който искате да прегледате.</span><span class="sxs-lookup"><span data-stu-id="63ac0-212">On the **Segments** page, select the segment you want to review.</span></span>

<span data-ttu-id="63ac0-213">Горната част на страницата включва графика на тенденциите, която визуализира промените в броя членове.</span><span class="sxs-lookup"><span data-stu-id="63ac0-213">The upper part of the page includes a trend graph that visualizes changes in member count.</span></span> <span data-ttu-id="63ac0-214">Задръжте курсора на мишката над точките от данни, за да видите броя членове за определена дата.</span><span class="sxs-lookup"><span data-stu-id="63ac0-214">Hover over data points to see the member count on a specific date.</span></span>

<span data-ttu-id="63ac0-215">Можете да актуализирате продължителността на визуализацията.</span><span class="sxs-lookup"><span data-stu-id="63ac0-215">You can update the time frame of the visualization.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="63ac0-216">![Времеви диапазон на сегмент](media/segment-time-range.png "Времеви диапазон на сегмент")</span><span class="sxs-lookup"><span data-stu-id="63ac0-216">![Segment time range](media/segment-time-range.png "Segment time range")</span></span>

<span data-ttu-id="63ac0-217">Долната част съдържа списък на членовете на сегмента.</span><span class="sxs-lookup"><span data-stu-id="63ac0-217">The lower part contains a list of the segment members.</span></span>

> [!NOTE]
> <span data-ttu-id="63ac0-218">Полетата, които се появяват в този списък, се основават на атрибутите на обектите на сегмента.</span><span class="sxs-lookup"><span data-stu-id="63ac0-218">Fields that appear in this list are based on the attributes of your segment's entities.</span></span>
>
><span data-ttu-id="63ac0-219">Списъкът е преглед на съпоставените членове на сегмента и показва първите 100 записа на сегмента, за да можете бързо да го оцените и да прегледате дефинициите му, ако е необходимо.</span><span class="sxs-lookup"><span data-stu-id="63ac0-219">The list is a preview of the matching segment members and shows the first 100 records of your segment so that you can quickly evaluate it and review its definitions if needed.</span></span> <span data-ttu-id="63ac0-220">За да видите всички съвпадащи записи, трябва да [експортирате сегмента](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="63ac0-220">To see all matching records, you need to [export the segment](export-destinations.md).</span></span>

## <a name="quick-segments"></a><span data-ttu-id="63ac0-221">Бързи сегменти</span><span class="sxs-lookup"><span data-stu-id="63ac0-221">Quick segments</span></span>

<span data-ttu-id="63ac0-222">В допълнение към конструктора на сегменти, има и друг път за създаване на сегменти.</span><span class="sxs-lookup"><span data-stu-id="63ac0-222">In addition to the segment builder, there's another path for creating segments.</span></span> <span data-ttu-id="63ac0-223">Бързите сегменти ви позволяват да изграждате прости сегменти с един оператор бързо и с незабавни прозрения.</span><span class="sxs-lookup"><span data-stu-id="63ac0-223">Quick segments let you build simple segments with a single operator quickly and with instant insights.</span></span>

1. <span data-ttu-id="63ac0-224">На страницата **Сегменти** изберете **Нов** > **Бързо създаване от**.</span><span class="sxs-lookup"><span data-stu-id="63ac0-224">On the **Segments** page, select **New** > **Quickly create from**.</span></span>

   - <span data-ttu-id="63ac0-225">Изберете опцията **Профили** за изграждане на сегмент, който се основава на унифицирания обект на клиент.</span><span class="sxs-lookup"><span data-stu-id="63ac0-225">Select the **Profiles** option to build a segment that is based on the unified Customer entity.</span></span>
   - <span data-ttu-id="63ac0-226">Изберете опцията **Мерки** за създаване на сегмент по всеки тип мярка на атрибут на клиент, който предварително сте създали в страницата **Мерки**.</span><span class="sxs-lookup"><span data-stu-id="63ac0-226">Select the **Measures** option to build a segment around each of the Customer Attribute type of measures you have previously created on the **Measures** page.</span></span>
   - <span data-ttu-id="63ac0-227">Изберете опцията **Разузнаване** за изграждане на сегмент по един от изходните обекти, който генерирахте чрез възможностите **Прогнози** или **Персонализирани модели**.</span><span class="sxs-lookup"><span data-stu-id="63ac0-227">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="63ac0-228">В диалоговия прозорец **Нов бърз сегмент** изберете атрибут от падащия списък **Поле**.</span><span class="sxs-lookup"><span data-stu-id="63ac0-228">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="63ac0-229">Системата ще предостави някои допълнителни аналитични данни, които ще ви помогнат да създадете по-добри сегменти за клиентите.</span><span class="sxs-lookup"><span data-stu-id="63ac0-229">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="63ac0-230">За полета на категории ще покажем 10-те най-добри клиенти.</span><span class="sxs-lookup"><span data-stu-id="63ac0-230">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="63ac0-231">Изберете **Стойност** и след това **Преглед**.</span><span class="sxs-lookup"><span data-stu-id="63ac0-231">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="63ac0-232">За числов атрибут системата ще покаже каква стойност на атрибута попада в рамките на процентила на всеки клиент.</span><span class="sxs-lookup"><span data-stu-id="63ac0-232">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="63ac0-233">Изберете **Оператор** и **Стойност**, след което изберете **Преглед**.</span><span class="sxs-lookup"><span data-stu-id="63ac0-233">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="63ac0-234">Системата ще ви предостави **Прогнозен размер на сегмента**.</span><span class="sxs-lookup"><span data-stu-id="63ac0-234">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="63ac0-235">Можете да изберете дали да генерирате определения от вас сегмент или първо да го преразгледате, за да получите различен размер на сегмента.</span><span class="sxs-lookup"><span data-stu-id="63ac0-235">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="63ac0-236">![Име и оценка за бърз сегмент](media/quick-segment-name.png "Име и оценка за бърз сегмент")</span><span class="sxs-lookup"><span data-stu-id="63ac0-236">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="63ac0-237">Посочете **Име** за сегмента.</span><span class="sxs-lookup"><span data-stu-id="63ac0-237">Provide a **Name** for your segment.</span></span> <span data-ttu-id="63ac0-238">По избор въведете **Показвано име**.</span><span class="sxs-lookup"><span data-stu-id="63ac0-238">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="63ac0-239">Изберете **Записване**, за да създадете сегмента.</span><span class="sxs-lookup"><span data-stu-id="63ac0-239">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="63ac0-240">След като обработката на сегмента завърши, можете да го прегледате като всеки друг сегмент, който сте създали.</span><span class="sxs-lookup"><span data-stu-id="63ac0-240">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

<span data-ttu-id="63ac0-241">За следните сценарии съветваме да използваме конструктора на сегменти, а не препоръчителните възможности за сегменти:</span><span class="sxs-lookup"><span data-stu-id="63ac0-241">For the following scenarios, we advise using the segment builder rather than the recommended segments capability:</span></span>

- <span data-ttu-id="63ac0-242">Създаване на сегменти с филтри на полета за категории, където операторът е различен от оператора **Е**</span><span class="sxs-lookup"><span data-stu-id="63ac0-242">Creating segments with filters on categorical fields where the operator is different than the **Is** operator</span></span>
- <span data-ttu-id="63ac0-243">Създаване на сегменти с филтри в числови полета, където операторът е различен от операторите **Между**, **По-голямо от** и **По-малко от**</span><span class="sxs-lookup"><span data-stu-id="63ac0-243">Creating segments with filters on numerical fields where the operator is different than the **Between**, **Greater than**, and **Less than** operators</span></span>
- <span data-ttu-id="63ac0-244">Създаване на сегменти с филтри на полета от тип дата</span><span class="sxs-lookup"><span data-stu-id="63ac0-244">Creating segments with filters on date type fields</span></span>

## <a name="next-steps"></a><span data-ttu-id="63ac0-245">Следващи стъпки</span><span class="sxs-lookup"><span data-stu-id="63ac0-245">Next steps</span></span>

<span data-ttu-id="63ac0-246">[Експортирайте сегмент](export-destinations.md) и разгледайте [картата на клиента](customer-card-add-in.md) и [конекторите](export-power-bi.md), за да получите аналитични данни на ниво клиент.</span><span class="sxs-lookup"><span data-stu-id="63ac0-246">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>
