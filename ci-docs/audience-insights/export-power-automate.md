---
title: Конектор на Power Automate | Microsoft Docs
description: Създавайте потоци в Microsoft Power Automate от Dynamics 365 Customer Insights.
ms.date: 08/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: ffe92414365b0b777691a4a2d585100e4fbea591
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405066"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="d1c22-103">Конектор на Power Automate (преглед)</span><span class="sxs-lookup"><span data-stu-id="d1c22-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="d1c22-104">Активирайте определени събития да възникват автоматично при промяна на данните и управлявайте по-сложни потоци директно в [Power Automate](https://flow.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="d1c22-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="d1c22-105">Активатори на Power Automate</span><span class="sxs-lookup"><span data-stu-id="d1c22-105">Power Automate triggers</span></span>

<span data-ttu-id="d1c22-106">Можете да използвате различни активатори, които ви позволяват да създавате потоци, за да автоматизирате повтарящи се задачи, като например известия или по-разширени действия.</span><span class="sxs-lookup"><span data-stu-id="d1c22-106">You can use a variety of triggers that allow you to create flows to automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="d1c22-107">Задейства се при неуспешно обновяване на източник на данни.</span><span class="sxs-lookup"><span data-stu-id="d1c22-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="d1c22-108">Задейства се при успешно обновяване на източник на данни.</span><span class="sxs-lookup"><span data-stu-id="d1c22-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="d1c22-109">Задейства се при преминаване на праг в сегмент.</span><span class="sxs-lookup"><span data-stu-id="d1c22-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="d1c22-110">Активаторът е ограничен до преминаване над прага.</span><span class="sxs-lookup"><span data-stu-id="d1c22-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="d1c22-111">Задейства се при преминаване на праг в бизнес метрика.</span><span class="sxs-lookup"><span data-stu-id="d1c22-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="d1c22-112">Активаторът е ограничен до преминаване над прага.</span><span class="sxs-lookup"><span data-stu-id="d1c22-112">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="d1c22-113">Задействайте, когато завърши пълно опресняване на (източници на данни, сегменти, мерки, ...).</span><span class="sxs-lookup"><span data-stu-id="d1c22-113">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="d1c22-114">Задейства се, когато завърши опресняване на процеса на обединяване (карта, съвпадение, сливане).</span><span class="sxs-lookup"><span data-stu-id="d1c22-114">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="d1c22-115">[Конфигурирайте вашите активатори в Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span><span class="sxs-lookup"><span data-stu-id="d1c22-115">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="d1c22-116">Действия на Power Automate</span><span class="sxs-lookup"><span data-stu-id="d1c22-116">Power Automate actions</span></span>
<span data-ttu-id="d1c22-117">Конекторът на Power Automate осигурява други действия освен наличните активатори.</span><span class="sxs-lookup"><span data-stu-id="d1c22-117">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="d1c22-118">За повече информация моля вижте [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="d1c22-118">For more information, see the [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow-in-audience-insights"></a><span data-ttu-id="d1c22-119">Създаване на поток на Power Automate в Аналитични данни за аудитория</span><span class="sxs-lookup"><span data-stu-id="d1c22-119">Create a Power Automate flow in audience insights</span></span>

1. <span data-ttu-id="d1c22-120">В Аналитични данни за аудитория отидете на **Администратор** > **Система**.</span><span class="sxs-lookup"><span data-stu-id="d1c22-120">In audience insights, go to **Admin** > **System**.</span></span>

1. <span data-ttu-id="d1c22-121">В страницата **Система** изберете раздела **Състояние**.</span><span class="sxs-lookup"><span data-stu-id="d1c22-121">On the **System** page, select the **Status** tab.</span></span>

1. <span data-ttu-id="d1c22-122">В секцията **Източници на данни** изберете **Потоци** и изберете **Създаване на поток** от падащия списък.</span><span class="sxs-lookup"><span data-stu-id="d1c22-122">In the **Data Sources** section, select **Flows** and select **Create a flow** from the dropdown list.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d1c22-123">![Конектор на Power Automate, който показва действие за създаване на поток](media/power-automate-connector-create-flow.png "Конектор на Power Automate, който показва действие за създаване на поток")</span><span class="sxs-lookup"><span data-stu-id="d1c22-123">![Power Automate connector showing Create a Flow action](media/power-automate-connector-create-flow.png "Power Automate connector showing Create a Flow action")</span></span>

1. <span data-ttu-id="d1c22-124">В Power Automate изберете един от наличните активатори, за да създадете предпочитания поток.</span><span class="sxs-lookup"><span data-stu-id="d1c22-124">In Power Automate, select one of the available triggers to create your preferred flow.</span></span> <span data-ttu-id="d1c22-125">Ако създавате първия си поток, първо ви е нужно удостоверяване с конектора на Power Automate.</span><span class="sxs-lookup"><span data-stu-id="d1c22-125">If you're creating your first flow, you'll need to authenticate with the Power Automate connector first.</span></span>
