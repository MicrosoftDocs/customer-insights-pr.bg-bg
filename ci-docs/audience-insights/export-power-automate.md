---
title: Конектор на Power Automate | Microsoft Docs
description: Създавайте потоци в Microsoft Power Automate от Dynamics 365 Customer Insights.
ms.date: 01/20/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: fb1df4e9ab1f78300b8ec1f8dfdfbfbac0e71447
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268811"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="dc769-103">Конектор на Power Automate (преглед)</span><span class="sxs-lookup"><span data-stu-id="dc769-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="dc769-104">Активирайте определени събития да възникват автоматично при промяна на данните и управлявайте по-сложни потоци директно в [Power Automate](https://flow.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="dc769-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="dc769-105">Активатори на Power Automate</span><span class="sxs-lookup"><span data-stu-id="dc769-105">Power Automate triggers</span></span>

<span data-ttu-id="dc769-106">Използвайте тригери за създаване на облачни потоци и автоматизиране на повтарящи се задачи, като известия или по-разширени действия.</span><span class="sxs-lookup"><span data-stu-id="dc769-106">Use triggers to create cloud flows and automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="dc769-107">Задейства се при неуспешно обновяване на източник на данни.</span><span class="sxs-lookup"><span data-stu-id="dc769-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="dc769-108">Задейства се при успешно обновяване на източник на данни.</span><span class="sxs-lookup"><span data-stu-id="dc769-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="dc769-109">Задейства се при преминаване на праг в сегмент.</span><span class="sxs-lookup"><span data-stu-id="dc769-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="dc769-110">Активаторът е ограничен до преминаване над прага.</span><span class="sxs-lookup"><span data-stu-id="dc769-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="dc769-111">Задейства се при преминаване на праг в бизнес метрика.</span><span class="sxs-lookup"><span data-stu-id="dc769-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="dc769-112">Активаторът е ограничен до преминаване над прага.</span><span class="sxs-lookup"><span data-stu-id="dc769-112">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="dc769-113">Задействайте, когато завърши пълно опресняване на (източници на данни, сегменти, мерки, ...).</span><span class="sxs-lookup"><span data-stu-id="dc769-113">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="dc769-114">Задейства се, когато завърши опресняване на процеса на обединяване (карта, съвпадение, сливане).</span><span class="sxs-lookup"><span data-stu-id="dc769-114">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="dc769-115">[Конфигурирайте вашите активатори в Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span><span class="sxs-lookup"><span data-stu-id="dc769-115">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="dc769-116">Действия на Power Automate</span><span class="sxs-lookup"><span data-stu-id="dc769-116">Power Automate actions</span></span>
<span data-ttu-id="dc769-117">Конекторът на Power Automate осигурява други действия освен наличните активатори.</span><span class="sxs-lookup"><span data-stu-id="dc769-117">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="dc769-118">За повече информация моля вижте [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="dc769-118">For more information, see the [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow"></a><span data-ttu-id="dc769-119">Създаване на поток на Power Automate</span><span class="sxs-lookup"><span data-stu-id="dc769-119">Create a Power Automate flow</span></span>

1. <span data-ttu-id="dc769-120">В статията за аудиторията отидете на **Администратор** > **Експортиране на местоположения**.</span><span class="sxs-lookup"><span data-stu-id="dc769-120">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="dc769-121">В плочката **Power Automate**, изберете **Настройка**.</span><span class="sxs-lookup"><span data-stu-id="dc769-121">On the **Power Automate** tile, select **Set up**.</span></span>

1. <span data-ttu-id="dc769-122">Конекторът на Customer Insights (преглед) в Power Automate се отваря.</span><span class="sxs-lookup"><span data-stu-id="dc769-122">The Customer Insights Connector (preview) in Power Automate opens.</span></span> <span data-ttu-id="dc769-123">**Влезте** в Power Automate.</span><span class="sxs-lookup"><span data-stu-id="dc769-123">**Sign in** to Power Automate.</span></span>

1. <span data-ttu-id="dc769-124">Изберете един от наличните задействания и добавете още стъпки към новия си поток.</span><span class="sxs-lookup"><span data-stu-id="dc769-124">Choose one of the available triggers and add more steps to your new flow.</span></span> <span data-ttu-id="dc769-125">За повече информация вижте [Създаване на поток за облак в Power Automate](https://docs.microsoft.com/power-automate/get-started-logic-flow).</span><span class="sxs-lookup"><span data-stu-id="dc769-125">For more information, see [Create a cloud flow in Power Automate](https://docs.microsoft.com/power-automate/get-started-logic-flow).</span></span>

<span data-ttu-id="dc769-126">Примери за използване на потоци:</span><span class="sxs-lookup"><span data-stu-id="dc769-126">Examples how to use flows:</span></span> 
- <span data-ttu-id="dc769-127">Публикувайте съобщение до канал на Microsoft Teams, ако източник на данни опресняването не успее.</span><span class="sxs-lookup"><span data-stu-id="dc769-127">Post a message to a Microsoft Teams channel if a data source refresh fails.</span></span> 
- <span data-ttu-id="dc769-128">Изпратете имейл до собствениците на данни, когато е превишен праг за сегмент.</span><span class="sxs-lookup"><span data-stu-id="dc769-128">Send an email to the data owners when a threshold on a segment is crossed.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]