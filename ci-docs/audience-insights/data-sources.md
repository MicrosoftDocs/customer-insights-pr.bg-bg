---
title: Използване на източници на данни за поглъщане на данни
description: Научете как да импортирате данни от различни източници.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 54dd7b629d4b4e7f640b932b0f9246e0602f46bd
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304683"
---
# <a name="data-sources-overview"></a><span data-ttu-id="fbd6d-103">Общ преглед на източниците на данни</span><span class="sxs-lookup"><span data-stu-id="fbd6d-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="fbd6d-104">Възможността на Аналитични данни за аудитория в Dynamics 365 Customer Insights свързва се с данни от широк набор от източници.</span><span class="sxs-lookup"><span data-stu-id="fbd6d-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="fbd6d-105">Свързването с източник на данни често се нарича процес на *поглъщане на данни*.</span><span class="sxs-lookup"><span data-stu-id="fbd6d-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="fbd6d-106">След като погълнете данните, можете [да ги обедините](data-unification.md) и да предприемете действия с тях.</span><span class="sxs-lookup"><span data-stu-id="fbd6d-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="fbd6d-107">Добавяне на източник на данни</span><span class="sxs-lookup"><span data-stu-id="fbd6d-107">Add a data source</span></span>

<span data-ttu-id="fbd6d-108">Вижте подробните статии за това как да добавите източник на данни в зависимост от избраната опция.</span><span class="sxs-lookup"><span data-stu-id="fbd6d-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="fbd6d-109">Можете да добавите източник на данни по три основни начина:</span><span class="sxs-lookup"><span data-stu-id="fbd6d-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="fbd6d-110">Чрез десетки конектори на Power Query</span><span class="sxs-lookup"><span data-stu-id="fbd6d-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="fbd6d-111">От папка в Common Data Model</span><span class="sxs-lookup"><span data-stu-id="fbd6d-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="fbd6d-112">От свое собствено хранилище в Microsoft Dataverse</span><span class="sxs-lookup"><span data-stu-id="fbd6d-112">From your own Microsoft Dataverse lake</span></span>](connect-common-data-service-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a><span data-ttu-id="fbd6d-113">Добавяне на данни от локални източници на данни</span><span class="sxs-lookup"><span data-stu-id="fbd6d-113">Add data from on-premises data sources</span></span>

<span data-ttu-id="fbd6d-114">Приемането на данни от локални източници на данни в аналитични данни за аудитории се поддържа въз основа на потоци от данни на Microsoft Power Platform.</span><span class="sxs-lookup"><span data-stu-id="fbd6d-114">Ingesting data from on-premises data sources in audience insights is supported based on Microsoft Power Platform dataflows.</span></span> <span data-ttu-id="fbd6d-115">Потоците от данни могат да се активират в Customer Insights чрез [въвеждане на URL адреса на средата на Microsoft Dataverse](manage-environments.md#create-an-environment-in-an-existing-organization) при настройка на средата.</span><span class="sxs-lookup"><span data-stu-id="fbd6d-115">Dataflows can be enabled in Customer Insights by [providing the Microsoft Dataverse environment URL](manage-environments.md#create-an-environment-in-an-existing-organization) when setting up the environment.</span></span>

<span data-ttu-id="fbd6d-116">Източници на данни, които се създават след свързване на среда на Dataverse с Customer Insights, ще използват [потоците от данни на Power Platform](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) по подразбиране.</span><span class="sxs-lookup"><span data-stu-id="fbd6d-116">Data sources that are created after associating a Dataverse environment with Customer Insights will use [Power Platform dataflows](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) by default.</span></span> <span data-ttu-id="fbd6d-117">Потоците от данни поддържат локална свързаност чрез шлюзовете за данни.</span><span class="sxs-lookup"><span data-stu-id="fbd6d-117">Dataflows support on-premises connectivity using the data gateway.</span></span> <span data-ttu-id="fbd6d-118">Премахнете и създайте повторно източници на данни, които са били налични преди свързването на среда на Dataverse за [използване на локалните шлюзове за данни](/data-integration/gateway/service-gateway-app.md).</span><span class="sxs-lookup"><span data-stu-id="fbd6d-118">Remove and recreate data sources that existed before a Dataverse environment was associated to [use the on-premises data gateways](/data-integration/gateway/service-gateway-app.md).</span></span>

<span data-ttu-id="fbd6d-119">Шлюзове за данни от съществуваща среда на Power BI или Power Apps ще са видими и можете да ги използвате повторно в Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="fbd6d-119">Data gateways from an existing Power BI or Power Apps environment will be visible and you can reuse in Customer Insights.</span></span> <span data-ttu-id="fbd6d-120">Страницата с източници на данни показва връзки към Microsoft Power Platform среда, където можете да преглеждате и конфигурирате локален шлюзове за данни.</span><span class="sxs-lookup"><span data-stu-id="fbd6d-120">The data sources page shows links to go to the Microsoft Power Platform environment where you can view and configure on-premises data gateways.</span></span>

## <a name="review-ingested-data"></a><span data-ttu-id="fbd6d-121">Преглед на погълнатите данни</span><span class="sxs-lookup"><span data-stu-id="fbd6d-121">Review ingested data</span></span>

<span data-ttu-id="fbd6d-122">Ще видите името на всеки погълнат източник на данни, неговото състояние и последното обновяване на данните за този източник.</span><span class="sxs-lookup"><span data-stu-id="fbd6d-122">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="fbd6d-123">Можете да сортирате списъка с източници на данни по всяка колона.</span><span class="sxs-lookup"><span data-stu-id="fbd6d-123">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="fbd6d-124">![Добавен източник на данни](media/configure-data-datasource-added.png "Добавен източник на данни")</span><span class="sxs-lookup"><span data-stu-id="fbd6d-124">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="fbd6d-125">Състояние</span><span class="sxs-lookup"><span data-stu-id="fbd6d-125">Status</span></span>  |<span data-ttu-id="fbd6d-126">Описание</span><span class="sxs-lookup"><span data-stu-id="fbd6d-126">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="fbd6d-127">Успешна</span><span class="sxs-lookup"><span data-stu-id="fbd6d-127">Successful</span></span>   |<span data-ttu-id="fbd6d-128">Източникът на данни в успешно погълнат, ако времето е указано в колоната **Обновено**.</span><span class="sxs-lookup"><span data-stu-id="fbd6d-128">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="fbd6d-129">Не е започнало</span><span class="sxs-lookup"><span data-stu-id="fbd6d-129">Not started</span></span>   |<span data-ttu-id="fbd6d-130">Източникът на данни все още няма погълнати данни или все още е в режим на чернова.</span><span class="sxs-lookup"><span data-stu-id="fbd6d-130">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="fbd6d-131">Обновяване</span><span class="sxs-lookup"><span data-stu-id="fbd6d-131">Refreshing</span></span>    |<span data-ttu-id="fbd6d-132">Приемането на данни е в ход.</span><span class="sxs-lookup"><span data-stu-id="fbd6d-132">Data ingestion is in progress.</span></span> <span data-ttu-id="fbd6d-133">Можете да отмените тази операция, като изберете **Спиране на обновяването** в колоната **Действия**.</span><span class="sxs-lookup"><span data-stu-id="fbd6d-133">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="fbd6d-134">Спирането на обновяването на източник на данни ще го върне в последното му състояние на обновяване.</span><span class="sxs-lookup"><span data-stu-id="fbd6d-134">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="fbd6d-135">Неуспешни</span><span class="sxs-lookup"><span data-stu-id="fbd6d-135">Failed</span></span>     |<span data-ttu-id="fbd6d-136">Приемането на данни се натъкна на грешки.</span><span class="sxs-lookup"><span data-stu-id="fbd6d-136">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="fbd6d-137">Изберете стойността в колоната **Състояние** на всеки източник на данни, за да прегледате повече подробности.</span><span class="sxs-lookup"><span data-stu-id="fbd6d-137">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="fbd6d-138">На екрана **Подробности за напредъка** разгънете **Източници на данни**.</span><span class="sxs-lookup"><span data-stu-id="fbd6d-138">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="fbd6d-139">Изберете **Вижте подробности** за повече информация относно състоянието на опресняване, включително подробности за грешки и актуализации на процеса надолу по веригата.</span><span class="sxs-lookup"><span data-stu-id="fbd6d-139">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="fbd6d-140">Зареждането на данни може да отнеме време.</span><span class="sxs-lookup"><span data-stu-id="fbd6d-140">Loading data can take time.</span></span> <span data-ttu-id="fbd6d-141">След успешно обновяване приетите данни могат да бъдат прегледани от страницата **Обекти**.</span><span class="sxs-lookup"><span data-stu-id="fbd6d-141">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="fbd6d-142">За повече информация вижте [Обекти](entities.md).</span><span class="sxs-lookup"><span data-stu-id="fbd6d-142">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="fbd6d-143">Обновяване на източник на данни</span><span class="sxs-lookup"><span data-stu-id="fbd6d-143">Refresh a data source</span></span>

<span data-ttu-id="fbd6d-144">Източниците на данни могат да се опресняват по автоматичен график или да се опресняват ръчно при поискване.</span><span class="sxs-lookup"><span data-stu-id="fbd6d-144">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="fbd6d-145">Отидете на **Администратор** > **Система** > [**График**](system.md#schedule-tab), за да конфигурирате планирани обновявания на всички ваши погълнати източници на данни.</span><span class="sxs-lookup"><span data-stu-id="fbd6d-145">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="fbd6d-146">За да опресните източник на данни при поискване, изпълнете следните стъпки:</span><span class="sxs-lookup"><span data-stu-id="fbd6d-146">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="fbd6d-147">В статията за аудиторията отидете на **Данни** > **Източници на данни**.</span><span class="sxs-lookup"><span data-stu-id="fbd6d-147">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="fbd6d-148">Изберете вертикалната елипса до източник на данни, която искате да опресните и изберете **Обнови** от падащия списък.</span><span class="sxs-lookup"><span data-stu-id="fbd6d-148">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the dropdown list.</span></span>

3. <span data-ttu-id="fbd6d-149">Източникът на данни вече се задейства за ръчно опресняване.</span><span class="sxs-lookup"><span data-stu-id="fbd6d-149">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="fbd6d-150">Обновяването на източник на данни ще актуализира както схемата на обекта, така и данните за всички обекти, посочени в източника на данни.</span><span class="sxs-lookup"><span data-stu-id="fbd6d-150">Refreshing a data source will update both the entity schema and data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="fbd6d-151">Изберете **Спиране на обновяването**, ако искате да отмените съществуващо опресняване и източник на данни ще се върне към последното си състояние на опресняване.</span><span class="sxs-lookup"><span data-stu-id="fbd6d-151">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="fbd6d-152">Изтриване на източник на данни</span><span class="sxs-lookup"><span data-stu-id="fbd6d-152">Delete a data source</span></span>

1. <span data-ttu-id="fbd6d-153">В статията за аудиторията отидете на **Данни** > **Източници на данни**.</span><span class="sxs-lookup"><span data-stu-id="fbd6d-153">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="fbd6d-154">Изберете вертикалната елипса до източник на данни, която искате да премахнете и изберете **изтриване** от падащото меню.</span><span class="sxs-lookup"><span data-stu-id="fbd6d-154">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the dropdown menu.</span></span>

3. <span data-ttu-id="fbd6d-155">Потвърдете изтриването.</span><span class="sxs-lookup"><span data-stu-id="fbd6d-155">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
