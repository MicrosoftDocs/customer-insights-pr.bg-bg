---
title: Примерно ръководство за прогноза за оттегляне на абонаменти
description: Използвайте това примерно ръководство, за да изпробвате модела за прогноза за оттегляне на абонаменти.
ms.date: 11/19/2020
ms.reviewer: digranad
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 2537cfb5dde0d1ce1af16f585f0bf91d15ea1870
ms.sourcegitcommit: a6e7df90d61450e00886753eb5db116f2f35bb6c
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 12/01/2020
ms.locfileid: "4653967"
---
# <a name="subscription-churn-prediction-preview-sample-guide"></a><span data-ttu-id="1625c-103">Примерно ръководство за прогноза за оттегляне на абонаменти (преглед)</span><span class="sxs-lookup"><span data-stu-id="1625c-103">Subscription churn prediction (preview) sample guide</span></span>

<span data-ttu-id="1625c-104">Ще ви преведем от край до край през прогноза за оттегляне на абонаменти, използвайки примерните данни, предоставени по-долу.</span><span class="sxs-lookup"><span data-stu-id="1625c-104">We'll walk you through an end to end example of subscription churn prediction using the sample data provided below.</span></span> 

## <a name="scenario"></a><span data-ttu-id="1625c-105">Сценарий</span><span class="sxs-lookup"><span data-stu-id="1625c-105">Scenario</span></span>

<span data-ttu-id="1625c-106">Contoso е компания, която произвежда висококачествено кафе и кафе машини, които продават чрез уебсайта си Contoso Coffee.</span><span class="sxs-lookup"><span data-stu-id="1625c-106">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="1625c-107">Наскоро те започнаха абонаментен бизнес за своите клиенти, за да получават кафе редовно.</span><span class="sxs-lookup"><span data-stu-id="1625c-107">They recently started a subscription business for their customers to get coffee on a regular basis.</span></span> <span data-ttu-id="1625c-108">Целта им е да разберат кои абонирани клиенти могат да анулират абонамента си през следващите няколко месеца.</span><span class="sxs-lookup"><span data-stu-id="1625c-108">Their goal is to understand, which subscribed customers might cancel their subscription in the next few months.</span></span> <span data-ttu-id="1625c-109">Знаейки кой е от техните клиенти **вероятно да се оттегли**, може да им помогне да спестят маркетингови усилия, като се съсредоточат върху запазването им.</span><span class="sxs-lookup"><span data-stu-id="1625c-109">Knowing which of their customers is **likely to churn**, can help them save marketing efforts by focusing on keeping them.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1625c-110">Предварителни изисквания</span><span class="sxs-lookup"><span data-stu-id="1625c-110">Prerequisites</span></span>

- <span data-ttu-id="1625c-111">Поне [Разрешения на сътрудник](permissions.md) в Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="1625c-111">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="1625c-112">Препоръчваме ви да изпълните следните стъпки [в нова среда](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="1625c-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="1625c-113">Задача 1 - Поглъщане на данни</span><span class="sxs-lookup"><span data-stu-id="1625c-113">Task 1 - Ingest Data</span></span>

<span data-ttu-id="1625c-114">Прегледайте статиите [за поглъщане на данни](data-sources.md) и [импортиране на източници на данни с помощта на конектори на Power Query](connect-power-query.md) конкретно.</span><span class="sxs-lookup"><span data-stu-id="1625c-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="1625c-115">Следващата информация предполага, че сте се запознали с поглъщането на данни като цяло.</span><span class="sxs-lookup"><span data-stu-id="1625c-115">The following information assumes you familiarized with ingesting data in general.</span></span> 

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="1625c-116">Поглъщайте клиентски данни от платформата за електронна търговия</span><span class="sxs-lookup"><span data-stu-id="1625c-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="1625c-117">Създайте име на източник на данни **електронна търговия**, изберете опцията за импортиране и изберете конектора **Текст/CSV**.</span><span class="sxs-lookup"><span data-stu-id="1625c-117">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="1625c-118">Въведете URL адреса за контакти за електронна търговия https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="1625c-118">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="1625c-119">Докато редактирате данните, изберете **Трансформирайте** и тогава **Използвайте първия ред за заглавки**.</span><span class="sxs-lookup"><span data-stu-id="1625c-119">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="1625c-120">Актуализирайте типа данни за колоните, изброени по-долу:</span><span class="sxs-lookup"><span data-stu-id="1625c-120">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="1625c-121">**DateOfBirth**: Дата</span><span class="sxs-lookup"><span data-stu-id="1625c-121">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="1625c-122">**CreatedOn**: Дата/час/зона</span><span class="sxs-lookup"><span data-stu-id="1625c-122">**CreatedOn**: Date/Time/Zone</span></span>

   [!div class="mx-imgBorder"]
   <span data-ttu-id="1625c-123">![Преобразуване на ДН в дата](media/ecommerce-dob-date.PNG "трансформира датата на раждане в дата")</span><span class="sxs-lookup"><span data-stu-id="1625c-123">![Transform DoB to Date](media/ecommerce-dob-date.PNG "transform date of birth to date")</span></span>

1. <span data-ttu-id="1625c-124">В полето „Име“ в десния прозорец преименувайте вашия източник на данни от **Запитване** на **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="1625c-124">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="1625c-125">Запишете източника на данни.</span><span class="sxs-lookup"><span data-stu-id="1625c-125">Save the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="1625c-126">Поглъщайте клиентски данни от схема за лоялност</span><span class="sxs-lookup"><span data-stu-id="1625c-126">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="1625c-127">Създайте име на източник на данни **LoyaltyScheme**, изберете опцията за импортиране и изберете конектора **Текст/CSV**.</span><span class="sxs-lookup"><span data-stu-id="1625c-127">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="1625c-128">Въведете URL адреса за контакти за електронна търговия https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="1625c-128">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="1625c-129">Докато редактирате данните, изберете **Трансформирайте** и тогава **Използвайте първия ред за заглавки**.</span><span class="sxs-lookup"><span data-stu-id="1625c-129">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="1625c-130">Актуализирайте типа данни за колоните, изброени по-долу:</span><span class="sxs-lookup"><span data-stu-id="1625c-130">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="1625c-131">**DateOfBirth**: Дата</span><span class="sxs-lookup"><span data-stu-id="1625c-131">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="1625c-132">**RewardsPoints**: Цяло число</span><span class="sxs-lookup"><span data-stu-id="1625c-132">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="1625c-133">**CreatedOn**: Дата/час</span><span class="sxs-lookup"><span data-stu-id="1625c-133">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="1625c-134">В полето „Име“ в десния прозорец преименувайте вашия източник на данни от **Запитване** на **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="1625c-134">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="1625c-135">Запишете източника на данни.</span><span class="sxs-lookup"><span data-stu-id="1625c-135">Save the data source.</span></span>

### <a name="ingest-subscription-information"></a><span data-ttu-id="1625c-136">Поглъщане на информация за синхронизиране</span><span class="sxs-lookup"><span data-stu-id="1625c-136">Ingest subscription information</span></span>

1. <span data-ttu-id="1625c-137">Създайте име на източник на данни **SubscriptionHistory**, изберете опцията за импортиране и изберете конектора **Текст/CSV**.</span><span class="sxs-lookup"><span data-stu-id="1625c-137">Create a data source named **SubscriptionHistory**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="1625c-138">Въведете URL адреса за контакти за електронна търговия https://aka.ms/ciadchurnsubscriptionhistory.</span><span class="sxs-lookup"><span data-stu-id="1625c-138">Enter the URL for eCommerce contacts https://aka.ms/ciadchurnsubscriptionhistory.</span></span>

1. <span data-ttu-id="1625c-139">Докато редактирате данните, изберете **Трансформирайте** и тогава **Използвайте първия ред за заглавки**.</span><span class="sxs-lookup"><span data-stu-id="1625c-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="1625c-140">Актуализирайте типа данни за колоните, изброени по-долу:</span><span class="sxs-lookup"><span data-stu-id="1625c-140">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="1625c-141">**SubscriptioID**: Цяло число</span><span class="sxs-lookup"><span data-stu-id="1625c-141">**SubscriptioID**: Whole Number</span></span>
   - <span data-ttu-id="1625c-142">**SubscriptionAmount**: Валута</span><span class="sxs-lookup"><span data-stu-id="1625c-142">**SubscriptionAmount**: Currency</span></span>
   - <span data-ttu-id="1625c-143">**SubscriptionEndDate**: Дата/час</span><span class="sxs-lookup"><span data-stu-id="1625c-143">**SubscriptionEndDate**: Date/Time</span></span>
   - <span data-ttu-id="1625c-144">**SubscriptionStartDate**: Дата/час</span><span class="sxs-lookup"><span data-stu-id="1625c-144">**SubscriptionStartDate**: Date/Time</span></span>
   - <span data-ttu-id="1625c-145">**TransactionDate**: Дата/час</span><span class="sxs-lookup"><span data-stu-id="1625c-145">**TransactionDate**: Date/Time</span></span>
   - <span data-ttu-id="1625c-146">**IsRecurring**: Вярно/невярно</span><span class="sxs-lookup"><span data-stu-id="1625c-146">**IsRecurring**: True/False</span></span>
   - <span data-ttu-id="1625c-147">**Is_auto_renew**: Вярно/невярно</span><span class="sxs-lookup"><span data-stu-id="1625c-147">**Is_auto_renew**: True/False</span></span>
   - <span data-ttu-id="1625c-148">**RecurringFrequencyInMonths**: Цяло число</span><span class="sxs-lookup"><span data-stu-id="1625c-148">**RecurringFrequencyInMonths**: Whole Number</span></span>

1. <span data-ttu-id="1625c-149">В полето „Име“ в десния прозорец преименувайте вашия източник на данни от **Запитване** на **SubscriptionHistory**.</span><span class="sxs-lookup"><span data-stu-id="1625c-149">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **SubscriptionHistory**.</span></span>

1. <span data-ttu-id="1625c-150">Запишете източника на данни.</span><span class="sxs-lookup"><span data-stu-id="1625c-150">Save the data source.</span></span>

### <a name="ingest-customer-data-from-website-reviews"></a><span data-ttu-id="1625c-151">Поглъщайте данни за клиенти от рецензии на уебсайтове</span><span class="sxs-lookup"><span data-stu-id="1625c-151">Ingest customer data from website reviews</span></span>

1. <span data-ttu-id="1625c-152">Създайте име на източник на данни **Уеб сайт**, изберете опцията за импортиране и изберете конектора **Текст/CSV**.</span><span class="sxs-lookup"><span data-stu-id="1625c-152">Create a data source named **Website**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="1625c-153">Въведете URL адреса за контакти за електронна търговия https://aka.ms/ciadclasswebsite.</span><span class="sxs-lookup"><span data-stu-id="1625c-153">Enter the URL for eCommerce contacts https://aka.ms/ciadclasswebsite.</span></span>

1. <span data-ttu-id="1625c-154">Докато редактирате данните, изберете **Трансформирайте** и тогава **Използвайте първия ред за заглавки**.</span><span class="sxs-lookup"><span data-stu-id="1625c-154">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="1625c-155">Актуализирайте типа данни за колоните, изброени по-долу:</span><span class="sxs-lookup"><span data-stu-id="1625c-155">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="1625c-156">**ReviewRating**: Средна оценка</span><span class="sxs-lookup"><span data-stu-id="1625c-156">**ReviewRating**: Whole Number</span></span>
   - <span data-ttu-id="1625c-157">**ReviewDate**: Дата</span><span class="sxs-lookup"><span data-stu-id="1625c-157">**ReviewDate**: Date</span></span>

1. <span data-ttu-id="1625c-158">В полето „Име“ в десния прозорец преименувайте вашия източник на данни от **Запитване** на **webReviews**.</span><span class="sxs-lookup"><span data-stu-id="1625c-158">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **webReviews**.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="1625c-159">Задача 2 – Обединяване на данни</span><span class="sxs-lookup"><span data-stu-id="1625c-159">Task 2 - Data unification</span></span>

<span data-ttu-id="1625c-160">След поглъщането на данните сега започваме процеса **Нанасяне, Съпоставяне, Обединяване** за създаване на единен потребителски профил.</span><span class="sxs-lookup"><span data-stu-id="1625c-160">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="1625c-161">За повече информация вж. [Унифициране на данни](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="1625c-161">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="1625c-162">Картова</span><span class="sxs-lookup"><span data-stu-id="1625c-162">Map</span></span>

1. <span data-ttu-id="1625c-163">След поглъщането на данните, картографирайте контактите от електронна търговия и данни за лоялност към често срещани типове данни.</span><span class="sxs-lookup"><span data-stu-id="1625c-163">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="1625c-164">Отидете на **Данни** > **Унифициране** > **Нанасяне**.</span><span class="sxs-lookup"><span data-stu-id="1625c-164">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="1625c-165">Изберете обектите, които представляват потребителския профил – **eCommerceContacts** и **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="1625c-165">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="обединява източниците на данни за електронна търговия и лоялност.":::

1. <span data-ttu-id="1625c-167">Изберете **ContactId** като първичен ключ за **eCommerceContacts** и **LoyaltyID** като първичен ключ за **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="1625c-167">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="Обединете LoyaltyId като първичен ключ.":::

### <a name="match"></a><span data-ttu-id="1625c-169">Съвпадение</span><span class="sxs-lookup"><span data-stu-id="1625c-169">Match</span></span>

1. <span data-ttu-id="1625c-170">Отидете на раздела **съвпадение** и изберете **Задаване на ред**.</span><span class="sxs-lookup"><span data-stu-id="1625c-170">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="1625c-171">В падащ списък **Основно**, изберете **eCommerceContacts : eCommerce** като първоизточник и включете всички записи.</span><span class="sxs-lookup"><span data-stu-id="1625c-171">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="1625c-172">В падащ списък **Обект 2**, изберете **loyCustomers : LoyaltyScheme** и включват всички записи.</span><span class="sxs-lookup"><span data-stu-id="1625c-172">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   :::image type="content" source="media/unify-match-order.PNG" alt-text="Унифицирайте съпоставянето на eCommerce и Лоялност.":::

1. <span data-ttu-id="1625c-174">Изберете **Създаване на ново правило**</span><span class="sxs-lookup"><span data-stu-id="1625c-174">Select **Create a new rule**</span></span>

1. <span data-ttu-id="1625c-175">Добавете първото си условие с помощта на FullName.</span><span class="sxs-lookup"><span data-stu-id="1625c-175">Add your first condition using FullName.</span></span>

   * <span data-ttu-id="1625c-176">За eCommerceContacts изберете **Пълно име** в падащото меню.</span><span class="sxs-lookup"><span data-stu-id="1625c-176">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="1625c-177">За loyCustomers изберете **Пълно име** в падащото меню.</span><span class="sxs-lookup"><span data-stu-id="1625c-177">For loyCustomers select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="1625c-178">Изберете **Нормализирайте** падащото меню и изберете **Тип (Телефон, Име, Адрес, ...)**.</span><span class="sxs-lookup"><span data-stu-id="1625c-178">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   * <span data-ttu-id="1625c-179">Задайте **Ниво на прецизност**: **Основен** и **Стойност**: **Високо**.</span><span class="sxs-lookup"><span data-stu-id="1625c-179">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="1625c-180">Въведете името **Пълно име, имейл** за новото правило.</span><span class="sxs-lookup"><span data-stu-id="1625c-180">Enter the name **FullName, Email** for the new rule.</span></span>

   * <span data-ttu-id="1625c-181">Добавете второ условие за имейл адрес, като изберете **Добавяне на условие**</span><span class="sxs-lookup"><span data-stu-id="1625c-181">Add a second condition for email address by selecting **Add Condition**</span></span>
   * <span data-ttu-id="1625c-182">За обект eCommerceContacts изберете **Електронна поща** в падащо меню.</span><span class="sxs-lookup"><span data-stu-id="1625c-182">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   * <span data-ttu-id="1625c-183">За обект loyCustomers изберете **Електронна поща** в падащо меню.</span><span class="sxs-lookup"><span data-stu-id="1625c-183">For entity loyCustomers, choose **EMail** in the drop-down.</span></span> 
   * <span data-ttu-id="1625c-184">Оставете Нормализиране празно.</span><span class="sxs-lookup"><span data-stu-id="1625c-184">Leave Normalize blank.</span></span> 
   * <span data-ttu-id="1625c-185">Задайте **Ниво на прецизност**: **Основен** и **Стойност**: **Високо**.</span><span class="sxs-lookup"><span data-stu-id="1625c-185">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="Обединете правилото за съвпадение за име и имейл.":::

7. <span data-ttu-id="1625c-187">Изберете **Записване** и **Изпълнение**.</span><span class="sxs-lookup"><span data-stu-id="1625c-187">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="1625c-188">Обедини</span><span class="sxs-lookup"><span data-stu-id="1625c-188">Merge</span></span>

1. <span data-ttu-id="1625c-189">Отидете на раздела **Обединяване**.</span><span class="sxs-lookup"><span data-stu-id="1625c-189">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="1625c-190">В **ContactId** за **loyCustomers** обект, променете показваното име на **ContactIdLOYALTY**, за да се разграничи от останалите погълнати лични документи.</span><span class="sxs-lookup"><span data-stu-id="1625c-190">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="преименувайте contactid от идентификатор за лоялност.":::

1. <span data-ttu-id="1625c-192">Изберете **Запазете** и **Изпълнение**, за да стартирате процеса на обединяване.</span><span class="sxs-lookup"><span data-stu-id="1625c-192">Select **Save** and **Run** to start the Merge Process.</span></span>


## <a name="task-3---configure-the-subscription-churn-prediction"></a><span data-ttu-id="1625c-193">Задача 3 - Конфигуриране на прогноза за оттегляне на абонаменти</span><span class="sxs-lookup"><span data-stu-id="1625c-193">Task 3 - Configure the subscription churn prediction</span></span>

<span data-ttu-id="1625c-194">С установените унифицирани клиентски профили вече можем да стартираме прогнозата за оттегляне на абонаменти.</span><span class="sxs-lookup"><span data-stu-id="1625c-194">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span> <span data-ttu-id="1625c-195">За подробни стъпки вижте [Прекъсване на прогнозата за абонамент (преглед)](predict-subscription-churn.md) статия.</span><span class="sxs-lookup"><span data-stu-id="1625c-195">For detailed steps, see the [Subscription churn prediction (preview)](predict-subscription-churn.md) article.</span></span> 

1. <span data-ttu-id="1625c-196">Отидете на **Разузнаване** > **Открийте** и изберете да използвате **Модел за отлив на клиенти**.</span><span class="sxs-lookup"><span data-stu-id="1625c-196">Go to **Intelligence** > **Discover** and select to use the **Customer churn model**.</span></span>

1. <span data-ttu-id="1625c-197">Изберете опцията **Абонамент** и изберете **Начало**.</span><span class="sxs-lookup"><span data-stu-id="1625c-197">Select the **Subscription** option and select **Get started**.</span></span>

1. <span data-ttu-id="1625c-198">Назовете модела **OOB Subscription Churn Prediction** и изходния обект **OOBSubscriptionChurnPrediction**.</span><span class="sxs-lookup"><span data-stu-id="1625c-198">Name the model **OOB Subscription Churn Prediction** and the output entity **OOBSubscriptionChurnPrediction**.</span></span>

1. <span data-ttu-id="1625c-199">Определете две условия за модела на оттегляне:</span><span class="sxs-lookup"><span data-stu-id="1625c-199">Define two conditions for the churn model:</span></span>

   * <span data-ttu-id="1625c-200">**Дни след приключване на абонамента**: **поне 60** дни.</span><span class="sxs-lookup"><span data-stu-id="1625c-200">**Days since subscription ended**: **at least 60** days.</span></span> <span data-ttu-id="1625c-201">Ако клиентът не е подновил абонамента си през този период след приключването на абонамента, се счита за оттеглен.</span><span class="sxs-lookup"><span data-stu-id="1625c-201">If a customer doesn't renew the subscription in this period after their subscription ended, they are considered churned.</span></span> 

   * <span data-ttu-id="1625c-202">**Определение за оттегляне**: **поне 93** дни.</span><span class="sxs-lookup"><span data-stu-id="1625c-202">**Churn definition**: **at least 93** days.</span></span> <span data-ttu-id="1625c-203">Продължителността, която моделът предвижда кои клиенти могат да отхвърлят.</span><span class="sxs-lookup"><span data-stu-id="1625c-203">The duration the model predict which customers might churn.</span></span> <span data-ttu-id="1625c-204">Колкото по-нататък в бъдещето изглеждате, толкова по-малко точни са резултатите.</span><span class="sxs-lookup"><span data-stu-id="1625c-204">The further in the future you look, the less precise the results.</span></span>

     :::image type="content" source="media/model-subs-levers.PNG" alt-text="Изберете определение за прозорец и оттегляне на прогноза за лостовете на модела.":::

1. <span data-ttu-id="1625c-206">Изберете **Добавяне на необходими данни** и изберете **Добавете данни** за история на абонамента.</span><span class="sxs-lookup"><span data-stu-id="1625c-206">Select **Add required data** and select **Add data** for subscription history.</span></span>

1. <span data-ttu-id="1625c-207">Добавете обект **Subscription : SubscriptionHistory** и нанесете полетата от eCommerce към съответните полета, изисквани от модела.</span><span class="sxs-lookup"><span data-stu-id="1625c-207">Add the **Subscription : SubscriptionHistory** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="1625c-208">Присъедини се към обекта **Subscription : SubscriptionHistory** с **eCommerceContacts : eCommerce**, назовете връзката **eCommerceSubscription**.</span><span class="sxs-lookup"><span data-stu-id="1625c-208">Join the **Subscription : SubscriptionHistory** entity with **eCommerceContacts : eCommerce**, name the relationship **eCommerceSubscription**.</span></span>

   :::image type="content" source="media/model-subscription-join.PNG" alt-text="Присъединете се към обекти на eCommerce.":::

1. <span data-ttu-id="1625c-210">Под „Дейности на клиент” добавете обект **webReviews : Website** и нанесете полетата от webReviews към съответните полета, изисквани от модела.</span><span class="sxs-lookup"><span data-stu-id="1625c-210">Under Customer Activities, add the **webReviews : Website** entity and map the fields from webReviews to the corresponding fields required by the model.</span></span> 
   - <span data-ttu-id="1625c-211">Основен ключ: ReviewId</span><span class="sxs-lookup"><span data-stu-id="1625c-211">Primary key: ReviewId</span></span>
   - <span data-ttu-id="1625c-212">Времево клеймо: ReviewDate</span><span class="sxs-lookup"><span data-stu-id="1625c-212">Timestamp: ReviewDate</span></span>
   - <span data-ttu-id="1625c-213">Събитие: ReviewRating</span><span class="sxs-lookup"><span data-stu-id="1625c-213">Event: ReviewRating</span></span>

1. <span data-ttu-id="1625c-214">Конфигурирайте дейност за рецензии на уебсайтове.</span><span class="sxs-lookup"><span data-stu-id="1625c-214">Configure an activity for website reviews.</span></span> <span data-ttu-id="1625c-215">Изберете дейността **Преглед** и присъединете към обекта **webReviews : Website** с **eCommerceContacts : eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="1625c-215">Select the activity **Review** and join the **webReviews : Website** entity with **eCommerceContacts : eCommerce**.</span></span>

1. <span data-ttu-id="1625c-216">Изберете **Напред**, за да зададете графика на модела.</span><span class="sxs-lookup"><span data-stu-id="1625c-216">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="1625c-217">Моделът трябва да тренира редовно, за да научи нови модели, когато има погълнати нови данни.</span><span class="sxs-lookup"><span data-stu-id="1625c-217">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="1625c-218">За този пример изберете **Месечно**.</span><span class="sxs-lookup"><span data-stu-id="1625c-218">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="1625c-219">След като прегледате всички подробности, изберете **Запазете и стартирайте**.</span><span class="sxs-lookup"><span data-stu-id="1625c-219">After reviewing all the details, select **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="1625c-220">Задача 4 - Преглед на резултатите от модела и обяснения</span><span class="sxs-lookup"><span data-stu-id="1625c-220">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="1625c-221">Нека моделът завърши обучението и точкуването на данните.</span><span class="sxs-lookup"><span data-stu-id="1625c-221">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="1625c-222">Вече можете да прегледате обясненията за модела на отбиване на абонамента.</span><span class="sxs-lookup"><span data-stu-id="1625c-222">You can now review the subscription churn model explanations.</span></span> <span data-ttu-id="1625c-223">За повече информация вижте [Прегледайте състоянието и резултатите на прогноза](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="1625c-223">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a><span data-ttu-id="1625c-224">Задача 5 - Създайте сегмент от клиенти с висок риск</span><span class="sxs-lookup"><span data-stu-id="1625c-224">Task 5 - Create a segment of high churn-risk customers</span></span>

<span data-ttu-id="1625c-225">Изпълнението на производствения модел създава нов обект, който можете да видите в **Данни** > **Обекти**.</span><span class="sxs-lookup"><span data-stu-id="1625c-225">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>   

<span data-ttu-id="1625c-226">Можете да създадете нов сегмент въз основа на обекта, създаден от модела.</span><span class="sxs-lookup"><span data-stu-id="1625c-226">You can create a new segment based on the entity created by the model.</span></span>

1.  <span data-ttu-id="1625c-227">Към **Сегменти**.</span><span class="sxs-lookup"><span data-stu-id="1625c-227">Go to **Segments**.</span></span> <span data-ttu-id="1625c-228">Изберете **Ново** и изберете **Създаване от** > **Разузнаване**.</span><span class="sxs-lookup"><span data-stu-id="1625c-228">Select **New** and choose **Create from** > **Intelligence**.</span></span> 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Създаване на сегмент с изхода на модела.":::

1. <span data-ttu-id="1625c-230">Изберете **OOBSubscriptionChurnPrediction** крайна точка и дефинирайте сегмента:</span><span class="sxs-lookup"><span data-stu-id="1625c-230">Select the **OOBSubscriptionChurnPrediction** endpoint and define the segment:</span></span> 
   - <span data-ttu-id="1625c-231">Поле: ChurnScore</span><span class="sxs-lookup"><span data-stu-id="1625c-231">Field: ChurnScore</span></span>
   - <span data-ttu-id="1625c-232">Оператор: по-голямо от</span><span class="sxs-lookup"><span data-stu-id="1625c-232">Operator: greater than</span></span>
   - <span data-ttu-id="1625c-233">Стойност: 0,6</span><span class="sxs-lookup"><span data-stu-id="1625c-233">Value: 0.6</span></span>
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Настройте сегмента за отбиване на абонамент.":::

<span data-ttu-id="1625c-235">Вече имате сегмент, който се актуализира динамично, който идентифицира клиенти с висок риск за този абонаментен бизнес.</span><span class="sxs-lookup"><span data-stu-id="1625c-235">You now have a segment that is dynamically updated which identifies high churn-risk customers for this subscription business.</span></span>

<span data-ttu-id="1625c-236">За повече информация вижте [Създаване и управление на сегменти](segments.md).</span><span class="sxs-lookup"><span data-stu-id="1625c-236">For more information, see [Create and manage segments](segments.md).</span></span>
