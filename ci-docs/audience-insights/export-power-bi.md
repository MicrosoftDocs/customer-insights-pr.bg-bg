---
title: Конектор на Power BI
description: Научете как да използвате конектора на Dynamics 365 Customer Insights в Power BI.
ms.date: 09/21/2020
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d497ca779a337c512a7254524f597cff226bcb45
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405071"
---
# <a name="connector-for-power-bi-preview"></a><span data-ttu-id="71619-103">Конектор за Power BI (преглед)</span><span class="sxs-lookup"><span data-stu-id="71619-103">Connector for Power BI (preview)</span></span>

<span data-ttu-id="71619-104">Създайте визуализации за вашите данни с Power BI Desktop.</span><span class="sxs-lookup"><span data-stu-id="71619-104">Create visualizations for your data with the Power BI Desktop.</span></span> <span data-ttu-id="71619-105">Генерирайте допълнителна информация и създавайте отчети с обединените клиентски данни.</span><span class="sxs-lookup"><span data-stu-id="71619-105">Generate additional insights and build reports with your unified customer data.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="71619-106">Предварителни изисквания</span><span class="sxs-lookup"><span data-stu-id="71619-106">Prerequisites</span></span>

- <span data-ttu-id="71619-107">Имате унифицирани клиентски профили.</span><span class="sxs-lookup"><span data-stu-id="71619-107">You have unified customer profiles.</span></span>
- <span data-ttu-id="71619-108">Последната версия на [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) е инсталирана на вашия компютър.</span><span class="sxs-lookup"><span data-stu-id="71619-108">The latest version of [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) is installed on your computer.</span></span> <span data-ttu-id="71619-109">[Научете повече за Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).</span><span class="sxs-lookup"><span data-stu-id="71619-109">[Learn more about Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).</span></span>

## <a name="configure-the-connector-for-power-bi"></a><span data-ttu-id="71619-110">Конфигуриране на конектора за Power BI</span><span class="sxs-lookup"><span data-stu-id="71619-110">Configure the connector for Power BI</span></span>

1. <span data-ttu-id="71619-111">В Power BI Desktop изберете **Файл** > **Получаване на данни**.</span><span class="sxs-lookup"><span data-stu-id="71619-111">In Power BI Desktop, select **File** > **Get Data**.</span></span>

1. <span data-ttu-id="71619-112">Изберете **Вижте още** и търсете **Dynamics 365 Customer Insights**</span><span class="sxs-lookup"><span data-stu-id="71619-112">Select **See more** and search for **Dynamics 365 Customer Insights**</span></span>

1. <span data-ttu-id="71619-113">Изберете резултата и изберете **Свързване**.</span><span class="sxs-lookup"><span data-stu-id="71619-113">Select the result and select **Connect**.</span></span>

1. <span data-ttu-id="71619-114">**Влезте** със същия акаунт на организация, който използвате за Customer Insights, и изберете **Свързване**.</span><span class="sxs-lookup"><span data-stu-id="71619-114">**Sign in** with the same organizational account you use for Customer Insights and select **Connect**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="71619-115">Акаунтът, който посочите в тази стъпка, се използва за извличане на данни от Customer Insights и не е необходимо да бъде същият, с който сте влезли в Power BI.</span><span class="sxs-lookup"><span data-stu-id="71619-115">The account you indicate in this step is used to fetch data from Customer Insights and doesn't need to be the same you are signed in to Power BI.</span></span> <span data-ttu-id="71619-116">За да нулирате акаунта, който се използва за извличане на данни, отворете Power BI и отидете на **Файл** > **Настроики** > **Настройки** > **Насторойки на източник на данни**.</span><span class="sxs-lookup"><span data-stu-id="71619-116">To reset the account that is used for data fetching, open Power BI and go to **File** > **Options** > **Settings** > **Data source settings**.</span></span> <span data-ttu-id="71619-117">В списъка с източници на данни изберете **Влизане в Dynamics 365 Customer Insights** и изберете **Изчистване на разрешенията**.</span><span class="sxs-lookup"><span data-stu-id="71619-117">In the list of data sources, select **Dynamics 365 Customer Insights Login** and select **Clear permissions**.</span></span>  

1. <span data-ttu-id="71619-118">В диалоговия прозорец на **Навигатор**.</span><span class="sxs-lookup"><span data-stu-id="71619-118">In the **Navigator** dialog box.</span></span> <span data-ttu-id="71619-119">виждате списъка с всички среди, до които имате достъп.</span><span class="sxs-lookup"><span data-stu-id="71619-119">you see the list of all environments you have access to.</span></span> <span data-ttu-id="71619-120">Разгънете среда и отворете някоя от папките (обекти, мерки, сегменти, обогатявания).</span><span class="sxs-lookup"><span data-stu-id="71619-120">Expand an environment and open any of the folders (entities, measures, segments, enrichments).</span></span> <span data-ttu-id="71619-121">Например отворете папката **Обекти**, за да видите всички обекти, които можете да импортирате.</span><span class="sxs-lookup"><span data-stu-id="71619-121">For example, open the **Entities** folder, to see all entities you can import.</span></span>

   <span data-ttu-id="71619-122">![Навигатор за конектор на Power BI](media/power-bi-navigator.png "Навигатор за конектор на Power BI")</span><span class="sxs-lookup"><span data-stu-id="71619-122">![Power BI Connector Navigator](media/power-bi-navigator.png "Power BI Connector Navigator")</span></span>

1. <span data-ttu-id="71619-123">Поставете отметки в квадратчетата до обектите, които да се включат и **заредят**.</span><span class="sxs-lookup"><span data-stu-id="71619-123">Select the check boxes next to the entities to include and **Load**.</span></span> <span data-ttu-id="71619-124">Можете да изберете няколко обекта от няколко среди.</span><span class="sxs-lookup"><span data-stu-id="71619-124">You can select multiple entities from multiple environments.</span></span>

1. <span data-ttu-id="71619-125">Ще видите диалогов прозорец за зареждане, докато обектите се зареждат.</span><span class="sxs-lookup"><span data-stu-id="71619-125">You'll see a loading dialog box while your entities are loaded.</span></span> <span data-ttu-id="71619-126">След като всички избрани обекти се заредят, можете да използвате възможностите на Power BI за да визуализирате данните.</span><span class="sxs-lookup"><span data-stu-id="71619-126">Once all of your selected entities have loaded, you can use the capabilities of Power BI to visualize the data.</span></span>

## <a name="large-data-sets"></a><span data-ttu-id="71619-127">Големи набори от данни</span><span class="sxs-lookup"><span data-stu-id="71619-127">Large data sets</span></span>

<span data-ttu-id="71619-128">Конекторът на Customer Insights за Power BI е проектиран да работи за набори от данни, които съдържат до 1 милион клиентски профила.</span><span class="sxs-lookup"><span data-stu-id="71619-128">The Customer Insights connector for Power BI is designed to work for data sets that contain up to 1 million customer profiles.</span></span> <span data-ttu-id="71619-129">Импортирането на по-големи набори от данни може да работи, но отнема много време.</span><span class="sxs-lookup"><span data-stu-id="71619-129">Importing larger data sets may work, but it takes a long time.</span></span> <span data-ttu-id="71619-130">Освен това процесът може да изтече по време на изчакване поради ограничения на Power BI.</span><span class="sxs-lookup"><span data-stu-id="71619-130">Additionally, the process could run into a time-out because of Power BI limitations.</span></span> <span data-ttu-id="71619-131">За повече информация вижте [Power BI: Препоръки за големи масиви от данни](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets).</span><span class="sxs-lookup"><span data-stu-id="71619-131">For more information, see [Power BI: Recommendations for large data sets](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets).</span></span> 

### <a name="work-with-a-subset-of-data"></a><span data-ttu-id="71619-132">Работа с подмножество данни</span><span class="sxs-lookup"><span data-stu-id="71619-132">Work with a subset of data</span></span>

<span data-ttu-id="71619-133">Помислете за работа с подмножество от вашите данни.</span><span class="sxs-lookup"><span data-stu-id="71619-133">Consider working with a subset of your data.</span></span> <span data-ttu-id="71619-134">Например можете да създавате [сегменти](segments.md) вместо да експортирате всички клиентски записи в Power BI.</span><span class="sxs-lookup"><span data-stu-id="71619-134">For example, you can create [segments](segments.md) instead of exporting all customer records to Power BI.</span></span>
