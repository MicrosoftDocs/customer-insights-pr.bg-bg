---
title: Постепенно опресняване за източници на данни, базирани на Power Query
description: Обновяване на нови и актуализирани данни за големи източници на данни въз основа на Power Query.
ms.date: 09/28/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d4b01be75d25fa0e120904924a193171eefec579
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268535"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a><span data-ttu-id="9cd56-103">Постъпково обновяване за източници на данни, базирани на Power Query</span><span class="sxs-lookup"><span data-stu-id="9cd56-103">Incremental refresh for data sources based on Power Query</span></span>

<span data-ttu-id="9cd56-104">Постъпковото обновяване за източници на данни предоставя следните предимства:</span><span class="sxs-lookup"><span data-stu-id="9cd56-104">Incremental refresh for data sources provides the following advantages:</span></span>

- <span data-ttu-id="9cd56-105">**По-бързо обновяване** – Само данните, които са променени, се обновяват.</span><span class="sxs-lookup"><span data-stu-id="9cd56-105">**Faster refreshes** - Only data that has changed gets refreshed.</span></span> <span data-ttu-id="9cd56-106">Например, можете да обновите само последните пет дни от хронологичен набор от данни.</span><span class="sxs-lookup"><span data-stu-id="9cd56-106">For example, you might refresh only the past five days of a historical dataset.</span></span>
- <span data-ttu-id="9cd56-107">**Повишена надеждност** – При по-малки обновявания не е необходимо да поддържате връзки към системи с променливи източници за дълго време, като така се намалява риска от проблеми с връзката.</span><span class="sxs-lookup"><span data-stu-id="9cd56-107">**Increased reliability** - With smaller refreshes, you don't need to maintain connections to volatile source systems for as long, reducing the risk of connection issues.</span></span>
- <span data-ttu-id="9cd56-108">**Намалено потребление на ресурси** – Обновяването само на поднабор от общите ви данни води до по-ефективно използване на ресурси за изчисление и намалява следите от него в средата.</span><span class="sxs-lookup"><span data-stu-id="9cd56-108">**Reduced resource consumption** - Refreshing only a subset of your total data leads to more efficient use of computing resources and decreases the environmental footprint.</span></span>

## <a name="configure-incremental-refresh"></a><span data-ttu-id="9cd56-109">Конфигуриране на постъпково обновяване</span><span class="sxs-lookup"><span data-stu-id="9cd56-109">Configure incremental refresh</span></span>

<span data-ttu-id="9cd56-110">Статистика за аудиторията позволява постепенно опресняване за източници на данни, импортирани чрез Power Query, които поддържат постепенно поглъщане.</span><span class="sxs-lookup"><span data-stu-id="9cd56-110">Audience insights allows incremental refresh for data sources imported through Power Query that support incremental ingestion.</span></span> <span data-ttu-id="9cd56-111">Например бази данни на SQL в Azure с полета за дата и час, които показват кога записите на данни са актуализирани за последен път.</span><span class="sxs-lookup"><span data-stu-id="9cd56-111">For example, Azure SQL databases with date and time fields, which indicate when data records were last updated.</span></span>

1. <span data-ttu-id="9cd56-112">[Създаване на нов източник на данни въз основа на Power Query](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="9cd56-112">[Create a new data source based on Power Query](connect-power-query.md).</span></span>

1. <span data-ttu-id="9cd56-113">Въведете име за източника на данни.</span><span class="sxs-lookup"><span data-stu-id="9cd56-113">Provide a name for the data source.</span></span>

1. <span data-ttu-id="9cd56-114">Изберете източник на данни, който поддържа постъпково обновяване, като например база данни на SQL в Azure.</span><span class="sxs-lookup"><span data-stu-id="9cd56-114">Select a data source that supports incremental refresh, such as Azure SQL database.</span></span>

1. <span data-ttu-id="9cd56-115">Изберете обектите или таблиците за поглъщане.</span><span class="sxs-lookup"><span data-stu-id="9cd56-115">Select the entities or tables to ingest.</span></span>

1. <span data-ttu-id="9cd56-116">Изпълнете стъпките за трансформация и изберете **Напред**.</span><span class="sxs-lookup"><span data-stu-id="9cd56-116">Complete the transformation steps and select **Next**.</span></span>

1. <span data-ttu-id="9cd56-117">В диалоговия прозорец **Настройка на постъпково обновяване** изберете **Настройка**, за да отворите **Настройки на постъпково обновяване**.</span><span class="sxs-lookup"><span data-stu-id="9cd56-117">In the **Set up incremental refresh** dialog box, select **Set up** to open the **Incremental refresh settings**.</span></span> <span data-ttu-id="9cd56-118">Ако изберете **Пропускане**, източникът на данни ще обнови целия набор от данни.</span><span class="sxs-lookup"><span data-stu-id="9cd56-118">If you select **Skip**, the data source will refresh the entire data set.</span></span>
   > [!TIP]
   > <span data-ttu-id="9cd56-119">Можете също да приложите постъпково обновяване по-късно, като редактирате съществуващ източник на данни.</span><span class="sxs-lookup"><span data-stu-id="9cd56-119">You can also apply incremental refresh later by editing an existing data source.</span></span>

1. <span data-ttu-id="9cd56-120">В **Настройки за постъпково обновяване** ще конфигурирате постъпковото обновяване за всички обекти, които сте избрали при създаването на източника на данни.</span><span class="sxs-lookup"><span data-stu-id="9cd56-120">On **Incremental refresh settings**, you'll configure the incremental refresh for all entities that you selected when creating the data source.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9cd56-121">![Конфигуриране на обекти в източник на данни за постъпково обновяване](media/incremental-refresh-settings.png "Конфигуриране на обекти в източник на данни за постъпково обновяване")</span><span class="sxs-lookup"><span data-stu-id="9cd56-121">![Configure entities in a data source for incremental refresh](media/incremental-refresh-settings.png "Configure entities in a data source for incremental refresh")</span></span>

1. <span data-ttu-id="9cd56-122">Изберете обект и предоставете следните подробности:</span><span class="sxs-lookup"><span data-stu-id="9cd56-122">Select an entity, and provide the following details:</span></span>

   - <span data-ttu-id="9cd56-123">**Дефиниране на първичния ключ**: Изберете първичен ключ за обекта или таблицата.</span><span class="sxs-lookup"><span data-stu-id="9cd56-123">**Define the primary key**: Select a primary key for the entity or table.</span></span>
   - <span data-ttu-id="9cd56-124">**Дефиниране на „последно актуализирано“ поле**: Това поле ще показва само атрибути от тип дата или час.</span><span class="sxs-lookup"><span data-stu-id="9cd56-124">**Define the "last updated" field**: This field will only display attributes of type date or time.</span></span> <span data-ttu-id="9cd56-125">Изберете атрибут, който показва кога записите са актуализирани за последен път.</span><span class="sxs-lookup"><span data-stu-id="9cd56-125">Select an attribute that indicates when the records were last updated.</span></span> <span data-ttu-id="9cd56-126">Той ще се използва за идентифициране на записите, които попадат в границите на продължителността на постъпковото обновяване.</span><span class="sxs-lookup"><span data-stu-id="9cd56-126">It will be used to identify the records that fall within the incremental refresh time frame.</span></span>
   - <span data-ttu-id="9cd56-127">**Проверка за актуализации на всеки**: Укажете колко дълго искате да продължава периодът на постъпково обновяване.</span><span class="sxs-lookup"><span data-stu-id="9cd56-127">**Check for updates every**: Specify how long you want the incremental refresh time frame to be.</span></span>

1. <span data-ttu-id="9cd56-128">Изберете **Записване**, за да завършите създаването на източника на данни.</span><span class="sxs-lookup"><span data-stu-id="9cd56-128">Select **Save** to complete the creation of the data source.</span></span> <span data-ttu-id="9cd56-129">Първоначалното обновяване на данните ще бъде пълно обновяване.</span><span class="sxs-lookup"><span data-stu-id="9cd56-129">The initial data refresh will be a full refresh.</span></span> <span data-ttu-id="9cd56-130">След това постъпковото обновяване на данните става както е конфигурирано в предишната стъпка.</span><span class="sxs-lookup"><span data-stu-id="9cd56-130">Afterwards, the incremental data refresh happens as configured in the previous step.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]