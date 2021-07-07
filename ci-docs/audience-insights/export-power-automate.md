---
title: Конектор на Power Automate | Microsoft Docs
description: Създавайте потоци я Microsoft Power Automate от Dynamics 365 Customer Insights.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 57be0a204ef920b7a4bb31cf9a5b3a77f96eca0d
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305051"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="dabb0-103">Конектор на Power Automate (преглед)</span><span class="sxs-lookup"><span data-stu-id="dabb0-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="dabb0-104">Активирайте определени събития да възникват автоматично при промяна на данните и управлявайте по-сложни потоци директно в [Power Automate](https://flow.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="dabb0-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="dabb0-105">Активатори на Power Automate</span><span class="sxs-lookup"><span data-stu-id="dabb0-105">Power Automate triggers</span></span>

<span data-ttu-id="dabb0-106">Използвайте тригери за създаване на облачни потоци и автоматизиране на повтарящи се задачи, като известия или по-разширени действия.</span><span class="sxs-lookup"><span data-stu-id="dabb0-106">Use triggers to create cloud flows and automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="dabb0-107">Задейства се при неуспешно обновяване на източник на данни.</span><span class="sxs-lookup"><span data-stu-id="dabb0-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="dabb0-108">Задейства се при успешно обновяване на източник на данни.</span><span class="sxs-lookup"><span data-stu-id="dabb0-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="dabb0-109">Задейства се при преминаване на праг в сегмент.</span><span class="sxs-lookup"><span data-stu-id="dabb0-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="dabb0-110">Активаторът е ограничен до преминаване над прага.</span><span class="sxs-lookup"><span data-stu-id="dabb0-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="dabb0-111">Задейства се при преминаване на праг в бизнес метрика.</span><span class="sxs-lookup"><span data-stu-id="dabb0-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="dabb0-112">Поддържат се само бизнес мерки без измерение.</span><span class="sxs-lookup"><span data-stu-id="dabb0-112">Only business measures without a dimension are supported.</span></span> <span data-ttu-id="dabb0-113">Активаторът е ограничен до преминаване над прага.</span><span class="sxs-lookup"><span data-stu-id="dabb0-113">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="dabb0-114">Задействайте, когато завърши пълно опресняване на (източници на данни, сегменти, мерки, ...).</span><span class="sxs-lookup"><span data-stu-id="dabb0-114">Trigger when a full refresh of (data sources, segments, measures, ...) is completed.</span></span>
- <span data-ttu-id="dabb0-115">Задейства се, когато завърши опресняване на процеса на обединяване (карта, съвпадение, сливане).</span><span class="sxs-lookup"><span data-stu-id="dabb0-115">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

[<span data-ttu-id="dabb0-116">Конфигурирайте вашите активатори в Power Automate.</span><span class="sxs-lookup"><span data-stu-id="dabb0-116">Configure your triggers in Power Automate.</span></span>](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a><span data-ttu-id="dabb0-117">Действия на Power Automate</span><span class="sxs-lookup"><span data-stu-id="dabb0-117">Power Automate actions</span></span>

<span data-ttu-id="dabb0-118">Конекторът на Power Automate осигурява други действия освен наличните активатори.</span><span class="sxs-lookup"><span data-stu-id="dabb0-118">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="dabb0-119">За повече информация моля вижте [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="dabb0-119">For more information, see the [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow"></a><span data-ttu-id="dabb0-120">Създаване на поток на Power Automate</span><span class="sxs-lookup"><span data-stu-id="dabb0-120">Create a Power Automate flow</span></span>

1. <span data-ttu-id="dabb0-121">В статията за аудиторията отидете на **Администратор** > **Експортиране на местоположения**.</span><span class="sxs-lookup"><span data-stu-id="dabb0-121">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="dabb0-122">В плочката **Power Automate**, изберете **Настройка**.</span><span class="sxs-lookup"><span data-stu-id="dabb0-122">On the **Power Automate** tile, select **Set up**.</span></span>

1. <span data-ttu-id="dabb0-123">Конекторът на Customer Insights (преглед) в Power Automate се отваря.</span><span class="sxs-lookup"><span data-stu-id="dabb0-123">The Customer Insights Connector (preview) in Power Automate opens.</span></span> <span data-ttu-id="dabb0-124">**Влезте** в Power Automate.</span><span class="sxs-lookup"><span data-stu-id="dabb0-124">**Sign in** to Power Automate.</span></span>

1. <span data-ttu-id="dabb0-125">Изберете един от наличните задействания и добавете още стъпки към новия си поток.</span><span class="sxs-lookup"><span data-stu-id="dabb0-125">Choose one of the available triggers and add more steps to your new flow.</span></span> <span data-ttu-id="dabb0-126">За повече информация вижте [Създаване на поток за облак в Power Automate](/power-automate/get-started-logic-flow).</span><span class="sxs-lookup"><span data-stu-id="dabb0-126">For more information, see [Create a cloud flow in Power Automate](/power-automate/get-started-logic-flow).</span></span>

<span data-ttu-id="dabb0-127">Примери за използване на потоци:</span><span class="sxs-lookup"><span data-stu-id="dabb0-127">Examples of how to use flows:</span></span> 
- <span data-ttu-id="dabb0-128">Публикувайте съобщение до канал на Microsoft Teams, ако източник на данни опресняването не успее.</span><span class="sxs-lookup"><span data-stu-id="dabb0-128">Post a message to a Microsoft Teams channel if a data source refresh fails.</span></span> 
- <span data-ttu-id="dabb0-129">Изпратете имейл до собствениците на данни, когато е превишен праг за сегмент.</span><span class="sxs-lookup"><span data-stu-id="dabb0-129">Send an email to the data owners when a threshold on a segment is crossed.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]
