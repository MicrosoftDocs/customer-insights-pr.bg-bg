---
title: Поглъщане на данни чрез конектор на Power Query
description: Конектори за източници на данни, базирани на Power Query.
ms.date: 09/29/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d51a7efa5fd9f7336d1662500eb804a674738493
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267755"
---
# <a name="connect-to-a-power-query-data-source"></a><span data-ttu-id="73d66-103">Свързване към източник на данни на Power Query</span><span class="sxs-lookup"><span data-stu-id="73d66-103">Connect to a Power Query data source</span></span>

<span data-ttu-id="73d66-104">Power Query предлага широк набор от конектори за поглъщане на данни.</span><span class="sxs-lookup"><span data-stu-id="73d66-104">Power Query offers a broad set of connectors to ingest data.</span></span> <span data-ttu-id="73d66-105">Повечето от тези конектори се поддържат от Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="73d66-105">Most of these connectors are supported by Dynamics 365 Customer Insights.</span></span> <span data-ttu-id="73d66-106">Добавянето на източници на данни въз основа на конектори на Power Query обикновено следва стъпките, описани в следващия раздел.</span><span class="sxs-lookup"><span data-stu-id="73d66-106">Adding data sources based on Power Query connectors generally follows the steps outlined in the next section.</span></span> <span data-ttu-id="73d66-107">В зависимост от конектора, който използвате обаче, се изисква различна информация.</span><span class="sxs-lookup"><span data-stu-id="73d66-107">However, depending on the connector you use, different information is required.</span></span> <span data-ttu-id="73d66-108">За повече информация вижте документацията за отделните конектори в [справката за конекторите на Power Query](https://docs.microsoft.com/power-query/connectors/).</span><span class="sxs-lookup"><span data-stu-id="73d66-108">For more information, see the documentation about individual connectors in the [Power Query connector reference](https://docs.microsoft.com/power-query/connectors/).</span></span>

## <a name="create-a-new-data-source"></a><span data-ttu-id="73d66-109">Създаване на нов източник на данни</span><span class="sxs-lookup"><span data-stu-id="73d66-109">Create a new data source</span></span>

1. <span data-ttu-id="73d66-110">В статията за аудиторията отидете на **Данни** > **Източници на данни**.</span><span class="sxs-lookup"><span data-stu-id="73d66-110">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="73d66-111">Изберете **Добавяне на източник на данни**.</span><span class="sxs-lookup"><span data-stu-id="73d66-111">Select **Add data source**.</span></span>

1. <span data-ttu-id="73d66-112">Изберете метода **Импортиране на данни** и изберете **Напред**.</span><span class="sxs-lookup"><span data-stu-id="73d66-112">Choose the **Import data** method and select **Next**.</span></span>

1. <span data-ttu-id="73d66-113">Посочете **Име** за източник на данни и изберете **Напред**, за да създадете източника на данни.</span><span class="sxs-lookup"><span data-stu-id="73d66-113">Provide a **Name** for the data source, and select **Next** to create the data source.</span></span> <span data-ttu-id="73d66-114">Насоки за име:</span><span class="sxs-lookup"><span data-stu-id="73d66-114">Name guidelines:</span></span> 
   - <span data-ttu-id="73d66-115">Започнете с буква.</span><span class="sxs-lookup"><span data-stu-id="73d66-115">Start with a letter.</span></span>
   - <span data-ttu-id="73d66-116">Използвайте само букви и цифри.</span><span class="sxs-lookup"><span data-stu-id="73d66-116">Use letters and numbers only.</span></span> <span data-ttu-id="73d66-117">Не е разрешено въвеждането на специални знаци и интервали.</span><span class="sxs-lookup"><span data-stu-id="73d66-117">Special characters and spaces are not allowed.</span></span>
   - <span data-ttu-id="73d66-118">Използвайте между 3 и 64 знака.</span><span class="sxs-lookup"><span data-stu-id="73d66-118">Use between 3 and 64 characters.</span></span>

1. <span data-ttu-id="73d66-119">Изберете един от [наличните конектори](#available-power-query-data-sources).</span><span class="sxs-lookup"><span data-stu-id="73d66-119">Choose one of the [available connectors](#available-power-query-data-sources).</span></span> <span data-ttu-id="73d66-120">За този пример избираме конектора **Текст/CSV**.</span><span class="sxs-lookup"><span data-stu-id="73d66-120">For this example, we select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="73d66-121">Въведете необходимите подробности в **Настройки за връзка** за избрания конектор и изберете **Напред**, за да визуализирате данните.</span><span class="sxs-lookup"><span data-stu-id="73d66-121">Enter the required details in the **Connection settings** for the selected connector and select **Next** to see a preview of the data.</span></span>

1. <span data-ttu-id="73d66-122">Изберете **Трансформиране на данни**.</span><span class="sxs-lookup"><span data-stu-id="73d66-122">Select **Transform data**.</span></span> <span data-ttu-id="73d66-123">В тази стъпка ще добавите обекти към източника на данни.</span><span class="sxs-lookup"><span data-stu-id="73d66-123">In this step, you'll add entities to your data source.</span></span> <span data-ttu-id="73d66-124">Обектите са набори от данни.</span><span class="sxs-lookup"><span data-stu-id="73d66-124">Entities are datasets.</span></span> <span data-ttu-id="73d66-125">Ако имате база данни, която включва много набори от данни, всеки набор от данни е собствен обект.</span><span class="sxs-lookup"><span data-stu-id="73d66-125">If you have a database that includes multiple datasets, each dataset is its own entity.</span></span>

1. <span data-ttu-id="73d66-126">Диалоговият прозорец **Power Query – Редактиране на заявки** ви позволява да прегледате и прецизирате данните.</span><span class="sxs-lookup"><span data-stu-id="73d66-126">The **Power Query - Edit queries** dialog lets you review and refine the data.</span></span> <span data-ttu-id="73d66-127">Обектите, идентифицирани от системите в избрания източник на данни, се показват в левия екран.</span><span class="sxs-lookup"><span data-stu-id="73d66-127">The entities that the systems identified in your selected data source appear in the left pane.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="73d66-128">![Диалогов прозорец „Редактиране на заявки“](media/data-manager-configure-edit-queries.png "Диалогов прозорец „Редактиране на заявки“")</span><span class="sxs-lookup"><span data-stu-id="73d66-128">![Edit queries dialog](media/data-manager-configure-edit-queries.png "Edit queries dialog")</span></span>

1. <span data-ttu-id="73d66-129">Можете също да преобразувате данните.</span><span class="sxs-lookup"><span data-stu-id="73d66-129">You can also transform your data.</span></span> <span data-ttu-id="73d66-130">Изберете обект, който да редактирате или преобразувате.</span><span class="sxs-lookup"><span data-stu-id="73d66-130">Select an entity to edit or transform.</span></span> <span data-ttu-id="73d66-131">Използвайте опциите в прозореца Power Query, за да приложите трансформации.</span><span class="sxs-lookup"><span data-stu-id="73d66-131">Use the options in the Power Query window to apply transformations.</span></span> <span data-ttu-id="73d66-132">Всяка трансформация се посочва под **Приложени стъпки**.</span><span class="sxs-lookup"><span data-stu-id="73d66-132">Each transformation gets listed under **Applied steps**.</span></span> <span data-ttu-id="73d66-133">Power Query предоставя многобройни предварително създадени опции за трансформация.</span><span class="sxs-lookup"><span data-stu-id="73d66-133">Power Query provides numerous pre-built transformation options.</span></span> <span data-ttu-id="73d66-134">За повече информация вижте [Трансформации на Power Query](https://docs.microsoft.com/power-query/power-query-what-is-power-query#transformations).</span><span class="sxs-lookup"><span data-stu-id="73d66-134">For more information, see [Power Query Transformations](https://docs.microsoft.com/power-query/power-query-what-is-power-query#transformations).</span></span>

1. <span data-ttu-id="73d66-135">Можете да добавите допълнителни обекти към източника на данни, като изберете **Получаване на данни** в диалоговия прозорец **Редактиране на заявки**.</span><span class="sxs-lookup"><span data-stu-id="73d66-135">You can add additional entities to your data source by selecting **Get data** in the **Edit queries** dialog.</span></span>

   <span data-ttu-id="73d66-136">Тези трансформации са силно препоръчителни:</span><span class="sxs-lookup"><span data-stu-id="73d66-136">These transformations are highly recommended:</span></span>

   - <span data-ttu-id="73d66-137">Ако поглъщате данни от CSV файл, първият ред често съдържа заглавки.</span><span class="sxs-lookup"><span data-stu-id="73d66-137">If you're ingesting data from a CSV file, the first row often contains headers.</span></span> <span data-ttu-id="73d66-138">Отидете на **Таблица за трансформиране** и изберете **Използване на заглавки като първи ред**.</span><span class="sxs-lookup"><span data-stu-id="73d66-138">Go to **Transform table** and select **Use headers as first row**.</span></span>
   - <span data-ttu-id="73d66-139">Уверете се, че типът данни е зададен съответстващо.</span><span class="sxs-lookup"><span data-stu-id="73d66-139">Ensure the data type is set appropriately.</span></span>

1. <span data-ttu-id="73d66-140">Изберете **Записване** в долния край на прозореца на Power Query, за да запишете трансформациите.</span><span class="sxs-lookup"><span data-stu-id="73d66-140">Select **Save** at the bottom of the Power Query window to save the transformations.</span></span> <span data-ttu-id="73d66-141">След записване ще намерите вашия източник на данни в **Данни** > **Източници на данни**.</span><span class="sxs-lookup"><span data-stu-id="73d66-141">After saving, you'll find your data source on **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="73d66-142">В страницата **Източници на данни** ще забележите, че новият източник на данни е състояние **Обновяване**.</span><span class="sxs-lookup"><span data-stu-id="73d66-142">On the **Data sources** page, you'll notice the new data source is in **Refreshing** status.</span></span>

## <a name="available-power-query-data-sources"></a><span data-ttu-id="73d66-143">Налични източници на данни на Power Query</span><span class="sxs-lookup"><span data-stu-id="73d66-143">Available Power Query data sources</span></span>

<span data-ttu-id="73d66-144">Вижте [справката за конектори на Power Query](https://docs.microsoft.com/power-query/connectors/) за актуален списък на конекторите, които можете да избирате за импортиране на данни в Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="73d66-144">See the [Power Query connector reference](https://docs.microsoft.com/power-query/connectors/) for an up-to-date list of connectors that you can select to import data to Customer Insights.</span></span> 

<span data-ttu-id="73d66-145">Конекторите с отметка в колоната **Customer Insights (потоци от данни)** са достъпни за създаване на нови източници на данни въз основа на Power Query.</span><span class="sxs-lookup"><span data-stu-id="73d66-145">Connectors with a checkmark in the **Customer Insights (Dataflows)** column are available to create new data sources based on Power Query.</span></span> <span data-ttu-id="73d66-146">Прегледайте документацията на конкретен конектор, за да научите повече за неговите изисквания, ограничения и други подробности.</span><span class="sxs-lookup"><span data-stu-id="73d66-146">Review the documentation of a specific connector to learn more about its prerequisites, limitations, and other details.</span></span>

## <a name="edit-power-query-data-sources"></a><span data-ttu-id="73d66-147">Редактиране на източници на данни на Power Query</span><span class="sxs-lookup"><span data-stu-id="73d66-147">Edit Power Query data sources</span></span>

> [!NOTE]
> <span data-ttu-id="73d66-148">Може да няма възможност за извършване на промени в източниците на данни, които в момента се използват в някой от процесите на приложението (*сегментиране*, *съвпадение* или *обединяване* например).</span><span class="sxs-lookup"><span data-stu-id="73d66-148">It might not be possible to make changes to data sources that are currently being used in one of the app's processes (*segmentation*, *match*, or *merge*, for example).</span></span> 
>
> <span data-ttu-id="73d66-149">Като използвате страницата **Настройки**, можете да проследите напредъка на всеки от активните процеси.</span><span class="sxs-lookup"><span data-stu-id="73d66-149">Using the **Settings** page, you can track the progress of each of the active processes.</span></span> <span data-ttu-id="73d66-150">Когато даден процес приключи, можете да се върнете в страницата **Източници на данни** и да направите промени.</span><span class="sxs-lookup"><span data-stu-id="73d66-150">When a process completes, you can return to the **Data Sources** page and make your changes.</span></span>

1. <span data-ttu-id="73d66-151">В статията за аудиторията отидете на **Данни** > **Източници на данни**.</span><span class="sxs-lookup"><span data-stu-id="73d66-151">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="73d66-152">Изберете вертикалното многоточие до източника на данни, който искате да промените, и изберете **Редактиране** от падащото меню.</span><span class="sxs-lookup"><span data-stu-id="73d66-152">Select the vertical ellipsis next to the data source you want to change and select **Edit** from the drop-down menu.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="73d66-153">![Опция „Редактиране“](media/edit-option-data-sources.png "Опция „Редактиране“")</span><span class="sxs-lookup"><span data-stu-id="73d66-153">![Edit option](media/edit-option-data-sources.png "Edit option")</span></span>

3. <span data-ttu-id="73d66-154">Приложете вашите промени и трансформации в диалоговия прозорец **Power Query – Редактиране на заявки**, както е описано в раздела [Създаване на нов източник на данни](#create-a-new-data-source).</span><span class="sxs-lookup"><span data-stu-id="73d66-154">Apply your changes and transformations in the **Power Query - Edit queries** dialog as described in the [Create a new data source](#create-a-new-data-source) section.</span></span>

4. <span data-ttu-id="73d66-155">Изберете **Записване** в Power Query, след като завършите редакциите си, за да запазите промените.</span><span class="sxs-lookup"><span data-stu-id="73d66-155">Select **Save** in Power Query after completing your edits to save your changes.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]