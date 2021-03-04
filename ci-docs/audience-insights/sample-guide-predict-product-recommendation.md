---
title: Примерно ръководство на прогноза за препоръки за продукти
description: Използвайте това примерно ръководство, за да изпробвате модела за прогноза за препоръка на продукти.
ms.date: 02/10/2021
ms.reviewer: digranad
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0ee873d9b7caa5f891cb2d5b8c665dec90ad0e59
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270468"
---
# <a name="product-recommendation-prediction-preview-sample-guide"></a><span data-ttu-id="4c16a-103">Примерно ръководство на прогноза (преглед) за препоръки за продукти</span><span class="sxs-lookup"><span data-stu-id="4c16a-103">Product recommendation prediction (preview) sample guide</span></span>

<span data-ttu-id="4c16a-104">Ще ви преведем от край до край през прогноза за препоръка на продукти, използвайки примерните данни, предоставени по-долу.</span><span class="sxs-lookup"><span data-stu-id="4c16a-104">We'll walk you through an end to end example of product recommendation prediction using the sample data provided below.</span></span>

## <a name="scenario"></a><span data-ttu-id="4c16a-105">Сценарий</span><span class="sxs-lookup"><span data-stu-id="4c16a-105">Scenario</span></span>

<span data-ttu-id="4c16a-106">Contoso е компания, която произвежда висококачествено кафе и кафе машини, които продават чрез уебсайта си Contoso Coffee.</span><span class="sxs-lookup"><span data-stu-id="4c16a-106">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="4c16a-107">Целта им е да разберат кои продукти трябва да препоръчат на своите повтарящи се клиенти.</span><span class="sxs-lookup"><span data-stu-id="4c16a-107">Their goal is to understand which products should they recommend to their recurring customers.</span></span> <span data-ttu-id="4c16a-108">Като знаете за кои клиенти има по-голяма **вероятност да закупят**, може да им помогне да спестят маркетингови усилия, като се фокусират върху конкретни елементи.</span><span class="sxs-lookup"><span data-stu-id="4c16a-108">Knowing what customers are more **likely to purchase**, can help them save marketing efforts by focusing on specific items.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4c16a-109">Предварителни изисквания</span><span class="sxs-lookup"><span data-stu-id="4c16a-109">Prerequisites</span></span>

- <span data-ttu-id="4c16a-110">Поне [Разрешения на сътрудник](permissions.md) в Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="4c16a-110">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="4c16a-111">Препоръчваме ви да изпълните следните стъпки [в нова среда](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="4c16a-111">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="4c16a-112">Задача 1 - Поглъщане на данни</span><span class="sxs-lookup"><span data-stu-id="4c16a-112">Task 1 - Ingest data</span></span>

<span data-ttu-id="4c16a-113">Прегледайте статиите [за поглъщане на данни](data-sources.md) и [импортиране на източници на данни с помощта на конектори на Power Query](connect-power-query.md) конкретно.</span><span class="sxs-lookup"><span data-stu-id="4c16a-113">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="4c16a-114">Следващата информация предполага, че сте се запознали с поглъщането на данни като цяло.</span><span class="sxs-lookup"><span data-stu-id="4c16a-114">The following information assumes you familiarized with ingesting data in general.</span></span>

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="4c16a-115">Поглъщайте клиентски данни от платформата за електронна търговия</span><span class="sxs-lookup"><span data-stu-id="4c16a-115">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="4c16a-116">Създайте име на източник на данни **електронна търговия**, изберете опцията за импортиране и изберете конектора **Текст/CSV**.</span><span class="sxs-lookup"><span data-stu-id="4c16a-116">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="4c16a-117">Въведете URL адреса за контакти за електронна търговия https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="4c16a-117">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="4c16a-118">Докато редактирате данните, изберете **Трансформирайте** и тогава **Използвайте първия ред за заглавки**.</span><span class="sxs-lookup"><span data-stu-id="4c16a-118">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="4c16a-119">Актуализирайте типа данни за колоните, изброени по-долу:</span><span class="sxs-lookup"><span data-stu-id="4c16a-119">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="4c16a-120">**DateOfBirth**: Дата</span><span class="sxs-lookup"><span data-stu-id="4c16a-120">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="4c16a-121">**CreatedOn**: Дата/час/зона</span><span class="sxs-lookup"><span data-stu-id="4c16a-121">**CreatedOn**: Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Трансформиране на датата на раждане в дата.":::

5. <span data-ttu-id="4c16a-123">В полето „Име“ в десния прозорец преименувайте вашия източник на данни от **Запитване** на **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="4c16a-123">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

6. <span data-ttu-id="4c16a-124">**Запишете** източника на данни.</span><span class="sxs-lookup"><span data-stu-id="4c16a-124">**Save** the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="4c16a-125">Поглъщайте данни за онлайн покупки</span><span class="sxs-lookup"><span data-stu-id="4c16a-125">Ingest online purchase data</span></span>

1. <span data-ttu-id="4c16a-126">Добавете друг набор от данни към същия източник на данни на **eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="4c16a-126">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="4c16a-127">Изберете отново съединител **Текст/CSV**.</span><span class="sxs-lookup"><span data-stu-id="4c16a-127">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="4c16a-128">Въведете URL адреса за данните за **Онлайн покупки** https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="4c16a-128">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="4c16a-129">Докато редактирате данните, изберете **Трансформирайте** и тогава **Използвайте първия ред за заглавки**.</span><span class="sxs-lookup"><span data-stu-id="4c16a-129">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="4c16a-130">Актуализирайте типа данни за колоните, изброени по-долу:</span><span class="sxs-lookup"><span data-stu-id="4c16a-130">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="4c16a-131">**PurchasedOn**: Дата/час</span><span class="sxs-lookup"><span data-stu-id="4c16a-131">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="4c16a-132">**TotalPrice**: Валута</span><span class="sxs-lookup"><span data-stu-id="4c16a-132">**TotalPrice**: Currency</span></span>

1. <span data-ttu-id="4c16a-133">В полето **Име** в страничния прозорец преименувайте вашия източник на данни от **Заявка** на **eCommercePurchases**.</span><span class="sxs-lookup"><span data-stu-id="4c16a-133">In the **Name** field on the side pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="4c16a-134">Запишете източника на данни.</span><span class="sxs-lookup"><span data-stu-id="4c16a-134">Save the data source.</span></span>


### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="4c16a-135">Поглъщайте клиентски данни от схема за лоялност</span><span class="sxs-lookup"><span data-stu-id="4c16a-135">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="4c16a-136">Създайте име на източник на данни **LoyaltyScheme**, изберете опцията за импортиране и изберете конектора **Текст/CSV**.</span><span class="sxs-lookup"><span data-stu-id="4c16a-136">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="4c16a-137">Въведете URL адреса за контакти за електронна търговия https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="4c16a-137">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="4c16a-138">Докато редактирате данните, изберете **Трансформирайте** и тогава **Използвайте първия ред за заглавки**.</span><span class="sxs-lookup"><span data-stu-id="4c16a-138">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="4c16a-139">Актуализирайте типа данни за колоните, изброени по-долу:</span><span class="sxs-lookup"><span data-stu-id="4c16a-139">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="4c16a-140">**DateOfBirth**: Дата</span><span class="sxs-lookup"><span data-stu-id="4c16a-140">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="4c16a-141">**RewardsPoints**: Цяло число</span><span class="sxs-lookup"><span data-stu-id="4c16a-141">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="4c16a-142">**CreatedOn**: Дата/час</span><span class="sxs-lookup"><span data-stu-id="4c16a-142">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="4c16a-143">В полето **Име** в десния прозорец преименувайте вашия източник на данни от **заявка** на **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="4c16a-143">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="4c16a-144">Запишете източника на данни.</span><span class="sxs-lookup"><span data-stu-id="4c16a-144">Save the data source.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="4c16a-145">Задача 2 – Обединяване на данни</span><span class="sxs-lookup"><span data-stu-id="4c16a-145">Task 2 - Data unification</span></span>

<span data-ttu-id="4c16a-146">След поглъщането на данните сега започваме процеса **Нанасяне, Съпоставяне, Обединяване** за създаване на единен потребителски профил.</span><span class="sxs-lookup"><span data-stu-id="4c16a-146">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="4c16a-147">За повече информация вж. [Унифициране на данни](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="4c16a-147">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="4c16a-148">Картова</span><span class="sxs-lookup"><span data-stu-id="4c16a-148">Map</span></span>

1. <span data-ttu-id="4c16a-149">След поглъщането на данните, картографирайте контактите от електронна търговия и данни за лоялност към често срещани типове данни.</span><span class="sxs-lookup"><span data-stu-id="4c16a-149">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="4c16a-150">Отидете на **Данни** > **Унифициране** > **Нанасяне**.</span><span class="sxs-lookup"><span data-stu-id="4c16a-150">Go to **Data** > **Unify** > **Map**.</span></span>

2. <span data-ttu-id="4c16a-151">Изберете обектите, които представляват потребителския профил – **eCommerceContacts** и **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="4c16a-151">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span>

   ![обединява източниците на данни за електронна търговия и лоялност.](media/unify-ecommerce-loyalty.png)

3. <span data-ttu-id="4c16a-153">Изберете **ContactId** като първичен ключ за **eCommerceContacts** и **LoyaltyID** като първичен ключ за **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="4c16a-153">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   ![Обединете LoyaltyId като първичен ключ.](media/unify-loyaltyid.png)

### <a name="match"></a><span data-ttu-id="4c16a-155">Съвпадение</span><span class="sxs-lookup"><span data-stu-id="4c16a-155">Match</span></span>

1. <span data-ttu-id="4c16a-156">Отидете на раздела **съвпадение** и изберете **Задаване на ред**.</span><span class="sxs-lookup"><span data-stu-id="4c16a-156">Go to the **Match** tab and select **Set Order**.</span></span>

2. <span data-ttu-id="4c16a-157">В падащ списък **Основно**, изберете **eCommerceContacts : eCommerce** като първоизточник и включете всички записи.</span><span class="sxs-lookup"><span data-stu-id="4c16a-157">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

3. <span data-ttu-id="4c16a-158">В падащ списък **Обект 2**, изберете **loyCustomers : LoyaltyScheme** и включват всички записи.</span><span class="sxs-lookup"><span data-stu-id="4c16a-158">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   ![Унифицирайте съпоставянето на eCommerce и Лоялност.](media/unify-match-order.png)

4. <span data-ttu-id="4c16a-160">Изберете **Създаване на ново правило**</span><span class="sxs-lookup"><span data-stu-id="4c16a-160">Select **Create a new rule**</span></span>

5. <span data-ttu-id="4c16a-161">Добавете първото си условие с помощта на FullName.</span><span class="sxs-lookup"><span data-stu-id="4c16a-161">Add your first condition using FullName.</span></span>

   - <span data-ttu-id="4c16a-162">За eCommerceContacts изберете **Пълно име** в падащото меню.</span><span class="sxs-lookup"><span data-stu-id="4c16a-162">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="4c16a-163">За loyCustomers изберете **Пълно име** в падащото меню.</span><span class="sxs-lookup"><span data-stu-id="4c16a-163">For loyCustomers select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="4c16a-164">Изберете **Нормализирайте** падащото меню и изберете **Тип (Телефон, Име, Адрес, ...)**.</span><span class="sxs-lookup"><span data-stu-id="4c16a-164">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   - <span data-ttu-id="4c16a-165">Задайте **Ниво на прецизност**: **Основен** и **Стойност**: **Високо**.</span><span class="sxs-lookup"><span data-stu-id="4c16a-165">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

6. <span data-ttu-id="4c16a-166">Въведете името **Пълно име, имейл** за новото правило.</span><span class="sxs-lookup"><span data-stu-id="4c16a-166">Enter the name **FullName, Email** for the new rule.</span></span>

   - <span data-ttu-id="4c16a-167">Добавете второ условие за имейл адрес, като изберете **Добавяне на условие**</span><span class="sxs-lookup"><span data-stu-id="4c16a-167">Add a second condition for email address by selecting **Add Condition**</span></span>
   - <span data-ttu-id="4c16a-168">За обект eCommerceContacts изберете **Електронна поща** в падащо меню.</span><span class="sxs-lookup"><span data-stu-id="4c16a-168">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   - <span data-ttu-id="4c16a-169">За обект loyCustomers изберете **Електронна поща** в падащо меню.</span><span class="sxs-lookup"><span data-stu-id="4c16a-169">For entity loyCustomers, choose **EMail** in the drop-down.</span></span>
   - <span data-ttu-id="4c16a-170">Оставете Нормализиране празно.</span><span class="sxs-lookup"><span data-stu-id="4c16a-170">Leave Normalize blank.</span></span>
   - <span data-ttu-id="4c16a-171">Задайте **Ниво на прецизност**: **Основен** и **Стойност**: **Високо**.</span><span class="sxs-lookup"><span data-stu-id="4c16a-171">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   ![Обединете правилото за съвпадение за име и имейл.](media/unify-match-rule.png)

7. <span data-ttu-id="4c16a-173">Изберете **Записване** и **Изпълнение**.</span><span class="sxs-lookup"><span data-stu-id="4c16a-173">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="4c16a-174">Обедини</span><span class="sxs-lookup"><span data-stu-id="4c16a-174">Merge</span></span>

1. <span data-ttu-id="4c16a-175">Отидете на раздела **Обединяване**.</span><span class="sxs-lookup"><span data-stu-id="4c16a-175">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="4c16a-176">В **ContactId** за **loyCustomers** обект, променете показваното име на **ContactIdLOYALTY**, за да се разграничи от останалите погълнати лични документи.</span><span class="sxs-lookup"><span data-stu-id="4c16a-176">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   ![преименувайте contactid от идентификатор за лоялност.](media/unify-merge-contactid.png)

1. <span data-ttu-id="4c16a-178">Изберете **Запазете** и **Изпълнение**, за да стартирате процеса на обединяване.</span><span class="sxs-lookup"><span data-stu-id="4c16a-178">Select **Save** and **Run** to start the Merge Process.</span></span>

## <a name="task-3---configure-product-recommendation-prediction"></a><span data-ttu-id="4c16a-179">Задача 3 - Конфигуриране на препоръка за продукт прогноза</span><span class="sxs-lookup"><span data-stu-id="4c16a-179">Task 3 - Configure product recommendation prediction</span></span>

<span data-ttu-id="4c16a-180">С установените унифицирани клиентски профили вече можем да стартираме прогнозата за оттегляне на абонаменти.</span><span class="sxs-lookup"><span data-stu-id="4c16a-180">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span>

1. <span data-ttu-id="4c16a-181">Отидете на **разузнаване** > **прогноза** изберете **Препоръка за продукти**.</span><span class="sxs-lookup"><span data-stu-id="4c16a-181">Go to **Intelligence** > **Prediction** choose **Product recommendation**.</span></span>

1. <span data-ttu-id="4c16a-182">Изберете **Първи стъпки**.</span><span class="sxs-lookup"><span data-stu-id="4c16a-182">Select **Get started**.</span></span>

1. <span data-ttu-id="4c16a-183">Назовете модела **OOB Модел за препоръка на продукти прогноза** и изходния обект **OOBProductRecommendationModelPrediction**.</span><span class="sxs-lookup"><span data-stu-id="4c16a-183">Name the model **OOB Product Recommendation Model Prediction** and the output entity **OOBProductRecommendationModelPrediction**.</span></span>

1. <span data-ttu-id="4c16a-184">Определете три условия за модела:</span><span class="sxs-lookup"><span data-stu-id="4c16a-184">Define three conditions for the model:</span></span>

   - <span data-ttu-id="4c16a-185">**Брой продукти**: Задайте тази стойност на **5**.</span><span class="sxs-lookup"><span data-stu-id="4c16a-185">**Number of products**: Set this value to **5**.</span></span> <span data-ttu-id="4c16a-186">Тази настройка определя колко продукти искате да препоръчате на клиентите си.</span><span class="sxs-lookup"><span data-stu-id="4c16a-186">This setting defines how many products you want to recommend to your customers.</span></span>

   - <span data-ttu-id="4c16a-187">**Предложете продукти, които клиентите са закупили наскоро?**: Изберете **Да**, за да посочите, че искате да включите продукти в препоръката, която клиентите ви са закупили преди.</span><span class="sxs-lookup"><span data-stu-id="4c16a-187">**Suggest products customers have recently purchased?**: Select **Yes** to indicate that you want to include products in the recommendation that your customers have purchased before.</span></span>

   - <span data-ttu-id="4c16a-188">**Прозорец за поглед назад:** Изберете поне **365 дни**.</span><span class="sxs-lookup"><span data-stu-id="4c16a-188">**Look back window:** Select at least **365 days**.</span></span> <span data-ttu-id="4c16a-189">Тази настройка определя колко далеч ще погледне моделът назад в дейността на клиента, който да се използва като входящи данни за препоръките.</span><span class="sxs-lookup"><span data-stu-id="4c16a-189">This setting defines how far the model will look back at the customer's activity to use it as input to their recommendations.</span></span>
   
   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Предпочитания на модел за модел на препоръка на продукт.":::

1. <span data-ttu-id="4c16a-191">Изберете **Задължителни данни** и изберете **Добавете данни** за хронология на покупка.</span><span class="sxs-lookup"><span data-stu-id="4c16a-191">Select **Required data** and select **Add data** for purchase history.</span></span>

1. <span data-ttu-id="4c16a-192">Добавете обект **eCommercePurchases : eCommerce** обект и картографирайте полетата от eCommerce към съответните полета, изисквани от модела.</span><span class="sxs-lookup"><span data-stu-id="4c16a-192">Add the **eCommercePurchases : eCommerce** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="4c16a-193">Присъединете се към обекта **eCommercePurchases : eCommerce** с **eCommerceContacts : eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="4c16a-193">Join the **eCommercePurchases : eCommerce** entity with **eCommerceContacts : eCommerce**.</span></span>

   ![Присъединете се към обекти на eCommerce.](media/model-purchase-join.png)

1. <span data-ttu-id="4c16a-195">Изберете **Напред**, за да зададете графика на модела.</span><span class="sxs-lookup"><span data-stu-id="4c16a-195">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="4c16a-196">Моделът трябва да тренира редовно, за да научи нови модели, когато има погълнати нови данни.</span><span class="sxs-lookup"><span data-stu-id="4c16a-196">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="4c16a-197">За този пример изберете **Месечно**.</span><span class="sxs-lookup"><span data-stu-id="4c16a-197">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="4c16a-198">След като прегледате всички подробности, изберете **Запазете и стартирайте**.</span><span class="sxs-lookup"><span data-stu-id="4c16a-198">After reviewing all the details, select **Save and Run**.</span></span>


## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="4c16a-199">Задача 4 - Преглед на резултатите от модела и обяснения</span><span class="sxs-lookup"><span data-stu-id="4c16a-199">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="4c16a-200">Нека моделът завърши обучението и точкуването на данните.</span><span class="sxs-lookup"><span data-stu-id="4c16a-200">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="4c16a-201">Вече можете да прегледате обясненията за модела на препоръка на продукти.</span><span class="sxs-lookup"><span data-stu-id="4c16a-201">You can now review the product recommendation model explanations.</span></span> <span data-ttu-id="4c16a-202">За повече информация вижте [Прегледайте състоянието и резултатите на прогноза](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="4c16a-202">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-purchased-products"></a><span data-ttu-id="4c16a-203">Задача 5 - Създайте сегмент от високо закупени продукти</span><span class="sxs-lookup"><span data-stu-id="4c16a-203">Task 5 - Create a segment of high purchased products</span></span>

<span data-ttu-id="4c16a-204">Изпълнението на производствения модел създава нов обект, който можете да видите в **Данни** > **Обекти**.</span><span class="sxs-lookup"><span data-stu-id="4c16a-204">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>

<span data-ttu-id="4c16a-205">Можете да създадете нов сегмент въз основа на обекта, създаден от модела.</span><span class="sxs-lookup"><span data-stu-id="4c16a-205">You can create a new segment based on the entity created by the model.</span></span>

1. <span data-ttu-id="4c16a-206">Към **Сегменти**.</span><span class="sxs-lookup"><span data-stu-id="4c16a-206">Go to **Segments**.</span></span> <span data-ttu-id="4c16a-207">Изберете **Ново** и изберете **Създаване от** > **Разузнаване**.</span><span class="sxs-lookup"><span data-stu-id="4c16a-207">Select **New** and choose **Create from** > **Intelligence**.</span></span>

   ![Създаване на сегмент с изхода на модела.](media/segment-intelligence.png)

1. <span data-ttu-id="4c16a-209">Изберете **OOBProductRecommendationModelPrediction** крайна точка и дефинирайте сегмента:</span><span class="sxs-lookup"><span data-stu-id="4c16a-209">Select the **OOBProductRecommendationModelPrediction** endpoint and define the segment:</span></span>

   - <span data-ttu-id="4c16a-210">Поле: ИД на продукт</span><span class="sxs-lookup"><span data-stu-id="4c16a-210">Field: ProductID</span></span>
   - <span data-ttu-id="4c16a-211">Оператор: Стойност</span><span class="sxs-lookup"><span data-stu-id="4c16a-211">Operator: Value</span></span>
   - <span data-ttu-id="4c16a-212">Стойност: Изберете първите три идентификатора на продукта</span><span class="sxs-lookup"><span data-stu-id="4c16a-212">Value: Select the top three product IDs</span></span>

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="Създайте сегмент от резултатите от модела.":::

<span data-ttu-id="4c16a-214">Вече имате сегмент, който се актуализира динамично, който идентифицира клиентите, които са по-склонни да закупят трите най-препоръчани продукта</span><span class="sxs-lookup"><span data-stu-id="4c16a-214">You now have a segment that is dynamically updated which identifies the customers who are more willing to purchase the three most recommended products</span></span> 

<span data-ttu-id="4c16a-215">За повече информация вижте [Създаване и управление на сегменти](segments.md).</span><span class="sxs-lookup"><span data-stu-id="4c16a-215">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]