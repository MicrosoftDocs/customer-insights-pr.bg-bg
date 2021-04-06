---
title: Конектор на Power BI
description: Научете как да използвате конектора на Dynamics 365 Customer Insights в Power BI.
ms.date: 09/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: e43e2f9dbc84ebfbf2154990a752740f973296cb
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596026"
---
# <a name="connector-for-power-bi-preview"></a><span data-ttu-id="9d8eb-103">Конектор за Power BI (преглед)</span><span class="sxs-lookup"><span data-stu-id="9d8eb-103">Connector for Power BI (preview)</span></span>

<span data-ttu-id="9d8eb-104">Създайте визуализации за вашите данни с Power BI Desktop.</span><span class="sxs-lookup"><span data-stu-id="9d8eb-104">Create visualizations for your data with the Power BI Desktop.</span></span> <span data-ttu-id="9d8eb-105">Генерирайте допълнителна информация и създавайте отчети с обединените клиентски данни.</span><span class="sxs-lookup"><span data-stu-id="9d8eb-105">Generate additional insights and build reports with your unified customer data.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9d8eb-106">Предварителни изисквания</span><span class="sxs-lookup"><span data-stu-id="9d8eb-106">Prerequisites</span></span>

- <span data-ttu-id="9d8eb-107">Имате унифицирани клиентски профили.</span><span class="sxs-lookup"><span data-stu-id="9d8eb-107">You have unified customer profiles.</span></span>
- <span data-ttu-id="9d8eb-108">Най-новата версия на [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) е инсталирана на вашия компютър.</span><span class="sxs-lookup"><span data-stu-id="9d8eb-108">The latest version of [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) is installed on your computer.</span></span> <span data-ttu-id="9d8eb-109">[Научете повече за Power BI Desktop](/power-bi/desktop-what-is-desktop).</span><span class="sxs-lookup"><span data-stu-id="9d8eb-109">[Learn more about Power BI Desktop](/power-bi/desktop-what-is-desktop).</span></span>

## <a name="configure-the-connector-for-power-bi"></a><span data-ttu-id="9d8eb-110">Конфигуриране на конектора за Power BI</span><span class="sxs-lookup"><span data-stu-id="9d8eb-110">Configure the connector for Power BI</span></span>

1. <span data-ttu-id="9d8eb-111">В Power BI Desktop изберете **Файл** > **Получаване на данни**.</span><span class="sxs-lookup"><span data-stu-id="9d8eb-111">In Power BI Desktop, select **File** > **Get Data**.</span></span>

1. <span data-ttu-id="9d8eb-112">Изберете **Вижте още** и търсете **Dynamics 365 Customer Insights**</span><span class="sxs-lookup"><span data-stu-id="9d8eb-112">Select **See more** and search for **Dynamics 365 Customer Insights**</span></span>

1. <span data-ttu-id="9d8eb-113">Изберете **Свързване**.</span><span class="sxs-lookup"><span data-stu-id="9d8eb-113">Select **Connect**.</span></span>

1. <span data-ttu-id="9d8eb-114">**Влезте** със същия акаунт на организация, който използвате за Customer Insights, и изберете **Свързване**.</span><span class="sxs-lookup"><span data-stu-id="9d8eb-114">**Sign in** with the same organizational account you use for Customer Insights and select **Connect**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="9d8eb-115">Акаунтът, който посочите в тази стъпка, се използва за извличане на данни от Customer Insights и не е необходимо да бъде същият, с който сте влезли в Power BI.</span><span class="sxs-lookup"><span data-stu-id="9d8eb-115">The account you indicate in this step is used to fetch data from Customer Insights and doesn't need to be the same you are signed in to Power BI.</span></span> <span data-ttu-id="9d8eb-116">За да нулирате акаунта, който се използва за извличане на данни, отворете Power BI и отидете на **Файл** > **Настроики** > **Настройки** > **Насторойки на източник на данни**.</span><span class="sxs-lookup"><span data-stu-id="9d8eb-116">To reset the account that is used for data fetching, open Power BI and go to **File** > **Options** > **Settings** > **Data source settings**.</span></span> <span data-ttu-id="9d8eb-117">В списъка с източници на данни изберете **Влизане в Dynamics 365 Customer Insights** и изберете **Изчистване на разрешенията**.</span><span class="sxs-lookup"><span data-stu-id="9d8eb-117">In the list of data sources, select **Dynamics 365 Customer Insights Login** and select **Clear permissions**.</span></span>  

1. <span data-ttu-id="9d8eb-118">В диалоговия прозорец на **Навигатор**.</span><span class="sxs-lookup"><span data-stu-id="9d8eb-118">In the **Navigator** dialog box.</span></span> <span data-ttu-id="9d8eb-119">виждате списъка с всички среди, до които имате достъп.</span><span class="sxs-lookup"><span data-stu-id="9d8eb-119">you see the list of all environments you have access to.</span></span> <span data-ttu-id="9d8eb-120">Разгънете среда и отворете някоя от папките (обекти, мерки, сегменти, обогатявания).</span><span class="sxs-lookup"><span data-stu-id="9d8eb-120">Expand an environment and open any of the folders (entities, measures, segments, enrichments).</span></span> <span data-ttu-id="9d8eb-121">Например отворете папката **Обекти**, за да видите всички обекти, които можете да импортирате.</span><span class="sxs-lookup"><span data-stu-id="9d8eb-121">For example, open the **Entities** folder, to see all entities you can import.</span></span>

   <span data-ttu-id="9d8eb-122">![Навигатор за конектор на Power BI](media/power-bi-navigator.png "Навигатор за конектор на Power BI")</span><span class="sxs-lookup"><span data-stu-id="9d8eb-122">![Power BI Connector Navigator](media/power-bi-navigator.png "Power BI Connector Navigator")</span></span>

1. <span data-ttu-id="9d8eb-123">Поставете отметки в квадратчетата до обектите, които да се включат и **заредят**.</span><span class="sxs-lookup"><span data-stu-id="9d8eb-123">Select the check boxes next to the entities to include and **Load**.</span></span> <span data-ttu-id="9d8eb-124">Можете да изберете няколко обекта от няколко среди.</span><span class="sxs-lookup"><span data-stu-id="9d8eb-124">You can select multiple entities from multiple environments.</span></span>

1. <span data-ttu-id="9d8eb-125">Ще видите диалогов прозорец за зареждане, докато обектите се зареждат.</span><span class="sxs-lookup"><span data-stu-id="9d8eb-125">You'll see a loading dialog box while your entities are loaded.</span></span> <span data-ttu-id="9d8eb-126">След като всички избрани обекти се заредят, можете да използвате възможностите на Power BI за да визуализирате данните.</span><span class="sxs-lookup"><span data-stu-id="9d8eb-126">Once all of your selected entities have loaded, you can use the capabilities of Power BI to visualize the data.</span></span>

## <a name="large-data-sets"></a><span data-ttu-id="9d8eb-127">Големи набори от данни</span><span class="sxs-lookup"><span data-stu-id="9d8eb-127">Large data sets</span></span>

<span data-ttu-id="9d8eb-128">Конекторът на Customer Insights за Power BI е проектиран да работи за набори от данни, които съдържат до 1 милион клиентски профила.</span><span class="sxs-lookup"><span data-stu-id="9d8eb-128">The Customer Insights connector for Power BI is designed to work for data sets that contain up to 1 million customer profiles.</span></span> <span data-ttu-id="9d8eb-129">Импортирането на по-големи набори от данни може да работи, но отнема много време.</span><span class="sxs-lookup"><span data-stu-id="9d8eb-129">Importing larger data sets may work, but it takes a long time.</span></span> <span data-ttu-id="9d8eb-130">Освен това процесът може да изтече по време на изчакване поради ограничения на Power BI.</span><span class="sxs-lookup"><span data-stu-id="9d8eb-130">Additionally, the process could run into a time-out because of Power BI limitations.</span></span> <span data-ttu-id="9d8eb-131">За повече информация вижте [Power BI: Препоръки за големи масиви от данни](/power-bi/admin/service-premium-what-is#large-datasets).</span><span class="sxs-lookup"><span data-stu-id="9d8eb-131">For more information, see [Power BI: Recommendations for large data sets](/power-bi/admin/service-premium-what-is#large-datasets).</span></span> 

### <a name="work-with-a-subset-of-data"></a><span data-ttu-id="9d8eb-132">Работа с подмножество данни</span><span class="sxs-lookup"><span data-stu-id="9d8eb-132">Work with a subset of data</span></span>

<span data-ttu-id="9d8eb-133">Помислете за работа с подмножество от вашите данни.</span><span class="sxs-lookup"><span data-stu-id="9d8eb-133">Consider working with a subset of your data.</span></span> <span data-ttu-id="9d8eb-134">Например можете да създавате [сегменти](segments.md) вместо да експортирате всички клиентски записи в Power BI.</span><span class="sxs-lookup"><span data-stu-id="9d8eb-134">For example, you can create [segments](segments.md) instead of exporting all customer records to Power BI.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="9d8eb-135">Отстраняване на неизправности</span><span class="sxs-lookup"><span data-stu-id="9d8eb-135">Troubleshooting</span></span>

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a><span data-ttu-id="9d8eb-136">Средата на Customer Insights не се показва в Power BI</span><span class="sxs-lookup"><span data-stu-id="9d8eb-136">Customer Insights environment doesn't show in Power BI</span></span>

<span data-ttu-id="9d8eb-137">Среда, която има повече от една [релация](relationships.md) дефинирани между две идентични обекти в статистика за аудиторията няма да бъдат налични в конектор Power BI.</span><span class="sxs-lookup"><span data-stu-id="9d8eb-137">Environments that have more than one [relationship](relationships.md) defined between two identical entities in audience insights will not be available in the Power BI connector.</span></span>

<span data-ttu-id="9d8eb-138">Можете да идентифицирате и премахнете дублираните връзки.</span><span class="sxs-lookup"><span data-stu-id="9d8eb-138">You can identify and remove the duplicated relationships.</span></span>

1. <span data-ttu-id="9d8eb-139">В статията за аудиторията отидете на **Данни** > **Релации** върху средата, която ви липсва в Power BI.</span><span class="sxs-lookup"><span data-stu-id="9d8eb-139">In audience insights, go to **Data** > **Relationships** on the environment you're missing in Power BI.</span></span>
2. <span data-ttu-id="9d8eb-140">Идентифицирайте дублирани релации:</span><span class="sxs-lookup"><span data-stu-id="9d8eb-140">Identify duplicated relationships:</span></span>
   - <span data-ttu-id="9d8eb-141">Проверете дали има дефинирани повече от една връзка между едни и същи две обекти.</span><span class="sxs-lookup"><span data-stu-id="9d8eb-141">Check if there is more than one relationship defined between the same two entities.</span></span>
   - <span data-ttu-id="9d8eb-142">Проверете дали е създадена връзка между две обекти, които са включени в процеса на обединение.</span><span class="sxs-lookup"><span data-stu-id="9d8eb-142">Check if there is a relationship created between two entities that are both included in the unification process.</span></span> <span data-ttu-id="9d8eb-143">Има дефинирана имплицитна връзка между всички обекти, включени в процеса на обединение.</span><span class="sxs-lookup"><span data-stu-id="9d8eb-143">There is an implicit relationship defined between all entities included in the unification process.</span></span>
3. <span data-ttu-id="9d8eb-144">Премахнете всички идентифицирани дублирани връзки.</span><span class="sxs-lookup"><span data-stu-id="9d8eb-144">Remove any duplicate relationships identified.</span></span>

<span data-ttu-id="9d8eb-145">След премахване на дублираните връзки, опитайте да конфигурирате конектора на Power BI отново.</span><span class="sxs-lookup"><span data-stu-id="9d8eb-145">After removal of the duplicated relationships, try to configure the Power BI connector again.</span></span> <span data-ttu-id="9d8eb-146">Средата трябва да е налична сега.</span><span class="sxs-lookup"><span data-stu-id="9d8eb-146">The environment should be available now.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]