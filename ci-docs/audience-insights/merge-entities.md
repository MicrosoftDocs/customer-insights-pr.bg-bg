---
title: Обединяване на обекти в унифициране на данни
description: Обединявайте обекти, за да създадете унифицирани клиентски профили.
ms.date: 05/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 86ab3cefa70e5fab4bdb27cde363adee26efee4c
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305610"
---
# <a name="merge-entities"></a><span data-ttu-id="f57e2-103">Сливане на обекти</span><span class="sxs-lookup"><span data-stu-id="f57e2-103">Merge entities</span></span>

<span data-ttu-id="f57e2-104">Фазата на обединяване е последната фаза в процеса на унифициране на данни.</span><span class="sxs-lookup"><span data-stu-id="f57e2-104">The merge phase is the last phase in the data unification process.</span></span> <span data-ttu-id="f57e2-105">Целта е съгласуване на конфликтни данни.</span><span class="sxs-lookup"><span data-stu-id="f57e2-105">Its purpose is reconciling conflicting data.</span></span> <span data-ttu-id="f57e2-106">Примерите за конфликтни данни могат да включват име на клиента, което се намира в два от вашите набори от данни, но това се показва малко по-различно във всеки (като „Грант Маршал“ в сравнение с „Грант Марша“) или телефонен номер, различаващ се по формат (617-803-091X в сравнение с 617803091X).</span><span class="sxs-lookup"><span data-stu-id="f57e2-106">Examples of conflicting data could include a customer name found in two of your datasets but that shows up a little differently in each ("Grant Marshall" versus "Grant Marshal"), or a phone number that differs in format (617-803-091X versus 617803091X).</span></span> <span data-ttu-id="f57e2-107">Обединяването на тези конфликтни точки от данни се извършва на база атрибут по атрибут.</span><span class="sxs-lookup"><span data-stu-id="f57e2-107">Merging those conflicting data points is done on an attribute-by-attribute basis.</span></span>

:::image type="content" source="media/merge-fields-page.png" alt-text="Страница за обединяване в процеса на обединяване на данни, показваща таблица с обединени полета, които дефинират единния клиентски профил.":::

<span data-ttu-id="f57e2-109">След завършване на [фазата на съвпадение](match-entities.md) можете да започнете фазата на обединяване, като изберете плочката **Обединяване** на страницата **Унифициране**.</span><span class="sxs-lookup"><span data-stu-id="f57e2-109">After completing the [match phase](match-entities.md), you start the merge phase by selecting the **Merge** tile on the **Unify** page.</span></span>

## <a name="review-system-recommendations"></a><span data-ttu-id="f57e2-110">Преглед на системни препоръки</span><span class="sxs-lookup"><span data-stu-id="f57e2-110">Review system recommendations</span></span>

<span data-ttu-id="f57e2-111">В **Данни** > **Обединяване** > **Сливане**, вие избирате и изключвате атрибути за сливане в рамките на вашия обединен обект на потребителски профил.</span><span class="sxs-lookup"><span data-stu-id="f57e2-111">On **Data** > **Unify** > **Merge**, you choose and exclude attributes to merge within your unified customer profile entity.</span></span> <span data-ttu-id="f57e2-112">Единният потребителски профил е резултат от процеса на обединяване на данните.</span><span class="sxs-lookup"><span data-stu-id="f57e2-112">The unified customer profile is the result of the data unification process.</span></span> <span data-ttu-id="f57e2-113">Някои атрибути се обединяват автоматично от системата.</span><span class="sxs-lookup"><span data-stu-id="f57e2-113">Some attributes are automatically merged by the system.</span></span>

<span data-ttu-id="f57e2-114">За да видите атрибутите, които са включени в един от вашите автоматично обединени атрибути, изберете този обединен атрибут в **Полета за клиенти** раздел на таблицата.</span><span class="sxs-lookup"><span data-stu-id="f57e2-114">To view the attributes that are included in one of your automatically merged attributes, select that merged attribute in the **Customer fields** tab of the table.</span></span> <span data-ttu-id="f57e2-115">Двата атрибута, които съставят този обединен атрибут, ще се покажат в два нови реда под обединения атрибут.</span><span class="sxs-lookup"><span data-stu-id="f57e2-115">The attributes that compose that merged attribute display in two new rows beneath the merged attribute.</span></span>

## <a name="separate-rename-exclude-and-edit-merged-fields"></a><span data-ttu-id="f57e2-116">Отделете, преименувайте, изключете и редактирайте обединените полета</span><span class="sxs-lookup"><span data-stu-id="f57e2-116">Separate, rename, exclude, and edit merged fields</span></span>

<span data-ttu-id="f57e2-117">Можете да промените начина, по който системата обработва обединени атрибути, за да генерира обединения потребителски профил.</span><span class="sxs-lookup"><span data-stu-id="f57e2-117">You can change how the system processes merged attributes to generate the unified customer profile.</span></span> <span data-ttu-id="f57e2-118">Изберете **Покажи още** и изберете какво искате да промените.</span><span class="sxs-lookup"><span data-stu-id="f57e2-118">Select **Show more** and choose what you want to change.</span></span>

:::image type="content" source="media/manage-merged-attributes.png" alt-text="Опции в падащото меню Показване на повече за управление на обединени атрибути.":::

<span data-ttu-id="f57e2-120">За повече информация вижте следващите секции.</span><span class="sxs-lookup"><span data-stu-id="f57e2-120">For more information, see the following sections.</span></span>

## <a name="separate-merged-fields"></a><span data-ttu-id="f57e2-121">Разделяне на слети полета</span><span class="sxs-lookup"><span data-stu-id="f57e2-121">Separate merged fields</span></span>

<span data-ttu-id="f57e2-122">За да разделите обединените полета, намерете атрибута в таблицата.</span><span class="sxs-lookup"><span data-stu-id="f57e2-122">To separate merged fields, find the attribute in the table.</span></span> <span data-ttu-id="f57e2-123">Отделените полета се показват като отделни точки от данни в единния потребителски профил.</span><span class="sxs-lookup"><span data-stu-id="f57e2-123">Separated fields show as individual data points on the unified customer profile.</span></span> 

1. <span data-ttu-id="f57e2-124">Изберете слятото поле.</span><span class="sxs-lookup"><span data-stu-id="f57e2-124">Select the merged field.</span></span>
  
1. <span data-ttu-id="f57e2-125">Изберете **Покажи повече** и изберете **Отделни полета**.</span><span class="sxs-lookup"><span data-stu-id="f57e2-125">Select **Show more** and choose **Separate fields**.</span></span>
 
1. <span data-ttu-id="f57e2-126">Потвърдете разделянето.</span><span class="sxs-lookup"><span data-stu-id="f57e2-126">Confirm the separation.</span></span>

1. <span data-ttu-id="f57e2-127">Изберете **Записване** и **Изпълнение** за обработка на промените.</span><span class="sxs-lookup"><span data-stu-id="f57e2-127">Select **Save** and **Run** to process the changes.</span></span>

## <a name="rename-merged-fields"></a><span data-ttu-id="f57e2-128">Преименувайте обединените полета</span><span class="sxs-lookup"><span data-stu-id="f57e2-128">Rename merged fields</span></span>

<span data-ttu-id="f57e2-129">Променете показваното име на обединени атрибути.</span><span class="sxs-lookup"><span data-stu-id="f57e2-129">Change the display name of merged attributes.</span></span> <span data-ttu-id="f57e2-130">Не можете да промените името на изходния обект.</span><span class="sxs-lookup"><span data-stu-id="f57e2-130">You can't change the name of the output entity.</span></span>

1. <span data-ttu-id="f57e2-131">Изберете слятото поле.</span><span class="sxs-lookup"><span data-stu-id="f57e2-131">Select the merged field.</span></span>
  
1. <span data-ttu-id="f57e2-132">Изберете **Покажи повече** и изберете **Преименуване**.</span><span class="sxs-lookup"><span data-stu-id="f57e2-132">Select **Show more** and choose **Rename**.</span></span>

1. <span data-ttu-id="f57e2-133">Потвърдете промененото име на дисплея.</span><span class="sxs-lookup"><span data-stu-id="f57e2-133">Confirm the changed display name.</span></span> 

1. <span data-ttu-id="f57e2-134">Изберете **Записване** и **Изпълнение** за обработка на промените.</span><span class="sxs-lookup"><span data-stu-id="f57e2-134">Select **Save** and **Run** to process the changes.</span></span>

## <a name="exclude-merged-fields"></a><span data-ttu-id="f57e2-135">Изключване на слети полета</span><span class="sxs-lookup"><span data-stu-id="f57e2-135">Exclude merged fields</span></span>

<span data-ttu-id="f57e2-136">Изключете атрибут от единния потребителски профил.</span><span class="sxs-lookup"><span data-stu-id="f57e2-136">Exclude an attribute from the unified customer profile.</span></span> <span data-ttu-id="f57e2-137">Ако полето се използва в други процеси, например в сегмент, премахнете го от тези процеси, преди да го изключите от потребителския профил.</span><span class="sxs-lookup"><span data-stu-id="f57e2-137">If the field is used in other processes, for example in a segment, remove it from these processes before excluding it from the customer profile.</span></span> 

1. <span data-ttu-id="f57e2-138">Изберете слятото поле.</span><span class="sxs-lookup"><span data-stu-id="f57e2-138">Select the merged field.</span></span>
  
1. <span data-ttu-id="f57e2-139">Изберете **Покажи повече** и изберете **Изключване**.</span><span class="sxs-lookup"><span data-stu-id="f57e2-139">Select **Show more** and choose **Exclude**.</span></span>

1. <span data-ttu-id="f57e2-140">Потвърдете изключването.</span><span class="sxs-lookup"><span data-stu-id="f57e2-140">Confirm the exclusion.</span></span>

1. <span data-ttu-id="f57e2-141">Изберете **Записване** и **Изпълнение** за обработка на промените.</span><span class="sxs-lookup"><span data-stu-id="f57e2-141">Select **Save** and **Run** to process the changes.</span></span> 

<span data-ttu-id="f57e2-142">На **Обединяване** страница, изберете **Изключени полета**, за да видите списъка с всички изключени полета.</span><span class="sxs-lookup"><span data-stu-id="f57e2-142">On the **Merge** page, select **Excluded fields** to see the list of all excluded fields.</span></span> <span data-ttu-id="f57e2-143">Този панел ви позволява да добавяте обратно изключени полета.</span><span class="sxs-lookup"><span data-stu-id="f57e2-143">This pane lets you add excluded fields back.</span></span>

## <a name="manually-combine-fields"></a><span data-ttu-id="f57e2-144">Ръчно комбиниране на полета</span><span class="sxs-lookup"><span data-stu-id="f57e2-144">Manually combine fields</span></span>

<span data-ttu-id="f57e2-145">Посочете обединен атрибут ръчно.</span><span class="sxs-lookup"><span data-stu-id="f57e2-145">Specify a merged attribute manually.</span></span> 

1. <span data-ttu-id="f57e2-146">На **Обединяване** страница, изберете **Комбинирайте полета**.</span><span class="sxs-lookup"><span data-stu-id="f57e2-146">On the **Merge** page, select **Combine fields**.</span></span>

1. <span data-ttu-id="f57e2-147">Предоставете **Име** и **Име на изходното поле**.</span><span class="sxs-lookup"><span data-stu-id="f57e2-147">Provide a **Name** and an **Output field name**.</span></span>

1. <span data-ttu-id="f57e2-148">Изберете поле за добавяне.</span><span class="sxs-lookup"><span data-stu-id="f57e2-148">Choose a field to add.</span></span> <span data-ttu-id="f57e2-149">Изберете **Добавяне на полета**, за да комбинирате повече полета.</span><span class="sxs-lookup"><span data-stu-id="f57e2-149">Select **Add fields** to combine more fields.</span></span>

1. <span data-ttu-id="f57e2-150">Потвърдете изключването.</span><span class="sxs-lookup"><span data-stu-id="f57e2-150">Confirm the exclusion.</span></span>

1. <span data-ttu-id="f57e2-151">Изберете **Записване** и **Изпълнение** за обработка на промените.</span><span class="sxs-lookup"><span data-stu-id="f57e2-151">Select **Save** and **Run** to process the changes.</span></span> 

## <a name="change-the-order-of-fields"></a><span data-ttu-id="f57e2-152">Промяна на реда на полета</span><span class="sxs-lookup"><span data-stu-id="f57e2-152">Change the order of fields</span></span>

<span data-ttu-id="f57e2-153">Някои обекти съдържат повече подробности от други.</span><span class="sxs-lookup"><span data-stu-id="f57e2-153">Some entities contain more details than others.</span></span> <span data-ttu-id="f57e2-154">Ако обектът включва най-новите данни за дадено поле, можете да го приоритизирате пред други обекти при обединяване на стойности.</span><span class="sxs-lookup"><span data-stu-id="f57e2-154">If an entity includes the latest data about a field, you can prioritize it over other entities when merging values.</span></span>

1. <span data-ttu-id="f57e2-155">Изберете слятото поле.</span><span class="sxs-lookup"><span data-stu-id="f57e2-155">Select the merged field.</span></span>
  
1. <span data-ttu-id="f57e2-156">Изберете **Покажи повече** и изберете **Редактиране**.</span><span class="sxs-lookup"><span data-stu-id="f57e2-156">Select **Show more** and choose **Edit**.</span></span>

1. <span data-ttu-id="f57e2-157">В екрана **Комбинирайте полета**, изберете **Преместване нагоре/надолу**, за да зададете реда или да ги плъзнете и пуснете в желаната позиция.</span><span class="sxs-lookup"><span data-stu-id="f57e2-157">In the **Combine fields** pane, select **Move up/down** to set the order or drag and drop them in the desired position.</span></span>

1. <span data-ttu-id="f57e2-158">Потвърждение на промяната.</span><span class="sxs-lookup"><span data-stu-id="f57e2-158">Confirm the change.</span></span>

1. <span data-ttu-id="f57e2-159">Изберете **Записване** и **Изпълнение** за обработка на промените.</span><span class="sxs-lookup"><span data-stu-id="f57e2-159">Select **Save** and **Run** to process the changes.</span></span>

## <a name="run-your-merge"></a><span data-ttu-id="f57e2-160">Изпълнение на обединяване</span><span class="sxs-lookup"><span data-stu-id="f57e2-160">Run your merge</span></span>

<span data-ttu-id="f57e2-161">Независимо дали ръчно обединявате атрибути, или оставяте системата да ги обединява, винаги можете да изпълните обединяването.</span><span class="sxs-lookup"><span data-stu-id="f57e2-161">Whether you manually merge attributes or let the system merge them, you can always run your merge.</span></span> <span data-ttu-id="f57e2-162">На страницата **Съвпадение** изберете **Изпълнение**, за да стартирате процеса.</span><span class="sxs-lookup"><span data-stu-id="f57e2-162">Select **Run** on the **Merge** page to start the process.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="f57e2-163">![Записване и изпълнение на обединяване на данни](media/configure-data-merge-save-run.png "Записване и изпълнение на обединяване на данни")</span><span class="sxs-lookup"><span data-stu-id="f57e2-163">![Data merge Save and Run](media/configure-data-merge-save-run.png "Data merge Save and Run")</span></span>

<span data-ttu-id="f57e2-164">Изберете **Стартирайте само сливане**, ако искате само да видите продукцията, отразена в обединения клиентски обект.</span><span class="sxs-lookup"><span data-stu-id="f57e2-164">Choose **Run only Merge** if you only want to see the output reflected in the unified customer entity.</span></span> <span data-ttu-id="f57e2-165">Процесите надолу по веригата ще бъдат освежени като [дефинирани в графика за опресняване](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="f57e2-165">Downstream processes will be refreshed as [defined in the refresh schedule](system.md#schedule-tab).</span></span>

<span data-ttu-id="f57e2-166">Избирам **Стартирайте процесите за сливане и поток**, за да обновите системата с вашите промени.</span><span class="sxs-lookup"><span data-stu-id="f57e2-166">Choose **Run Merge and downstream processes** to refresh the system with your changes.</span></span> <span data-ttu-id="f57e2-167">Всички процеси, включително обогатяване, сегменти и мерки ще се повторят автоматично.</span><span class="sxs-lookup"><span data-stu-id="f57e2-167">All processes, including enrichment, segments, and measures will rerun automatically.</span></span> <span data-ttu-id="f57e2-168">След приключване на всички процеси надолу по веригата, потребителските профили отразяват всички промени, които сте направили.</span><span class="sxs-lookup"><span data-stu-id="f57e2-168">After all downstream processes have completed, the customer profiles reflect any changes you made.</span></span>

<span data-ttu-id="f57e2-169">За да направите повече промени и да повторите стъпката, можете да отмените текущо обединяване.</span><span class="sxs-lookup"><span data-stu-id="f57e2-169">To make more changes and rerun the step, you can cancel an in-progress merge.</span></span> <span data-ttu-id="f57e2-170">Изберете **Обновяване...** и изберете **Отмяна на задача**  в страничния панел, който се показва.</span><span class="sxs-lookup"><span data-stu-id="f57e2-170">Select **Refreshing ...** and select **Cancel job**  in the side pane that appears.</span></span>

> [!TIP]
> <span data-ttu-id="f57e2-171">Съществуват [шест вида статус](system.md#status-types) на задачите/процесите.</span><span class="sxs-lookup"><span data-stu-id="f57e2-171">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="f57e2-172">Освен това повечето процеси [зависят от други процеси надолу по веригата](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="f57e2-172">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="f57e2-173">Можете да изберете състоянието на процес, за да видите подробности за напредъка на цялата задача.</span><span class="sxs-lookup"><span data-stu-id="f57e2-173">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="f57e2-174">След като изберете **Вижте подробности** за една от задачите на заданието, ще намерите допълнителна информация: време за обработка, дата на последната обработка и всички грешки и предупреждения, свързани със задачата.</span><span class="sxs-lookup"><span data-stu-id="f57e2-174">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="f57e2-175">Следваща стъпка</span><span class="sxs-lookup"><span data-stu-id="f57e2-175">Next Step</span></span>

<span data-ttu-id="f57e2-176">Конфигурирайте [дейности](activities.md), [допълване](enrichment-hub.md) или [релации](relationships.md), за да получите повече аналитични данни за клиентите.</span><span class="sxs-lookup"><span data-stu-id="f57e2-176">Configure [activities](activities.md), [enrichment](enrichment-hub.md), or [relationships](relationships.md) to gain more insights about your customers.</span></span>

<span data-ttu-id="f57e2-177">Ако вече сте конфигурирали дейности, обогатяване или сегменти, те ще бъдат обработени автоматично, за да се използват най-новите клиентски данни.</span><span class="sxs-lookup"><span data-stu-id="f57e2-177">If you already configured activities, enrichment, or segments, they'll be processed automatically to use the latest customer data.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
