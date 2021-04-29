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
ms.openlocfilehash: 0fc13d3ac0a5176637b6fe481dabe0b2aec11649
ms.sourcegitcommit: d89b19b2a3497722b78362aeee688ae7e94915d9
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 04/13/2021
ms.locfileid: "5887881"
---
# <a name="data-sources-overview"></a><span data-ttu-id="48299-103">Общ преглед на източниците на данни</span><span class="sxs-lookup"><span data-stu-id="48299-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="48299-104">Възможността на Аналитични данни за аудитория в Dynamics 365 Customer Insights свързва се с данни от широк набор от източници.</span><span class="sxs-lookup"><span data-stu-id="48299-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="48299-105">Свързването с източник на данни често се нарича процес на *поглъщане на данни*.</span><span class="sxs-lookup"><span data-stu-id="48299-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="48299-106">След като погълнете данните, можете [да ги обедините](data-unification.md) и да предприемете действия с тях.</span><span class="sxs-lookup"><span data-stu-id="48299-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="48299-107">Добавяне на източник на данни</span><span class="sxs-lookup"><span data-stu-id="48299-107">Add a data source</span></span>

<span data-ttu-id="48299-108">Вижте подробните статии за това как да добавите източник на данни в зависимост от избраната опция.</span><span class="sxs-lookup"><span data-stu-id="48299-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="48299-109">Можете да добавите източник на данни по три основни начина:</span><span class="sxs-lookup"><span data-stu-id="48299-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="48299-110">Чрез десетки конектори на Power Query</span><span class="sxs-lookup"><span data-stu-id="48299-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="48299-111">От папка в Common Data Model</span><span class="sxs-lookup"><span data-stu-id="48299-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="48299-112">От свое собствено хранилище в Common Data Service</span><span class="sxs-lookup"><span data-stu-id="48299-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a><span data-ttu-id="48299-113">Добавяне на данни от локални източници на данни</span><span class="sxs-lookup"><span data-stu-id="48299-113">Add data from on-premises data sources</span></span>

<span data-ttu-id="48299-114">Приемането на данни от локални източници на данни в аналитични данни за аудитории се поддържа въз основа на потоци от данни на Power Platform.</span><span class="sxs-lookup"><span data-stu-id="48299-114">Ingesting data from on-premises data sources in Audience Insights is supported based on Power Platform dataflows.</span></span> <span data-ttu-id="48299-115">Потоците от данни могат да се активират в Customer Insights чрез [въвеждане на URL адреса на средата на Microsoft Dataverse](manage-environments.md#create-an-environment-in-an-existing-organization) при настройка на средата.</span><span class="sxs-lookup"><span data-stu-id="48299-115">Dataflows can be enabled in Customer Insights by [providing the Microsoft Dataverse environment URL](manage-environments.md#create-an-environment-in-an-existing-organization) when setting up the environment.</span></span>

<span data-ttu-id="48299-116">Източници на данни, които се създават след свързване на среда на Dataverse с Customer Insights, ще използват [потоците от данни на Power Platform](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) по подразбиране.</span><span class="sxs-lookup"><span data-stu-id="48299-116">Data sources that are created after associating a Dataverse environment with Customer Insights will use [Power Platform dataflows](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) by default.</span></span> <span data-ttu-id="48299-117">Потоците от данни поддържат локална свързаност чрез шлюзовете за данни.</span><span class="sxs-lookup"><span data-stu-id="48299-117">Dataflows support on-prem connectivity using the data gateways.</span></span> <span data-ttu-id="48299-118">Премахнете и създайте повторно източници на данни, които са били налични преди свързването на среда на Dataverse за използване на локалните шлюзове за данни.</span><span class="sxs-lookup"><span data-stu-id="48299-118">Remove and recreate data sources that existed before a Dataverse environment was associated to use the on-premises data gateways.</span></span>

<span data-ttu-id="48299-119">Шлюзове за данни от съществуваща среда на Power BI или Power Apps ще са видими и можете да ги използвате повторно в Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="48299-119">Data gateways from an existing Power BI or Power Apps environment will be visible and you can reuse in Customer Insights.</span></span> <span data-ttu-id="48299-120">Страницата с източници на данни показва връзки към средата на Power Platform, където можете да преглеждате и конфигурирате локални шлюзове за данни.</span><span class="sxs-lookup"><span data-stu-id="48299-120">The data sources page shows links to go the Power Platform environment where you can view and configure on-premises data gateways.</span></span>

:::image type="content" source="media/data-sources-onpremises-gateways.png" alt-text="Екранна снимка на страницата с източници на данни, която показва връзки, сочещи към средата на Power Platform.":::

## <a name="review-ingested-data"></a><span data-ttu-id="48299-122">Преглед на погълнатите данни</span><span class="sxs-lookup"><span data-stu-id="48299-122">Review ingested data</span></span>

<span data-ttu-id="48299-123">Ще видите името на всеки погълнат източник на данни, неговото състояние и последното обновяване на данните за този източник.</span><span class="sxs-lookup"><span data-stu-id="48299-123">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="48299-124">Можете да сортирате списъка с източници на данни по всяка колона.</span><span class="sxs-lookup"><span data-stu-id="48299-124">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="48299-125">![Добавен източник на данни](media/configure-data-datasource-added.png "Добавен източник на данни")</span><span class="sxs-lookup"><span data-stu-id="48299-125">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="48299-126">Състояние</span><span class="sxs-lookup"><span data-stu-id="48299-126">Status</span></span>  |<span data-ttu-id="48299-127">Описание</span><span class="sxs-lookup"><span data-stu-id="48299-127">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="48299-128">Успешна</span><span class="sxs-lookup"><span data-stu-id="48299-128">Successful</span></span>   |<span data-ttu-id="48299-129">Източникът на данни в успешно погълнат, ако времето е указано в колоната **Обновено**.</span><span class="sxs-lookup"><span data-stu-id="48299-129">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="48299-130">Не е започнало</span><span class="sxs-lookup"><span data-stu-id="48299-130">Not started</span></span>   |<span data-ttu-id="48299-131">Източникът на данни все още няма погълнати данни или все още е в режим на чернова.</span><span class="sxs-lookup"><span data-stu-id="48299-131">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="48299-132">Обновяване</span><span class="sxs-lookup"><span data-stu-id="48299-132">Refreshing</span></span>    |<span data-ttu-id="48299-133">Приемането на данни е в ход.</span><span class="sxs-lookup"><span data-stu-id="48299-133">Data ingestion is in progress.</span></span> <span data-ttu-id="48299-134">Можете да отмените тази операция, като изберете **Спиране на обновяването** в колоната **Действия**.</span><span class="sxs-lookup"><span data-stu-id="48299-134">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="48299-135">Спирането на обновяването на източник на данни ще го върне в последното му състояние на обновяване.</span><span class="sxs-lookup"><span data-stu-id="48299-135">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="48299-136">Неуспешни</span><span class="sxs-lookup"><span data-stu-id="48299-136">Failed</span></span>     |<span data-ttu-id="48299-137">Приемането на данни се натъкна на грешки.</span><span class="sxs-lookup"><span data-stu-id="48299-137">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="48299-138">Изберете стойността в колоната **Състояние** на всеки източник на данни, за да прегледате повече подробности.</span><span class="sxs-lookup"><span data-stu-id="48299-138">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="48299-139">На екрана **Подробности за напредъка** разгънете **Източници на данни**.</span><span class="sxs-lookup"><span data-stu-id="48299-139">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="48299-140">Изберете **Вижте подробности** за повече информация относно състоянието на опресняване, включително подробности за грешки и актуализации на процеса надолу по веригата.</span><span class="sxs-lookup"><span data-stu-id="48299-140">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="48299-141">Зареждането на данните може да отнеме известно време.</span><span class="sxs-lookup"><span data-stu-id="48299-141">Loading data can take some time.</span></span> <span data-ttu-id="48299-142">След успешно обновяване приетите данни могат да бъдат прегледани от страницата **Обекти**.</span><span class="sxs-lookup"><span data-stu-id="48299-142">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="48299-143">За повече информация вижте [Обекти](entities.md).</span><span class="sxs-lookup"><span data-stu-id="48299-143">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="48299-144">Обновяване на източник на данни</span><span class="sxs-lookup"><span data-stu-id="48299-144">Refresh a data source</span></span>

<span data-ttu-id="48299-145">Източниците на данни могат да се опресняват по автоматичен график или да се опресняват ръчно при поискване.</span><span class="sxs-lookup"><span data-stu-id="48299-145">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="48299-146">Отидете на **Администратор** > **Система** > [**График**](system.md#schedule-tab), за да конфигурирате планирани обновявания на всички ваши погълнати източници на данни.</span><span class="sxs-lookup"><span data-stu-id="48299-146">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="48299-147">За да опресните източник на данни при поискване, изпълнете следните стъпки:</span><span class="sxs-lookup"><span data-stu-id="48299-147">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="48299-148">В статията за аудиторията отидете на **Данни** > **Източници на данни**</span><span class="sxs-lookup"><span data-stu-id="48299-148">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="48299-149">Изберете вертикалната елипса до източник на данни, която искате да опресните и изберете **Обнови** от падащия списък.</span><span class="sxs-lookup"><span data-stu-id="48299-149">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="48299-150">Източникът на данни вече се задейства за ръчно опресняване.</span><span class="sxs-lookup"><span data-stu-id="48299-150">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="48299-151">Обновяването на източник на данни ще актуализира както схемата на обекта, така и данните за всички обекти, посочени в източника на данни.</span><span class="sxs-lookup"><span data-stu-id="48299-151">Refreshing a data source will update both the entity schema and data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="48299-152">Изберете **Спиране на обновяването**, ако искате да отмените съществуващо опресняване и източник на данни ще се върне към последното си състояние на опресняване.</span><span class="sxs-lookup"><span data-stu-id="48299-152">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="48299-153">Изтриване на източник на данни</span><span class="sxs-lookup"><span data-stu-id="48299-153">Delete a data source</span></span>

1. <span data-ttu-id="48299-154">В статията за аудиторията отидете на **Данни** > **Източници на данни**.</span><span class="sxs-lookup"><span data-stu-id="48299-154">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="48299-155">Изберете вертикалното многоточие до източника на данни, който искате да премахнете, и изберете **Изтриване** от падащото меню.</span><span class="sxs-lookup"><span data-stu-id="48299-155">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="48299-156">Потвърдете изтриването.</span><span class="sxs-lookup"><span data-stu-id="48299-156">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
