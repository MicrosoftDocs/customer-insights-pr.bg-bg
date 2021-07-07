---
title: Преглед на профили на клиент
description: Получете комбиниран изглед на своите унифицирани клиентски данни.
ms.date: 12/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: c9adb4d7db74573d0512ae7a68a0e7ab51c994a0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304591"
---
# <a name="customer-profiles"></a><span data-ttu-id="a31e2-103">Профили на клиент</span><span class="sxs-lookup"><span data-stu-id="a31e2-103">Customer profiles</span></span>

<span data-ttu-id="a31e2-104">Страницата **Клиенти** показва комбиниран изглед на вашите клиенти въз основа на данните от профила, събрани от [всички източници на данни](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="a31e2-104">The **Customers** page shows a combined view of your customers, based on profile data gathered from [all data sources](data-sources.md).</span></span> <span data-ttu-id="a31e2-105">Клиентските профили са достъпни, след като [създадете унифицирания обект на клиент](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="a31e2-105">Customer profiles are available once you [create the unified Customer entity](data-unification.md).</span></span> <span data-ttu-id="a31e2-106">Уверете се, че сте завършили процеса на унифициране на данни, за да получите по-обогатен изглед на своите клиенти.</span><span class="sxs-lookup"><span data-stu-id="a31e2-106">Make sure you complete the data unification process to get richer views of your customers.</span></span> <span data-ttu-id="a31e2-107">Страницата ви позволява също да търсите клиенти.</span><span class="sxs-lookup"><span data-stu-id="a31e2-107">The page also lets you search for customers.</span></span>

<span data-ttu-id="a31e2-108">Клиентите могат да бъдат физически лица или организации (преглед).</span><span class="sxs-lookup"><span data-stu-id="a31e2-108">Customers can be individuals or organizations (preview).</span></span> <span data-ttu-id="a31e2-109">Всеки клиентски или организационен профил е представен с плочка.</span><span class="sxs-lookup"><span data-stu-id="a31e2-109">Each customer or organization profile is represented by a tile.</span></span> <span data-ttu-id="a31e2-110">Изберете плочка, за да видите допълнителна информация за конкретния клиент или организация.</span><span class="sxs-lookup"><span data-stu-id="a31e2-110">Select a tile to see additional information on that specific customer or organization.</span></span> <span data-ttu-id="a31e2-111">Използвайте контролите за страниране в долната част на страницата, за да видите допълнителни записи.</span><span class="sxs-lookup"><span data-stu-id="a31e2-111">Use the pagination controls at the bottom of the page to see additional records.</span></span>

> [!div class="mx-imgBorder"] 
> <span data-ttu-id="a31e2-112">![Профил на клиент B2C](media/profiles-customers.png "Профил на клиент B2C")</span><span class="sxs-lookup"><span data-stu-id="a31e2-112">![B2C customer profiles](media/profiles-customers.png "B2C customer profiles")</span></span>

<span data-ttu-id="a31e2-113">Организации (преглед)</span><span class="sxs-lookup"><span data-stu-id="a31e2-113">Organizations (Preview)</span></span>
> [!div class="mx-imgBorder"] 
> <span data-ttu-id="a31e2-114">![Профил на клиент B2B](media/profile-customers-b2b.png "Профил на клиент B2B")</span><span class="sxs-lookup"><span data-stu-id="a31e2-114">![B2B customer profiles](media/profile-customers-b2b.png "B2B customer profiles")</span></span>

> [!NOTE]
> <span data-ttu-id="a31e2-115">Ако не можете да видите плочките, когато изберете **Клиенти** в навигацията, администраторът трябва да [дефинира поне един атрибут с възможност за търсене](search-filter-index.md) в **индекса за търсене и филтриране**.</span><span class="sxs-lookup"><span data-stu-id="a31e2-115">If you can't see the tiles when you select **Customers** in navigation, your administrator needs to [define at least one searchable attribute](search-filter-index.md) on the **Search & filter index**.</span></span>

## <a name="search-for-customers"></a><span data-ttu-id="a31e2-116">Търсене на клиенти</span><span class="sxs-lookup"><span data-stu-id="a31e2-116">Search for customers</span></span>

<span data-ttu-id="a31e2-117">Търсете клиенти, като въведете име или някакъв друг атрибут в полето за търсене.</span><span class="sxs-lookup"><span data-stu-id="a31e2-117">Search for customers by entering a name or some other attribute in the search box.</span></span> <span data-ttu-id="a31e2-118">Търсенето работи само в рамките на обекта на клиентски профил, създаден по време на процеса на унифициране на данни.</span><span class="sxs-lookup"><span data-stu-id="a31e2-118">The search only works within the Customer Profile entity created during the data unification process.</span></span>

<span data-ttu-id="a31e2-119">Като администратор можете да конфигурирате атрибутите с възможност за търсене с помощта на страницата **Показалец за търсене и филтриране**.</span><span class="sxs-lookup"><span data-stu-id="a31e2-119">As an admin, you can configure the searchable attributes using the **Search & filter index** page.</span></span> <span data-ttu-id="a31e2-120">За повече информация вижте [Управление на показалеца за търсене и филтриране](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="a31e2-120">For more information, see [Manage search & filter index](search-filter-index.md).</span></span>

## <a name="filter-customers"></a><span data-ttu-id="a31e2-121">Филтриране на клиенти</span><span class="sxs-lookup"><span data-stu-id="a31e2-121">Filter customers</span></span>

<span data-ttu-id="a31e2-122">Можете да филтрирате клиенти по полетата на обекта на клиентския профил.</span><span class="sxs-lookup"><span data-stu-id="a31e2-122">You can filter customers by the Customer Profile entity fields.</span></span> <span data-ttu-id="a31e2-123">Подобно на търсенето, първо е необходимо администратор да определи полетата като възможни за филтриране с помощта на страницата **Показалец за търсене и филтриране**.</span><span class="sxs-lookup"><span data-stu-id="a31e2-123">Similar to search, your admin will first need to define the fields as filterable using the **Search & filter index** page.</span></span>

1. <span data-ttu-id="a31e2-124">Изберете **Филтър** на страницата **Клиенти**.</span><span class="sxs-lookup"><span data-stu-id="a31e2-124">Select **Filter** on the **Customers** page.</span></span>

2. <span data-ttu-id="a31e2-125">Поставете отметки в квадратчетата до атрибутите, по които искате да филтрирате клиенти.</span><span class="sxs-lookup"><span data-stu-id="a31e2-125">Check the boxes next to the attributes you want to filter customers by.</span></span>

   > [!div class="mx-imgBorder"] 
   > <span data-ttu-id="a31e2-126">![Профили на клиент](media/profiles-customers3.png "Профили на клиент")</span><span class="sxs-lookup"><span data-stu-id="a31e2-126">![Customer profiles](media/profiles-customers3.png "Customer profiles")</span></span>

3. <span data-ttu-id="a31e2-127">Премахнете филтрите си, като изберете **Изчистване на филтрите** на страницата **Клиенти**.</span><span class="sxs-lookup"><span data-stu-id="a31e2-127">Remove your filters by selecting **Clear filters** on the **Customers** page.</span></span>

##  <a name="customer-details-page"></a><span data-ttu-id="a31e2-128">Страница с клиентски данни</span><span class="sxs-lookup"><span data-stu-id="a31e2-128">Customer details page</span></span>

<span data-ttu-id="a31e2-129">Изберете някоя от плочките на клиента, за да отворите **Страница с подробности за клиента**.</span><span class="sxs-lookup"><span data-stu-id="a31e2-129">Select any of the customer tiles to open the **Customer details page**.</span></span> <span data-ttu-id="a31e2-130">Този изглед съдържа унифицирана информация за избрания клиент.</span><span class="sxs-lookup"><span data-stu-id="a31e2-130">This view contains unified information for the selected customer.</span></span>

<span data-ttu-id="a31e2-131">Клиентските данни включват:</span><span class="sxs-lookup"><span data-stu-id="a31e2-131">Customer details include:</span></span>

-   <span data-ttu-id="a31e2-132">**Плочка на потребителския профил**: Тази плочка показва различните стойности от обединения обект на потребителския профил.</span><span class="sxs-lookup"><span data-stu-id="a31e2-132">**Customer profile tile**: This tile shows the different values from the unified customer profile entity.</span></span> <span data-ttu-id="a31e2-133">Тези подробности могат да включват имейл адрес, име, град и т.н.</span><span class="sxs-lookup"><span data-stu-id="a31e2-133">These details can include email address, name, city, and so on.</span></span> 

-   <span data-ttu-id="a31e2-134">**Потенциални интереси, потенциални марки**: Показва дали сте конфигурирали собствено обогатяване.</span><span class="sxs-lookup"><span data-stu-id="a31e2-134">**Potential interests, potential brands**: Shows if you configured a first-party enrichment.</span></span> <span data-ttu-id="a31e2-135">Той представлява потенциални интереси и афинитети към марки, които клиент с профил, подобен на този клиент, може да има.</span><span class="sxs-lookup"><span data-stu-id="a31e2-135">It represents potential interests and affinities for brands a customer with a profile similar to this customer might have.</span></span> <span data-ttu-id="a31e2-136">За повече информация вижте [Обогатете потребителските профили с афинитет към марката и интереса](enrichment-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="a31e2-136">For more information, see [Enrich customer profiles with brand and interest affinities](enrichment-microsoft.md).</span></span>

-   <span data-ttu-id="a31e2-137">**Мерки**: Показва дали сте конфигурирали една или повече мерки от определен тип: атрибути на клиента.</span><span class="sxs-lookup"><span data-stu-id="a31e2-137">**Measures**: Shows if you configured one or more measures of a specific type: customer attribute measures.</span></span> <span data-ttu-id="a31e2-138">Те включват изчислени KPI около вашите клиенти на индивидуално ниво на клиента.</span><span class="sxs-lookup"><span data-stu-id="a31e2-138">They include calculated KPIs around your customers on the individual customer level.</span></span> <span data-ttu-id="a31e2-139">За повече информация вижте [Определете и управлявайте мерките](measures.md).</span><span class="sxs-lookup"><span data-stu-id="a31e2-139">For more information, see [Define and manage measures](measures.md).</span></span>

-   <span data-ttu-id="a31e2-140">**Хронология на дейността**: Показва дали сте конфигурирали дейности.</span><span class="sxs-lookup"><span data-stu-id="a31e2-140">**Activity timeline**: Shows if you have configured activities.</span></span> <span data-ttu-id="a31e2-141">Изгледът на времевата линия съдържа хронологично сортирани дейности на този клиент, започвайки с най-новата дейност.</span><span class="sxs-lookup"><span data-stu-id="a31e2-141">The timeline view contains chronologically sorted activities of this customer, starting with the most recent activity.</span></span> <span data-ttu-id="a31e2-142">За повече информация вижте [Дейности на клиент](activities.md).</span><span class="sxs-lookup"><span data-stu-id="a31e2-142">For more information, see [Customer activities](activities.md).</span></span>

<span data-ttu-id="a31e2-143">Изберете **Обратно към клиентите**, за да се върнете на страницата за търсене на клиенти.</span><span class="sxs-lookup"><span data-stu-id="a31e2-143">Select **Back to Customers** to return to the customer search page.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a31e2-144">Следващи стъпки</span><span class="sxs-lookup"><span data-stu-id="a31e2-144">Next steps</span></span>

<span data-ttu-id="a31e2-145">[Добавяне на още източници на данни](data-sources.md) или [създаване на клиентски сегменти](segments.md).</span><span class="sxs-lookup"><span data-stu-id="a31e2-145">[Add more data sources](data-sources.md) or [create customer segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
