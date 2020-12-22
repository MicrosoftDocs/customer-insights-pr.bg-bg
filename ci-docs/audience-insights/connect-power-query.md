---
title: Поглъщане на данни чрез конектор на Power Query
description: Конектори за източници на данни, базирани на Power Query.
ms.date: 09/29/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 8a170cc5b64b4b383501021232c83948e838a0e2
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405090"
---
# <a name="connect-to-a-power-query-data-source"></a><span data-ttu-id="c5c11-103">Свързване към източник на данни на Power Query</span><span class="sxs-lookup"><span data-stu-id="c5c11-103">Connect to a Power Query data source</span></span>

<span data-ttu-id="c5c11-104">Power Query предлага широк набор от конектори за поглъщане на данни.</span><span class="sxs-lookup"><span data-stu-id="c5c11-104">Power Query offers a broad set of connectors to ingest data.</span></span> <span data-ttu-id="c5c11-105">Повечето от тези конектори се поддържат от Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="c5c11-105">Most of these connectors are supported by Dynamics 365 Customer Insights.</span></span> <span data-ttu-id="c5c11-106">Добавянето на източници на данни въз основа на конектори на Power Query обикновено следва стъпките, описани в следващия раздел.</span><span class="sxs-lookup"><span data-stu-id="c5c11-106">Adding data sources based on Power Query connectors generally follows the steps outlined in the next section.</span></span> <span data-ttu-id="c5c11-107">В зависимост от конектора, който използвате обаче, се изисква различна информация.</span><span class="sxs-lookup"><span data-stu-id="c5c11-107">However, depending on the connector you use, different information is required.</span></span> <span data-ttu-id="c5c11-108">За повече информация вижте документацията за отделните конектори в [справката за конекторите на Power Query](https://docs.microsoft.com/power-query/connectors/).</span><span class="sxs-lookup"><span data-stu-id="c5c11-108">For more information, see the documentation about individual connectors in the [Power Query connector reference](https://docs.microsoft.com/power-query/connectors/).</span></span>

## <a name="create-a-new-data-source"></a><span data-ttu-id="c5c11-109">Създаване на нов източник на данни</span><span class="sxs-lookup"><span data-stu-id="c5c11-109">Create a new data source</span></span>

1. <span data-ttu-id="c5c11-110">В статията за аудиторията отидете на **Данни** > **Източници на данни**.</span><span class="sxs-lookup"><span data-stu-id="c5c11-110">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="c5c11-111">Изберете **Добавяне на източник на данни**.</span><span class="sxs-lookup"><span data-stu-id="c5c11-111">Select **Add data source**.</span></span>

1. <span data-ttu-id="c5c11-112">Изберете метода **Импортиране на данни** и изберете **Напред**.</span><span class="sxs-lookup"><span data-stu-id="c5c11-112">Choose the **Import data** method and select **Next**.</span></span>

1. <span data-ttu-id="c5c11-113">Посочете **Име** за източник на данни и изберете **Напред**, за да създадете източника на данни.</span><span class="sxs-lookup"><span data-stu-id="c5c11-113">Provide a **Name** for the data source, and select **Next** to create the data source.</span></span>

1. <span data-ttu-id="c5c11-114">Изберете един от [наличните конектори](#available-power-query-data-sources).</span><span class="sxs-lookup"><span data-stu-id="c5c11-114">Choose one of the [available connectors](#available-power-query-data-sources).</span></span> <span data-ttu-id="c5c11-115">За този пример избираме конектора **Текст/CSV**.</span><span class="sxs-lookup"><span data-stu-id="c5c11-115">For this example, we select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="c5c11-116">Въведете необходимите подробности в **Настройки за връзка** за избрания конектор и изберете **Напред**, за да визуализирате данните.</span><span class="sxs-lookup"><span data-stu-id="c5c11-116">Enter the required details in the **Connection settings** for the selected connector and select **Next** to see a preview of the data.</span></span>

1. <span data-ttu-id="c5c11-117">Изберете **Трансформиране на данни**.</span><span class="sxs-lookup"><span data-stu-id="c5c11-117">Select **Transform data**.</span></span> <span data-ttu-id="c5c11-118">В тази стъпка ще добавите обекти към източника на данни.</span><span class="sxs-lookup"><span data-stu-id="c5c11-118">In this step, you'll add entities to your data source.</span></span> <span data-ttu-id="c5c11-119">Обектите са набори от данни.</span><span class="sxs-lookup"><span data-stu-id="c5c11-119">Entities are datasets.</span></span> <span data-ttu-id="c5c11-120">Ако имате база данни, която включва много набори от данни, всеки набор от данни е собствен обект.</span><span class="sxs-lookup"><span data-stu-id="c5c11-120">If you have a database that includes multiple datasets, each dataset is its own entity.</span></span>

1. <span data-ttu-id="c5c11-121">Диалоговият прозорец **Power Query – Редактиране на заявки** ви позволява да прегледате и прецизирате данните.</span><span class="sxs-lookup"><span data-stu-id="c5c11-121">The **Power Query - Edit queries** dialog lets you review and refine the data.</span></span> <span data-ttu-id="c5c11-122">Обектите, идентифицирани от системите в избрания източник на данни, се показват в левия екран.</span><span class="sxs-lookup"><span data-stu-id="c5c11-122">The entities that the systems identified in your selected data source appear in the left pane.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c5c11-123">![Диалогов прозорец „Редактиране на заявки“](media/data-manager-configure-edit-queries.png "Диалогов прозорец „Редактиране на заявки“")</span><span class="sxs-lookup"><span data-stu-id="c5c11-123">![Edit queries dialog](media/data-manager-configure-edit-queries.png "Edit queries dialog")</span></span>

1. <span data-ttu-id="c5c11-124">Можете също да преобразувате данните.</span><span class="sxs-lookup"><span data-stu-id="c5c11-124">You can also transform your data.</span></span> <span data-ttu-id="c5c11-125">Изберете обект, който да редактирате или преобразувате.</span><span class="sxs-lookup"><span data-stu-id="c5c11-125">Select an entity to edit or transform.</span></span> <span data-ttu-id="c5c11-126">Използвайте опциите в прозореца Power Query, за да приложите трансформации.</span><span class="sxs-lookup"><span data-stu-id="c5c11-126">Use the options in the Power Query window to apply transformations.</span></span> <span data-ttu-id="c5c11-127">Всяка трансформация се посочва под **Приложени стъпки**.</span><span class="sxs-lookup"><span data-stu-id="c5c11-127">Each transformation gets listed under **Applied steps**.</span></span> <span data-ttu-id="c5c11-128">Power Query предоставя многобройни предварително създадени опции за трансформация.</span><span class="sxs-lookup"><span data-stu-id="c5c11-128">Power Query provides numerous pre-built transformation options.</span></span> <span data-ttu-id="c5c11-129">За повече информация вижте [Трансформации на Power Query](https://docs.microsoft.com/power-query/power-query-what-is-power-query#transformations).</span><span class="sxs-lookup"><span data-stu-id="c5c11-129">For more information, see [Power Query Transformations](https://docs.microsoft.com/power-query/power-query-what-is-power-query#transformations).</span></span>

1. <span data-ttu-id="c5c11-130">Можете да добавите допълнителни обекти към източника на данни, като изберете **Получаване на данни** в диалоговия прозорец **Редактиране на заявки**.</span><span class="sxs-lookup"><span data-stu-id="c5c11-130">You can add additional entities to your data source by selecting **Get data** in the **Edit queries** dialog.</span></span>

   <span data-ttu-id="c5c11-131">Тези трансформации са силно препоръчителни:</span><span class="sxs-lookup"><span data-stu-id="c5c11-131">These transformations are highly recommended:</span></span>

   - <span data-ttu-id="c5c11-132">Ако поглъщате данни от CSV файл, първият ред често съдържа заглавки.</span><span class="sxs-lookup"><span data-stu-id="c5c11-132">If you're ingesting data from a CSV file, the first row often contains headers.</span></span> <span data-ttu-id="c5c11-133">Отидете на **Таблица за трансформиране** и изберете **Използване на заглавки като първи ред**.</span><span class="sxs-lookup"><span data-stu-id="c5c11-133">Go to **Transform table** and select **Use headers as first row**.</span></span>
   - <span data-ttu-id="c5c11-134">Уверете се, че типът данни е зададен съответстващо.</span><span class="sxs-lookup"><span data-stu-id="c5c11-134">Ensure the data type is set appropriately.</span></span>

1. <span data-ttu-id="c5c11-135">Изберете **Записване** в долния край на прозореца на Power Query, за да запишете трансформациите.</span><span class="sxs-lookup"><span data-stu-id="c5c11-135">Select **Save** at the bottom of the Power Query window to save the transformations.</span></span> <span data-ttu-id="c5c11-136">След записване ще намерите вашия източник на данни в **Данни** > **Източници на данни**.</span><span class="sxs-lookup"><span data-stu-id="c5c11-136">After saving, you'll find your data source on **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="c5c11-137">В страницата **Източници на данни** ще забележите, че новият източник на данни е състояние **Обновяване**.</span><span class="sxs-lookup"><span data-stu-id="c5c11-137">On the **Data sources** page, you'll notice the new data source is in **Refreshing** status.</span></span>

## <a name="available-power-query-data-sources"></a><span data-ttu-id="c5c11-138">Налични източници на данни на Power Query</span><span class="sxs-lookup"><span data-stu-id="c5c11-138">Available Power Query data sources</span></span>

<span data-ttu-id="c5c11-139">Вижте [справката за конектори на Power Query](https://docs.microsoft.com/power-query/connectors/) за актуален списък на конекторите, които можете да избирате за импортиране на данни в Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="c5c11-139">See the [Power Query connector reference](https://docs.microsoft.com/power-query/connectors/) for an up-to-date list of connectors that you can select to import data to Customer Insights.</span></span> 

<span data-ttu-id="c5c11-140">Конекторите с отметка в колоната **Customer Insights (потоци от данни)** са достъпни за създаване на нови източници на данни въз основа на Power Query.</span><span class="sxs-lookup"><span data-stu-id="c5c11-140">Connectors with a checkmark in the **Customer Insights (Dataflows)** column are available to create new data sources based on Power Query.</span></span> <span data-ttu-id="c5c11-141">Прегледайте документацията на конкретен конектор, за да научите повече за неговите изисквания, ограничения и други подробности.</span><span class="sxs-lookup"><span data-stu-id="c5c11-141">Review the documentation of a specific connector to learn more about its prerequisites, limitations, and other details.</span></span>

## <a name="edit-power-query-data-sources"></a><span data-ttu-id="c5c11-142">Редактиране на източници на данни на Power Query</span><span class="sxs-lookup"><span data-stu-id="c5c11-142">Edit Power Query data sources</span></span>

> [!NOTE]
> <span data-ttu-id="c5c11-143">Може да няма възможност за извършване на промени в източниците на данни, които в момента се използват в някой от процесите на приложението (*сегментиране*, *съвпадение* или *обединяване* например).</span><span class="sxs-lookup"><span data-stu-id="c5c11-143">It might not be possible to make changes to data sources that are currently being used in one of the app's processes (*segmentation*, *match*, or *merge*, for example).</span></span> 
>
> <span data-ttu-id="c5c11-144">Като използвате страницата **Настройки**, можете да проследите напредъка на всеки от активните процеси.</span><span class="sxs-lookup"><span data-stu-id="c5c11-144">Using the **Settings** page, you can track the progress of each of the active processes.</span></span> <span data-ttu-id="c5c11-145">Когато даден процес приключи, можете да се върнете в страницата **Източници на данни** и да направите промени.</span><span class="sxs-lookup"><span data-stu-id="c5c11-145">When a process completes, you can return to the **Data Sources** page and make your changes.</span></span>

1. <span data-ttu-id="c5c11-146">В статията за аудиторията отидете на **Данни** > **Източници на данни**.</span><span class="sxs-lookup"><span data-stu-id="c5c11-146">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="c5c11-147">Изберете вертикалното многоточие до източника на данни, който искате да промените, и изберете **Редактиране** от падащото меню.</span><span class="sxs-lookup"><span data-stu-id="c5c11-147">Select the vertical ellipsis next to the data source you want to change and select **Edit** from the drop-down menu.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c5c11-148">![Опция „Редактиране“](media/edit-option-data-sources.png "Опция „Редактиране“")</span><span class="sxs-lookup"><span data-stu-id="c5c11-148">![Edit option](media/edit-option-data-sources.png "Edit option")</span></span>

3. <span data-ttu-id="c5c11-149">Приложете вашите промени и трансформации в диалоговия прозорец **Power Query – Редактиране на заявки**, както е описано в раздела [Създаване на нов източник на данни](#create-a-new-data-source).</span><span class="sxs-lookup"><span data-stu-id="c5c11-149">Apply your changes and transformations in the **Power Query - Edit queries** dialog as described in the [Create a new data source](#create-a-new-data-source) section.</span></span>

4. <span data-ttu-id="c5c11-150">Изберете **Записване** в Power Query, след като завършите редакциите си, за да запазите промените.</span><span class="sxs-lookup"><span data-stu-id="c5c11-150">Select **Save** in Power Query after completing your edits to save your changes.</span></span>
