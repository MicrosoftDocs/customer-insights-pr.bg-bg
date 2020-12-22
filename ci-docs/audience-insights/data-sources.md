---
title: Използване на източници на данни за поглъщане на данни
description: Научете как да импортирате данни от различни източници.
ms.date: 11/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: a720641f7499fc71ff5bceeba48d296c51f77242
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643940"
---
# <a name="overview-about-data-sources"></a><span data-ttu-id="8c8a0-103">Общ преглед на източниците на данни</span><span class="sxs-lookup"><span data-stu-id="8c8a0-103">Overview about data sources</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="8c8a0-104">Възможността на Аналитични данни за аудитория в Dynamics 365 Customer Insights свързва се с данни от широк набор от източници.</span><span class="sxs-lookup"><span data-stu-id="8c8a0-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="8c8a0-105">Свързването с източник на данни често се нарича процес на *поглъщане на данни*.</span><span class="sxs-lookup"><span data-stu-id="8c8a0-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="8c8a0-106">След като погълнете данните, можете [да ги обедините](data-unification.md) и да предприемете действия с тях.</span><span class="sxs-lookup"><span data-stu-id="8c8a0-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="8c8a0-107">Добавяне на източник на данни</span><span class="sxs-lookup"><span data-stu-id="8c8a0-107">Add a data source</span></span>

<span data-ttu-id="8c8a0-108">Вижте подробните статии за това как да добавите източник на данни в зависимост от избраната опция.</span><span class="sxs-lookup"><span data-stu-id="8c8a0-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="8c8a0-109">Можете да добавите източник на данни по три основни начина:</span><span class="sxs-lookup"><span data-stu-id="8c8a0-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="8c8a0-110">Чрез десетки конектори на Power Query</span><span class="sxs-lookup"><span data-stu-id="8c8a0-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="8c8a0-111">От папка в Common Data Model</span><span class="sxs-lookup"><span data-stu-id="8c8a0-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="8c8a0-112">От свое собствено хранилище в Common Data Service</span><span class="sxs-lookup"><span data-stu-id="8c8a0-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

> [!NOTE]
> <span data-ttu-id="8c8a0-113">Все още не можете да добавяте данни от локални източници на данни.</span><span class="sxs-lookup"><span data-stu-id="8c8a0-113">You can't add data from on-premises data sources yet.</span></span>

## <a name="review-ingested-data"></a><span data-ttu-id="8c8a0-114">Преглед на погълнатите данни</span><span class="sxs-lookup"><span data-stu-id="8c8a0-114">Review ingested data</span></span>

<span data-ttu-id="8c8a0-115">Ще видите името на всеки погълнат източник на данни, неговото състояние и последното обновяване на данните за този източник.</span><span class="sxs-lookup"><span data-stu-id="8c8a0-115">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="8c8a0-116">Можете да сортирате списъка с източници на данни по всяка колона.</span><span class="sxs-lookup"><span data-stu-id="8c8a0-116">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="8c8a0-117">![Добавен източник на данни](media/configure-data-datasource-added.png "Добавен източник на данни")</span><span class="sxs-lookup"><span data-stu-id="8c8a0-117">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="8c8a0-118">Състояние</span><span class="sxs-lookup"><span data-stu-id="8c8a0-118">Status</span></span>  |<span data-ttu-id="8c8a0-119">Описание</span><span class="sxs-lookup"><span data-stu-id="8c8a0-119">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="8c8a0-120">Успешна</span><span class="sxs-lookup"><span data-stu-id="8c8a0-120">Successful</span></span>   |<span data-ttu-id="8c8a0-121">Източникът на данни в успешно погълнат, ако времето е указано в колоната **Обновено**.</span><span class="sxs-lookup"><span data-stu-id="8c8a0-121">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="8c8a0-122">Не е започнало</span><span class="sxs-lookup"><span data-stu-id="8c8a0-122">Not started</span></span>   |<span data-ttu-id="8c8a0-123">Източникът на данни все още няма погълнати данни или все още е в режим на чернова.</span><span class="sxs-lookup"><span data-stu-id="8c8a0-123">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="8c8a0-124">Обновяване</span><span class="sxs-lookup"><span data-stu-id="8c8a0-124">Refreshing</span></span>    |<span data-ttu-id="8c8a0-125">Приемането на данни е в ход.</span><span class="sxs-lookup"><span data-stu-id="8c8a0-125">Data ingestion is in progress.</span></span> <span data-ttu-id="8c8a0-126">Можете да отмените тази операция, като изберете **Спиране на обновяването** в колоната **Действия**.</span><span class="sxs-lookup"><span data-stu-id="8c8a0-126">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="8c8a0-127">Спирането на обновяването на източник на данни ще го върне в последното му състояние на обновяване.</span><span class="sxs-lookup"><span data-stu-id="8c8a0-127">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="8c8a0-128">Неуспешни</span><span class="sxs-lookup"><span data-stu-id="8c8a0-128">Failed</span></span>     |<span data-ttu-id="8c8a0-129">Приемането на данни се натъкна на грешки.</span><span class="sxs-lookup"><span data-stu-id="8c8a0-129">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="8c8a0-130">Изберете **Опресняване на състоянието** за преглед на повече подробности за състоянието на опресняване, включително подробности за грешки и актуализации на процеса надолу по веригата.</span><span class="sxs-lookup"><span data-stu-id="8c8a0-130">Select **Refresh status** to review more details on the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="8c8a0-131">Зареждането на данните може да отнеме известно време.</span><span class="sxs-lookup"><span data-stu-id="8c8a0-131">Loading data can take some time.</span></span> <span data-ttu-id="8c8a0-132">След успешно обновяване приетите данни могат да бъдат прегледани от страницата **Обекти**.</span><span class="sxs-lookup"><span data-stu-id="8c8a0-132">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="8c8a0-133">За повече информация вижте [Обекти](entities.md).</span><span class="sxs-lookup"><span data-stu-id="8c8a0-133">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="8c8a0-134">Обновяване на източник на данни</span><span class="sxs-lookup"><span data-stu-id="8c8a0-134">Refresh a data source</span></span>

<span data-ttu-id="8c8a0-135">Източниците на данни могат да се опресняват по автоматичен график или да се опресняват ръчно при поискване.</span><span class="sxs-lookup"><span data-stu-id="8c8a0-135">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="8c8a0-136">Отидете на **Администратор** > **Система** > [**График**](system.md#schedule-tab), за да конфигурирате планирани обновявания на всички ваши погълнати източници на данни.</span><span class="sxs-lookup"><span data-stu-id="8c8a0-136">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="8c8a0-137">За да опресните източник на данни при поискване, изпълнете следните стъпки:</span><span class="sxs-lookup"><span data-stu-id="8c8a0-137">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="8c8a0-138">В статията за аудиторията отидете на **Данни** > **Източници на данни**</span><span class="sxs-lookup"><span data-stu-id="8c8a0-138">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="8c8a0-139">Изберете вертикалната елипса до източник на данни, която искате да опресните и изберете **Обнови** от падащия списък.</span><span class="sxs-lookup"><span data-stu-id="8c8a0-139">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="8c8a0-140">Източникът на данни вече се задейства за ръчно опресняване.</span><span class="sxs-lookup"><span data-stu-id="8c8a0-140">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="8c8a0-141">Опресняването на източник на данни ще актуализира както схемата на обекта, така и данните за всички обекти, посочени в източник на данни.</span><span class="sxs-lookup"><span data-stu-id="8c8a0-141">Refreshing a data source will update both the entity schema as well as data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="8c8a0-142">Изберете **Спиране на обновяването**, ако искате да отмените съществуващо опресняване и източник на данни ще се върне към последното си състояние на опресняване.</span><span class="sxs-lookup"><span data-stu-id="8c8a0-142">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="8c8a0-143">Изтриване на източник на данни</span><span class="sxs-lookup"><span data-stu-id="8c8a0-143">Delete a data source</span></span>

1. <span data-ttu-id="8c8a0-144">В статията за аудиторията отидете на **Данни** > **Източници на данни**.</span><span class="sxs-lookup"><span data-stu-id="8c8a0-144">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="8c8a0-145">Изберете вертикалното многоточие до източника на данни, който искате да премахнете, и изберете **Изтриване** от падащото меню.</span><span class="sxs-lookup"><span data-stu-id="8c8a0-145">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="8c8a0-146">Потвърдете изтриването.</span><span class="sxs-lookup"><span data-stu-id="8c8a0-146">Confirm your deletion.</span></span>
