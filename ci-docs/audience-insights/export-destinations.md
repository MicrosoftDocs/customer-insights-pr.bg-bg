---
title: Експортиране на данни от Customer Insights
description: Управлявайте експортирането, за да споделяте данни.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 28563e3a76535cb0c92bfcda4ef5037430d00cfa
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305465"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="de680-103">Общ преглед на експортирания (преглед)</span><span class="sxs-lookup"><span data-stu-id="de680-103">Exports (preview) overview</span></span>

<span data-ttu-id="de680-104">Страницата **Експортиране** ви показва всички конфигурирани експортирания.</span><span class="sxs-lookup"><span data-stu-id="de680-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="de680-105">Експортирането споделя специфични данни с различни приложения.</span><span class="sxs-lookup"><span data-stu-id="de680-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="de680-106">Те могат да включват клиентски профили или обекти, схеми и подробности за съпоставяне.</span><span class="sxs-lookup"><span data-stu-id="de680-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="de680-107">Всяко експортиране изисква [връзка, настроена от администратор, за управление на удостоверяване и достъп](connections.md).</span><span class="sxs-lookup"><span data-stu-id="de680-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

<span data-ttu-id="de680-108">Отидете на **Данни** > **Експортиране**, за да видите страницата за експортиране.</span><span class="sxs-lookup"><span data-stu-id="de680-108">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="de680-109">Всички потребителски роли могат да преглеждат конфигуриран износ.</span><span class="sxs-lookup"><span data-stu-id="de680-109">All user roles can view configured exports.</span></span> <span data-ttu-id="de680-110">Използвайте полето за търсене в командната лента, за да намерите експортиране по тяхно име, име на връзка или тип връзка.</span><span class="sxs-lookup"><span data-stu-id="de680-110">Use the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="de680-111">Настройване на ново експортиране</span><span class="sxs-lookup"><span data-stu-id="de680-111">Set up a new export</span></span>

<span data-ttu-id="de680-112">За да настроите или редактирате експортиране, трябва да имате налични връзки.</span><span class="sxs-lookup"><span data-stu-id="de680-112">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="de680-113">Връзките зависят от [потребителската роля](permissions.md):</span><span class="sxs-lookup"><span data-stu-id="de680-113">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="de680-114">Администраторите имат достъп до всички връзки.</span><span class="sxs-lookup"><span data-stu-id="de680-114">Administrators have access to all connections.</span></span> <span data-ttu-id="de680-115">Те също могат да създават нови връзки, когато настройват експортиране.</span><span class="sxs-lookup"><span data-stu-id="de680-115">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="de680-116">Сътрудниците могат да осъществяват достъп до конкретни връзки.</span><span class="sxs-lookup"><span data-stu-id="de680-116">Contributors can have access to specific connections.</span></span> <span data-ttu-id="de680-117">Те зависят от администраторите за конфигуриране и споделяне на връзки.</span><span class="sxs-lookup"><span data-stu-id="de680-117">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="de680-118">Списъкът за износ показва участници в това дали те могат да редактират или да преглеждат само износ в колоната **Вашите разрешения**.</span><span class="sxs-lookup"><span data-stu-id="de680-118">The exports list shows contributors whether they can edit or only view an export in the **Your permissions** column.</span></span> <span data-ttu-id="de680-119">За повече информация вижте [Разрешаване на сътрудници да използват връзка за експортиране](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="de680-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="de680-120">Преглеждащите могат да виждат само съществуващи експортирания, но не и да ги създават.</span><span class="sxs-lookup"><span data-stu-id="de680-120">Viewers can only view existing exports but not create them.</span></span>

### <a name="define-a-new-export"></a><span data-ttu-id="de680-121">Определяне на ново експортиране</span><span class="sxs-lookup"><span data-stu-id="de680-121">Define a new export</span></span>

1. <span data-ttu-id="de680-122">Отидете на **Данни** > **Експортиране**.</span><span class="sxs-lookup"><span data-stu-id="de680-122">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="de680-123">За да създадете ново експортиране, изберете **Добавяне на експортиране**.</span><span class="sxs-lookup"><span data-stu-id="de680-123">Select **Add export** to create a new export.</span></span>

1. <span data-ttu-id="de680-124">В прозореца **Настройване на експортиране** изберете коя връзка да използвате.</span><span class="sxs-lookup"><span data-stu-id="de680-124">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="de680-125">[Връзките](connections.md) се управляват от администратори.</span><span class="sxs-lookup"><span data-stu-id="de680-125">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="de680-126">Посочете необходимите подробности и изберете **Записване** за създаване на експортиране.</span><span class="sxs-lookup"><span data-stu-id="de680-126">Provide the required details and select **Save** to create the export.</span></span>

### <a name="define-a-new-export-based-on-an-existing-export"></a><span data-ttu-id="de680-127">Дефинирайте нов износ въз основа на съществуващ износ</span><span class="sxs-lookup"><span data-stu-id="de680-127">Define a new export based on an existing export</span></span>

1. <span data-ttu-id="de680-128">Отидете на **Данни** > **Експортиране**.</span><span class="sxs-lookup"><span data-stu-id="de680-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="de680-129">В списъка с експортирания изберете експортирането, който желаете да дублирате.</span><span class="sxs-lookup"><span data-stu-id="de680-129">In the list of exports, select the export you want to duplicate.</span></span>

1. <span data-ttu-id="de680-130">Изберете **Създайте дубликат** в командната лента, за да отворите **Настройте експортиране** панел с подробности за избрания експорт.</span><span class="sxs-lookup"><span data-stu-id="de680-130">Select **Create duplicate** in the command bar to open the **Set up export** pane with the details of the selected export.</span></span>

1. <span data-ttu-id="de680-131">Прегледайте и адаптирайте експорта и изберете **Запазете** за да създадете нов износ.</span><span class="sxs-lookup"><span data-stu-id="de680-131">Review and adapt the export and select **Save** to create a new export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="de680-132">Редактиране на експортиране</span><span class="sxs-lookup"><span data-stu-id="de680-132">Edit an export</span></span>

1. <span data-ttu-id="de680-133">Отидете на **Данни** > **Експортиране**.</span><span class="sxs-lookup"><span data-stu-id="de680-133">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="de680-134">В списъка с експортирания изберете експортирането, който желаете да редактирате.</span><span class="sxs-lookup"><span data-stu-id="de680-134">In the list of exports, select the export you want to edit.</span></span>

1. <span data-ttu-id="de680-135">В командната лента изберете **Редактирай**.</span><span class="sxs-lookup"><span data-stu-id="de680-135">Select **Edit** in the command bar.</span></span>

1. <span data-ttu-id="de680-136">Променете стойностите, които искате да актуализирате, и изберете **Записване**.</span><span class="sxs-lookup"><span data-stu-id="de680-136">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="de680-137">Преглед на експортирания и подробностите за експортиране</span><span class="sxs-lookup"><span data-stu-id="de680-137">View exports and export details</span></span>

<span data-ttu-id="de680-138">След създаването на местоназначение за експортиране, те са изброени в **Данни** > **Експортирания**.</span><span class="sxs-lookup"><span data-stu-id="de680-138">After creating export destinations, they're listed on **Data** > **Exports**.</span></span> <span data-ttu-id="de680-139">Всички потребители могат да видят кои данни се споделят и последното им състояние.</span><span class="sxs-lookup"><span data-stu-id="de680-139">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="de680-140">Отидете на **Данни** > **Експортиране**.</span><span class="sxs-lookup"><span data-stu-id="de680-140">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="de680-141">Избират потребители без разрешения за редактиране **Изглед** вместо **редактиране** за да видите подробности за износа.</span><span class="sxs-lookup"><span data-stu-id="de680-141">Users without edit permissions select **View** instead of **Edit** to see the export details.</span></span>

1. <span data-ttu-id="de680-142">Страничният екран показва конфигурацията на експортиране.</span><span class="sxs-lookup"><span data-stu-id="de680-142">The side pane shows the configuration of an export.</span></span> <span data-ttu-id="de680-143">Без разрешения за редактиране не можете да променяте стойности.</span><span class="sxs-lookup"><span data-stu-id="de680-143">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="de680-144">Изберете **Затваряне**, за да се върнете към страницата за експортиране.</span><span class="sxs-lookup"><span data-stu-id="de680-144">Select **Close** to return to the exports page.</span></span>

## <a name="schedule-and-run-exports"></a><span data-ttu-id="de680-145">Планиране и изпълнение на експортирания</span><span class="sxs-lookup"><span data-stu-id="de680-145">Schedule and run exports</span></span>

<span data-ttu-id="de680-146">Всеки експорт, който конфигурирате, има график за опресняване.</span><span class="sxs-lookup"><span data-stu-id="de680-146">Each export you configure has a refresh schedule.</span></span> <span data-ttu-id="de680-147">По време на опресняване системата търси нови или актуализирани данни, които да включи в експортирането.</span><span class="sxs-lookup"><span data-stu-id="de680-147">During a refresh, the system looks for new or updated data to include in an export.</span></span> <span data-ttu-id="de680-148">По подразбиране експортирането се изпълнява като част от всяко [планирано обновяване на системата](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="de680-148">By default, exports are run as part of every [scheduled system refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="de680-149">Можете да персонализирате графика за опресняване или да го изключите, за да стартирате ръчно експортиране.</span><span class="sxs-lookup"><span data-stu-id="de680-149">You can customize the refresh schedule or turn it off to run exports manually.</span></span>

<span data-ttu-id="de680-150">Графиците за износ зависят от състоянието на вашата среда.</span><span class="sxs-lookup"><span data-stu-id="de680-150">Export schedules depend on the state of your environment.</span></span> <span data-ttu-id="de680-151">Ако има актуализации в процес на [зависимости](system.md#refresh-policies) когато трябва да започне планиран износ, системата първо ще завърши актуализациите и след това ще стартира експортирането.</span><span class="sxs-lookup"><span data-stu-id="de680-151">If there are updates in progress on [dependencies](system.md#refresh-policies) when a scheduled export should start, the system will first complete the updates and then run the export.</span></span> <span data-ttu-id="de680-152">Можете да видите кога за последен път е бил опреснен износ в колона **Опресняване**.</span><span class="sxs-lookup"><span data-stu-id="de680-152">You can see when an export was last refreshed in column **Refreshed**.</span></span>

### <a name="schedule-exports"></a><span data-ttu-id="de680-153">Планиране на експортирания</span><span class="sxs-lookup"><span data-stu-id="de680-153">Schedule exports</span></span>

<span data-ttu-id="de680-154">Можеш дефинирайте персонализирани графици за опресняване за индивидуален износ или няколко износа наведнъж.</span><span class="sxs-lookup"><span data-stu-id="de680-154">You can define custom refresh schedules for individual exports or several exports at once.</span></span> <span data-ttu-id="de680-155">В момента дефинираният график е посочен в **График** колона на списъка за износ.</span><span class="sxs-lookup"><span data-stu-id="de680-155">The currently defined schedule is listed in the **Schedule** column of the export list.</span></span> <span data-ttu-id="de680-156">Разрешението за промяна на графика е същото като за [редактиране и дефиниране на износа](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="de680-156">The permission to change the schedule is the same as for [editing and defining exports](export-destinations.md#set-up-a-new-export).</span></span> 

1. <span data-ttu-id="de680-157">Отидете на **Данни** > **Експортиране**.</span><span class="sxs-lookup"><span data-stu-id="de680-157">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="de680-158">Изберете експортирането, което искате да планирате.</span><span class="sxs-lookup"><span data-stu-id="de680-158">Select the export you want to schedule.</span></span>

1. <span data-ttu-id="de680-159">В командната лента изберете **Изтриване**.</span><span class="sxs-lookup"><span data-stu-id="de680-159">Select **Schedule** in the command bar.</span></span>

1. <span data-ttu-id="de680-160">В **График на експортирането** панел, задайте **Изпълнение на графика** на **Вкл.** за да стартирате експортирането автоматично.</span><span class="sxs-lookup"><span data-stu-id="de680-160">In the **Schedule export** pane, set the **Schedule run** to **On** to run the export automatically.</span></span> <span data-ttu-id="de680-161">Задайте го на **Изключено** за да го опресните ръчно.</span><span class="sxs-lookup"><span data-stu-id="de680-161">Set it to **Off** to refresh it manually.</span></span>

1. <span data-ttu-id="de680-162">За автоматично обновен износ изберете **Повторение** стойност и посочете подробностите за нея.</span><span class="sxs-lookup"><span data-stu-id="de680-162">For automatically refreshed exports, choose a **Recurrence** value and specify the details for it.</span></span> <span data-ttu-id="de680-163">Определеното време се прилага за всички случаи на повторение.</span><span class="sxs-lookup"><span data-stu-id="de680-163">The time defined applies to all instances of a recurrence.</span></span> <span data-ttu-id="de680-164">Време е, когато износът трябва да започне да се освежава.</span><span class="sxs-lookup"><span data-stu-id="de680-164">It's the time when an export should start refreshing.</span></span>

1. <span data-ttu-id="de680-165">Приложете и активирайте вашите промени, като изберете **Запазете**.</span><span class="sxs-lookup"><span data-stu-id="de680-165">Apply and activate your changes by selecting **Save**.</span></span>

<span data-ttu-id="de680-166">Когато редактирате графика за няколко износа, трябва да направите избор под **Запазете или заменете графиците**:</span><span class="sxs-lookup"><span data-stu-id="de680-166">When editing the schedule for several exports, you need to make a selection under **Keep or override schedules**:</span></span>
- <span data-ttu-id="de680-167">**Пазете индивидуални графици**: Запазете предварително дефинирания график за избрания износ и само ги деактивирайте или активирайте.</span><span class="sxs-lookup"><span data-stu-id="de680-167">**Keep individual schedules**: Persist the previously defined schedule for the selected exports and only disable or enable them.</span></span>
- <span data-ttu-id="de680-168">**Дефинирайте нов график за всички избрани експорти**: Замяна на съществуващите графици на избрания износ.</span><span class="sxs-lookup"><span data-stu-id="de680-168">**Define new schedule for all selected exports**: Override the existing schedules of the selected exports.</span></span>

### <a name="run-exports-on-demand"></a><span data-ttu-id="de680-169">Изпълнение на експортиране при поискване</span><span class="sxs-lookup"><span data-stu-id="de680-169">Run exports on demand</span></span>

<span data-ttu-id="de680-170">За да експортирате данни, без да чакате планирано обновяване, отидете на **Данни** > **Експортиране**.</span><span class="sxs-lookup"><span data-stu-id="de680-170">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span>

- <span data-ttu-id="de680-171">За да стартирате всички експортирания, изберете **Изпълнение на всички** в командната лента.</span><span class="sxs-lookup"><span data-stu-id="de680-171">To run all exports, select **Run all** in the command bar.</span></span> <span data-ttu-id="de680-172">Това действие ще изпълнява само експорти, които имат активен график.</span><span class="sxs-lookup"><span data-stu-id="de680-172">This action will only run exports that have an active schedule.</span></span>
- <span data-ttu-id="de680-173">За да стартирате единичен експорт, изберете го в списъка и изберете **изпълнение** в командната лента.</span><span class="sxs-lookup"><span data-stu-id="de680-173">To run a single export, select it in the list and select **Run** in the command bar.</span></span> <span data-ttu-id="de680-174">По този начин стартирате износ без активен график.</span><span class="sxs-lookup"><span data-stu-id="de680-174">That's how you run exports with no active schedule.</span></span> 

## <a name="remove-an-export"></a><span data-ttu-id="de680-175">Премахване на експортиране</span><span class="sxs-lookup"><span data-stu-id="de680-175">Remove an Export</span></span>

1. <span data-ttu-id="de680-176">Отидете на **Данни** > **Експортиране**.</span><span class="sxs-lookup"><span data-stu-id="de680-176">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="de680-177">Изберете експортирането, което искате да премахнете.</span><span class="sxs-lookup"><span data-stu-id="de680-177">Select the export you want to remove.</span></span>

1. <span data-ttu-id="de680-178">В командната лента изберете **Премахване**.</span><span class="sxs-lookup"><span data-stu-id="de680-178">Select **Remove** in the command bar.</span></span>

1. <span data-ttu-id="de680-179">Потвърдете премахването, като изберете **Премахване** в екрана за потвърждение.</span><span class="sxs-lookup"><span data-stu-id="de680-179">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
