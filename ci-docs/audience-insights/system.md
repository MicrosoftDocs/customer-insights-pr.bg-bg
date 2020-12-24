---
title: Конфигурация на системата в Аналитични данни за аудитория
description: Научете за системните настройки в Аналитични данни за аудитория на Dynamics 365 Customer Insights.
ms.date: 06/02/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: nimagen
manager: shellyha
ms.openlocfilehash: 7dd72e6512cd87ac70235d21667399298408db21
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405110"
---
# <a name="system-configuration"></a><span data-ttu-id="24332-103">Конфигурация на системата</span><span class="sxs-lookup"><span data-stu-id="24332-103">System configuration</span></span>

<span data-ttu-id="24332-104">Страницата **Система** включва четири раздела: **Състояние**, **График**, **Относно** и **Общ**.</span><span class="sxs-lookup"><span data-stu-id="24332-104">The **System** page includes four tabs: **Status**, **Schedule**, **About**, and **General**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="24332-105">![Страница „Система”](media/system-tabs.png "Страница „Система”")</span><span class="sxs-lookup"><span data-stu-id="24332-105">![System page](media/system-tabs.png "System page")</span></span>

## <a name="status-tab"></a><span data-ttu-id="24332-106">Раздел за състояние</span><span class="sxs-lookup"><span data-stu-id="24332-106">Status tab</span></span>

<span data-ttu-id="24332-107">Разделът **Състояние** ви позволява да проследявате напредъка на приемането на данни, експортирането на данни и няколко важни продуктови процеса.</span><span class="sxs-lookup"><span data-stu-id="24332-107">The **Status tab** lets you track the progress of data ingestion, data exports, and several important product processes.</span></span> <span data-ttu-id="24332-108">Прегледайте информацията в този раздел, за да се уверите в пълнотата на активните процеси.</span><span class="sxs-lookup"><span data-stu-id="24332-108">Review the information on this tab to ensure the completeness of active processes.</span></span>

<span data-ttu-id="24332-109">Този раздел включва таблици за състоянието за **Източници на данни**, **Системни процеси** и **Подготовка на данни**.</span><span class="sxs-lookup"><span data-stu-id="24332-109">This tab includes status tables for **Data sources**, **System processes**, and **Data preparation**.</span></span> <span data-ttu-id="24332-110">Всяка таблица проследява **Името** на задачата и съответния й обект, **Състоянието** на най-скорошното й изпълнение и кога е била **Последната актуализация**.</span><span class="sxs-lookup"><span data-stu-id="24332-110">Each table tracks the **Name** of the task and its corresponding entity, the **Status** of its most recent run, and when it was **Last updated**.</span></span>

<span data-ttu-id="24332-111">Прегледайте подробностите за последните няколко изпълнения на задачата, като изберете нейното име.</span><span class="sxs-lookup"><span data-stu-id="24332-111">View the details of the tasks' last several runs by selecting its name.</span></span>

### <a name="status-types"></a><span data-ttu-id="24332-112">Типове състояния</span><span class="sxs-lookup"><span data-stu-id="24332-112">Status types</span></span>

<span data-ttu-id="24332-113">Съществуват шест вида статус на задачите.</span><span class="sxs-lookup"><span data-stu-id="24332-113">There are six types of status for tasks.</span></span> <span data-ttu-id="24332-114">Следните типове състояния се показват на страниците *Съвпадение*, *Обединяване*, *Източници на данни*, *Сегменти*, *Метрики*, *Допълване*, *Дейности* и *Прогнози*:</span><span class="sxs-lookup"><span data-stu-id="24332-114">The following status types also show on the *Match*, *Merge*, *Data sources*, *Segments*, *Measures*, *Enrichment*, *Activities*, and *Predictions* pages:</span></span>

- <span data-ttu-id="24332-115">**Обработване:** Задачата е в ход.</span><span class="sxs-lookup"><span data-stu-id="24332-115">**Processing:** Task is in progress.</span></span> <span data-ttu-id="24332-116">Състоянието може да се промени на „Успешно” или „Неуспешно”.</span><span class="sxs-lookup"><span data-stu-id="24332-116">The status can change to Successful or Failure.</span></span>
- <span data-ttu-id="24332-117">**Успешно:** Задачата е завършена успешно.</span><span class="sxs-lookup"><span data-stu-id="24332-117">**Successful:** Task completed successfully.</span></span>
- <span data-ttu-id="24332-118">**Пропусната:** Задачата е пропусната.</span><span class="sxs-lookup"><span data-stu-id="24332-118">**Skipped:** Task got skipped.</span></span> <span data-ttu-id="24332-119">Един или повече от процесите надолу по веригата, от които зависи тази задача, са неуспешни или пропуснати.</span><span class="sxs-lookup"><span data-stu-id="24332-119">One or more of the downstream processes this task depends on are failing or got skipped.</span></span>
- <span data-ttu-id="24332-120">**Неуспешно:** Обработването на задачата е неуспешно.</span><span class="sxs-lookup"><span data-stu-id="24332-120">**Failure:** Processing  of the task has failed.</span></span>
- <span data-ttu-id="24332-121">**Отменено:** Обработването е отменено от потребителя, преди да приключи.</span><span class="sxs-lookup"><span data-stu-id="24332-121">**Canceled:** Processing was canceled by the user before it finished.</span></span>
- <span data-ttu-id="24332-122">**В опашка:** Обработването е в опашка и ще започне след приключване на всички задачи надолу по веригата.</span><span class="sxs-lookup"><span data-stu-id="24332-122">**Queued:** Processing is queued and will start once all the downstream tasks are completed.</span></span> <span data-ttu-id="24332-123">За повече информация вижте [Правила за обновяване](#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="24332-123">For more information, see [Refresh policies](#refresh-policies).</span></span>

### <a name="refresh-policies"></a><span data-ttu-id="24332-124">Правила за обновяване</span><span class="sxs-lookup"><span data-stu-id="24332-124">Refresh policies</span></span>

<span data-ttu-id="24332-125">Този списък показва политиките за обновяване за всеки от основните процеси:</span><span class="sxs-lookup"><span data-stu-id="24332-125">This list shows the refresh policies for each of the main processes:</span></span>

- <span data-ttu-id="24332-126">**Източници на данни:** Изпълнява се в съответствие с [конфигурирания график](#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="24332-126">**Data sources:** Runs according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="24332-127">Не зависи от друг процес.</span><span class="sxs-lookup"><span data-stu-id="24332-127">Doesn't depend on any other process.</span></span> <span data-ttu-id="24332-128">Съвпадението зависи от успешното приключване на този процес.</span><span class="sxs-lookup"><span data-stu-id="24332-128">Match depends on the successful completion of this process.</span></span>
- <span data-ttu-id="24332-129">**Съвпадение:** Изпълнява се в съответствие с [конфигурирания график](#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="24332-129">**Match:** Runs according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="24332-130">Зависи от обработката на източниците на данни, използвани в дефиницията на съвпадението.</span><span class="sxs-lookup"><span data-stu-id="24332-130">Depends on the processing of the data sources used in the match definition.</span></span> <span data-ttu-id="24332-131">Обединяването зависи от успешното приключване на този процес.</span><span class="sxs-lookup"><span data-stu-id="24332-131">Merge depends on the successful completion of this process.</span></span>
- <span data-ttu-id="24332-132">**Обединяване**: Изпълнява се в съответствие с [конфигурирания график](#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="24332-132">**Merge**: Runs according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="24332-133">Зависи от успешното приключване на процеса на съвпадение.</span><span class="sxs-lookup"><span data-stu-id="24332-133">Depends on the completion of the match process.</span></span> <span data-ttu-id="24332-134">Сегментите, мерките, допълването, търсенето, дейностите, прогнозите и подготовката на данни зависят от успешното приключване на този процес.</span><span class="sxs-lookup"><span data-stu-id="24332-134">Segments, measures, enrichment, search, activities, predictions, and data preparation depend on the successful completion of this process.</span></span>
- <span data-ttu-id="24332-135">**Сегменти**: Изпълнява се ръчно (еднократно обновяване) и според [конфигурирания график](#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="24332-135">**Segments**: Runs manually (single time refresh) and according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="24332-136">Зависи от обединяването.</span><span class="sxs-lookup"><span data-stu-id="24332-136">Depends on Merge.</span></span> <span data-ttu-id="24332-137">Аналитичните данни зависят от обработката.</span><span class="sxs-lookup"><span data-stu-id="24332-137">Insights depend on its processing.</span></span>
- <span data-ttu-id="24332-138">**Мерки**: Изпълнява се ръчно (еднократно обновяване) и според [конфигурирания график](#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="24332-138">**Measures**: Runs manually (single time refresh) and according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="24332-139">Зависи от обединяването.</span><span class="sxs-lookup"><span data-stu-id="24332-139">Depends on Merge.</span></span>
- <span data-ttu-id="24332-140">**Дейности**: Изпълнява се ръчно (еднократно обновяване) и според [конфигурирания график](#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="24332-140">**Activities**: Runs manually (single time refresh) and according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="24332-141">Зависи от обединяването.</span><span class="sxs-lookup"><span data-stu-id="24332-141">Depends on Merge.</span></span>
- <span data-ttu-id="24332-142">**Допълване**: Изпълнява се ръчно (еднократно обновяване) и според [конфигурирания график](#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="24332-142">**Enrichment**: Runs manually (single time refresh) and according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="24332-143">Зависи от обединяването.</span><span class="sxs-lookup"><span data-stu-id="24332-143">Depends on Merge.</span></span>
- <span data-ttu-id="24332-144">**Търсене**: Изпълнява се ръчно (еднократно обновяване) и според [конфигурирания график](#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="24332-144">**Search**: Runs manually (single time refresh) and according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="24332-145">Зависи от обединяването.</span><span class="sxs-lookup"><span data-stu-id="24332-145">Depends on Merge.</span></span>
- <span data-ttu-id="24332-146">**Подготовка на данни**: Изпълнява се в съответствие с [конфигурирания график](#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="24332-146">**Data preparation**: Runs according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="24332-147">Зависи от обединяването.</span><span class="sxs-lookup"><span data-stu-id="24332-147">Depends on Merge.</span></span>
- <span data-ttu-id="24332-148">**Аналитични данни**: Изпълнява се ръчно (еднократно обновяване) и според [конфигурирания график](#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="24332-148">**Insights**: Runs manually (single time refresh) and according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="24332-149">Зависи от сегментите.</span><span class="sxs-lookup"><span data-stu-id="24332-149">Depends on Segments.</span></span>

<span data-ttu-id="24332-150">Изберете състоянието на задача, за да видите подробности за напредъка на цялата задача, от която е част.</span><span class="sxs-lookup"><span data-stu-id="24332-150">Select the status of a task to see the progress details of the entire job it was in.</span></span> <span data-ttu-id="24332-151">Правилата за обновяване по-горе може да помогнат да разберете какво можете да направите, за да се справите със задача, която е **пропусната** или **в опашка**.</span><span class="sxs-lookup"><span data-stu-id="24332-151">The refresh policies above can help to understand what you can do to address a **Skipped** or **Queued** task.</span></span>

## <a name="schedule-tab"></a><span data-ttu-id="24332-152">Раздел за планиране</span><span class="sxs-lookup"><span data-stu-id="24332-152">Schedule tab</span></span>

<span data-ttu-id="24332-153">Използвайте раздела **График**, за да планирате автоматично опресняване на всички ваши [погълнати източници на данни](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="24332-153">Use the **Schedule** tab to schedule automatic refreshes of all your [ingested data sources](data-sources.md).</span></span> <span data-ttu-id="24332-154">Автоматичните обновявания помагат да се гарантира, че актуализациите от вашите източници на данни се отразяват във вашите унифицирани потребителски профили.</span><span class="sxs-lookup"><span data-stu-id="24332-154">Automatic refreshes help ensure that updates from your data sources are reflected in your unified customer profiles.</span></span>

1. <span data-ttu-id="24332-155">В статията за аудиторията отидете на **Администратор** > **Система** и изберете раздела **График**.</span><span class="sxs-lookup"><span data-stu-id="24332-155">In audience insights, go to **Admin** > **System** and select the **Schedule** tab.</span></span>

2. <span data-ttu-id="24332-156">Състоянието по подразбиране за планираното обновяване е **Изключено**.</span><span class="sxs-lookup"><span data-stu-id="24332-156">The default state for the scheduled refresh is **Off**.</span></span> <span data-ttu-id="24332-157">За да активирате планираните обновявания, променете превключвателя в горната част на екрана на **Вкл**.</span><span class="sxs-lookup"><span data-stu-id="24332-157">To enable scheduled refreshes, change the toggle at the top of the screen to **On**.</span></span>

3. <span data-ttu-id="24332-158">Изберете между **Ежеседмично** (по подразбиране) и **Ежедневно** обновяване.</span><span class="sxs-lookup"><span data-stu-id="24332-158">Choose between **Weekly** (default) and **Daily** refreshes.</span></span> <span data-ttu-id="24332-159">Ако възнамерявате да планирате ежеседмично обновяване, изберете един или повече дни, в които искате да изпълните обновяване.</span><span class="sxs-lookup"><span data-stu-id="24332-159">If you intend to schedule weekly refreshes, select one or more days on which you want to run the refresh.</span></span>

4. <span data-ttu-id="24332-160">Задайте **Часова зона**, след това използвайте падащото меню **Час**, за да зададете времето за обновяване.</span><span class="sxs-lookup"><span data-stu-id="24332-160">Set your **Time zone**, then use the **Time** dropdown to set your refresh timing.</span></span> <span data-ttu-id="24332-161">Когато сте готови, изберете **Задаване**.</span><span class="sxs-lookup"><span data-stu-id="24332-161">When you're finished, select **Set**.</span></span> <span data-ttu-id="24332-162">Ако искате да планирате няколко обновявания за един ден, изберете **Добавяне на друго време**.</span><span class="sxs-lookup"><span data-stu-id="24332-162">If you'd like to schedule multiple refreshes in a single day, select **Add another time**.</span></span>

5. <span data-ttu-id="24332-163">Изберете **Записване**, за да приложите промените.</span><span class="sxs-lookup"><span data-stu-id="24332-163">Select **Save** to apply your changes.</span></span>

## <a name="about-tab"></a><span data-ttu-id="24332-164">Раздел „Относно”</span><span class="sxs-lookup"><span data-stu-id="24332-164">About tab</span></span>

<span data-ttu-id="24332-165">Разделът **Относно** съдържа **Показвано име** на организацията, активния **ИД на среда**, **Регион** и вашия **ИД на сесия**.</span><span class="sxs-lookup"><span data-stu-id="24332-165">The **About** tab contains your organization's **Display name**, the active **Environment ID**, the **Region**, and your **Session ID**.</span></span> <span data-ttu-id="24332-166">Ако имате повече от една работна среда, трябва да дадете на всяко лесно разпознаваемо име за показване.</span><span class="sxs-lookup"><span data-stu-id="24332-166">If you have more than one work environment, you should give each an easily identifiable display name.</span></span>

## <a name="general-tab"></a><span data-ttu-id="24332-167">Раздел „Общи”</span><span class="sxs-lookup"><span data-stu-id="24332-167">General tab</span></span>

<span data-ttu-id="24332-168">Има две опции в раздела **Общи** – **Език** и **Формат на страната/региона**.</span><span class="sxs-lookup"><span data-stu-id="24332-168">There are two options on the **General** tab, **Language** and **Country/Region format**.</span></span>

<span data-ttu-id="24332-169">Приложението [поддържа редица езици](supported-languages.md).</span><span class="sxs-lookup"><span data-stu-id="24332-169">The app [supports a number of languages](supported-languages.md).</span></span> <span data-ttu-id="24332-170">За да промените предпочитания от вас език, изберете **език** от падащия списък.</span><span class="sxs-lookup"><span data-stu-id="24332-170">To change your preferred language, choose a **Language** from the dropdown.</span></span>

<span data-ttu-id="24332-171">За да промените предпочитаното от вас форматиране на дати, час и числа, използвайте падащия списък **Формат на страната/региона**.</span><span class="sxs-lookup"><span data-stu-id="24332-171">To change your preferred formatting for dates, time, and numbers, use the **Country/Region format** dropdown.</span></span> <span data-ttu-id="24332-172">Под това поле се показва преглед на форматирането.</span><span class="sxs-lookup"><span data-stu-id="24332-172">A formatting preview is displayed under this field.</span></span> <span data-ttu-id="24332-173">Системата автоматично ще предложи избор, когато изберете нов език.</span><span class="sxs-lookup"><span data-stu-id="24332-173">The system will automatically suggest a selection when you choose a new language.</span></span>

<span data-ttu-id="24332-174">Изберете **Записване**, за да потвърдите избора.</span><span class="sxs-lookup"><span data-stu-id="24332-174">Select **Save** to confirm your selections.</span></span>

## <a name="api-usage-tab"></a><span data-ttu-id="24332-175">Раздел за използване на API</span><span class="sxs-lookup"><span data-stu-id="24332-175">API usage tab</span></span>

<span data-ttu-id="24332-176">Намерете подробности за използването на API в реално време и вижте кои събития са се случили в даден диапазон от време.</span><span class="sxs-lookup"><span data-stu-id="24332-176">Find details about the real-time API usage and see which events happened in a given time range.</span></span> <span data-ttu-id="24332-177">За повече информация вижте [Приемане на данни в реално време](real-time-data-ingestion.md).</span><span class="sxs-lookup"><span data-stu-id="24332-177">For more information, see [Real-time data ingestion](real-time-data-ingestion.md).</span></span>