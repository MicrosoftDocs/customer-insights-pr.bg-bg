---
title: Конектор на Power Apps
description: Свързване с Power Apps и Power Automate.
ms.date: 08/21/2020
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b6ec103e29e218b2f27bfc1193300ea793a6b30b
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405068"
---
# <a name="microsoft-power-apps-connector-preview"></a><span data-ttu-id="58ffb-103">Конектор на Microsoft Power Apps (преглед)</span><span class="sxs-lookup"><span data-stu-id="58ffb-103">Microsoft Power Apps connector (preview)</span></span>

<span data-ttu-id="58ffb-104">Включете унифицирани клиентски профили в персонализираните приложения с Power Apps.</span><span class="sxs-lookup"><span data-stu-id="58ffb-104">Bring unified customer profiles into your personalized apps with Power Apps.</span></span>

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a><span data-ttu-id="58ffb-105">Свързване на Power Apps и Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="58ffb-105">Connect Power Apps and Dynamics 365 Customer Insights</span></span>

<span data-ttu-id="58ffb-106">Customer Insights е сред многото [налични източници за данни в Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/working-with-data-sources).</span><span class="sxs-lookup"><span data-stu-id="58ffb-106">Customer Insights is one of the many [available sources for data in Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/working-with-data-sources).</span></span>

<span data-ttu-id="58ffb-107">Вижте документацията на Power Apps, за да научите как да [добавяте връзка за данни към приложение](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-data-connection).</span><span class="sxs-lookup"><span data-stu-id="58ffb-107">Refer to the Power Apps documentation to learn how to [add a data connection to an app](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-data-connection).</span></span> <span data-ttu-id="58ffb-108">Препоръчваме ви също да прегледате [как Power Apps използва делегиране за обработка на големи набори от данни в приложения за платно](https://docs.microsoft.com/powerapps/maker/canvas-apps/delegation-overview).</span><span class="sxs-lookup"><span data-stu-id="58ffb-108">We recommend you also review [how Power Apps uses delegation to handle large datasets in Canvas apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/delegation-overview).</span></span>

## <a name="available-entities"></a><span data-ttu-id="58ffb-109">Свободни обекти</span><span class="sxs-lookup"><span data-stu-id="58ffb-109">Available entities</span></span>

<span data-ttu-id="58ffb-110">След като добавите Customer Insights като връзка за данни, можете да използвате следните обекти в Power Apps:</span><span class="sxs-lookup"><span data-stu-id="58ffb-110">After adding Customer Insights as a data connection, you can choose the following entities in Power Apps:</span></span>

- <span data-ttu-id="58ffb-111">Клиент: за да се използват данни от [унифицирания клиентски профил](customer-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="58ffb-111">Customer: to use data from the [unified customer profile](customer-profiles.md).</span></span>
- <span data-ttu-id="58ffb-112">Унифицирана клиентска дейност: за показване на [времевата линия на дейност](activities.md) в приложението.</span><span class="sxs-lookup"><span data-stu-id="58ffb-112">Unified Customer Activity: to display the [activity timeline](activities.md) on the app.</span></span>

## <a name="limitations"></a><span data-ttu-id="58ffb-113">Ограничения</span><span class="sxs-lookup"><span data-stu-id="58ffb-113">Limitations</span></span>

### <a name="retrievable-entities"></a><span data-ttu-id="58ffb-114">Възможни за извличане обекти</span><span class="sxs-lookup"><span data-stu-id="58ffb-114">Retrievable entities</span></span>

<span data-ttu-id="58ffb-115">Можете да изтеглите само **Клиент**, **UnifiedActivity** и **Сегменти** обекти чрез Power Apps съединител.</span><span class="sxs-lookup"><span data-stu-id="58ffb-115">You can only retrieve the **Customer**, **UnifiedActivity**, and **Segments** entities through the Power Apps connector.</span></span> <span data-ttu-id="58ffb-116">Показани са други обекти, защото основният конектор ги поддържа чрез задействания в Power Automate.</span><span class="sxs-lookup"><span data-stu-id="58ffb-116">Other entities are shown because the underlying connector supports them through triggers in Power Automate.</span></span>  

### <a name="delegation"></a><span data-ttu-id="58ffb-117">Делегиране</span><span class="sxs-lookup"><span data-stu-id="58ffb-117">Delegation</span></span>

<span data-ttu-id="58ffb-118">Делегирането работи за обекта на клиента и обекта на UnifiedActivity.</span><span class="sxs-lookup"><span data-stu-id="58ffb-118">Delegation works for the Customer entity and UnifiedActivity entity.</span></span> 

- <span data-ttu-id="58ffb-119">Делегация за обекта **Клиент**: За да се използва делегиране за този обект, полетата трябва да бъдат индексирани в [Индекс за търсене и филтриране](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="58ffb-119">Delegation for **Customer** entity: To use delegation for this entity, the fields need to be indexed in [Search & filter index](search-filter-index.md).</span></span>  

- <span data-ttu-id="58ffb-120">Делегиране за **UnifiedActivity**: Делегирането за този обект работи само за полетата **ActivityId** и **Клиентски номер**.</span><span class="sxs-lookup"><span data-stu-id="58ffb-120">Delegation for **UnifiedActivity**: Delegation for this entity only works for the fields **ActivityId** and **CustomerId**.</span></span>  

- <span data-ttu-id="58ffb-121">За повече информация относно делегирането вижте [делегируеми функции и операции на Power Apps](https://docs.microsoft.com/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps).</span><span class="sxs-lookup"><span data-stu-id="58ffb-121">For more information about delegation, see [Power Apps delegable functions and operations](https://docs.microsoft.com/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps).</span></span> 

## <a name="example-gallery-control"></a><span data-ttu-id="58ffb-122">Контрола на примерна галерия</span><span class="sxs-lookup"><span data-stu-id="58ffb-122">Example gallery control</span></span>

<span data-ttu-id="58ffb-123">Например добавяте потребителски профили към [контрола на галерията](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-gallery).</span><span class="sxs-lookup"><span data-stu-id="58ffb-123">For example, you add customer profiles to a [gallery control](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-gallery).</span></span>

1. <span data-ttu-id="58ffb-124">Добавете контрола **Галерия** към приложението, което създавате.</span><span class="sxs-lookup"><span data-stu-id="58ffb-124">Add a **Gallery** control to an app you're building.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="58ffb-125">![Добавяне на елемент от галерията](media/connector-powerapps9.png "Добавяне на елемент от галерията")</span><span class="sxs-lookup"><span data-stu-id="58ffb-125">![Add a gallery element](media/connector-powerapps9.png "Add a gallery element")</span></span>

1. <span data-ttu-id="58ffb-126">Изберете **Клиент** като източник на данни за елементите.</span><span class="sxs-lookup"><span data-stu-id="58ffb-126">Select **Customer** as the data source for items.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="58ffb-127">![Избор на източник на данни](media/choose-datasource-powerapps.png "Избор на източник на данни")</span><span class="sxs-lookup"><span data-stu-id="58ffb-127">![Select a data source](media/choose-datasource-powerapps.png "Select a data source")</span></span>

1. <span data-ttu-id="58ffb-128">Можете да промените панела с данни вдясно, за да изберете полето за обекта на клиента, което ще бъде показано в галерията.</span><span class="sxs-lookup"><span data-stu-id="58ffb-128">You can change the data panel on the right to select which field for the Customer entity to show on the gallery.</span></span>

1. <span data-ttu-id="58ffb-129">Ако искате да покажете в галерията някое поле от избрания клиент, попълнете свойството „Текст” на етикет: **{Name_of_the_gallery}.Избрано.{property_name}**</span><span class="sxs-lookup"><span data-stu-id="58ffb-129">If you want to show any field from the selected customer on the gallery, fill in the Text property of a label:  **{Name_of_the_gallery}.Selected.{property_name}**</span></span>

    <span data-ttu-id="58ffb-130">Пример: Gallery1.Selected.address1_city</span><span class="sxs-lookup"><span data-stu-id="58ffb-130">Example: Gallery1.Selected.address1_city</span></span>

1. <span data-ttu-id="58ffb-131">За да се покаже унифицираната времева линия за клиент, добавете елемент от галерията и добавете свойството „Елементи“: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**</span><span class="sxs-lookup"><span data-stu-id="58ffb-131">To display the unified timeline for a customer, add a Gallery element, and add the Items property: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**</span></span>

    <span data-ttu-id="58ffb-132">Пример: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span><span class="sxs-lookup"><span data-stu-id="58ffb-132">Example: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span></span>
