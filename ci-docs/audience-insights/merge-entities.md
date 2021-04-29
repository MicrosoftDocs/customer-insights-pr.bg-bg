---
title: Обединяване на обекти в унифициране на данни
description: Обединявайте обекти, за да създадете унифицирани клиентски профили.
ms.date: 04/16/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 4ad06a0baf57e612fc0e0214dfd23d28e7d2b6be
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896498"
---
# <a name="merge-entities"></a><span data-ttu-id="34ac1-103">Сливане на обекти</span><span class="sxs-lookup"><span data-stu-id="34ac1-103">Merge entities</span></span>

<span data-ttu-id="34ac1-104">Фазата на обединяване е последната фаза в процеса на унифициране на данни.</span><span class="sxs-lookup"><span data-stu-id="34ac1-104">The merge phase is the last phase in the data unification process.</span></span> <span data-ttu-id="34ac1-105">Целта е съгласуване на конфликтни данни.</span><span class="sxs-lookup"><span data-stu-id="34ac1-105">Its purpose is reconciling conflicting data.</span></span> <span data-ttu-id="34ac1-106">Примерите за конфликтни данни могат да включват име на клиента, което се намира в два от вашите набори от данни, но това се показва малко по-различно във всеки (като „Грант Маршал“ в сравнение с „Грант Марша“) или телефонен номер, различаващ се по формат (617-803-091X в сравнение с 617803091X).</span><span class="sxs-lookup"><span data-stu-id="34ac1-106">Examples of conflicting data could include a customer name found in two of your datasets but that shows up a little differently in each ("Grant Marshall" versus "Grant Marshal"), or a phone number that differs in format (617-803-091X versus 617803091X).</span></span> <span data-ttu-id="34ac1-107">Обединяването на тези конфликтни точки от данни се извършва на база атрибут по атрибут.</span><span class="sxs-lookup"><span data-stu-id="34ac1-107">Merging those conflicting data points is done on an attribute-by-attribute basis.</span></span>

<span data-ttu-id="34ac1-108">След завършване на [фазата на съвпадение](match-entities.md) можете да започнете фазата на обединяване, като изберете плочката **Обединяване** на страницата **Унифициране**.</span><span class="sxs-lookup"><span data-stu-id="34ac1-108">After completing the [match phase](match-entities.md), you start the merge phase by selecting the **Merge** tile on the **Unify** page.</span></span>

## <a name="review-system-recommendations"></a><span data-ttu-id="34ac1-109">Преглед на системни препоръки</span><span class="sxs-lookup"><span data-stu-id="34ac1-109">Review system recommendations</span></span>

<span data-ttu-id="34ac1-110">На страницата **Обединяване**, можете да изберете и изключите атрибутите за обединяване в обекта на унифицирания клиентски профил (резултат от процеса на конфигуриране).</span><span class="sxs-lookup"><span data-stu-id="34ac1-110">On the **Merge** page, you choose and exclude attributes to merge within your unified customer profile entity (the result of the configuration process).</span></span> <span data-ttu-id="34ac1-111">Някои атрибути се обединяват автоматично от системата.</span><span class="sxs-lookup"><span data-stu-id="34ac1-111">Some attributes are automatically merged by the system.</span></span>

### <a name="view-merged-attributes"></a><span data-ttu-id="34ac1-112">Преглед на обединени атрибути</span><span class="sxs-lookup"><span data-stu-id="34ac1-112">View merged attributes</span></span>

<span data-ttu-id="34ac1-113">За да видите атрибутите, които са включени в някой от автоматично обединените атрибути, изберете съответния обединен атрибут.</span><span class="sxs-lookup"><span data-stu-id="34ac1-113">To view the attributes that are included in one of your automatically merged attributes, select that merged attribute.</span></span> <span data-ttu-id="34ac1-114">Двата атрибута, които съставят този обединен атрибут, се показват в два нови реда под обединения атрибут.</span><span class="sxs-lookup"><span data-stu-id="34ac1-114">The two attributes that compose that merged attribute display in two new rows beneath the merged attribute.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="34ac1-115">![Избор на обединен атрибут](media/configure-data-merge-profile-attributes.png "Избор на обединен атрибут")</span><span class="sxs-lookup"><span data-stu-id="34ac1-115">![Select merged attribute](media/configure-data-merge-profile-attributes.png "Select merged attribute")</span></span>

### <a name="separate-merged-attributes"></a><span data-ttu-id="34ac1-116">Разделяне на обединени атрибути</span><span class="sxs-lookup"><span data-stu-id="34ac1-116">Separate merged attributes</span></span>

<span data-ttu-id="34ac1-117">За да разделите или отмените обединението на някой от автоматично обединените атрибути, намерете атрибута в таблицата **Атрибути на профила**.</span><span class="sxs-lookup"><span data-stu-id="34ac1-117">To separate or unmerge any of the automatically merged attributes, find the attribute in the **Profile attributes** table.</span></span>

1. <span data-ttu-id="34ac1-118">Изберете бутона с многоточие (...).</span><span class="sxs-lookup"><span data-stu-id="34ac1-118">Select the ellipsis (...) button.</span></span>
  
2. <span data-ttu-id="34ac1-119">В падащия списък изберете **Разделяне на полета**.</span><span class="sxs-lookup"><span data-stu-id="34ac1-119">In the dropdown list, select **Separate fields**.</span></span>

### <a name="remove-merged-attributes"></a><span data-ttu-id="34ac1-120">Премахване на обединени атрибути</span><span class="sxs-lookup"><span data-stu-id="34ac1-120">Remove merged attributes</span></span>

<span data-ttu-id="34ac1-121">За да изключите атрибут от окончателния обект на клиентски профил, намерете го в таблицата **Атрибути на профил**.</span><span class="sxs-lookup"><span data-stu-id="34ac1-121">To exclude an attribute from the final customer profile entity, find it in the **Profile attributes** table.</span></span>

1. <span data-ttu-id="34ac1-122">Изберете бутона с многоточие (...).</span><span class="sxs-lookup"><span data-stu-id="34ac1-122">Select the ellipsis (...) button.</span></span>
  
2. <span data-ttu-id="34ac1-123">В падащия списък изберете **Да не се обединява**.</span><span class="sxs-lookup"><span data-stu-id="34ac1-123">In the dropdown list, select **Don't merge**.</span></span>

   <span data-ttu-id="34ac1-124">Атрибутът се премества в секцията **Премахнати от запис на клиент**.</span><span class="sxs-lookup"><span data-stu-id="34ac1-124">The attribute is moved to the **Removed from customer record** section.</span></span>

## <a name="manually-add-a-merged-attribute"></a><span data-ttu-id="34ac1-125">Ръчно добавяне на обединен атрибут</span><span class="sxs-lookup"><span data-stu-id="34ac1-125">Manually add a merged attribute</span></span>

<span data-ttu-id="34ac1-126">За да добавите обединен атрибут, отидете в страницата **Обединяване**.</span><span class="sxs-lookup"><span data-stu-id="34ac1-126">To add a merged attribute, go to the **Merge** page.</span></span>

1. <span data-ttu-id="34ac1-127">Изберете **Добавяне на обединен атрибут**.</span><span class="sxs-lookup"><span data-stu-id="34ac1-127">Select **Add merged attribute**.</span></span>

2. <span data-ttu-id="34ac1-128">Въведете **име**, за да го идентифицирате на страницата **Обединяване** по-късно.</span><span class="sxs-lookup"><span data-stu-id="34ac1-128">Provide a **Name** to identify it on the **Merge** page later.</span></span>

3. <span data-ttu-id="34ac1-129">По желание, посочете **Показвано име**, което да се показва в обекта на унифицирания клиентски профил.</span><span class="sxs-lookup"><span data-stu-id="34ac1-129">Optionally, provide a **Display name** to appear in the unified Customer Profile entity.</span></span>

4. <span data-ttu-id="34ac1-130">Конфигурирайте **Избор на дублирани атрибути**, за да изберете атрибутите, които искате да обедините от съпоставените обекти.</span><span class="sxs-lookup"><span data-stu-id="34ac1-130">Configure **Select duplicate attributes** to select the attributes that you want to merge from the matched entities.</span></span> <span data-ttu-id="34ac1-131">Можете също да търсите атрибути.</span><span class="sxs-lookup"><span data-stu-id="34ac1-131">You can also search for attributes.</span></span>

5. <span data-ttu-id="34ac1-132">Задайте **Категоризиране по важност**, за да подредите по приоритет някой атрибут над останалите.</span><span class="sxs-lookup"><span data-stu-id="34ac1-132">Set the **Rank by importance** to prioritize one attribute above the others.</span></span> <span data-ttu-id="34ac1-133">Например, ако обектът *WebAccountCSV* включва най-точните данни за атрибута *Пълни имена*, можете да подредите по приоритет този обект над *ContactCSV*, като изберете *WebAccountCSV*.</span><span class="sxs-lookup"><span data-stu-id="34ac1-133">For example, if the *WebAccountCSV* entity includes the most accurate data about the *Full Names* attribute, you could prioritize this entity over *ContactCSV* by selecting *WebAccountCSV*.</span></span> <span data-ttu-id="34ac1-134">В резултат *WebAccountCSV* се премества на първо място по приоритет, докато *ContactCSV* се премества на второ място по приоритет при изтегляне на стойности за атрибута *Пълно име*.</span><span class="sxs-lookup"><span data-stu-id="34ac1-134">As a result, *WebAccountCSV* moves to first priority, while *ContactCSV* moves to second priority when pulling values for the *Full Name* attribute.</span></span>

## <a name="run-your-merge"></a><span data-ttu-id="34ac1-135">Изпълнение на обединяване</span><span class="sxs-lookup"><span data-stu-id="34ac1-135">Run your merge</span></span>

<span data-ttu-id="34ac1-136">Независимо дали ръчно обединявате атрибути, или оставяте системата да ги обединява, винаги можете да изпълните обединяването.</span><span class="sxs-lookup"><span data-stu-id="34ac1-136">Whether you manually merge attributes or let the system merge them, you can always run your merge.</span></span> <span data-ttu-id="34ac1-137">На страницата **Съвпадение** изберете **Изпълнение**, за да стартирате процеса.</span><span class="sxs-lookup"><span data-stu-id="34ac1-137">Select **Run** on the **Merge** page to start the process.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="34ac1-138">![Записване и изпълнение на обединяване на данни](media/configure-data-merge-save-run.png "Записване и изпълнение на обединяване на данни")</span><span class="sxs-lookup"><span data-stu-id="34ac1-138">![Data merge Save and Run](media/configure-data-merge-save-run.png "Data merge Save and Run")</span></span>

<span data-ttu-id="34ac1-139">За да направите допълнителни промени и да изпълните отново стъпката, можете да отмените обединяване в ход.</span><span class="sxs-lookup"><span data-stu-id="34ac1-139">To make additional changes and rerun the step, you can cancel an in-progress merge.</span></span> <span data-ttu-id="34ac1-140">Изберете **Обновяване...** и изберете **Отмяна на задача**  в страничния панел, който се показва.</span><span class="sxs-lookup"><span data-stu-id="34ac1-140">Select **Refreshing ...** and select **Cancel job**  in the side pane that appears.</span></span>

<span data-ttu-id="34ac1-141">Когато текстът **Обновяване...** се промени на **Успешно**, обединяването е приключило и отстранило противоречия в данните според определените от вас правила.</span><span class="sxs-lookup"><span data-stu-id="34ac1-141">After the **Refreshing ...** text changes to **Successful**, merge has completed and resolved contradictions in your data according to the policies you defined.</span></span> <span data-ttu-id="34ac1-142">Обединените и необединените атрибути се включват в обекта на унифицирания профил.</span><span class="sxs-lookup"><span data-stu-id="34ac1-142">Merged and unmerged attributes are included in the unified profile entity.</span></span> <span data-ttu-id="34ac1-143">Изключените атрибути не се включват в обекта на унифицирания профил.</span><span class="sxs-lookup"><span data-stu-id="34ac1-143">Excluded attributes aren't included in the unified profile entity.</span></span>

<span data-ttu-id="34ac1-144">Ако това не е първият път, когато изпълнявате успешно обединяване, всички процеси надолу по веригата, включително допълване, сегментиране и мерки, ще се изпълнят повторно автоматично.</span><span class="sxs-lookup"><span data-stu-id="34ac1-144">If it wasn't the first time you ran a merge successfully, all downstream processes, including enrichment, segmentation, and measures will rerun automatically.</span></span> <span data-ttu-id="34ac1-145">След като всички процеси надолу по веригата се изпълнят повторно, клиентските профили ще отразяват всички промени, които сте направили.</span><span class="sxs-lookup"><span data-stu-id="34ac1-145">After all downstream processes have been rerun, the customer profiles reflect any changes you made.</span></span>

> [!TIP]
> <span data-ttu-id="34ac1-146">Съществуват [шест вида статус](system.md#status-types) на задачите/процесите.</span><span class="sxs-lookup"><span data-stu-id="34ac1-146">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="34ac1-147">Освен това повечето процеси [зависят от други процеси надолу по веригата](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="34ac1-147">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="34ac1-148">Можете да изберете състоянието на процес, за да видите подробности за напредъка на цялата задача.</span><span class="sxs-lookup"><span data-stu-id="34ac1-148">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="34ac1-149">След като изберете **Вижте подробности** за една от задачите на заданието, ще намерите допълнителна информация: време за обработка, дата на последната обработка и всички грешки и предупреждения, свързани със задачата.</span><span class="sxs-lookup"><span data-stu-id="34ac1-149">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="34ac1-150">Следваща стъпка</span><span class="sxs-lookup"><span data-stu-id="34ac1-150">Next Step</span></span>

<span data-ttu-id="34ac1-151">Конфигурирайте [дейности](activities.md), [допълване](enrichment-hub.md) или [релации](relationships.md), за да получите повече аналитични данни за клиентите.</span><span class="sxs-lookup"><span data-stu-id="34ac1-151">Configure [activities](activities.md), [enrichment](enrichment-hub.md), or [relationships](relationships.md) to gain more insights about your customers.</span></span>

<span data-ttu-id="34ac1-152">Ако вече сте конфигурирали дейности, допълване или релации или ако сте дефинирали сегменти, те ще се обработват автоматично, за да използват най-новите данни за клиента.</span><span class="sxs-lookup"><span data-stu-id="34ac1-152">If you already configured activities, enrichment, or relationships, or if you defined segments, they'll be processed automatically to use the latest customer data.</span></span>




[!INCLUDE[footer-include](../includes/footer-banner.md)]