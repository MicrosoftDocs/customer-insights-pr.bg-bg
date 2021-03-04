---
title: Създаване и управление на измерения
description: Определете мерки за анализ и отразяване на резултатите от вашия бизнес.
ms.date: 02/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 5bcee3b4c51880740715575b18fd7a4dbf87e6d0
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269915"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="2d0f2-103">Определяне и управление на мерки</span><span class="sxs-lookup"><span data-stu-id="2d0f2-103">Define and manage measures</span></span>

<span data-ttu-id="2d0f2-104">Мерките ви помагат да разберете по-добре поведението на клиентите и бизнес представянето, като извличате съответните ценности от [унифицирани профили](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="2d0f2-104">Measures help you to better understand customer behaviors and business performance by retrieving relevant values from [unified profiles](data-unification.md).</span></span> <span data-ttu-id="2d0f2-105">Например, бизнес иска да види *общи разходи на клиент*, за да разберете историята на покупките на отделните клиенти.</span><span class="sxs-lookup"><span data-stu-id="2d0f2-105">For example, a business wants to see the *total spend per customer* to understand individual customer’s purchase history.</span></span> <span data-ttu-id="2d0f2-106">Или измерете *общи продажби на компанията*, за да разберете съвкупните приходи на целия бизнес.</span><span class="sxs-lookup"><span data-stu-id="2d0f2-106">Or measure *total sales of the company* to understand the aggregate-level revenue in the whole business.</span></span>  

<span data-ttu-id="2d0f2-107">Мерките се създават с помощта на конструктора на мерки, платформа за заявки за данни с различни оператори и прости опции за картографиране.</span><span class="sxs-lookup"><span data-stu-id="2d0f2-107">Measures are created using the measure builder, a data query platform with various operators and simple mapping options.</span></span> <span data-ttu-id="2d0f2-108">Позволява ви да филтрирате данните, да групирате резултатите, да откривате [пътища на взаимоотношения на обекта](relationships.md) и прегледайте изхода.</span><span class="sxs-lookup"><span data-stu-id="2d0f2-108">It lets you filter the data, group results, detect [entity relationship paths](relationships.md), and preview the output.</span></span>

<span data-ttu-id="2d0f2-109">Използвайте конструктора на измервания, за да планирате бизнес дейности чрез запитване на клиентски данни и извличане на статистика.</span><span class="sxs-lookup"><span data-stu-id="2d0f2-109">Use the measure builder to plan business activities by querying customer data and extract insights.</span></span> <span data-ttu-id="2d0f2-110">Например, създаване на мярка за *общи разходи на клиент* и *обща възвръщаемост на клиент* помага да се идентифицира група клиенти с високи разходи, но висока възвръщаемост.</span><span class="sxs-lookup"><span data-stu-id="2d0f2-110">For example, creating a measure of *total spend per customer* and *total return per customer* helps identify a group of customers with high spend yet high return.</span></span> <span data-ttu-id="2d0f2-111">Можете да [създадете сегмент](segments.md), за да стимулирате следващите най-добри действия.</span><span class="sxs-lookup"><span data-stu-id="2d0f2-111">You can [create a segment](segments.md) to drive next best actions.</span></span> 

## <a name="create-a-measure"></a><span data-ttu-id="2d0f2-112">Създаване на мярка</span><span class="sxs-lookup"><span data-stu-id="2d0f2-112">Create a measure</span></span>

<span data-ttu-id="2d0f2-113">Този раздел ви превежда през създаването на нова мярка от нулата.</span><span class="sxs-lookup"><span data-stu-id="2d0f2-113">This section walks you through creating a new measure from scratch.</span></span> <span data-ttu-id="2d0f2-114">Можете да изградите мярка с атрибути на данни от обекти на данни, които имат настройка за връзка с обекта на клиента.</span><span class="sxs-lookup"><span data-stu-id="2d0f2-114">You can build a measure with data attributes from data entities that have a relationship set up to connect with the Customer entity.</span></span> 

1. <span data-ttu-id="2d0f2-115">В Аналитични данни за аудиторията отидете на **Мерки**.</span><span class="sxs-lookup"><span data-stu-id="2d0f2-115">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="2d0f2-116">Изберете **Нова**.</span><span class="sxs-lookup"><span data-stu-id="2d0f2-116">Select **New**.</span></span>

1. <span data-ttu-id="2d0f2-117">Изберете **Редактиране на име** и предоставете **Име** за мярката.</span><span class="sxs-lookup"><span data-stu-id="2d0f2-117">Select **Edit name** and provide a **Name** for the measure.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="2d0f2-118">Ако вашата нова конфигурация на мярка има само две полета, за пример, CustomerID и едно изчисление, изходът ще бъде добавен като нова колона към генерираната от системата обект, наречен Customer_Measure.</span><span class="sxs-lookup"><span data-stu-id="2d0f2-118">If your new measure configuration has only two fields, for exmample, CustomerID and one calculation, the output will be added as a new column to the system generated entity called Customer_Measure.</span></span> <span data-ttu-id="2d0f2-119">И ще можете да видите стойността на мярката в единния клиентски профил.</span><span class="sxs-lookup"><span data-stu-id="2d0f2-119">And you will be able to see the measure’s value in the unified customer profile.</span></span> <span data-ttu-id="2d0f2-120">Други мерки ще генерират свои собствени образувания.</span><span class="sxs-lookup"><span data-stu-id="2d0f2-120">Other measures will generate their own entities.</span></span>

1. <span data-ttu-id="2d0f2-121">В областта за конфигуриране изберете функцията за агрегиране от падащо меню **Изберете Функция**.</span><span class="sxs-lookup"><span data-stu-id="2d0f2-121">In the configuration area, choose the aggregation function from the **Select Function** drop-down menu.</span></span> <span data-ttu-id="2d0f2-122">Функциите за агрегиране включват:</span><span class="sxs-lookup"><span data-stu-id="2d0f2-122">Aggregation functions include:</span></span> 
   - <span data-ttu-id="2d0f2-123">**Sum**</span><span class="sxs-lookup"><span data-stu-id="2d0f2-123">**Sum**</span></span>
   - <span data-ttu-id="2d0f2-124">**Средно**</span><span class="sxs-lookup"><span data-stu-id="2d0f2-124">**Average**</span></span>
   - <span data-ttu-id="2d0f2-125">**Брой**</span><span class="sxs-lookup"><span data-stu-id="2d0f2-125">**Count**</span></span>
   - <span data-ttu-id="2d0f2-126">**Преброяване на уникални**</span><span class="sxs-lookup"><span data-stu-id="2d0f2-126">**Count Unique**</span></span>
   - <span data-ttu-id="2d0f2-127">**Максимум**</span><span class="sxs-lookup"><span data-stu-id="2d0f2-127">**Max**</span></span>
   - <span data-ttu-id="2d0f2-128">**Min**</span><span class="sxs-lookup"><span data-stu-id="2d0f2-128">**Min**</span></span>
   - <span data-ttu-id="2d0f2-129">**Първо**: взема първата стойност на записа на данни</span><span class="sxs-lookup"><span data-stu-id="2d0f2-129">**First**: takes the first value of the data record</span></span>
   - <span data-ttu-id="2d0f2-130">**Последно**: взема последната стойност, която е добавена към записа на данни</span><span class="sxs-lookup"><span data-stu-id="2d0f2-130">**Last**: takes the last value that was added to the data record</span></span>

   :::image type="content" source="media/measure-operators.png" alt-text="Оператори за изчисления на мерките.":::

1. <span data-ttu-id="2d0f2-132">Изберете **Добавяне на атрибут**, за да изберете данните, от които се нуждаете, за да създадете тази мярка.</span><span class="sxs-lookup"><span data-stu-id="2d0f2-132">Select **Add attribute** to select the data you need to create this measure.</span></span>
   
   1. <span data-ttu-id="2d0f2-133">Изберете раздел **Атрибути**.</span><span class="sxs-lookup"><span data-stu-id="2d0f2-133">Select the **Attributes** tab.</span></span> 
   1. <span data-ttu-id="2d0f2-134">Обект на данни: Изберете обекта, който включва атрибута, който искате да измерите.</span><span class="sxs-lookup"><span data-stu-id="2d0f2-134">Data entity: Choose the entity that includes the attribute you want to measure.</span></span> 
   1. <span data-ttu-id="2d0f2-135">Атрибут на данните: Изберете атрибута, който искате да използвате във функцията за агрегиране, за да изчислите мярката.</span><span class="sxs-lookup"><span data-stu-id="2d0f2-135">Data attribute: Choose the attribute you want to use in the aggregation function to calculate the measure.</span></span> <span data-ttu-id="2d0f2-136">Можете да избирате само по един атрибут наведнъж.</span><span class="sxs-lookup"><span data-stu-id="2d0f2-136">You can only select one attribute at a time.</span></span>
   1. <span data-ttu-id="2d0f2-137">Можете също да изберете атрибут на данни от съществуваща мярка, като изберете раздел **Мерки**. Или можете да търсите име на обект или мярка.</span><span class="sxs-lookup"><span data-stu-id="2d0f2-137">You can also select a data attribute from an existing measure by selecting the **Measures** tab. Or, you can search for an entity or measure name.</span></span> 
   1. <span data-ttu-id="2d0f2-138">Изберете **Добавяне**, за да добавите избрания атрибут към мярката.</span><span class="sxs-lookup"><span data-stu-id="2d0f2-138">Select **Add** to add the selected attribute to the measure.</span></span>

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Изберете атрибут, който да използвате при изчисленията.":::

1. <span data-ttu-id="2d0f2-140">За да изградите по-сложни мерки, можете да добавите още атрибути или да използвате математически оператори във вашата функция за измерване.</span><span class="sxs-lookup"><span data-stu-id="2d0f2-140">To build more complex measures, you can add more attributes or use math operators on your measure function.</span></span>

   :::image type="content" source="media/measure-math-operators.png" alt-text="Създайте сложна мярка с математически оператори.":::

1. <span data-ttu-id="2d0f2-142">За да добавите филтри, изберете **Филтър** в зоната за конфигуриране.</span><span class="sxs-lookup"><span data-stu-id="2d0f2-142">To add filters, select the **Filter** in the configuration area.</span></span> 
  
   1. <span data-ttu-id="2d0f2-143">В **Добавяне на атрибут** раздел на екрана **Филтри** изберете атрибута, който искате да използвате за създаване на филтри.</span><span class="sxs-lookup"><span data-stu-id="2d0f2-143">In **Add attribute** section of the **Filters** pane, select the attribute you want to use to create filters.</span></span>
   1. <span data-ttu-id="2d0f2-144">Задайте операторите на филтъра да дефинират филтъра за всеки избран атрибут.</span><span class="sxs-lookup"><span data-stu-id="2d0f2-144">Set the filter operators to define the filter for every selected attribute.</span></span>
   1. <span data-ttu-id="2d0f2-145">Изберете **Прилагане**, за да добавите филтри към мярката.</span><span class="sxs-lookup"><span data-stu-id="2d0f2-145">Select **Apply** to add the filters to the measure.</span></span>

1. <span data-ttu-id="2d0f2-146">За да добавите измерения, изберете **Измерение** в зоната за конфигуриране.</span><span class="sxs-lookup"><span data-stu-id="2d0f2-146">To add dimensions, select **Dimension** in the configuration area.</span></span> <span data-ttu-id="2d0f2-147">Размерите ще се показват като колони в изходния обект на мярката.</span><span class="sxs-lookup"><span data-stu-id="2d0f2-147">Dimensions will show as columns in the measure output entity.</span></span>
   1. <span data-ttu-id="2d0f2-148">Изберете **Редактиране на размери** за да добавите атрибути на данни, по които искате да групирате стойностите на мярката.</span><span class="sxs-lookup"><span data-stu-id="2d0f2-148">Select **Edit dimensions** to add data attributes you want to group the measure values by.</span></span> <span data-ttu-id="2d0f2-149">Например град или пол.</span><span class="sxs-lookup"><span data-stu-id="2d0f2-149">For example, city or gender.</span></span> <span data-ttu-id="2d0f2-150">По подразбиране измерението *ИД на клиент* е избран за създаване на *мерки на ниво клиент*.</span><span class="sxs-lookup"><span data-stu-id="2d0f2-150">By default, the *CustomerID* dimension is selected to create *customer-level measures*.</span></span> <span data-ttu-id="2d0f2-151">Можете да премахнете измерението по подразбиране, ако искате да създадете *мерки на ниво бизнес*.</span><span class="sxs-lookup"><span data-stu-id="2d0f2-151">You can remove the default dimension if you want to create *business-level measures*.</span></span>
   1. <span data-ttu-id="2d0f2-152">Изберете **Готово**, за да добавите измерения към мярката.</span><span class="sxs-lookup"><span data-stu-id="2d0f2-152">Select **Done** to add the dimensions to the measure.</span></span>

1. <span data-ttu-id="2d0f2-153">Ако има множество пътища между обекта на данни, който сте картографирали, и обекта на клиента, трябва да изберете един от идентифицираните [пътища на взаимоотношения на обекта](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="2d0f2-153">If there are multiple paths between the data entity you mapped and the Customer entity, you have to choose one of the identified [entity relationship paths](relationships.md).</span></span> <span data-ttu-id="2d0f2-154">Резултатите от измерването могат да варират в зависимост от избрания път.</span><span class="sxs-lookup"><span data-stu-id="2d0f2-154">Measure results can vary depending on the selected path.</span></span>
   1. <span data-ttu-id="2d0f2-155">Изберете **Предпочитания за данни** и изберете пътя на обекта, който трябва да се използва за идентифициране на вашата мярка.</span><span class="sxs-lookup"><span data-stu-id="2d0f2-155">Select **Data preferences** and choose the entity path that should be used to identify your measure.</span></span>
   1. <span data-ttu-id="2d0f2-156">Изберете **Готово**, за да приложите своя избор.</span><span class="sxs-lookup"><span data-stu-id="2d0f2-156">Select **Done** to apply your selection.</span></span> 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Избор на път на обект за мярката.":::

1. <span data-ttu-id="2d0f2-158">За да добавите още изчисления за мярката, изберете **Ново изчисление**.</span><span class="sxs-lookup"><span data-stu-id="2d0f2-158">To add more calculations for the measure, select **New calculation**.</span></span> <span data-ttu-id="2d0f2-159">Можете да използвате само обекти на същия път на обекта за нови изчисления.</span><span class="sxs-lookup"><span data-stu-id="2d0f2-159">You can only use entities on the same entity path for new calculations.</span></span> <span data-ttu-id="2d0f2-160">Още изчисления ще се показват като нови колони в изходния обект на мярката.</span><span class="sxs-lookup"><span data-stu-id="2d0f2-160">More calculations will show as new columns in the measure output entity.</span></span>

1. <span data-ttu-id="2d0f2-161">Изберете **...** върху изчислението до **Дубликат**, **Преименувайте** или **Премахване** изчисление от мярка.</span><span class="sxs-lookup"><span data-stu-id="2d0f2-161">Select **...** on the calculation to **Duplicate**, **Rename**, or **Remove** a calculation from a measure.</span></span>

1. <span data-ttu-id="2d0f2-162">В областта **Преглед** ще видите схемата за данни на изходния обект на мярката, включително филтри и размери.</span><span class="sxs-lookup"><span data-stu-id="2d0f2-162">In the **Preview** area, you'll see the data schema of the measure output entity, including filters and dimensions.</span></span> <span data-ttu-id="2d0f2-163">Визуализацията реагира динамично на промени в конфигурацията.</span><span class="sxs-lookup"><span data-stu-id="2d0f2-163">The preview reacts dynamically to changes in the configuration.</span></span>

1. <span data-ttu-id="2d0f2-164">Изберете **Изпълнение** за изчисляване на резултатите за конфигурираната мярка.</span><span class="sxs-lookup"><span data-stu-id="2d0f2-164">Select **Run** to calculate results for the configured measure.</span></span> <span data-ttu-id="2d0f2-165">Изберете **Записване и затваряне**, ако искате да запазите текущата конфигурация и да изпълните мярката по-късно.</span><span class="sxs-lookup"><span data-stu-id="2d0f2-165">Select **Save and close** if you want to keep the current configuration and run the measure later.</span></span>

1. <span data-ttu-id="2d0f2-166">Отидете на **Мерки**, за да видите новосъздадената мярка в списъка.</span><span class="sxs-lookup"><span data-stu-id="2d0f2-166">Go to **Measures** to see the newly created measure in the list.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="2d0f2-167">Управление на мерките</span><span class="sxs-lookup"><span data-stu-id="2d0f2-167">Manage your measures</span></span>

<span data-ttu-id="2d0f2-168">След като [създадете мярка](#create-a-measure), ще видите списък с мерки на страницата **Мерки**.</span><span class="sxs-lookup"><span data-stu-id="2d0f2-168">After [creating a measure](#create-a-measure), you see a list of measures on the **Measures** page.</span></span>

<span data-ttu-id="2d0f2-169">Ще намерите информация за типа мярка, създателя, датата на създаване, състоянието и състоянието.</span><span class="sxs-lookup"><span data-stu-id="2d0f2-169">You'll find information about the measure type, the creator, creation date, status, and state.</span></span> <span data-ttu-id="2d0f2-170">Когато изберете мярка от списъка, можете да прегледате изхода и да изтеглите .CSV файл.</span><span class="sxs-lookup"><span data-stu-id="2d0f2-170">When you select a measure from the list, you can preview the output and download a .CSV file.</span></span>

<span data-ttu-id="2d0f2-171">За да обновите всичките си мерки едновременно, изберете **Обновяване на всички** без да избирате конкретна мярка.</span><span class="sxs-lookup"><span data-stu-id="2d0f2-171">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="2d0f2-172">![Действия за управление на единични мерки](media/measure-actions.png "Действия за управление на единични мерки")</span><span class="sxs-lookup"><span data-stu-id="2d0f2-172">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="2d0f2-173">Изберете мярка от списъка за следните опции:</span><span class="sxs-lookup"><span data-stu-id="2d0f2-173">Select a measure from the list for the following options:</span></span>

- <span data-ttu-id="2d0f2-174">Изберете името на мярката, за да видите подробности за нея.</span><span class="sxs-lookup"><span data-stu-id="2d0f2-174">Select the measure name to see its details.</span></span>
- <span data-ttu-id="2d0f2-175">**Редактиране** на конфигурацията на мярката.</span><span class="sxs-lookup"><span data-stu-id="2d0f2-175">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="2d0f2-176">**Обновете** мярката въз основа на последните данни.</span><span class="sxs-lookup"><span data-stu-id="2d0f2-176">**Refresh** the measure based on the latest data.</span></span>
- <span data-ttu-id="2d0f2-177">**Преименуване** на мярката.</span><span class="sxs-lookup"><span data-stu-id="2d0f2-177">**Rename** the measure.</span></span>
- <span data-ttu-id="2d0f2-178">**Изтриване** на мярката.</span><span class="sxs-lookup"><span data-stu-id="2d0f2-178">**Delete** the measure.</span></span>
- <span data-ttu-id="2d0f2-179">**Активирайте** или **дезактивирайте**.</span><span class="sxs-lookup"><span data-stu-id="2d0f2-179">**Activate** or **Deactivate**.</span></span> <span data-ttu-id="2d0f2-180">Неактивните мерки няма да се обновят по време на [планирано опресняване](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="2d0f2-180">Inactive measures won't get refreshed during a [scheduled refresh](system.md#schedule-tab).</span></span>

> [!TIP]
> <span data-ttu-id="2d0f2-181">Съществуват [шест вида статус](system.md#status-types) на задачите/процесите.</span><span class="sxs-lookup"><span data-stu-id="2d0f2-181">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="2d0f2-182">Освен това повечето процеси [зависят от други процеси надолу по веригата](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="2d0f2-182">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="2d0f2-183">Можете да изберете състоянието на процес, за да видите подробности за напредъка на цялата задача.</span><span class="sxs-lookup"><span data-stu-id="2d0f2-183">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="2d0f2-184">След като изберете **Вижте подробности** за една от задачите на заданието, ще намерите допълнителна информация: време за обработка, дата на последната обработка и всички грешки и предупреждения, свързани със задачата.</span><span class="sxs-lookup"><span data-stu-id="2d0f2-184">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="2d0f2-185">Следваща стъпка</span><span class="sxs-lookup"><span data-stu-id="2d0f2-185">Next step</span></span>

<span data-ttu-id="2d0f2-186">Можете да използвате съществуващите мерки за създаване на [клиентски сегмент](segments.md).</span><span class="sxs-lookup"><span data-stu-id="2d0f2-186">You cam use existing measures to create [a customer segment](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]