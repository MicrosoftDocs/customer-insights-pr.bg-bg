---
title: Примерно ръководство за прогноза за оттегляне на трансакции
description: Използвайте това примерно ръководство, за да изпробвате модела за прогноза за оттегляне на трансакции.
ms.date: 11/19/2020
ms.reviewer: digranad
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 81540ad2f490cf566f031233543b3cb6aa838033
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269777"
---
# <a name="transactional-churn-prediction-preview-sample-guide"></a><span data-ttu-id="a1702-103">Примерно ръководство за прогноза за оттегляне на трансакции (преглед)</span><span class="sxs-lookup"><span data-stu-id="a1702-103">Transactional churn prediction (preview) sample guide</span></span>

<span data-ttu-id="a1702-104">Това ръководство ще ви обясни пример от край до край на прогноза транзакционно оттегляне в Customer Insights, използвайки данните, предоставени по-долу.</span><span class="sxs-lookup"><span data-stu-id="a1702-104">This guide will walk you through an end to end example of Transactional Churn prediction in Customer Insights using the data provided below.</span></span> <span data-ttu-id="a1702-105">Всички данни, използвани в това ръководство, не са реални клиентски данни и са част от набора от данни Contoso, намерен в средата *Демонстрация* в рамките на вашия абонамент за Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="a1702-105">All data used in this guide is not real customer data and is part of the Contoso dataset found in the *Demo* environment within your Customer Insights Subscription.</span></span>

## <a name="scenario"></a><span data-ttu-id="a1702-106">Сценарий</span><span class="sxs-lookup"><span data-stu-id="a1702-106">Scenario</span></span>

<span data-ttu-id="a1702-107">Contoso е компания, която произвежда висококачествено кафе и кафе машини, които продават чрез уебсайта си Contoso Coffee.</span><span class="sxs-lookup"><span data-stu-id="a1702-107">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="a1702-108">Целта им е да знаят кои клиенти, които обикновено купуват редовно техните продукти, ще спрат да бъдат активни клиенти през следващите 60 дни.</span><span class="sxs-lookup"><span data-stu-id="a1702-108">Their goal is to know which customers who typically purchase their products on a regular basis, will stop being active customers in the next 60 days.</span></span> <span data-ttu-id="a1702-109">Знаейки кой е от техните клиенти **вероятно да се оттегли**, може да им помогне да спестят маркетингови усилия, като се съсредоточат върху запазването им.</span><span class="sxs-lookup"><span data-stu-id="a1702-109">Knowing which of their customers is **likely to churn**, can help them save marketing efforts by focusing on keeping them.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a1702-110">Предварителни изисквания</span><span class="sxs-lookup"><span data-stu-id="a1702-110">Prerequisites</span></span>

- <span data-ttu-id="a1702-111">Поне [Разрешения на сътрудник](permissions.md) в Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="a1702-111">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="a1702-112">Препоръчваме ви да изпълните следните стъпки [в нова среда](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="a1702-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="a1702-113">Задача 1 - Поглъщане на данни</span><span class="sxs-lookup"><span data-stu-id="a1702-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="a1702-114">Прегледайте статиите [за поглъщане на данни](data-sources.md) и [импортиране на източници на данни с помощта на конектори на Power Query](connect-power-query.md) конкретно.</span><span class="sxs-lookup"><span data-stu-id="a1702-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="a1702-115">Следващата информация предполага, че сте се запознали с поглъщането на данни като цяло.</span><span class="sxs-lookup"><span data-stu-id="a1702-115">The following information assumes you familiarized with ingesting data in general.</span></span> 

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="a1702-116">Поглъщайте клиентски данни от платформата за електронна търговия</span><span class="sxs-lookup"><span data-stu-id="a1702-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="a1702-117">Създайте име на източник на данни **електронна търговия**, изберете опцията за импортиране и изберете конектора **Текст/CSV**.</span><span class="sxs-lookup"><span data-stu-id="a1702-117">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="a1702-118">Въведете URL адреса за контакти за електронна търговия https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="a1702-118">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="a1702-119">Докато редактирате данните, изберете **Трансформирайте** и тогава **Използвайте първия ред за заглавки**.</span><span class="sxs-lookup"><span data-stu-id="a1702-119">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="a1702-120">Актуализирайте типа данни за колоните, изброени по-долу:</span><span class="sxs-lookup"><span data-stu-id="a1702-120">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="a1702-121">**DateOfBirth**: Дата</span><span class="sxs-lookup"><span data-stu-id="a1702-121">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="a1702-122">**CreatedOn**: Дата/час/зона</span><span class="sxs-lookup"><span data-stu-id="a1702-122">**CreatedOn**: Date/Time/Zone</span></span>

   [!div class="mx-imgBorder"]
   <span data-ttu-id="a1702-123">![Преобразуване на ДН в дата](media/ecommerce-dob-date.PNG "трансформира датата на раждане в дата")</span><span class="sxs-lookup"><span data-stu-id="a1702-123">![Transform DoB to Date](media/ecommerce-dob-date.PNG "transform date of birth to date")</span></span>

1. <span data-ttu-id="a1702-124">В полето **Име** в десния прозорец преименувайте вашия източник на данни от **заявка** на **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="a1702-124">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="a1702-125">Запишете източника на данни.</span><span class="sxs-lookup"><span data-stu-id="a1702-125">Save the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="a1702-126">Поглъщайте данни за онлайн покупки</span><span class="sxs-lookup"><span data-stu-id="a1702-126">Ingest online purchase data</span></span>

1. <span data-ttu-id="a1702-127">Добавете друг набор от данни към същия източник на данни на **eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="a1702-127">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="a1702-128">Изберете отново съединител **Текст/CSV**.</span><span class="sxs-lookup"><span data-stu-id="a1702-128">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="a1702-129">Въведете URL адреса за данните за **Онлайн покупки** https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="a1702-129">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="a1702-130">Докато редактирате данните, изберете **Трансформирайте** и тогава **Използвайте първия ред за заглавки**.</span><span class="sxs-lookup"><span data-stu-id="a1702-130">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="a1702-131">Актуализирайте типа данни за колоните, изброени по-долу:</span><span class="sxs-lookup"><span data-stu-id="a1702-131">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="a1702-132">**PurchasedOn**: Дата/час</span><span class="sxs-lookup"><span data-stu-id="a1702-132">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="a1702-133">**TotalPrice**: Валута</span><span class="sxs-lookup"><span data-stu-id="a1702-133">**TotalPrice**: Currency</span></span>
   
1. <span data-ttu-id="a1702-134">В полето **Име** в десния прозорец преименувайте вашия източник на данни от **Заявка** на **eCommercePurchases**.</span><span class="sxs-lookup"><span data-stu-id="a1702-134">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="a1702-135">Запишете източника на данни.</span><span class="sxs-lookup"><span data-stu-id="a1702-135">Save the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="a1702-136">Поглъщайте клиентски данни от схема за лоялност</span><span class="sxs-lookup"><span data-stu-id="a1702-136">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="a1702-137">Създайте име на източник на данни **LoyaltyScheme**, изберете опцията за импортиране и изберете конектора **Текст/CSV**.</span><span class="sxs-lookup"><span data-stu-id="a1702-137">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="a1702-138">Въведете URL адреса за контакти за електронна търговия https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="a1702-138">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="a1702-139">Докато редактирате данните, изберете **Трансформирайте** и тогава **Използвайте първия ред за заглавки**.</span><span class="sxs-lookup"><span data-stu-id="a1702-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="a1702-140">Актуализирайте типа данни за колоните, изброени по-долу:</span><span class="sxs-lookup"><span data-stu-id="a1702-140">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="a1702-141">**DateOfBirth**: Дата</span><span class="sxs-lookup"><span data-stu-id="a1702-141">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="a1702-142">**RewardsPoints**: Цяло число</span><span class="sxs-lookup"><span data-stu-id="a1702-142">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="a1702-143">**CreatedOn**: Дата/час</span><span class="sxs-lookup"><span data-stu-id="a1702-143">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="a1702-144">В полето **Име** в десния прозорец преименувайте вашия източник на данни от **заявка** на **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="a1702-144">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="a1702-145">Запишете източника на данни.</span><span class="sxs-lookup"><span data-stu-id="a1702-145">Save the data source.</span></span>


## <a name="task-2---data-unification"></a><span data-ttu-id="a1702-146">Задача 2 – Обединяване на данни</span><span class="sxs-lookup"><span data-stu-id="a1702-146">Task 2 - Data unification</span></span>

<span data-ttu-id="a1702-147">След поглъщането на данните сега започваме процеса **Нанасяне, Съпоставяне, Обединяване** за създаване на единен потребителски профил.</span><span class="sxs-lookup"><span data-stu-id="a1702-147">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="a1702-148">За повече информация вж. [Унифициране на данни](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="a1702-148">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="a1702-149">Картова</span><span class="sxs-lookup"><span data-stu-id="a1702-149">Map</span></span>

1. <span data-ttu-id="a1702-150">След поглъщането на данните, картографирайте контактите от електронна търговия и данни за лоялност към често срещани типове данни.</span><span class="sxs-lookup"><span data-stu-id="a1702-150">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="a1702-151">Отидете на **Данни** > **Унифициране** > **Нанасяне**.</span><span class="sxs-lookup"><span data-stu-id="a1702-151">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="a1702-152">Изберете обектите, които представляват потребителския профил – **eCommerceContacts** и **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="a1702-152">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="обединява източниците на данни за електронна търговия и лоялност.":::

1. <span data-ttu-id="a1702-154">Изберете **ContactId** като първичен ключ за **eCommerceContacts** и **LoyaltyID** като първичен ключ за **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="a1702-154">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="Обединете LoyaltyId като първичен ключ.":::

### <a name="match"></a><span data-ttu-id="a1702-156">Съвпадение</span><span class="sxs-lookup"><span data-stu-id="a1702-156">Match</span></span>

1. <span data-ttu-id="a1702-157">Отидете на раздела **съвпадение** и изберете **Задаване на ред**.</span><span class="sxs-lookup"><span data-stu-id="a1702-157">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="a1702-158">В падащ списък **Основно**, изберете **eCommerceContacts : eCommerce** като първоизточник и включете всички записи.</span><span class="sxs-lookup"><span data-stu-id="a1702-158">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="a1702-159">В падащ списък **Обект 2**, изберете **loyCustomers : LoyaltyScheme** и включват всички записи.</span><span class="sxs-lookup"><span data-stu-id="a1702-159">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   :::image type="content" source="media/unify-match-order.PNG" alt-text="Унифицирайте съпоставянето на eCommerce и Лоялност.":::

1. <span data-ttu-id="a1702-161">Изберете **Създаване на ново правило**</span><span class="sxs-lookup"><span data-stu-id="a1702-161">Select **Create a new rule**</span></span>

1. <span data-ttu-id="a1702-162">Добавете първото си условие с помощта на FullName.</span><span class="sxs-lookup"><span data-stu-id="a1702-162">Add your first condition using FullName.</span></span>

   * <span data-ttu-id="a1702-163">За eCommerceContacts изберете **Пълно име** в падащото меню.</span><span class="sxs-lookup"><span data-stu-id="a1702-163">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="a1702-164">За loyCustomers изберете **Пълно име** в падащото меню.</span><span class="sxs-lookup"><span data-stu-id="a1702-164">For loyCustomers select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="a1702-165">Изберете **Нормализирайте** падащото меню и изберете **Тип (Телефон, Име, Адрес, ...)**.</span><span class="sxs-lookup"><span data-stu-id="a1702-165">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   * <span data-ttu-id="a1702-166">Задайте **Ниво на прецизност**: **Основен** и **Стойност**: **Високо**.</span><span class="sxs-lookup"><span data-stu-id="a1702-166">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="a1702-167">Въведете името **Пълно име, имейл** за новото правило.</span><span class="sxs-lookup"><span data-stu-id="a1702-167">Enter the name **FullName, Email** for the new rule.</span></span>

   * <span data-ttu-id="a1702-168">Добавете второ условие за имейл адрес, като изберете **Добавяне на условие**</span><span class="sxs-lookup"><span data-stu-id="a1702-168">Add a second condition for email address by selecting **Add Condition**</span></span>
   * <span data-ttu-id="a1702-169">За обект eCommerceContacts изберете **Електронна поща** в падащо меню.</span><span class="sxs-lookup"><span data-stu-id="a1702-169">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   * <span data-ttu-id="a1702-170">За обект loyCustomers изберете **Електронна поща** в падащо меню.</span><span class="sxs-lookup"><span data-stu-id="a1702-170">For entity loyCustomers, choose **EMail** in the drop-down.</span></span> 
   * <span data-ttu-id="a1702-171">Оставете Нормализиране празно.</span><span class="sxs-lookup"><span data-stu-id="a1702-171">Leave Normalize blank.</span></span> 
   * <span data-ttu-id="a1702-172">Задайте **Ниво на прецизност**: **Основен** и **Стойност**: **Високо**.</span><span class="sxs-lookup"><span data-stu-id="a1702-172">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="Обединете правилото за съвпадение за име и имейл.":::

7. <span data-ttu-id="a1702-174">Изберете **Записване** и **Изпълнение**.</span><span class="sxs-lookup"><span data-stu-id="a1702-174">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="a1702-175">Обедини</span><span class="sxs-lookup"><span data-stu-id="a1702-175">Merge</span></span>

1. <span data-ttu-id="a1702-176">Отидете на раздела **Обединяване**.</span><span class="sxs-lookup"><span data-stu-id="a1702-176">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="a1702-177">В **ContactId** за **loyCustomers** обект, променете показваното име на **ContactIdLOYALTY**, за да се разграничи от останалите погълнати лични документи.</span><span class="sxs-lookup"><span data-stu-id="a1702-177">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="преименувайте contactid от идентификатор за лоялност.":::

1. <span data-ttu-id="a1702-179">Изберете **Запазете** и **Изпълнение**, за да стартирате процеса на обединяване.</span><span class="sxs-lookup"><span data-stu-id="a1702-179">Select **Save** and **Run** to start the Merge Process.</span></span>



## <a name="task-3---configure-transaction-churn-prediction"></a><span data-ttu-id="a1702-180">Задача 3 - Конфигуриране на прогноза за оттегляне на трансакции</span><span class="sxs-lookup"><span data-stu-id="a1702-180">Task 3 - Configure transaction churn prediction</span></span>

<span data-ttu-id="a1702-181">С установените унифицирани клиентски профили вече можем да стартираме прогнозата за оттегляне на абонаменти.</span><span class="sxs-lookup"><span data-stu-id="a1702-181">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span> <span data-ttu-id="a1702-182">За подробни стъпки вижте [Прекъсване на прогнозата за абонамент (преглед)](predict-subscription-churn.md) статия.</span><span class="sxs-lookup"><span data-stu-id="a1702-182">For detailed steps, see the [Subscription churn prediction (preview)](predict-subscription-churn.md) article.</span></span> 

1. <span data-ttu-id="a1702-183">Отидете на **Разузнаване** > **Открийте** и изберете да използвате **Модел за отлив на клиенти**.</span><span class="sxs-lookup"><span data-stu-id="a1702-183">Go to **Intelligence** > **Discover** and select to use the **Customer churn model**.</span></span>

1. <span data-ttu-id="a1702-184">Изберете **Транзакционна** опция и изберете **Начало**.</span><span class="sxs-lookup"><span data-stu-id="a1702-184">Select the **Transactional** option and select **Get started**.</span></span>

1. <span data-ttu-id="a1702-185">Назовете модела **OOB eCommerce Transaction Churn Prediction** и изходния обект **OOBeCommerceChurnPrediction**.</span><span class="sxs-lookup"><span data-stu-id="a1702-185">Name the model **OOB eCommerce Transaction Churn Prediction** and the output entity **OOBeCommerceChurnPrediction**.</span></span>

1. <span data-ttu-id="a1702-186">Определете две условия за модела на оттегляне:</span><span class="sxs-lookup"><span data-stu-id="a1702-186">Define two conditions for the churn model:</span></span>

   * <span data-ttu-id="a1702-187">**Прогноза прозорец**: **поне 60** дни.</span><span class="sxs-lookup"><span data-stu-id="a1702-187">**Prediction window**: **at least 60** days.</span></span> <span data-ttu-id="a1702-188">Тази настройка определя колко далеч в бъдещето искаме да предскажем отлив на клиентите.</span><span class="sxs-lookup"><span data-stu-id="a1702-188">This setting defines how far into the future do we want to predict customer churn.</span></span>

   * <span data-ttu-id="a1702-189">**Определение за оттегляне**: **поне 60** дни.</span><span class="sxs-lookup"><span data-stu-id="a1702-189">**Churn definition**: **at least 60** days.</span></span> <span data-ttu-id="a1702-190">Продължителността без покупка, след която клиентът се счита за изхвърлен.</span><span class="sxs-lookup"><span data-stu-id="a1702-190">The duration without purchase after which a customer is considered churned.</span></span>

     :::image type="content" source="media/model-levers.PNG" alt-text="Изберете определение за прозорец и оттегляне на прогноза за лостовете на модела.":::

1. <span data-ttu-id="a1702-192">Изберете **История на покупките (задължително)** и изберете **Добавете данни** за история на закупуване.</span><span class="sxs-lookup"><span data-stu-id="a1702-192">Select **Purchase History (required)** and select **Add data** for purchase history.</span></span>

1. <span data-ttu-id="a1702-193">Добавете обект **eCommercePurchases : eCommerce** обект и картографирайте полетата от eCommerce към съответните полета, изисквани от модела.</span><span class="sxs-lookup"><span data-stu-id="a1702-193">Add the **eCommercePurchases : eCommerce** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="a1702-194">Присъединете се към обекта **eCommercePurchases : eCommerce** с **eCommerceContacts : eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="a1702-194">Join the **eCommercePurchases : eCommerce** entity with **eCommerceContacts : eCommerce**.</span></span>

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="Присъединете се към обекти на eCommerce.":::

1. <span data-ttu-id="a1702-196">Изберете **Напред**, за да зададете графика на модела.</span><span class="sxs-lookup"><span data-stu-id="a1702-196">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="a1702-197">Моделът трябва да тренира редовно, за да научи нови модели, когато има погълнати нови данни.</span><span class="sxs-lookup"><span data-stu-id="a1702-197">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="a1702-198">За този пример изберете **Месечно**.</span><span class="sxs-lookup"><span data-stu-id="a1702-198">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="a1702-199">След като прегледате всички подробности, изберете **Запазете и стартирайте**.</span><span class="sxs-lookup"><span data-stu-id="a1702-199">After reviewing all the details, select **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="a1702-200">Задача 4 - Преглед на резултатите от модела и обяснения</span><span class="sxs-lookup"><span data-stu-id="a1702-200">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="a1702-201">Нека моделът завърши обучението и точкуването на данните.</span><span class="sxs-lookup"><span data-stu-id="a1702-201">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="a1702-202">Вече можете да прегледате обясненията за модела на отбиване на абонамента.</span><span class="sxs-lookup"><span data-stu-id="a1702-202">You can now review the subscription churn model explanations.</span></span> <span data-ttu-id="a1702-203">За повече информация вижте [Прегледайте състоянието и резултатите на прогноза](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="a1702-203">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a><span data-ttu-id="a1702-204">Задача 5 - Създайте сегмент от клиенти с висок риск</span><span class="sxs-lookup"><span data-stu-id="a1702-204">Task 5 - Create a segment of high churn-risk customers</span></span>

<span data-ttu-id="a1702-205">Изпълнението на производствения модел създава нов обект, който можете да видите в **Данни** > **Обекти**.</span><span class="sxs-lookup"><span data-stu-id="a1702-205">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>   

<span data-ttu-id="a1702-206">Можете да създадете нов сегмент въз основа на обекта, създаден от модела.</span><span class="sxs-lookup"><span data-stu-id="a1702-206">You can create a new segment based on the entity created by the model.</span></span>

1.  <span data-ttu-id="a1702-207">Към **Сегменти**.</span><span class="sxs-lookup"><span data-stu-id="a1702-207">Go to **Segments**.</span></span> <span data-ttu-id="a1702-208">Изберете **Ново** и изберете **Създаване от** > **Разузнаване**.</span><span class="sxs-lookup"><span data-stu-id="a1702-208">Select **New** and choose **Create from** > **Intelligence**.</span></span> 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Създаване на сегмент с изхода на модела.":::

1. <span data-ttu-id="a1702-210">Изберете **OOBSubscriptionChurnPrediction** крайна точка и дефинирайте сегмента:</span><span class="sxs-lookup"><span data-stu-id="a1702-210">Select the **OOBSubscriptionChurnPrediction** endpoint and define the segment:</span></span> 
   - <span data-ttu-id="a1702-211">Поле: ChurnScore</span><span class="sxs-lookup"><span data-stu-id="a1702-211">Field: ChurnScore</span></span>
   - <span data-ttu-id="a1702-212">Оператор: по-голямо от</span><span class="sxs-lookup"><span data-stu-id="a1702-212">Operator: greater than</span></span>
   - <span data-ttu-id="a1702-213">Стойност: 0,6</span><span class="sxs-lookup"><span data-stu-id="a1702-213">Value: 0.6</span></span>
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Настройте сегмента за отбиване на абонамент.":::

<span data-ttu-id="a1702-215">Вече имате сегмент, който се актуализира динамично, който идентифицира клиенти с висок риск за този абонаментен бизнес.</span><span class="sxs-lookup"><span data-stu-id="a1702-215">You now have a segment that is dynamically updated which identifies high churn-risk customers for this subscription business.</span></span>

<span data-ttu-id="a1702-216">За повече информация вижте [Създаване и управление на сегменти](segments.md).</span><span class="sxs-lookup"><span data-stu-id="a1702-216">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]