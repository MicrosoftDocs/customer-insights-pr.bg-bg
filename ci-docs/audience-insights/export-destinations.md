---
title: Местоназначения на експортиране
description: Експортирайте данни и управлявайте дестинациите за експортиране.
ms.date: 07/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 9032d99357db86e66588eda544211a5f8eb2f23b
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643850"
---
# <a name="export-destinations-preview"></a><span data-ttu-id="909fc-103">Местоназначения на експортиране (преглед)</span><span class="sxs-lookup"><span data-stu-id="909fc-103">Export destinations (preview)</span></span>

<span data-ttu-id="909fc-104">Страницата **Местоназначения за експортиране** ви показва всички местоназначения, които сте задали за експортиране на данни.</span><span class="sxs-lookup"><span data-stu-id="909fc-104">The **Export destinations** page shows you all locations you've set up to export data to.</span></span> <span data-ttu-id="909fc-105">Можете също да добавите нови местоназначения за експортиране.</span><span class="sxs-lookup"><span data-stu-id="909fc-105">You can also add new destinations for export.</span></span> <span data-ttu-id="909fc-106">Освен това показва експортираните в момента опции.</span><span class="sxs-lookup"><span data-stu-id="909fc-106">Additionally, it shows export currently available options.</span></span> <span data-ttu-id="909fc-107">Получете бърз преглед, описание и разберете какво можете да направите с всяка опция за разширяване.</span><span class="sxs-lookup"><span data-stu-id="909fc-107">Get a quick overview, description, and find out what you can do with each extensibility option.</span></span> <span data-ttu-id="909fc-108">Експортирайте унифицирани профили, мерки и сегменти в поддържани приложения, подходящи за вашия бизнес.</span><span class="sxs-lookup"><span data-stu-id="909fc-108">Export unified profiles, measures, and segments to supported apps relevant for your business.</span></span>

<span data-ttu-id="909fc-109">Отидете на **Администриране** > **Експортиране на местоназначения**, за да намерите следните опции за разширяване:</span><span class="sxs-lookup"><span data-stu-id="909fc-109">Go to **Admin** > **Export destinations** to find the following extensibility options:</span></span>

- [<span data-ttu-id="909fc-110">Добавка за карта на клиент на Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="909fc-110">Dynamics 365 Customer Card Add-in</span></span>](customer-card-add-in.md)
- [<span data-ttu-id="909fc-111">Съединител на Мениджър на реклами на Facebook</span><span class="sxs-lookup"><span data-stu-id="909fc-111">Facebook Ads Manager connector</span></span>](export-facebook.md)
- [<span data-ttu-id="909fc-112">Конектор на Power Automate</span><span class="sxs-lookup"><span data-stu-id="909fc-112">Power Automate connector</span></span>](export-power-automate.md)
- [<span data-ttu-id="909fc-113">Конектор на Power Apps</span><span class="sxs-lookup"><span data-stu-id="909fc-113">Power Apps connector</span></span>](export-power-apps.md)
- [<span data-ttu-id="909fc-114">Конектор на Power BI</span><span class="sxs-lookup"><span data-stu-id="909fc-114">Power BI connector</span></span>](export-power-bi.md)
- [<span data-ttu-id="909fc-115">DotDigital</span><span class="sxs-lookup"><span data-stu-id="909fc-115">DotDigital</span></span>](export-dotdigital.md)
- [<span data-ttu-id="909fc-116">Продажби в Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="909fc-116">Dynamics 365 Sales</span></span>](export-dynamics365-sales.md)
- [<span data-ttu-id="909fc-117">Dynamics 365 Marketing</span><span class="sxs-lookup"><span data-stu-id="909fc-117">Dynamics 365 Marketing</span></span>](export-dynamics365-marketing.md)
- [<span data-ttu-id="909fc-118">Хранилище за BLOB на Azure</span><span class="sxs-lookup"><span data-stu-id="909fc-118">Azure Blob Storage</span></span>](export-azure-blob-storage.md)
- [<span data-ttu-id="909fc-119">LiveRamp&reg; съединител</span><span class="sxs-lookup"><span data-stu-id="909fc-119">LiveRamp&reg; connector</span></span>](export-liveramp.md)
- [<span data-ttu-id="909fc-120">Бот за Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="909fc-120">Bot for Microsoft Teams</span></span>](export-teams-bot.md)
- [<span data-ttu-id="909fc-121">Mailchimp</span><span class="sxs-lookup"><span data-stu-id="909fc-121">Mailchimp</span></span>](export-mailchimp.md)
- [<span data-ttu-id="909fc-122">API на Customer Insights</span><span class="sxs-lookup"><span data-stu-id="909fc-122">Customer Insights API</span></span>](apis.md)

## <a name="add-a-new-export-destination"></a><span data-ttu-id="909fc-123">Добавяне на ново местоназначение за експортиране</span><span class="sxs-lookup"><span data-stu-id="909fc-123">Add a new export destination</span></span>

<span data-ttu-id="909fc-124">За да добавите дестинации за експортиране, имате [администраторски разрешения](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="909fc-124">To add export destinations, you have [administrator permissions](permissions.md).</span></span> <span data-ttu-id="909fc-125">Ако експортирате към услуги на Microsoft, предполагаме, че и двете услуги са в една и съща организация.</span><span class="sxs-lookup"><span data-stu-id="909fc-125">If you export to Microsoft services, we assume both services are in the same organization.</span></span>

1. <span data-ttu-id="909fc-126">Отидете на **Администратор** > **Експортиране на дестинации**.</span><span class="sxs-lookup"><span data-stu-id="909fc-126">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="909fc-127">Превключете към раздела **Моите дестинации за експортиране**.</span><span class="sxs-lookup"><span data-stu-id="909fc-127">Switch to the **My export destinations** tab.</span></span>

1. <span data-ttu-id="909fc-128">Изберете **Добавете дестинация** за създаване на нова дестинация за експортиране.</span><span class="sxs-lookup"><span data-stu-id="909fc-128">Select **Add destination** to create a new export destination.</span></span>

1. <span data-ttu-id="909fc-129">В екрана **Добавете дестинация** изберете **Тип** на дестинация за експортиране в падащото меню.</span><span class="sxs-lookup"><span data-stu-id="909fc-129">In the **Add destination** pane, select the **Type** of export destination in the drop-down.</span></span>

1. <span data-ttu-id="909fc-130">Въведете необходимите подробности и изберете **Напред**, за да създадете експортната дестинация.</span><span class="sxs-lookup"><span data-stu-id="909fc-130">Provide the required details and select **Next** to create the export destination.</span></span>

<span data-ttu-id="909fc-131">Можете също да изберете **Настройка** върху плочка на раздела **Откриване**.</span><span class="sxs-lookup"><span data-stu-id="909fc-131">You can also select **Set up** on a tile on the **Discover** tab.</span></span>

## <a name="view-export-destinations"></a><span data-ttu-id="909fc-132">Преглед на местоназначенията за експортиране</span><span class="sxs-lookup"><span data-stu-id="909fc-132">View Export destinations</span></span>

<span data-ttu-id="909fc-133">След като създадете експортни дестинации, ще ги намерите в таблица на раздела **Моите дестинации за експортиране**. Тази таблица има три колони:</span><span class="sxs-lookup"><span data-stu-id="909fc-133">After creating export destinations, you'll find them in a table on the **My export destinations** tab. This table has three columns:</span></span>

- <span data-ttu-id="909fc-134">**Показвано име**: Името, което сте въвели при създаването на местоназначението.</span><span class="sxs-lookup"><span data-stu-id="909fc-134">**Display name**: The name you entered when creating the destination.</span></span>
- <span data-ttu-id="909fc-135">**Тип**: Типът на дестинацията за експортиране, който сте задали при създаването на дестинацията.</span><span class="sxs-lookup"><span data-stu-id="909fc-135">**Type**: The export destination type you set when creating the destination.</span></span>
- <span data-ttu-id="909fc-136">**Създадено на**: датата, на която сте създали местоназначението.</span><span class="sxs-lookup"><span data-stu-id="909fc-136">**Created**: The date you created the destination.</span></span>

## <a name="edit-an-export-destination"></a><span data-ttu-id="909fc-137">Редактиране на местоназначение за експортиране</span><span class="sxs-lookup"><span data-stu-id="909fc-137">Edit an export destination</span></span>

1. <span data-ttu-id="909fc-138">Изберете вертикалното многоточие за местоназначението за експортиране, което искате да редактирате.</span><span class="sxs-lookup"><span data-stu-id="909fc-138">Select the vertical ellipsis for the Export destination you want to edit.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="909fc-139">![Вертикално многоточие](media/export-destinations-page-ellipsis.png "Вертикално многоточие")</span><span class="sxs-lookup"><span data-stu-id="909fc-139">![Vertical ellipsis](media/export-destinations-page-ellipsis.png "Vertical ellipsis")</span></span>

1. <span data-ttu-id="909fc-140">Изберете **Редактиране** от падащото меню.</span><span class="sxs-lookup"><span data-stu-id="909fc-140">Select **Edit** from the dropdown menu.</span></span>

1. <span data-ttu-id="909fc-141">Променете стойностите, които изискват актуализация и изберете **Записване**.</span><span class="sxs-lookup"><span data-stu-id="909fc-141">Change the values that require update and select **Save**.</span></span>

## <a name="export-data-on-demand"></a><span data-ttu-id="909fc-142">Експортиране на данни при поискване</span><span class="sxs-lookup"><span data-stu-id="909fc-142">Export data on demand</span></span>

<span data-ttu-id="909fc-143">След конфигуриране на конектор за експортна дестинация, експортът ще се изпълнява с всяко [планирано опресняване](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="909fc-143">After configuring a connector for an export destination, exports will run with every [scheduled refresh](system.md#schedule-tab).</span></span>

<span data-ttu-id="909fc-144">За да експортирате данни, без да чакате планирано опресняване, отидете на раздела **Моите дестинации за експортиране** в **Администратор** > **Дестинации за експортиране**.</span><span class="sxs-lookup"><span data-stu-id="909fc-144">To export data without waiting for a scheduled refresh, go the **My export destinations** tab on **Admin** > **Export destinations**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="909fc-145">![Вертикално многоточие](media/export-destinations-page-ellipsis.png "Вертикално многоточие")</span><span class="sxs-lookup"><span data-stu-id="909fc-145">![Vertical ellipsis](media/export-destinations-page-ellipsis.png "Vertical ellipsis")</span></span>

- <span data-ttu-id="909fc-146">Изберете **Експортиране** над списъка, за да стартирате едновременно експортирането до всички дестинации за експортиране.</span><span class="sxs-lookup"><span data-stu-id="909fc-146">Select **Export** above the list to run the export to all export destinations simultaneously.</span></span>
- <span data-ttu-id="909fc-147">Изберете многоточието (...) след елемент от списъка и след това изберете опцията **Експортиране** за стартиране на експортирането за една експортна дестинация.</span><span class="sxs-lookup"><span data-stu-id="909fc-147">Select the ellipsis (...) after a list item and then choose the **Export** option to run the export for a single export destination.</span></span>

## <a name="remove-an-export-destination"></a><span data-ttu-id="909fc-148">Премахване на местоназначение за експортиране</span><span class="sxs-lookup"><span data-stu-id="909fc-148">Remove an Export destination</span></span>

<span data-ttu-id="909fc-149">За да премахнете местоназначение за експортиране, започнете от главната страница **Местоназначения за експортиране**.</span><span class="sxs-lookup"><span data-stu-id="909fc-149">To remove an Export destination, start from the main **Export destinations** page.</span></span>

1. <span data-ttu-id="909fc-150">Изберете вертикалното многоточие за местоназначението за експортиране, което искате да премахнете.</span><span class="sxs-lookup"><span data-stu-id="909fc-150">Select the vertical ellipsis for the Export destination you want to remove.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="909fc-151">![Вертикално многоточие](media/export-destinations-page-ellipsis.png "Вертикално многоточие")</span><span class="sxs-lookup"><span data-stu-id="909fc-151">![Vertical ellipsis](media/export-destinations-page-ellipsis.png "Vertical ellipsis")</span></span>

2. <span data-ttu-id="909fc-152">Изберете **Премахване** от падащото меню.</span><span class="sxs-lookup"><span data-stu-id="909fc-152">Select **Remove** from the dropdown menu.</span></span>

3. <span data-ttu-id="909fc-153">Потвърдете премахването, като изберете **Премахване** в екрана за потвърждение.</span><span class="sxs-lookup"><span data-stu-id="909fc-153">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>
