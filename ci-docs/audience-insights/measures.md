---
title: Създаване и управление на измерения
description: Определете мерки за анализ и отразяване на резултатите от вашия бизнес.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 9a94a32a04f2a8beb661c27271fe96f23d998722
ms.sourcegitcommit: d89b19b2a3497722b78362aeee688ae7e94915d9
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 04/13/2021
ms.locfileid: "5887927"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="530a7-103">Определяне и управление на мерки</span><span class="sxs-lookup"><span data-stu-id="530a7-103">Define and manage measures</span></span>

<span data-ttu-id="530a7-104">Мерките ви помагат да разберете по-добре поведението на клиентите и бизнес представянето.</span><span class="sxs-lookup"><span data-stu-id="530a7-104">Measures help you to better understand customer behaviors and business performance.</span></span> <span data-ttu-id="530a7-105">Те разглеждат съответните стойности от [унифицирани профили](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="530a7-105">They look at relevant values from [unified profiles](data-unification.md).</span></span> <span data-ttu-id="530a7-106">Например, дадена фирма иска да види *общия разход на клиент*, за да разбере хронологията на покупките на отделния клиент, или да измери *общите продажби на фирмата*, за да разбере общите приходи на целия бизнес.</span><span class="sxs-lookup"><span data-stu-id="530a7-106">For example, a business wants to see the *total spend per customer* to understand individual customer’s purchase history or measure *total sales of the company* to understand the aggregate-level revenue in the whole business.</span></span>  

<span data-ttu-id="530a7-107">Мерките се създават с помощта на конструктора на мерки, платформа за заявки за данни с различни оператори и прости опции за картографиране.</span><span class="sxs-lookup"><span data-stu-id="530a7-107">Measures are created using the measure builder, a data query platform with various operators and simple mapping options.</span></span> <span data-ttu-id="530a7-108">Позволява ви да филтрирате данните, да групирате резултатите, да откривате [пътища на взаимоотношения на обекта](relationships.md) и прегледайте изхода.</span><span class="sxs-lookup"><span data-stu-id="530a7-108">It lets you filter the data, group results, detect [entity relationship paths](relationships.md), and preview the output.</span></span>

<span data-ttu-id="530a7-109">Използвайте конструктора на измервания, за да планирате бизнес дейности чрез запитване на клиентски данни и извличане на статистика.</span><span class="sxs-lookup"><span data-stu-id="530a7-109">Use the measure builder to plan business activities by querying customer data and extract insights.</span></span> <span data-ttu-id="530a7-110">Например, създаване на мярка за *общи разходи на клиент* и *обща възвръщаемост на клиент* помага да се идентифицира група клиенти с високи разходи, но висока възвръщаемост.</span><span class="sxs-lookup"><span data-stu-id="530a7-110">For example, creating a measure of *total spend per customer* and *total return per customer* helps identify a group of customers with high spend yet high return.</span></span> <span data-ttu-id="530a7-111">Можете да [създадете сегмент](segments.md), за да стимулирате следващите най-добри действия.</span><span class="sxs-lookup"><span data-stu-id="530a7-111">You can [create a segment](segments.md) to drive next best actions.</span></span> 

## <a name="build-your-own-measure-from-scratch"></a><span data-ttu-id="530a7-112">Създаване на собствена мярка от самото начало</span><span class="sxs-lookup"><span data-stu-id="530a7-112">Build your own measure from scratch</span></span>

<span data-ttu-id="530a7-113">Този раздел ви превежда през създаването на нова мярка от нулата.</span><span class="sxs-lookup"><span data-stu-id="530a7-113">This section walks you through creating a new measure from scratch.</span></span> <span data-ttu-id="530a7-114">Можете да изградите мярка с атрибути на данни от обекти на данни, които имат настройка за връзка с обекта на клиента.</span><span class="sxs-lookup"><span data-stu-id="530a7-114">You can build a measure with data attributes from data entities that have a relationship set up to connect with the Customer entity.</span></span> 

1. <span data-ttu-id="530a7-115">В Аналитични данни за аудиторията отидете на **Мерки**.</span><span class="sxs-lookup"><span data-stu-id="530a7-115">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="530a7-116">Изберете **Нова** и изберете **Създаване на собствена**.</span><span class="sxs-lookup"><span data-stu-id="530a7-116">Select **New** and choose **Build your own**.</span></span>

1. <span data-ttu-id="530a7-117">Изберете **Редактиране на име** и предоставете **Име** за мярката.</span><span class="sxs-lookup"><span data-stu-id="530a7-117">Select **Edit name** and provide a **Name** for the measure.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="530a7-118">Ако вашата нова конфигурация на мярка има само две полета, за пример, CustomerID и едно изчисление, изходът ще бъде добавен като нова колона към генерираната от системата обект, наречен Customer_Measure.</span><span class="sxs-lookup"><span data-stu-id="530a7-118">If your new measure configuration has only two fields, for exmample, CustomerID and one calculation, the output will be added as a new column to the system generated entity called Customer_Measure.</span></span> <span data-ttu-id="530a7-119">И ще можете да видите стойността на мярката в единния клиентски профил.</span><span class="sxs-lookup"><span data-stu-id="530a7-119">And you will be able to see the measure’s value in the unified customer profile.</span></span> <span data-ttu-id="530a7-120">Други мерки ще генерират свои собствени образувания.</span><span class="sxs-lookup"><span data-stu-id="530a7-120">Other measures will generate their own entities.</span></span>

1. <span data-ttu-id="530a7-121">В областта за конфигуриране изберете функцията за агрегиране от падащо меню **Изберете Функция**.</span><span class="sxs-lookup"><span data-stu-id="530a7-121">In the configuration area, choose the aggregation function from the **Select Function** drop-down menu.</span></span> <span data-ttu-id="530a7-122">Функциите за агрегиране включват:</span><span class="sxs-lookup"><span data-stu-id="530a7-122">Aggregation functions include:</span></span> 
   - <span data-ttu-id="530a7-123">**Sum**</span><span class="sxs-lookup"><span data-stu-id="530a7-123">**Sum**</span></span>
   - <span data-ttu-id="530a7-124">**Средно**</span><span class="sxs-lookup"><span data-stu-id="530a7-124">**Average**</span></span>
   - <span data-ttu-id="530a7-125">**Брой**</span><span class="sxs-lookup"><span data-stu-id="530a7-125">**Count**</span></span>
   - <span data-ttu-id="530a7-126">**Преброяване на уникални**</span><span class="sxs-lookup"><span data-stu-id="530a7-126">**Count Unique**</span></span>
   - <span data-ttu-id="530a7-127">**Максимум**</span><span class="sxs-lookup"><span data-stu-id="530a7-127">**Max**</span></span>
   - <span data-ttu-id="530a7-128">**Min**</span><span class="sxs-lookup"><span data-stu-id="530a7-128">**Min**</span></span>
   - <span data-ttu-id="530a7-129">**Първо**: взема първата стойност на записа на данни</span><span class="sxs-lookup"><span data-stu-id="530a7-129">**First**: takes the first value of the data record</span></span>
   - <span data-ttu-id="530a7-130">**Последно**: взема последната стойност, която е добавена към записа на данни</span><span class="sxs-lookup"><span data-stu-id="530a7-130">**Last**: takes the last value that was added to the data record</span></span>

   :::image type="content" source="media/measure-operators.png" alt-text="Оператори за изчисления на мерките.":::

1. <span data-ttu-id="530a7-132">Изберете **Добавяне на атрибут**, за да изберете данните, от които се нуждаете, за да създадете тази мярка.</span><span class="sxs-lookup"><span data-stu-id="530a7-132">Select **Add attribute** to select the data you need to create this measure.</span></span>
   
   1. <span data-ttu-id="530a7-133">Изберете раздел **Атрибути**.</span><span class="sxs-lookup"><span data-stu-id="530a7-133">Select the **Attributes** tab.</span></span> 
   1. <span data-ttu-id="530a7-134">Обект на данни: Изберете обекта, който включва атрибута, който искате да измерите.</span><span class="sxs-lookup"><span data-stu-id="530a7-134">Data entity: Choose the entity that includes the attribute you want to measure.</span></span> 
   1. <span data-ttu-id="530a7-135">Атрибут на данните: Изберете атрибута, който искате да използвате във функцията за агрегиране, за да изчислите мярката.</span><span class="sxs-lookup"><span data-stu-id="530a7-135">Data attribute: Choose the attribute you want to use in the aggregation function to calculate the measure.</span></span> <span data-ttu-id="530a7-136">Можете да избирате само по един атрибут наведнъж.</span><span class="sxs-lookup"><span data-stu-id="530a7-136">You can only select one attribute at a time.</span></span>
   1. <span data-ttu-id="530a7-137">Можете също да изберете атрибут на данни от съществуваща мярка, като изберете раздел **Мерки**. Или можете да търсите име на обект или мярка.</span><span class="sxs-lookup"><span data-stu-id="530a7-137">You can also select a data attribute from an existing measure by selecting the **Measures** tab. Or, you can search for an entity or measure name.</span></span> 
   1. <span data-ttu-id="530a7-138">Изберете **Добавяне**, за да добавите избрания атрибут към мярката.</span><span class="sxs-lookup"><span data-stu-id="530a7-138">Select **Add** to add the selected attribute to the measure.</span></span>

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Изберете атрибут, който да използвате при изчисленията.":::

1. <span data-ttu-id="530a7-140">За да изградите по-сложни мерки, можете да добавите още атрибути или да използвате математически оператори във вашата функция за измерване.</span><span class="sxs-lookup"><span data-stu-id="530a7-140">To build more complex measures, you can add more attributes or use math operators on your measure function.</span></span>

   :::image type="content" source="media/measure-math-operators.png" alt-text="Създайте сложна мярка с математически оператори.":::

1. <span data-ttu-id="530a7-142">За да добавите филтри, изберете **Филтър** в зоната за конфигуриране.</span><span class="sxs-lookup"><span data-stu-id="530a7-142">To add filters, select the **Filter** in the configuration area.</span></span> 
  
   1. <span data-ttu-id="530a7-143">В **Добавяне на атрибут** раздел на екрана **Филтри** изберете атрибута, който искате да използвате за създаване на филтри.</span><span class="sxs-lookup"><span data-stu-id="530a7-143">In **Add attribute** section of the **Filters** pane, select the attribute you want to use to create filters.</span></span>
   1. <span data-ttu-id="530a7-144">Задайте операторите на филтъра да дефинират филтъра за всеки избран атрибут.</span><span class="sxs-lookup"><span data-stu-id="530a7-144">Set the filter operators to define the filter for every selected attribute.</span></span>
   1. <span data-ttu-id="530a7-145">Изберете **Прилагане**, за да добавите филтри към мярката.</span><span class="sxs-lookup"><span data-stu-id="530a7-145">Select **Apply** to add the filters to the measure.</span></span>

1. <span data-ttu-id="530a7-146">За да добавите измерения, изберете **Измерение** в зоната за конфигуриране.</span><span class="sxs-lookup"><span data-stu-id="530a7-146">To add dimensions, select **Dimension** in the configuration area.</span></span> <span data-ttu-id="530a7-147">Размерите ще се показват като колони в изходния обект на мярката.</span><span class="sxs-lookup"><span data-stu-id="530a7-147">Dimensions will show as columns in the measure output entity.</span></span>
   1. <span data-ttu-id="530a7-148">Изберете **Редактиране на размери** за да добавите атрибути на данни, по които искате да групирате стойностите на мярката.</span><span class="sxs-lookup"><span data-stu-id="530a7-148">Select **Edit dimensions** to add data attributes you want to group the measure values by.</span></span> <span data-ttu-id="530a7-149">Например град или пол.</span><span class="sxs-lookup"><span data-stu-id="530a7-149">For example, city or gender.</span></span> <span data-ttu-id="530a7-150">По подразбиране измерението *ИД на клиент* е избран за създаване на *мерки на ниво клиент*.</span><span class="sxs-lookup"><span data-stu-id="530a7-150">By default, the *CustomerID* dimension is selected to create *customer-level measures*.</span></span> <span data-ttu-id="530a7-151">Можете да премахнете измерението по подразбиране, ако искате да създадете *мерки на ниво бизнес*.</span><span class="sxs-lookup"><span data-stu-id="530a7-151">You can remove the default dimension if you want to create *business-level measures*.</span></span>
   1. <span data-ttu-id="530a7-152">Изберете **Готово**, за да добавите измерения към мярката.</span><span class="sxs-lookup"><span data-stu-id="530a7-152">Select **Done** to add the dimensions to the measure.</span></span>

1. <span data-ttu-id="530a7-153">Ако в данните има стойности, които трябва да замените с цяло число, например да замените *нула* с *0*, изберете **Правила**.</span><span class="sxs-lookup"><span data-stu-id="530a7-153">If there are values in your data that you need to replace with an integer, for example, replace *null* with *0*, select **Rules**.</span></span> <span data-ttu-id="530a7-154">Конфигурирайте правилото и се уверете, че сте избрали само цели числа като заместители.</span><span class="sxs-lookup"><span data-stu-id="530a7-154">Configure the rule and make sure that you choose only whole numbers as replacements.</span></span>

1. <span data-ttu-id="530a7-155">Ако има множество пътища между обекта на данни, който сте картографирали, и обекта на *клиента*, трябва да изберете един от идентифицираните [пътища на релации на обекта](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="530a7-155">If there are multiple paths between the data entity you mapped and the *Customer* entity, you have to choose one of the identified [entity relationship paths](relationships.md).</span></span> <span data-ttu-id="530a7-156">Резултатите от измерването могат да варират в зависимост от избрания път.</span><span class="sxs-lookup"><span data-stu-id="530a7-156">Measure results can vary depending on the selected path.</span></span> 
   1. <span data-ttu-id="530a7-157">Изберете **Предпочитания за данни** и изберете пътя на обекта, който трябва да се използва за идентифициране на вашата мярка.</span><span class="sxs-lookup"><span data-stu-id="530a7-157">Select **Data preferences** and choose the entity path that should be used to identify your measure.</span></span> <span data-ttu-id="530a7-158">Ако има само един път до обекта *Клиент*, този контрол няма да се показва.</span><span class="sxs-lookup"><span data-stu-id="530a7-158">If there's only a single path to the *Customer* entity, this control won't show.</span></span>
   1. <span data-ttu-id="530a7-159">Изберете **Готово**, за да приложите своя избор.</span><span class="sxs-lookup"><span data-stu-id="530a7-159">Select **Done** to apply your selection.</span></span> 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Избор на път на обект за мярката.":::

1. <span data-ttu-id="530a7-161">За да добавите още изчисления за мярката, изберете **Ново изчисление**.</span><span class="sxs-lookup"><span data-stu-id="530a7-161">To add more calculations for the measure, select **New calculation**.</span></span> <span data-ttu-id="530a7-162">Можете да използвате само обекти на същия път на обекта за нови изчисления.</span><span class="sxs-lookup"><span data-stu-id="530a7-162">You can only use entities on the same entity path for new calculations.</span></span> <span data-ttu-id="530a7-163">Още изчисления ще се показват като нови колони в изходния обект на мярката.</span><span class="sxs-lookup"><span data-stu-id="530a7-163">More calculations will show as new columns in the measure output entity.</span></span>

1. <span data-ttu-id="530a7-164">Изберете **...** върху изчислението до **Дубликат**, **Преименувайте** или **Премахване** изчисление от мярка.</span><span class="sxs-lookup"><span data-stu-id="530a7-164">Select **...** on the calculation to **Duplicate**, **Rename**, or **Remove** a calculation from a measure.</span></span>

1. <span data-ttu-id="530a7-165">В областта **Преглед** ще видите схемата за данни на изходния обект на мярката, включително филтри и размери.</span><span class="sxs-lookup"><span data-stu-id="530a7-165">In the **Preview** area, you'll see the data schema of the measure output entity, including filters and dimensions.</span></span> <span data-ttu-id="530a7-166">Визуализацията реагира динамично на промени в конфигурацията.</span><span class="sxs-lookup"><span data-stu-id="530a7-166">The preview reacts dynamically to changes in the configuration.</span></span>

1. <span data-ttu-id="530a7-167">Изберете **Изпълнение** за изчисляване на резултатите за конфигурираната мярка.</span><span class="sxs-lookup"><span data-stu-id="530a7-167">Select **Run** to calculate results for the configured measure.</span></span> <span data-ttu-id="530a7-168">Изберете **Записване и затваряне**, ако искате да запазите текущата конфигурация и да изпълните мярката по-късно.</span><span class="sxs-lookup"><span data-stu-id="530a7-168">Select **Save and close** if you want to keep the current configuration and run the measure later.</span></span>

1. <span data-ttu-id="530a7-169">Отидете на **Мерки**, за да видите новосъздадената мярка в списъка.</span><span class="sxs-lookup"><span data-stu-id="530a7-169">Go to **Measures** to see the newly created measure in the list.</span></span>

## <a name="use-a-template-to-build-a-measure"></a><span data-ttu-id="530a7-170">Използване на шаблон за създаване на мярка</span><span class="sxs-lookup"><span data-stu-id="530a7-170">Use a template to build a measure</span></span>

<span data-ttu-id="530a7-171">Можете да използвате предварително дефинирани шаблони на често използвани мерки, за да ги създадете.</span><span class="sxs-lookup"><span data-stu-id="530a7-171">You can use predefined templates of commonly used measures to create them.</span></span> <span data-ttu-id="530a7-172">Подробните описания на шаблоните и насоките ви помагат за ефективно създаване на мярка.</span><span class="sxs-lookup"><span data-stu-id="530a7-172">Detailed descriptions of the templates and a guided experience help you with efficient measure creation.</span></span> <span data-ttu-id="530a7-173">Шаблоните се основават на съпоставени данни от обекта *Обединена дейност*.</span><span class="sxs-lookup"><span data-stu-id="530a7-173">Templates build on mapped data from the *Unified Activity* entity.</span></span> <span data-ttu-id="530a7-174">Затова се уверете, че сте конфигурирали [клиентски дейности](activities.md), преди да създадете мярка от шаблон.</span><span class="sxs-lookup"><span data-stu-id="530a7-174">So make sure you have configured [customer activities](activities.md) before you create a measure from a template.</span></span>

<span data-ttu-id="530a7-175">Налични шаблони за мерки:</span><span class="sxs-lookup"><span data-stu-id="530a7-175">Available measure templates:</span></span> 
- <span data-ttu-id="530a7-176">Средна стойност на транзакцията (ATV)</span><span class="sxs-lookup"><span data-stu-id="530a7-176">Average transaction value (ATV)</span></span>
- <span data-ttu-id="530a7-177">Обща стойност на транзакциите</span><span class="sxs-lookup"><span data-stu-id="530a7-177">Total transaction value</span></span>
- <span data-ttu-id="530a7-178">Средни дневни приходи</span><span class="sxs-lookup"><span data-stu-id="530a7-178">Average daily revenue</span></span>
- <span data-ttu-id="530a7-179">Средни годишни приходи</span><span class="sxs-lookup"><span data-stu-id="530a7-179">Average yearly revenue</span></span>
- <span data-ttu-id="530a7-180">Брой транзакции</span><span class="sxs-lookup"><span data-stu-id="530a7-180">Transaction count</span></span>
- <span data-ttu-id="530a7-181">Спечелени точки за лоялност</span><span class="sxs-lookup"><span data-stu-id="530a7-181">Loyalty points earned</span></span>
- <span data-ttu-id="530a7-182">Използвани точки за лоялност</span><span class="sxs-lookup"><span data-stu-id="530a7-182">Loyalty points redeemed</span></span>
- <span data-ttu-id="530a7-183">Салдо на точките за лоялност</span><span class="sxs-lookup"><span data-stu-id="530a7-183">Loyalty points balance</span></span>
- <span data-ttu-id="530a7-184">Активен живот на клиента</span><span class="sxs-lookup"><span data-stu-id="530a7-184">Active customer lifespan</span></span>
- <span data-ttu-id="530a7-185">Времетраене на членството в програмата за лоялност</span><span class="sxs-lookup"><span data-stu-id="530a7-185">Loyalty membership duration</span></span>
- <span data-ttu-id="530a7-186">Време от последната покупка</span><span class="sxs-lookup"><span data-stu-id="530a7-186">Time since last purchase</span></span>

<span data-ttu-id="530a7-187">Следващата процедура очертава стъпките за създаване на нова мярка с помощта на шаблон.</span><span class="sxs-lookup"><span data-stu-id="530a7-187">The following procedure outlines the steps to build a new measure using a template.</span></span>

1. <span data-ttu-id="530a7-188">В Аналитични данни за аудиторията отидете на **Мерки**.</span><span class="sxs-lookup"><span data-stu-id="530a7-188">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="530a7-189">Изберете **Нов** и след това **Избор на шаблон**.</span><span class="sxs-lookup"><span data-stu-id="530a7-189">Select **New** and select **Choose a template**.</span></span>

   :::image type="content" source="media/measure-use-template.png" alt-text="Екранна снимка на падащото меню при създаване на нова мярка с маркиран шаблон.":::

1. <span data-ttu-id="530a7-191">Намерете шаблона, който отговаря на нуждите ви и изберете **Избор на шаблон**.</span><span class="sxs-lookup"><span data-stu-id="530a7-191">Find the template that fits your need and select **Choose template**.</span></span>

1. <span data-ttu-id="530a7-192">Прегледайте необходимите данни и изберете **Първи стъпки**, ако всички данни са налични.</span><span class="sxs-lookup"><span data-stu-id="530a7-192">Review the required data and select **Get started** if you have all the data in place.</span></span>

1. <span data-ttu-id="530a7-193">В прозореца **Редактиране на име** задайте името на мярката и изходния обект.</span><span class="sxs-lookup"><span data-stu-id="530a7-193">In the **Edit name** pane, set the name for your measure and the output entity.</span></span> 

1. <span data-ttu-id="530a7-194">Изберете **Готово**.</span><span class="sxs-lookup"><span data-stu-id="530a7-194">Select **Done**.</span></span>

1. <span data-ttu-id="530a7-195">В секцията **Задаване на период от време** дефинирайте времевата рамка на данните, които да използвате.</span><span class="sxs-lookup"><span data-stu-id="530a7-195">In the **Set time period** section, define the time frame of the data to use.</span></span> <span data-ttu-id="530a7-196">Изберете дали искате новата мярка да обхваща целия набор от данни, като изберете **През цялото време**.</span><span class="sxs-lookup"><span data-stu-id="530a7-196">Choose if you want the new measure to cover the entire data set by selecting **All time**.</span></span> <span data-ttu-id="530a7-197">Или ако искате мярката да се фокусира върху **Конкретен период от време**.</span><span class="sxs-lookup"><span data-stu-id="530a7-197">Or if you want the measure to focus on a **Specific time period**.</span></span>

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Екранна снимка, която показва раздела за период от време при конфигуриране на мярка от шаблон.":::

1. <span data-ttu-id="530a7-199">В следващата секция изберете **Добавяне на данни**, за да изберете дейностите и да съпоставите съответните данни от обекта *Обединена дейност*.</span><span class="sxs-lookup"><span data-stu-id="530a7-199">In the next section, select **Add data** to choose the activities and map the corresponding data from your *Unified Activity* entity.</span></span>

    1. <span data-ttu-id="530a7-200">Стъпка 1 от 2: Под **Тип дейност** изберете типа на обекта, който искате да използвате.</span><span class="sxs-lookup"><span data-stu-id="530a7-200">Step 1 of 2: Under **Activity type**, choose the type of the entity you want to use.</span></span> <span data-ttu-id="530a7-201">За **Дейности** изберете обектите, които искате да съпоставите.</span><span class="sxs-lookup"><span data-stu-id="530a7-201">For **Activities**, select the entities you want to map.</span></span>
    1. <span data-ttu-id="530a7-202">Стъпка 2 от 2: Изберете атрибута от обекта *Обединена дейност* за компонента, който е необходим за формулата.</span><span class="sxs-lookup"><span data-stu-id="530a7-202">Step 2 of 2: Choose the attribute from the *Unified Activity* entity for the component required by the formula.</span></span> <span data-ttu-id="530a7-203">Например за средна стойност на трансакцията това е атрибутът, представляващ стойността на трансакцията.</span><span class="sxs-lookup"><span data-stu-id="530a7-203">For example, for Average transaction value, it's the attribute representing the Transaction value.</span></span> <span data-ttu-id="530a7-204">За **Времево клеймо на дейност** изберете атрибута от обекта на обединена дейност, който представлява датата и часа на дейността.</span><span class="sxs-lookup"><span data-stu-id="530a7-204">For **Activity timestamp**, choose the attribute from the Unified Activity entity that represents the date and time of the activity.</span></span>
   
1. <span data-ttu-id="530a7-205">След успешното съпоставяне на данните може да видите състоянието като **Завършено** и името на съпоставените дейности и атрибути.</span><span class="sxs-lookup"><span data-stu-id="530a7-205">Once the data mapping is successful, you can see the status as **Complete** and the name of the mapped activities and attributes.</span></span>

   :::image type="content" source="media/measure-template-configured.png" alt-text="Екранна снимка на завършена конфигурация на шаблон за мярка.":::

1. <span data-ttu-id="530a7-207">Вече можете да изберете **Изпълнение** за изчисляване на резултатите от мярката.</span><span class="sxs-lookup"><span data-stu-id="530a7-207">You can now select **Run** to calculate the results of the measure.</span></span> <span data-ttu-id="530a7-208">За да го прецизирате по-късно, изберете **Записване на чернова**.</span><span class="sxs-lookup"><span data-stu-id="530a7-208">To refine it later, select **Save draft**.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="530a7-209">Управление на мерките</span><span class="sxs-lookup"><span data-stu-id="530a7-209">Manage your measures</span></span>

<span data-ttu-id="530a7-210">Можете да намерите списъка с мерки на страницата **Мерки**.</span><span class="sxs-lookup"><span data-stu-id="530a7-210">You can find the list of measures on the **Measures** page.</span></span>

<span data-ttu-id="530a7-211">Ще намерите информация за типа мярка, създателя, датата на създаване, състоянието и състоянието.</span><span class="sxs-lookup"><span data-stu-id="530a7-211">You'll find information about the measure type, the creator, creation date, status, and state.</span></span> <span data-ttu-id="530a7-212">Когато изберете мярка от списъка, можете да прегледате изхода и да изтеглите .CSV файл.</span><span class="sxs-lookup"><span data-stu-id="530a7-212">When you select a measure from the list, you can preview the output and download a .CSV file.</span></span>

<span data-ttu-id="530a7-213">За да обновите всичките си мерки едновременно, изберете **Обновяване на всички** без да избирате конкретна мярка.</span><span class="sxs-lookup"><span data-stu-id="530a7-213">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="530a7-214">![Действия за управление на единични мерки](media/measure-actions.png "Действия за управление на единични мерки")</span><span class="sxs-lookup"><span data-stu-id="530a7-214">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="530a7-215">Изберете мярка от списъка за следните опции:</span><span class="sxs-lookup"><span data-stu-id="530a7-215">Select a measure from the list for the following options:</span></span>

- <span data-ttu-id="530a7-216">Изберете името на мярката, за да видите подробности за нея.</span><span class="sxs-lookup"><span data-stu-id="530a7-216">Select the measure name to see its details.</span></span>
- <span data-ttu-id="530a7-217">**Редактиране** на конфигурацията на мярката.</span><span class="sxs-lookup"><span data-stu-id="530a7-217">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="530a7-218">**Обновете** мярката въз основа на последните данни.</span><span class="sxs-lookup"><span data-stu-id="530a7-218">**Refresh** the measure based on the latest data.</span></span>
- <span data-ttu-id="530a7-219">**Преименуване** на мярката.</span><span class="sxs-lookup"><span data-stu-id="530a7-219">**Rename** the measure.</span></span>
- <span data-ttu-id="530a7-220">**Изтриване** на мярката.</span><span class="sxs-lookup"><span data-stu-id="530a7-220">**Delete** the measure.</span></span>
- <span data-ttu-id="530a7-221">**Активирайте** или **дезактивирайте**.</span><span class="sxs-lookup"><span data-stu-id="530a7-221">**Activate** or **Deactivate**.</span></span> <span data-ttu-id="530a7-222">Неактивните мерки няма да се обновят по време на [планирано опресняване](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="530a7-222">Inactive measures won't get refreshed during a [scheduled refresh](system.md#schedule-tab).</span></span>

> [!TIP]
> <span data-ttu-id="530a7-223">Съществуват [шест вида статус](system.md#status-types) на задачите/процесите.</span><span class="sxs-lookup"><span data-stu-id="530a7-223">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="530a7-224">Освен това повечето процеси [зависят от други процеси надолу по веригата](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="530a7-224">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="530a7-225">Можете да изберете състоянието на процес, за да видите подробности за напредъка на цялата задача.</span><span class="sxs-lookup"><span data-stu-id="530a7-225">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="530a7-226">След като изберете **Вижте подробности** за една от задачите на заданието, ще намерите допълнителна информация: време за обработка, дата на последната обработка и всички грешки и предупреждения, свързани със задачата.</span><span class="sxs-lookup"><span data-stu-id="530a7-226">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="530a7-227">Следваща стъпка</span><span class="sxs-lookup"><span data-stu-id="530a7-227">Next step</span></span>

<span data-ttu-id="530a7-228">Можете да използвате съществуващите мерки за създаване на [клиентски сегмент](segments.md).</span><span class="sxs-lookup"><span data-stu-id="530a7-228">You cam use existing measures to create [a customer segment](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]