---
title: Създаване и управление на сегменти
description: Създайте сегменти с клиенти, за да ги групирате въз основа на различни атрибути.
ms.date: 03/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 4a6e8a3216a2c0738d60247054afa9fc18412f55
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597038"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="042d1-103">Създаване и управление на сегменти</span><span class="sxs-lookup"><span data-stu-id="042d1-103">Create and manage segments</span></span>

<span data-ttu-id="042d1-104">Сегментите ви позволяват да групирате клиентите си въз основа на демографски, транзакционни или поведенчески атрибути.</span><span class="sxs-lookup"><span data-stu-id="042d1-104">Segments let you group your customers based on demographic, transactional, or behavioral attributes.</span></span> <span data-ttu-id="042d1-105">Можете да използвате сегменти за насочване на промоционални кампании, търговски дейности и действия за поддръжка на клиенти за постигане на вашите бизнес цели.</span><span class="sxs-lookup"><span data-stu-id="042d1-105">You can use segments to target promotional campaigns, sales activities, and customer support actions to achieve your business goals.</span></span>

<span data-ttu-id="042d1-106">Можете да дефинирате сложни филтри за обекта на клиентския профил и свързаните с него обекти.</span><span class="sxs-lookup"><span data-stu-id="042d1-106">You can define complex filters around the Customer Profile entity and its related entities.</span></span> <span data-ttu-id="042d1-107">Всеки сегмент след обработка създава набор от клиентски записи, които можете да експортирате и да предприемете действия по тях.</span><span class="sxs-lookup"><span data-stu-id="042d1-107">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="042d1-108">Някои [лимити за обслужване](service-limits.md) се прилагат.</span><span class="sxs-lookup"><span data-stu-id="042d1-108">Some [service limits](service-limits.md) apply.</span></span>

<span data-ttu-id="042d1-109">Освен ако не е посочено друго, всички сегменти са **Динамични сегменти**, които се обновяват по периодичен график.</span><span class="sxs-lookup"><span data-stu-id="042d1-109">Unless stated otherwise, all segments are **Dynamic segments**, which are refreshed on a recurring schedule.</span></span>

<span data-ttu-id="042d1-110">Следващият пример илюстрира способността за сегментиране.</span><span class="sxs-lookup"><span data-stu-id="042d1-110">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="042d1-111">Определихме сегмент за клиенти, които са поръчали стоки за поне 500 долара през последните 90 дни *и* които са участвали в обаждане за обслужване на клиенти, което е ескалирало.</span><span class="sxs-lookup"><span data-stu-id="042d1-111">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="042d1-112">![Няколко групи](media/segmentation-group1-2.png "Няколко групи")</span><span class="sxs-lookup"><span data-stu-id="042d1-112">![Multiple groups](media/segmentation-group1-2.png "Multiple groups")</span></span>

## <a name="create-a-new-segment"></a><span data-ttu-id="042d1-113">Създаване на нов сегмент</span><span class="sxs-lookup"><span data-stu-id="042d1-113">Create a new segment</span></span>

<span data-ttu-id="042d1-114">Сегментите се управляват на страницата **Сегменти**.</span><span class="sxs-lookup"><span data-stu-id="042d1-114">Segments are managed on the **Segments** page.</span></span>

1. <span data-ttu-id="042d1-115">В Аналитични данни за аудитория отидете на страницата **Сегменти**.</span><span class="sxs-lookup"><span data-stu-id="042d1-115">In audience insights, go to the **Segments** page.</span></span>

1. <span data-ttu-id="042d1-116">Изберете **Нов** > **Празен сегмент**.</span><span class="sxs-lookup"><span data-stu-id="042d1-116">Select **New** > **Blank segment**.</span></span>

1. <span data-ttu-id="042d1-117">В прозореца **Нов сегмент** изберете тип на сегмент и въведете **Име**.</span><span class="sxs-lookup"><span data-stu-id="042d1-117">In the **New segment** pane, choose a segment type and provide a **Name**.</span></span>

   <span data-ttu-id="042d1-118">По избор въведете показвано име и описание, които да помогнат за идентифицирането на сегмента.</span><span class="sxs-lookup"><span data-stu-id="042d1-118">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

1. <span data-ttu-id="042d1-119">Изберете **Напред**, за да преминете към страницата **Конструктор на сегменти**, където ще определите група.</span><span class="sxs-lookup"><span data-stu-id="042d1-119">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="042d1-120">Групата представлява набор от клиенти.</span><span class="sxs-lookup"><span data-stu-id="042d1-120">A group is a set of customers.</span></span>

1. <span data-ttu-id="042d1-121">Изберете обекта, който включва атрибута, по който искате да сегментирате.</span><span class="sxs-lookup"><span data-stu-id="042d1-121">Choose the entity that includes the attribute you want to segment by.</span></span>

1. <span data-ttu-id="042d1-122">Изберете атрибута, по който да се сегментира.</span><span class="sxs-lookup"><span data-stu-id="042d1-122">Choose the attribute to segment by.</span></span> <span data-ttu-id="042d1-123">Този атрибут може да има един от четирите типа стойности: числова, низ, дата или булева.</span><span class="sxs-lookup"><span data-stu-id="042d1-123">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

1. <span data-ttu-id="042d1-124">Изберете оператор и стойност за избрания атрибут.</span><span class="sxs-lookup"><span data-stu-id="042d1-124">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="042d1-125">![Персонализиран филтър на група](media/customer-group-numbers.png "Филтър на група клиенти")</span><span class="sxs-lookup"><span data-stu-id="042d1-125">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="042d1-126">Номер</span><span class="sxs-lookup"><span data-stu-id="042d1-126">Number</span></span> |<span data-ttu-id="042d1-127">Дефиниция</span><span class="sxs-lookup"><span data-stu-id="042d1-127">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="042d1-128">1</span><span class="sxs-lookup"><span data-stu-id="042d1-128">1</span></span>     |<span data-ttu-id="042d1-129">Entity</span><span class="sxs-lookup"><span data-stu-id="042d1-129">Entity</span></span>          |
   |<span data-ttu-id="042d1-130">2</span><span class="sxs-lookup"><span data-stu-id="042d1-130">2</span></span>     |<span data-ttu-id="042d1-131">Атрибут</span><span class="sxs-lookup"><span data-stu-id="042d1-131">Attribute</span></span>          |
   |<span data-ttu-id="042d1-132">3</span><span class="sxs-lookup"><span data-stu-id="042d1-132">3</span></span>    |<span data-ttu-id="042d1-133">Оператор</span><span class="sxs-lookup"><span data-stu-id="042d1-133">Operator</span></span>         |
   |<span data-ttu-id="042d1-134">4</span><span class="sxs-lookup"><span data-stu-id="042d1-134">4</span></span>    |<span data-ttu-id="042d1-135">Стойност</span><span class="sxs-lookup"><span data-stu-id="042d1-135">Value</span></span>         |

8. <span data-ttu-id="042d1-136">Ако обекта е свързан с унифицирания обект на клиент чрез [релации](relationships.md), трябва да определите пътя на релацията, за да създадете валиден сегмент.</span><span class="sxs-lookup"><span data-stu-id="042d1-136">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="042d1-137">Добавяйте обектите от пътя на релацията, докато можете да изберете обекта **Клиент: CustomerInsights** от падащото меню.</span><span class="sxs-lookup"><span data-stu-id="042d1-137">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="042d1-138">След това изберете **Всички записи** за всяко състояние.</span><span class="sxs-lookup"><span data-stu-id="042d1-138">Then, choose **All records** for each condition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="042d1-139">![Път на релация по време на създаване на сегмент](media/segments-multiple-relationships.png "Път на релация по време на създаване на сегмент")</span><span class="sxs-lookup"><span data-stu-id="042d1-139">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

1. <span data-ttu-id="042d1-140">По подразбиране сегментите генерират изходен обект, който съдържа всички атрибути на клиентски профили, които съответстват на дефинираните филтри.</span><span class="sxs-lookup"><span data-stu-id="042d1-140">By default, segments generate an output entity that contains all attributes of customer profiles which match the defined filters.</span></span> <span data-ttu-id="042d1-141">Ако сегментът се основава на други обекти, различни от обект *Клиент*, можете да добавите още атрибути от тези обекти към изходния обект.</span><span class="sxs-lookup"><span data-stu-id="042d1-141">If a segment is based on other entities than the *Customer* entity, you can add more attributes from these entities to the output entity.</span></span> <span data-ttu-id="042d1-142">Изберете **Атрибути на проекта**, за да изберете атрибутите, които ще бъдат добавени към изходния обект.</span><span class="sxs-lookup"><span data-stu-id="042d1-142">Select **Project attributes** to choose the attributes that will be appended to the output entity.</span></span>  

   
   <span data-ttu-id="042d1-143">Пример: Сегментът се основава на обект, който съдържа данни за активността на клиентите, които са свързани с обект *Клиент*.</span><span class="sxs-lookup"><span data-stu-id="042d1-143">Example: A segment is based on an entity that contains customer activity data which is related to the *Customer* entity.</span></span> <span data-ttu-id="042d1-144">Сегментът търси всички клиенти, които са се обадили в бюрото за помощ през последните 60 дни.</span><span class="sxs-lookup"><span data-stu-id="042d1-144">The segment looks for all customers that called the help desk in the last 60 days.</span></span> <span data-ttu-id="042d1-145">Можете да изберете да добавите продължителността на разговора и броя на обажданията към всички съвпадащи клиентски записи в изходния обект.</span><span class="sxs-lookup"><span data-stu-id="042d1-145">You can choose to append the call duration and the number of calls to all matching customer records in the output entity.</span></span> <span data-ttu-id="042d1-146">Тази информация може да е полезна за изпращане на имейл с полезни връзки към онлайн помощни статии и често задавани въпроси на клиенти, които често са се обаждали.</span><span class="sxs-lookup"><span data-stu-id="042d1-146">This information might be useful to send an email with helpful links to online help articles and FAQs to customers who called frequently.</span></span>

1. <span data-ttu-id="042d1-147">Изберете **Записване**, за да запишете сегмента.</span><span class="sxs-lookup"><span data-stu-id="042d1-147">Select **Save** to save your segment.</span></span> <span data-ttu-id="042d1-148">Сегментът ще бъде записан и обработен, ако всички изисквания са потвърдени.</span><span class="sxs-lookup"><span data-stu-id="042d1-148">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="042d1-149">В противен случай ще бъде записан като чернова.</span><span class="sxs-lookup"><span data-stu-id="042d1-149">Otherwise, it will be saved as a draft.</span></span>

1. <span data-ttu-id="042d1-150">Изберете **Обратно към сегментите**, за да се върна на страницата **Сегменти**.</span><span class="sxs-lookup"><span data-stu-id="042d1-150">Select **Back to segments** to go back to the **Segments** page.</span></span>

## <a name="manage-existing-segments"></a><span data-ttu-id="042d1-151">Управление на съществуващи сегменти</span><span class="sxs-lookup"><span data-stu-id="042d1-151">Manage existing segments</span></span>

<span data-ttu-id="042d1-152">На страницата **Сегменти** можете да видите всички записани сегменти и да ги управлявате.</span><span class="sxs-lookup"><span data-stu-id="042d1-152">On the **Segments** page, you can view all your saved segments and manage them.</span></span>

<span data-ttu-id="042d1-153">Всеки сегмент е представен от ред, който включва допълнителна информация за сегмента.</span><span class="sxs-lookup"><span data-stu-id="042d1-153">Each segment is represented by a row that includes additional information about the segment.</span></span>

<span data-ttu-id="042d1-154">Можете да сортирате сегментите в колона, като изберете заглавието на колоната.</span><span class="sxs-lookup"><span data-stu-id="042d1-154">You can sort the segments in a column by selecting the column heading.</span></span>

<span data-ttu-id="042d1-155">Използвайте полето **Търсене** в горния десен ъгъл, за да филтрирате сегментите.</span><span class="sxs-lookup"><span data-stu-id="042d1-155">Use the **Search** box in the top-right corner to filter the segments.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="042d1-156">![Опции за управление на съществуващ сегмент](media/segments-selected-segment.png "Опции за управление на съществуващ сегмент")</span><span class="sxs-lookup"><span data-stu-id="042d1-156">![Options to manage an existing segment](media/segments-selected-segment.png "Options to manage an existing segment")</span></span>

<span data-ttu-id="042d1-157">Следното действие е достъпно, когато изберете сегмент:</span><span class="sxs-lookup"><span data-stu-id="042d1-157">The following action are available when you select a segment:</span></span>

- <span data-ttu-id="042d1-158">**Прегледайте** подробностите за сегмента, включително тенденцията за броя на членовете, преглед на членовете на сегмента.</span><span class="sxs-lookup"><span data-stu-id="042d1-158">**View** the segment details, including member count trend a preview of segment members.</span></span>
- <span data-ttu-id="042d1-159">**Редактирайте** сегмента, за да промените свойствата.</span><span class="sxs-lookup"><span data-stu-id="042d1-159">**Edit** the segment to change its properties.</span></span>
- <span data-ttu-id="042d1-160">**Създайте дубликат** на сегмент.</span><span class="sxs-lookup"><span data-stu-id="042d1-160">**Create duplicate** of a segment.</span></span> <span data-ttu-id="042d1-161">Можете да изберете да редактирате свойствата му веднага или просто да запазите дубликата.</span><span class="sxs-lookup"><span data-stu-id="042d1-161">You can choose to edit its properties right away or simply save the duplicate.</span></span>
- <span data-ttu-id="042d1-162">**Обновете** сегмента, за да включва най-новите данни.</span><span class="sxs-lookup"><span data-stu-id="042d1-162">**Refresh** the segment to include the latest data.</span></span>
- <span data-ttu-id="042d1-163">**Активирайте** или **деактивирайте** сегмента.</span><span class="sxs-lookup"><span data-stu-id="042d1-163">**Activate** or **Deactivate** the segment.</span></span> <span data-ttu-id="042d1-164">Сегментите имат две възможни състояния – активно или неактивно.</span><span class="sxs-lookup"><span data-stu-id="042d1-164">Segments have two possible states - active or inactive.</span></span> <span data-ttu-id="042d1-165">Тези състояния са полезни при редактиране на сегмент.</span><span class="sxs-lookup"><span data-stu-id="042d1-165">These states come in handy when editing a segment.</span></span> <span data-ttu-id="042d1-166">За неактивни сегменти дефиницията на сегмента съществува, но все още не съдържа клиенти.</span><span class="sxs-lookup"><span data-stu-id="042d1-166">For inactive segments, the segment definition exists but it doesn't contain any customers yet.</span></span> <span data-ttu-id="042d1-167">Когато активирате сегмент, състоянието му се променя от „неактивно“ на „активно“ и той започва да търси клиенти, които съответстват на дефиницията на сегмента.</span><span class="sxs-lookup"><span data-stu-id="042d1-167">When you activate a segment, its state changes from 'inactive' to 'active" and it starts looking for customers that match the segment definition.</span></span> <span data-ttu-id="042d1-168">Ако е конфигурирано [планирано обновяване](system.md#schedule-tab), неактивните сегменти имат **Състояние**, посочено като **Пропуснато**, което показва, че дори не е бил направен опит за обновяване.</span><span class="sxs-lookup"><span data-stu-id="042d1-168">If a [scheduled refresh](system.md#schedule-tab) is configured, inactive segments have the **Status** listed as **Skipped**, indicating that a refresh wasn't even attempted.</span></span> <span data-ttu-id="042d1-169">Когато се активира неактивен сегмент, той ще се обнови и ще бъде включен в планираните обновявания.</span><span class="sxs-lookup"><span data-stu-id="042d1-169">When an inactive segment is activated, it will refresh and will be included in scheduled refreshes.</span></span>
  <span data-ttu-id="042d1-170">Като алтернатива можете да използвате функционалността **Планиране по-късно** в падащия списък **Активиране/деактивиране**, за да посочите бъдеща дата и час за активиране и деактивиране на определен сегмент.</span><span class="sxs-lookup"><span data-stu-id="042d1-170">Alternatively, you can use the **Schedule later** functionality in the **Activate/Deactivate** dropdown to specify a future date and time for activation and deactivation of a particular segment.</span></span>
- <span data-ttu-id="042d1-171">**Преименувайте** сегмента.</span><span class="sxs-lookup"><span data-stu-id="042d1-171">**Rename** the segment.</span></span>
- <span data-ttu-id="042d1-172">**Изтеглете** списъка с членове като .CSV файл.</span><span class="sxs-lookup"><span data-stu-id="042d1-172">**Download** the list of members as a .CSV file.</span></span>
- <span data-ttu-id="042d1-173">Опцията **Добавяне към** изпраща списъка с идентификатори на клиенти в сегмента за обработка в друго приложение.</span><span class="sxs-lookup"><span data-stu-id="042d1-173">**Add to** option sends the list of customer IDs in the segment for processing in another application.</span></span>
- <span data-ttu-id="042d1-174">**Изтриване** на сегмента.</span><span class="sxs-lookup"><span data-stu-id="042d1-174">**Delete** the segment.</span></span>

## <a name="refresh-segments"></a><span data-ttu-id="042d1-175">Обновяване на сегменти</span><span class="sxs-lookup"><span data-stu-id="042d1-175">Refresh segments</span></span>

<span data-ttu-id="042d1-176">Можете да опресните всички сегменти наведнъж, като изберете **Обновяване на всички** на страницата **Сегменти**, или можете да опресните един или няколко сегмента, когато ги изберете и изберете **Обновяване** от опциите.</span><span class="sxs-lookup"><span data-stu-id="042d1-176">You can refresh all segments at once by selecting **Refresh all** on the **Segments** page or you can refresh one or multiple segments when you select them and choose **Refresh** in from the options.</span></span> <span data-ttu-id="042d1-177">Освен това можете да конфигурирате повтарящо се обновяване в **Администриране** > **Система** > **График**.</span><span class="sxs-lookup"><span data-stu-id="042d1-177">Alternatively, you can configure a recurring refresh on **Admin** > **System** > **Schedule**.</span></span>

> [!TIP]
> <span data-ttu-id="042d1-178">Съществуват [шест вида статус](system.md#status-types) на задачите/процесите.</span><span class="sxs-lookup"><span data-stu-id="042d1-178">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="042d1-179">Освен това повечето процеси [зависят от други процеси надолу по веригата](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="042d1-179">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="042d1-180">Можете да изберете състоянието на процес, за да видите подробности за напредъка на цялата задача.</span><span class="sxs-lookup"><span data-stu-id="042d1-180">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="042d1-181">След като изберете **Вижте подробности** за една от задачите на заданието, ще намерите допълнителна информация: време за обработка, дата на последната обработка и всички грешки и предупреждения, свързани със задачата.</span><span class="sxs-lookup"><span data-stu-id="042d1-181">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="download-and-export-segments"></a><span data-ttu-id="042d1-182">Изтегляне и експортиране на сегменти</span><span class="sxs-lookup"><span data-stu-id="042d1-182">Download and export segments</span></span>

<span data-ttu-id="042d1-183">Можете да изтеглите сегментите в CSV файл или да ги експортирате в Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="042d1-183">You can download your segments to a CSV file or export them to Dynamics 365 Sales.</span></span>

### <a name="download-segments-to-a-csv-file"></a><span data-ttu-id="042d1-184">Изтегляне на сегменти в CSV файл</span><span class="sxs-lookup"><span data-stu-id="042d1-184">Download segments to a CSV file</span></span>

1. <span data-ttu-id="042d1-185">В Аналитични данни за аудитория отидете на страницата **Сегменти**.</span><span class="sxs-lookup"><span data-stu-id="042d1-185">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="042d1-186">Изберете многоточието в определена плочка сегмент.</span><span class="sxs-lookup"><span data-stu-id="042d1-186">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="042d1-187">Изберете **Изтегляне като CSV** от падащия списък с действия.</span><span class="sxs-lookup"><span data-stu-id="042d1-187">Select **Download as CSV** from the actions drop-down list.</span></span>

### <a name="export-segments-to-dynamics-365-sales"></a><span data-ttu-id="042d1-188">Експортиране на сегменти в Dynamics 365 Sales</span><span class="sxs-lookup"><span data-stu-id="042d1-188">Export segments to Dynamics 365 Sales</span></span>

<span data-ttu-id="042d1-189">Преди да експортирате сегменти в Dynamics 365 Sales, администраторът трябва да [създаде местоназначение за експортиране](export-destinations.md) за Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="042d1-189">Before exporting segments to Dynamics 365 Sales, an admin needs to [create the export destination](export-destinations.md) for Dynamics 365 Sales.</span></span>

1. <span data-ttu-id="042d1-190">В Аналитични данни за аудитория отидете на страницата **Сегменти**.</span><span class="sxs-lookup"><span data-stu-id="042d1-190">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="042d1-191">Изберете многоточието в определена плочка сегмент.</span><span class="sxs-lookup"><span data-stu-id="042d1-191">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="042d1-192">Изберете **Добавяне към** от падащия списък с действия и изберете местоназначението за експортиране, в което искате да изпратите данните.</span><span class="sxs-lookup"><span data-stu-id="042d1-192">Select **Add to** from the actions drop-down list and select the export destination you want to send the data to.</span></span>

## <a name="draft-mode-for-segments"></a><span data-ttu-id="042d1-193">Режим на чернова за сегменти</span><span class="sxs-lookup"><span data-stu-id="042d1-193">Draft mode for segments</span></span>

<span data-ttu-id="042d1-194">Ако не са изпълнени всички изисквания за обработка на сегмент, можете да запишете сегмента като чернова и да получите достъп до него от страницата **Сегменти**.</span><span class="sxs-lookup"><span data-stu-id="042d1-194">If not all requirements to process a segment are met, you can save the segment as a draft and access it from the **Segments** page.</span></span>

<span data-ttu-id="042d1-195">Той ще се запише като неактивен сегмент и не може да се активира, докато не стане валиден.</span><span class="sxs-lookup"><span data-stu-id="042d1-195">It will be saved as an inactive segment, and can't be activated it until it's valid.</span></span>

## <a name="add-more-conditions-to-a-group"></a><span data-ttu-id="042d1-196">Добавяне на още условия към група</span><span class="sxs-lookup"><span data-stu-id="042d1-196">Add more conditions to a group</span></span>

<span data-ttu-id="042d1-197">За да добавите още условия към група, можете да използвате два логически оператора:</span><span class="sxs-lookup"><span data-stu-id="042d1-197">To add more conditions to a group, you can use two logical operators:</span></span>

- <span data-ttu-id="042d1-198">Оператор **И**: И двете условия трябва да бъдат изпълнени като част от процеса на сегментиране.</span><span class="sxs-lookup"><span data-stu-id="042d1-198">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="042d1-199">Тази опция е най-полезна, когато дефинирате условия за различни обекти.</span><span class="sxs-lookup"><span data-stu-id="042d1-199">This option is most useful when you define conditions across different entities.</span></span>

- <span data-ttu-id="042d1-200">Оператор **ИЛИ**: Едно от условията трябва да бъде изпълнено като част от процеса на сегментиране.</span><span class="sxs-lookup"><span data-stu-id="042d1-200">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="042d1-201">Тази опция е най-полезна, когато дефинирате няколко условия за един и същи обект.</span><span class="sxs-lookup"><span data-stu-id="042d1-201">This option is most useful when you define multiple conditions for the same entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="042d1-202">![Оператор ИЛИ, където трябва да бъде изпълнено едно от условията](media/segmentation-either-condition.png "Оператор ИЛИ, където трябва да бъде изпълнено едно от условията")</span><span class="sxs-lookup"><span data-stu-id="042d1-202">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

<span data-ttu-id="042d1-203">В момента е възможно да се вложи оператор **ИЛИ** под оператор **И**, но не и обратното.</span><span class="sxs-lookup"><span data-stu-id="042d1-203">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

## <a name="combine-multiple-groups"></a><span data-ttu-id="042d1-204">Комбиниране на няколко групи</span><span class="sxs-lookup"><span data-stu-id="042d1-204">Combine multiple groups</span></span>

<span data-ttu-id="042d1-205">Всяка група произвежда определен набор от клиенти.</span><span class="sxs-lookup"><span data-stu-id="042d1-205">Each group produces a specific set of customers.</span></span> <span data-ttu-id="042d1-206">Можете да комбинирате тези групи, за да включите клиентите, необходими за бизнес случая.</span><span class="sxs-lookup"><span data-stu-id="042d1-206">You can combine these groups to include the customers required for your business case.</span></span>

1. <span data-ttu-id="042d1-207">В статията за аудиторията отидете на страницата **Сегменти** и изберете сегмент.</span><span class="sxs-lookup"><span data-stu-id="042d1-207">In audience insights, go to the **Segments** page and select a segment.</span></span>

2. <span data-ttu-id="042d1-208">Изберете **Добавяне на група**.</span><span class="sxs-lookup"><span data-stu-id="042d1-208">Select **Add Group**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="042d1-209">![Добавяне на група за група клиенти](media/customer-group-add-group.png "Добавяне на група за група клиенти")</span><span class="sxs-lookup"><span data-stu-id="042d1-209">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

3. <span data-ttu-id="042d1-210">Изберете един от следните оператори: **Обединяване**, **Пресичане** или **Освен**.</span><span class="sxs-lookup"><span data-stu-id="042d1-210">Select one of the following set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="042d1-211">![Добавяне на обединяване за група клиенти](media/customer-group-union.png "Добавяне на обединяване за група клиенти")</span><span class="sxs-lookup"><span data-stu-id="042d1-211">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   <span data-ttu-id="042d1-212">Изберете зададен оператор, за да дефинирате нова група.</span><span class="sxs-lookup"><span data-stu-id="042d1-212">Select a set operator to define a new group.</span></span> <span data-ttu-id="042d1-213">Записване на различни групи за определяне на това какви данни се запазват:</span><span class="sxs-lookup"><span data-stu-id="042d1-213">Save different groups to determine what data gets retained:</span></span>

   - <span data-ttu-id="042d1-214">**Обединяването** съединява двете групи.</span><span class="sxs-lookup"><span data-stu-id="042d1-214">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="042d1-215">**Пресичането** припокрива двете групи.</span><span class="sxs-lookup"><span data-stu-id="042d1-215">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="042d1-216">Само данни, които *са често срещани* в двете групи, се задържат в единната група.</span><span class="sxs-lookup"><span data-stu-id="042d1-216">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="042d1-217">**Освен** комбинира двете групи.</span><span class="sxs-lookup"><span data-stu-id="042d1-217">**Except** combines the two groups.</span></span> <span data-ttu-id="042d1-218">Само данни в група А, които *не са често срещани* за данните в група B, се задържат.</span><span class="sxs-lookup"><span data-stu-id="042d1-218">Only data in group A that *is not common* to data in group B is retained.</span></span>

## <a name="view-processing-history-and-segment-members"></a><span data-ttu-id="042d1-219">Преглед на хронологията на обработката и членовете на сегмента</span><span class="sxs-lookup"><span data-stu-id="042d1-219">View processing history and segment members</span></span>

<span data-ttu-id="042d1-220">Можете да видите консолидирани данни за даден сегмент, като прегледате подробностите за него.</span><span class="sxs-lookup"><span data-stu-id="042d1-220">You can see consolidated data about a segment by reviewing its details.</span></span>

<span data-ttu-id="042d1-221">На страницата **Сегменти** изберете сегмента, който искате да прегледате.</span><span class="sxs-lookup"><span data-stu-id="042d1-221">On the **Segments** page, select the segment you want to review.</span></span>

<span data-ttu-id="042d1-222">Горната част на страницата включва графика на тенденциите, която визуализира промените в броя членове.</span><span class="sxs-lookup"><span data-stu-id="042d1-222">The upper part of the page includes a trend graph that visualizes changes in member count.</span></span> <span data-ttu-id="042d1-223">Задръжте курсора на мишката над точките от данни, за да видите броя членове за определена дата.</span><span class="sxs-lookup"><span data-stu-id="042d1-223">Hover over data points to see the member count on a specific date.</span></span>

<span data-ttu-id="042d1-224">Можете да актуализирате продължителността на визуализацията.</span><span class="sxs-lookup"><span data-stu-id="042d1-224">You can update the time frame of the visualization.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="042d1-225">![Времеви диапазон на сегмент](media/segment-time-range.png "Времеви диапазон на сегмент")</span><span class="sxs-lookup"><span data-stu-id="042d1-225">![Segment time range](media/segment-time-range.png "Segment time range")</span></span>

<span data-ttu-id="042d1-226">Долната част съдържа списък на членовете на сегмента.</span><span class="sxs-lookup"><span data-stu-id="042d1-226">The lower part contains a list of the segment members.</span></span>

> [!NOTE]
> <span data-ttu-id="042d1-227">Полетата, които се появяват в този списък, се основават на атрибутите на обектите на сегмента.</span><span class="sxs-lookup"><span data-stu-id="042d1-227">Fields that appear in this list are based on the attributes of your segment's entities.</span></span>
>
><span data-ttu-id="042d1-228">Списъкът е преглед на съпоставените членове на сегмента и показва първите 100 записа на сегмента, за да можете бързо да го оцените и да прегледате дефинициите му, ако е необходимо.</span><span class="sxs-lookup"><span data-stu-id="042d1-228">The list is a preview of the matching segment members and shows the first 100 records of your segment so that you can quickly evaluate it and review its definitions if needed.</span></span> <span data-ttu-id="042d1-229">За да видите всички съвпадащи записи, трябва да [експортирате сегмента](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="042d1-229">To see all matching records, you need to [export the segment](export-destinations.md).</span></span>

## <a name="quick-segments"></a><span data-ttu-id="042d1-230">Бързи сегменти</span><span class="sxs-lookup"><span data-stu-id="042d1-230">Quick segments</span></span>

<span data-ttu-id="042d1-231">В допълнение към конструктора на сегменти, има и друг път за създаване на сегменти.</span><span class="sxs-lookup"><span data-stu-id="042d1-231">In addition to the segment builder, there's another path for creating segments.</span></span> <span data-ttu-id="042d1-232">Бързите сегменти ви позволяват да изграждате прости сегменти с един оператор бързо и с незабавни прозрения.</span><span class="sxs-lookup"><span data-stu-id="042d1-232">Quick segments let you build simple segments with a single operator quickly and with instant insights.</span></span>

1. <span data-ttu-id="042d1-233">На страницата **Сегменти** изберете **Нов** > **Бързо създаване от**.</span><span class="sxs-lookup"><span data-stu-id="042d1-233">On the **Segments** page, select **New** > **Quickly create from**.</span></span>

   - <span data-ttu-id="042d1-234">Изберете опцията **Профили** за изграждане на сегмент, който се основава на унифицирания обект на клиент.</span><span class="sxs-lookup"><span data-stu-id="042d1-234">Select the **Profiles** option to build a segment that is based on the unified Customer entity.</span></span>
   - <span data-ttu-id="042d1-235">Изберете опцията **Мерки** за създаване на сегмент по всеки тип мярка на атрибут на клиент, който предварително сте създали в страницата **Мерки**.</span><span class="sxs-lookup"><span data-stu-id="042d1-235">Select the **Measures** option to build a segment around each of the Customer Attribute type of measures you have previously created on the **Measures** page.</span></span>
   - <span data-ttu-id="042d1-236">Изберете опцията **Разузнаване** за изграждане на сегмент по един от изходните обекти, който генерирахте чрез възможностите **Прогнози** или **Персонализирани модели**.</span><span class="sxs-lookup"><span data-stu-id="042d1-236">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="042d1-237">В диалоговия прозорец **Нов бърз сегмент** изберете атрибут от падащия списък **Поле**.</span><span class="sxs-lookup"><span data-stu-id="042d1-237">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="042d1-238">Системата ще предостави някои допълнителни аналитични данни, които ще ви помогнат да създадете по-добри сегменти за клиентите.</span><span class="sxs-lookup"><span data-stu-id="042d1-238">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="042d1-239">За полета на категории ще покажем 10-те най-добри клиенти.</span><span class="sxs-lookup"><span data-stu-id="042d1-239">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="042d1-240">Изберете **Стойност** и след това **Преглед**.</span><span class="sxs-lookup"><span data-stu-id="042d1-240">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="042d1-241">За числов атрибут системата ще покаже каква стойност на атрибута попада в рамките на процентила на всеки клиент.</span><span class="sxs-lookup"><span data-stu-id="042d1-241">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="042d1-242">Изберете **Оператор** и **Стойност**, след което изберете **Преглед**.</span><span class="sxs-lookup"><span data-stu-id="042d1-242">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="042d1-243">Системата ще ви предостави **Прогнозен размер на сегмента**.</span><span class="sxs-lookup"><span data-stu-id="042d1-243">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="042d1-244">Можете да изберете дали да генерирате определения от вас сегмент или първо да го преразгледате, за да получите различен размер на сегмента.</span><span class="sxs-lookup"><span data-stu-id="042d1-244">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="042d1-245">![Име и оценка за бърз сегмент](media/quick-segment-name.png "Име и оценка за бърз сегмент")</span><span class="sxs-lookup"><span data-stu-id="042d1-245">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="042d1-246">Посочете **Име** за сегмента.</span><span class="sxs-lookup"><span data-stu-id="042d1-246">Provide a **Name** for your segment.</span></span> <span data-ttu-id="042d1-247">По избор въведете **Показвано име**.</span><span class="sxs-lookup"><span data-stu-id="042d1-247">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="042d1-248">Изберете **Записване**, за да създадете сегмента.</span><span class="sxs-lookup"><span data-stu-id="042d1-248">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="042d1-249">След като обработката на сегмента завърши, можете да го прегледате като всеки друг сегмент, който сте създали.</span><span class="sxs-lookup"><span data-stu-id="042d1-249">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

<span data-ttu-id="042d1-250">За следните сценарии съветваме да използваме конструктора на сегменти, а не препоръчителните възможности за сегменти:</span><span class="sxs-lookup"><span data-stu-id="042d1-250">For the following scenarios, we advise using the segment builder rather than the recommended segments capability:</span></span>

- <span data-ttu-id="042d1-251">Създаване на сегменти с филтри на полета за категории, където операторът е различен от оператора **Е**</span><span class="sxs-lookup"><span data-stu-id="042d1-251">Creating segments with filters on categorical fields where the operator is different than the **Is** operator</span></span>
- <span data-ttu-id="042d1-252">Създаване на сегменти с филтри в числови полета, където операторът е различен от операторите **Между**, **По-голямо от** и **По-малко от**</span><span class="sxs-lookup"><span data-stu-id="042d1-252">Creating segments with filters on numerical fields where the operator is different than the **Between**, **Greater than**, and **Less than** operators</span></span>
- <span data-ttu-id="042d1-253">Създаване на сегменти с филтри на полета от тип дата</span><span class="sxs-lookup"><span data-stu-id="042d1-253">Creating segments with filters on date type fields</span></span>

## <a name="next-steps"></a><span data-ttu-id="042d1-254">Следващи стъпки</span><span class="sxs-lookup"><span data-stu-id="042d1-254">Next steps</span></span>

<span data-ttu-id="042d1-255">[Експортирайте сегмент](export-destinations.md) и разгледайте [картата на клиента](customer-card-add-in.md) и [конекторите](export-power-bi.md), за да получите аналитични данни на ниво клиент.</span><span class="sxs-lookup"><span data-stu-id="042d1-255">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]