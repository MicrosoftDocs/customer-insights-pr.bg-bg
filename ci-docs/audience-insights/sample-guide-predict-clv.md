---
title: Примерно ръководство за прогноза за стойност на жизнен цикъл на клиент
description: Използвайте това примерно ръководство, за да изпробвате модела за прогноза за стойност на жизнен цикъл на клиент.
ms.date: 05/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: 73d294a285b4ad706bec7fe925c1daa0b839ddd6
ms.sourcegitcommit: 7b6189e47ed1f87e7ce35d40e4cf7a6730f31ef2
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 06/01/2021
ms.locfileid: "6129932"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a><span data-ttu-id="ddcee-103">Примерно ръководство за прогноза за стойност на жизнен цикъл на клиент (CLV)</span><span class="sxs-lookup"><span data-stu-id="ddcee-103">Customer lifetime value (CLV) prediction sample guide</span></span>

<span data-ttu-id="ddcee-104">Това ръководство ще ви обясни пример от край до край прогнозата за стойността на жизнен цикъл на клиента (CLV) прогноза в Customer Insights, използвайки примерни данни.</span><span class="sxs-lookup"><span data-stu-id="ddcee-104">This guide will walk you through an end to end example of Customer lifetime value (CLV) prediction in Customer Insights using sample data.</span></span>

## <a name="scenario"></a><span data-ttu-id="ddcee-105">Сценарий</span><span class="sxs-lookup"><span data-stu-id="ddcee-105">Scenario</span></span>

<span data-ttu-id="ddcee-106">Contoso е компания, която произвежда висококачествено кафе и кафе машини.</span><span class="sxs-lookup"><span data-stu-id="ddcee-106">Contoso is a company that produces high-quality coffee and coffee machines.</span></span> <span data-ttu-id="ddcee-107">Те продават продуктите чрез своя уеб сайт на Contoso Coffee.</span><span class="sxs-lookup"><span data-stu-id="ddcee-107">They sell the products through their Contoso Coffee website.</span></span> <span data-ttu-id="ddcee-108">Компанията иска да разбере стойността (приходите), която клиентите им могат да генерират през следващите 12 месеца.</span><span class="sxs-lookup"><span data-stu-id="ddcee-108">The company wants to understand the value (revenue) that their customers can generate in the next 12 months.</span></span> <span data-ttu-id="ddcee-109">Познаването на очакваната стойност на техните клиенти през следващите 12 месеца ще им помогне да насочат своите маркетингови усилия към клиенти с висока стойност.</span><span class="sxs-lookup"><span data-stu-id="ddcee-109">Knowing the expected value of their customers in the next 12 months will help them steer their marketing efforts on high value customers.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ddcee-110">Предварителни изисквания</span><span class="sxs-lookup"><span data-stu-id="ddcee-110">Prerequisites</span></span>

- <span data-ttu-id="ddcee-111">Поне [Разрешения за сътрудници](permissions.md) в прозренията на публиката.</span><span class="sxs-lookup"><span data-stu-id="ddcee-111">At least [Contributor permissions](permissions.md) in audience insights.</span></span>
- <span data-ttu-id="ddcee-112">Препоръчваме ви да изпълните следните стъпки [в нова среда](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="ddcee-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="ddcee-113">Задача 1 - Поглъщане на данни</span><span class="sxs-lookup"><span data-stu-id="ddcee-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="ddcee-114">Прегледайте статиите [за поглъщане на данни](data-sources.md) и [импортиране на източници на данни с помощта на конектори на Power Query](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="ddcee-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md).</span></span> <span data-ttu-id="ddcee-115">Следващата информация предполага, че сте се запознали с поглъщането на данни като цяло.</span><span class="sxs-lookup"><span data-stu-id="ddcee-115">The following information assumes you familiarized with ingesting data in general.</span></span>

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="ddcee-116">Поглъщайте клиентски данни от платформата за електронна търговия</span><span class="sxs-lookup"><span data-stu-id="ddcee-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="ddcee-117">Създайте име на източник на данни **електронна търговия**, изберете опцията за импортиране и изберете конектора **Текст/CSV**.</span><span class="sxs-lookup"><span data-stu-id="ddcee-117">Create a data source named  **eCommerce** , choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="ddcee-118">Въведете URL адреса за контакти за електронна търговия [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).</span><span class="sxs-lookup"><span data-stu-id="ddcee-118">Enter the URL for eCommerce contacts [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).</span></span>

1. <span data-ttu-id="ddcee-119">Докато редактирате данните, изберете **Трансформирайте** и тогава **Използвайте първия ред за заглавки**.</span><span class="sxs-lookup"><span data-stu-id="ddcee-119">While editing the data, select  **Transform**  and then  **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="ddcee-120">Актуализирайте типа данни за колоните, изброени по-долу:</span><span class="sxs-lookup"><span data-stu-id="ddcee-120">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="ddcee-121">**DateOfBirth**: Дата</span><span class="sxs-lookup"><span data-stu-id="ddcee-121">**DateOfBirth** : Date</span></span>
   - <span data-ttu-id="ddcee-122">**CreatedOn**: Дата/час/зона</span><span class="sxs-lookup"><span data-stu-id="ddcee-122">**CreatedOn** : Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Трансформиране на датата на раждане в дата.":::

1. <span data-ttu-id="ddcee-124">В полето „Име“ в десния прозорец преименувайте вашия източник на данни от **Запитване** на **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="ddcee-124">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="ddcee-125">**Запишете** източника на данни.</span><span class="sxs-lookup"><span data-stu-id="ddcee-125">**Save** the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="ddcee-126">Поглъщайте данни за онлайн покупки</span><span class="sxs-lookup"><span data-stu-id="ddcee-126">Ingest online purchase data</span></span>

1. <span data-ttu-id="ddcee-127">Добавете друг набор от данни към същия източник на данни на **eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="ddcee-127">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="ddcee-128">Изберете отново съединител **Текст/CSV**.</span><span class="sxs-lookup"><span data-stu-id="ddcee-128">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="ddcee-129">Въведете URL адреса за данните за **Онлайн покупки** https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="ddcee-129">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="ddcee-130">Докато редактирате данните, изберете **Трансформирайте** и тогава **Използвайте първия ред за заглавки**.</span><span class="sxs-lookup"><span data-stu-id="ddcee-130">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="ddcee-131">Актуализирайте типа данни за колоните, изброени по-долу:</span><span class="sxs-lookup"><span data-stu-id="ddcee-131">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="ddcee-132">**PurchasedOn**: Дата/час</span><span class="sxs-lookup"><span data-stu-id="ddcee-132">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="ddcee-133">**TotalPrice**: Валута</span><span class="sxs-lookup"><span data-stu-id="ddcee-133">**TotalPrice**: Currency</span></span>

1. <span data-ttu-id="ddcee-134">В полето **Име** в страничния прозорец преименувайте вашия източник на данни от **Заявка** на **eCommercePurchases**.</span><span class="sxs-lookup"><span data-stu-id="ddcee-134">In the **Name** field on the side pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="ddcee-135">**Запишете** източника на данни.</span><span class="sxs-lookup"><span data-stu-id="ddcee-135">**Save** the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="ddcee-136">Поглъщайте клиентски данни от схема за лоялност</span><span class="sxs-lookup"><span data-stu-id="ddcee-136">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="ddcee-137">Създайте име на източник на данни **LoyaltyScheme**, изберете опцията за импортиране и изберете конектора **Текст/CSV**.</span><span class="sxs-lookup"><span data-stu-id="ddcee-137">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="ddcee-138">Въведете URL адреса за контакти за електронна търговия https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="ddcee-138">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="ddcee-139">Докато редактирате данните, изберете **Трансформирайте** и тогава **Използвайте първия ред за заглавки**.</span><span class="sxs-lookup"><span data-stu-id="ddcee-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="ddcee-140">Актуализирайте типа данни за колоните, изброени по-долу:</span><span class="sxs-lookup"><span data-stu-id="ddcee-140">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="ddcee-141">**DateOfBirth**: Дата</span><span class="sxs-lookup"><span data-stu-id="ddcee-141">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="ddcee-142">**RewardsPoints**: Цяло число</span><span class="sxs-lookup"><span data-stu-id="ddcee-142">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="ddcee-143">**CreatedOn**: Дата/час</span><span class="sxs-lookup"><span data-stu-id="ddcee-143">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="ddcee-144">В полето **Име** в десния прозорец преименувайте вашия източник на данни от **заявка** на **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="ddcee-144">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="ddcee-145">**Запишете** източника на данни.</span><span class="sxs-lookup"><span data-stu-id="ddcee-145">**Save** the data source.</span></span>

### <a name="ingest-customer-data-from-website-reviews"></a><span data-ttu-id="ddcee-146">Поглъщайте данни за клиенти от рецензии на уебсайтове</span><span class="sxs-lookup"><span data-stu-id="ddcee-146">Ingest customer data from website reviews</span></span>

1. <span data-ttu-id="ddcee-147">Създайте име на източник на данни **Уеб сайт**, изберете опцията за импортиране и изберете конектора **Текст/CSV**.</span><span class="sxs-lookup"><span data-stu-id="ddcee-147">Create a data source named **Website**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="ddcee-148">Въведете URL адреса за контакти за електронна търговия https://aka.ms/CI-ILT/WebReviews.</span><span class="sxs-lookup"><span data-stu-id="ddcee-148">Enter the URL for eCommerce contacts https://aka.ms/CI-ILT/WebReviews.</span></span>

1. <span data-ttu-id="ddcee-149">Докато редактирате данните, изберете **Трансформирайте** и тогава **Използвайте първия ред за заглавки**.</span><span class="sxs-lookup"><span data-stu-id="ddcee-149">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="ddcee-150">Актуализирайте типа данни за колоните, изброени по-долу:</span><span class="sxs-lookup"><span data-stu-id="ddcee-150">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="ddcee-151">**ReviewRating**: Десетично число</span><span class="sxs-lookup"><span data-stu-id="ddcee-151">**ReviewRating**: Decimal number</span></span>
   - <span data-ttu-id="ddcee-152">**ReviewDate**: Дата</span><span class="sxs-lookup"><span data-stu-id="ddcee-152">**ReviewDate**: Date</span></span>

1. <span data-ttu-id="ddcee-153">В полето „Име“ в десния панел преименувайте вашия източник на данни от **заявка** на **Прегледи**.</span><span class="sxs-lookup"><span data-stu-id="ddcee-153">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **Reviews**.</span></span>

1. <span data-ttu-id="ddcee-154">**Запишете** източника на данни.</span><span class="sxs-lookup"><span data-stu-id="ddcee-154">**Save** the data source.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="ddcee-155">Задача 2 – Обединяване на данни</span><span class="sxs-lookup"><span data-stu-id="ddcee-155">Task 2 - Data unification</span></span>

<span data-ttu-id="ddcee-156">След като погълнем данните, сега започваме процеса на обединяване на данните, за да създадем единен клиентски профил.</span><span class="sxs-lookup"><span data-stu-id="ddcee-156">After ingesting the data, we now begin the data unification process to create a unified customer profile.</span></span> <span data-ttu-id="ddcee-157">За повече информация вж. [Унифициране на данни](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="ddcee-157">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="ddcee-158">Картова</span><span class="sxs-lookup"><span data-stu-id="ddcee-158">Map</span></span>

1. <span data-ttu-id="ddcee-159">След поглъщането на данните, картографирайте контактите от електронна търговия и данни за лоялност към често срещани типове данни.</span><span class="sxs-lookup"><span data-stu-id="ddcee-159">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="ddcee-160">Отидете на **Данни** > **Унифициране** > **Нанасяне**.</span><span class="sxs-lookup"><span data-stu-id="ddcee-160">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="ddcee-161">Изберете обектите, които представляват потребителския профил – **eCommerceContacts** и **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="ddcee-161">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> <span data-ttu-id="ddcee-162">След това изберете **Прилагане**.</span><span class="sxs-lookup"><span data-stu-id="ddcee-162">Then, select **Apply**.</span></span>

   ![обединява източниците на данни за електронна търговия и лоялност.](media/unify-ecommerce-loyalty.png)

1. <span data-ttu-id="ddcee-164">Изберете **ContactId** като първичен ключ за **eCommerceContacts** и **LoyaltyID** като първичен ключ за **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="ddcee-164">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   ![Обединете LoyaltyId като първичен ключ.](media/unify-loyaltyid.png)

1. <span data-ttu-id="ddcee-166">Изберете **Записване**.</span><span class="sxs-lookup"><span data-stu-id="ddcee-166">Select **Save**.</span></span>

### <a name="match"></a><span data-ttu-id="ddcee-167">Съвпадение</span><span class="sxs-lookup"><span data-stu-id="ddcee-167">Match</span></span>

1. <span data-ttu-id="ddcee-168">Отидете на раздела **съвпадение** и изберете **Задаване на ред**.</span><span class="sxs-lookup"><span data-stu-id="ddcee-168">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="ddcee-169">В падащ списък **Основно**, изберете **eCommerceContacts : eCommerce** като първоизточник и включете всички записи.</span><span class="sxs-lookup"><span data-stu-id="ddcee-169">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="ddcee-170">В падащ списък **Обект 2**, изберете **loyCustomers : LoyaltyScheme** и включват всички записи.</span><span class="sxs-lookup"><span data-stu-id="ddcee-170">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   ![Унифицирайте съпоставянето на eCommerce и Лоялност.](media/unify-match-order.png)

1. <span data-ttu-id="ddcee-172">Изберете **Добавяне на правило**</span><span class="sxs-lookup"><span data-stu-id="ddcee-172">Select **Add rule**</span></span>

1. <span data-ttu-id="ddcee-173">Добавете първото си условие с помощта на FullName.</span><span class="sxs-lookup"><span data-stu-id="ddcee-173">Add your first condition using FullName.</span></span>

   - <span data-ttu-id="ddcee-174">За eCommerceContacts изберете **Пълно име** в падащото меню.</span><span class="sxs-lookup"><span data-stu-id="ddcee-174">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="ddcee-175">За loyCustomers изберете **Пълно име** в падащото меню.</span><span class="sxs-lookup"><span data-stu-id="ddcee-175">For loyCustomers select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="ddcee-176">Изберете **Нормализирайте** падащото меню и изберете **Тип (Телефон, Име, Адрес, ...)**.</span><span class="sxs-lookup"><span data-stu-id="ddcee-176">Select the **Normalize** drop-down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   - <span data-ttu-id="ddcee-177">Задайте **Ниво на прецизност**: **Основен** и **Стойност**: **Високо**.</span><span class="sxs-lookup"><span data-stu-id="ddcee-177">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="ddcee-178">Въведете името **Пълно име, имейл** за новото правило.</span><span class="sxs-lookup"><span data-stu-id="ddcee-178">Enter the name **FullName, Email** for the new rule.</span></span>

   - <span data-ttu-id="ddcee-179">Добавете второ условие за имейл адрес, като изберете **Добавяне на условие**</span><span class="sxs-lookup"><span data-stu-id="ddcee-179">Add a second condition for email address by selecting **Add Condition**</span></span>
   - <span data-ttu-id="ddcee-180">За обект eCommerceContacts изберете **Електронна поща** в падащо меню.</span><span class="sxs-lookup"><span data-stu-id="ddcee-180">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   - <span data-ttu-id="ddcee-181">За обект loyCustomers изберете **Електронна поща** в падащо меню.</span><span class="sxs-lookup"><span data-stu-id="ddcee-181">For entity loyCustomers, choose **EMail** in the drop-down.</span></span>
   - <span data-ttu-id="ddcee-182">Оставете Нормализиране празно.</span><span class="sxs-lookup"><span data-stu-id="ddcee-182">Leave Normalize blank.</span></span>
   - <span data-ttu-id="ddcee-183">Задайте **Ниво на прецизност**: **Основен** и **Стойност**: **Високо**.</span><span class="sxs-lookup"><span data-stu-id="ddcee-183">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   ![Обединете правилото за съвпадение за име и имейл.](media/unify-match-rule.png)

1. <span data-ttu-id="ddcee-185">Изберете **Готово**.</span><span class="sxs-lookup"><span data-stu-id="ddcee-185">Select **Done**.</span></span>

1. <span data-ttu-id="ddcee-186">Изберете **Записване** и **Изпълнение**.</span><span class="sxs-lookup"><span data-stu-id="ddcee-186">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="ddcee-187">Обединяване</span><span class="sxs-lookup"><span data-stu-id="ddcee-187">Merge</span></span>

1. <span data-ttu-id="ddcee-188">Отидете на раздела **Обединяване**.</span><span class="sxs-lookup"><span data-stu-id="ddcee-188">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="ddcee-189">В **ContactId** за **loyCustomers** обект, променете показваното име на **ContactIdLOYALTY**, за да се разграничи от останалите погълнати лични документи.</span><span class="sxs-lookup"><span data-stu-id="ddcee-189">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   ![преименувайте contactid от идентификатор за лоялност.](media/unify-merge-contactid.png)

1. <span data-ttu-id="ddcee-191">Изберете **Записване** и **Изпълняване на обединяване и процеси надолу по веригата**.</span><span class="sxs-lookup"><span data-stu-id="ddcee-191">Select **Save** and **Run merge and downstream processes**.</span></span>

## <a name="task-3---configure-customer-lifetime-value-prediction"></a><span data-ttu-id="ddcee-192">Задача 3 - Конфигуриране на стойността на живота на клиента прогноза</span><span class="sxs-lookup"><span data-stu-id="ddcee-192">Task 3 - Configure customer lifetime value prediction</span></span>

<span data-ttu-id="ddcee-193">С установените унифицирани клиентски профили вече можем да стартираме стойността на живота на клиента прогноза.</span><span class="sxs-lookup"><span data-stu-id="ddcee-193">With the unified customer profiles in place, we can now run the customer lifetime value prediction.</span></span> <span data-ttu-id="ddcee-194">За подробни стъпки вижте [Доживотна стойност на клиента прогноза (визуализация)](predict-customer-lifetime-value.md).</span><span class="sxs-lookup"><span data-stu-id="ddcee-194">For detailed steps, see [Customer Lifetime Value prediction (preview)](predict-customer-lifetime-value.md).</span></span>

1. <span data-ttu-id="ddcee-195">Отидете на **Интелигентност**  > **Прогнози** и изберете **Модел на стойност на живота на клиента**.</span><span class="sxs-lookup"><span data-stu-id="ddcee-195">Go to  **Intelligence**  > **Predictions**  and select the **Customer lifetime value model**.</span></span>

1. <span data-ttu-id="ddcee-196">Преминете през информацията в страничния прозорец и изберете **Първи стъпки**.</span><span class="sxs-lookup"><span data-stu-id="ddcee-196">Go through the information in the side pane and select **Get started**.</span></span>

1. <span data-ttu-id="ddcee-197">Назовете модела **OOB eCommerce CLV прогноза** и изходния обект **OOBeCommerceCLVPrediction**.</span><span class="sxs-lookup"><span data-stu-id="ddcee-197">Name the model **OOB eCommerce CLV Prediction** and the output entity  **OOBeCommerceCLVPrediction**.</span></span>

1. <span data-ttu-id="ddcee-198">Определете предпочитанията на модела за CLV модела:</span><span class="sxs-lookup"><span data-stu-id="ddcee-198">Define model preferences for the CLV model:</span></span>
   - <span data-ttu-id="ddcee-199">**Прогноза период от време**: **12 месеца или 1 година**.</span><span class="sxs-lookup"><span data-stu-id="ddcee-199">**Prediction time period**: **12 months or 1 year**.</span></span> <span data-ttu-id="ddcee-200">Тази настройка определя колко далеч в бъдещето да се предскаже стойността на живота на клиента.</span><span class="sxs-lookup"><span data-stu-id="ddcee-200">This setting defines how far into the future to predict customer lifetime value.</span></span>
   - <span data-ttu-id="ddcee-201">**Активни клиенти**: Посочете какво означават активните клиенти за вашия бизнес.</span><span class="sxs-lookup"><span data-stu-id="ddcee-201">**Active customers**: Specify what active customers mean for your business.</span></span> <span data-ttu-id="ddcee-202">Задайте историческа времева рамка, в която клиентът трябва да е имал поне една транзакция, за да се счита за активна.</span><span class="sxs-lookup"><span data-stu-id="ddcee-202">Set the historical time frame in which a customer must have had at least one transaction to be considered active.</span></span> <span data-ttu-id="ddcee-203">Моделът ще предсказва CLV само за активни клиенти.</span><span class="sxs-lookup"><span data-stu-id="ddcee-203">The model will only predict CLV for active customers.</span></span> <span data-ttu-id="ddcee-204">Изберете между оставяне на модела да изчислява периода от време въз основа на исторически данни за транзакциите или предоставяне на конкретна времева рамка.</span><span class="sxs-lookup"><span data-stu-id="ddcee-204">Choose between letting the model calculate the time period based on historical transaction data or provide a specific time frame.</span></span> <span data-ttu-id="ddcee-205">В това примерно ръководство ние **позволяваме на модела изчисли интервала на покупка**, което е опцията по подразбиране.</span><span class="sxs-lookup"><span data-stu-id="ddcee-205">In this sample guide, we **let the model calculate purchase interval**, which is the default option.</span></span>
   - <span data-ttu-id="ddcee-206">**Клиенти с висока стойност**: Определете клиентите с висока стойност като процент от най-добре платените клиенти.</span><span class="sxs-lookup"><span data-stu-id="ddcee-206">**High value customers**: Define high value customers as a percentile of top-paying customers.</span></span> <span data-ttu-id="ddcee-207">Моделът използва този вход, за да предостави резултати, които отговарят на вашата бизнес дефиниция за клиенти с висока стойност.</span><span class="sxs-lookup"><span data-stu-id="ddcee-207">The model uses this input to provide results that fit your business definition of high value customers.</span></span> <span data-ttu-id="ddcee-208">Можете да изберете да позволите на модела да определи клиентите с висока стойност.</span><span class="sxs-lookup"><span data-stu-id="ddcee-208">You can choose to let the model define high value customers.</span></span> <span data-ttu-id="ddcee-209">Той използва евристично правило, което извежда процентила.</span><span class="sxs-lookup"><span data-stu-id="ddcee-209">It uses a heuristic rule that derives the percentile.</span></span> <span data-ttu-id="ddcee-210">Можете също да оределите клиенти с висока стойност: Определете клиентите с висока стойност като процент от най-добре платените бъдещи клиенти.</span><span class="sxs-lookup"><span data-stu-id="ddcee-210">You can also define high value customers as a percentile of top future paying customers.</span></span> <span data-ttu-id="ddcee-211">В това примерно ръководство ние ръчно определяме клиентите с висока стойност като **топ 30% от активните плащащи клиенти** и изберете **Следващия**.</span><span class="sxs-lookup"><span data-stu-id="ddcee-211">In this sample guide, we manually define high value customers as **top 30% of active paying customers** and select **Next**.</span></span>

    :::image type="content" source="media/clv-model-preferences.png" alt-text="Предпочитания стъпка в ръководството за модела CLV.":::

1. <span data-ttu-id="ddcee-213">В **Необходими данни** стъпка, изберете **Добавете данни** за предоставяне на данни за историята на транзакциите.</span><span class="sxs-lookup"><span data-stu-id="ddcee-213">In the **Required Data** step, select **Add data** to provide the transaction history data.</span></span>

1. <span data-ttu-id="ddcee-214">Добавете **Електронна търговия Покупки: електронна търговия** обект и картографиране на атрибутите, които се изискват от модела:</span><span class="sxs-lookup"><span data-stu-id="ddcee-214">Add the **eCommercePurchases : eCommerce** entity and map the attributes that are required by the model:</span></span>
   - <span data-ttu-id="ddcee-215">Идент. № на транзакцията: eCommerce.eCommercePurchases.PurchaseId</span><span class="sxs-lookup"><span data-stu-id="ddcee-215">Transaction ID: eCommerce.eCommercePurchases.PurchaseId</span></span>
   - <span data-ttu-id="ddcee-216">Датата на транзакцията: eCommerce.eCommercePurchases.PurchasedOn</span><span class="sxs-lookup"><span data-stu-id="ddcee-216">Transaction date: eCommerce.eCommercePurchases.PurchasedOn</span></span>
   - <span data-ttu-id="ddcee-217">Сума на транзакцията: eCommerce.eCommercePurchases.TotalPrice</span><span class="sxs-lookup"><span data-stu-id="ddcee-217">Transaction amount: eCommerce.eCommercePurchases.TotalPrice</span></span>
   - <span data-ttu-id="ddcee-218">Идентификатор на продукта: eCommerce.eCommercePurchases.ProductId</span><span class="sxs-lookup"><span data-stu-id="ddcee-218">Product ID: eCommerce.eCommercePurchases.ProductId</span></span>

1. <span data-ttu-id="ddcee-219">Изберете **Напред**.</span><span class="sxs-lookup"><span data-stu-id="ddcee-219">Select **Next**.</span></span>

1. <span data-ttu-id="ddcee-220">Настройте връзката между **Електронна търговия Покупки: електронна търговия** субект и **eCommerceContacts: електронна търговия**.</span><span class="sxs-lookup"><span data-stu-id="ddcee-220">Set up the relationship between the **eCommercePurchases : eCommerce** entity and  **eCommerceContacts : eCommerce**.</span></span>

1. <span data-ttu-id="ddcee-221">**Допълнителни данни (по избор)** стъпка ви позволява да добавите още данни за активността на клиентите.</span><span class="sxs-lookup"><span data-stu-id="ddcee-221">The **Additional data (optional)** step allows you to add more customer activity data.</span></span> <span data-ttu-id="ddcee-222">Тези данни могат да ви помогнат да получите повече информация за взаимодействието на клиентите с вашия бизнес, което може да допринесе за CLV.</span><span class="sxs-lookup"><span data-stu-id="ddcee-222">This data can help to get more insights for customer interactions with your business, which can contribute to CLV.</span></span> <span data-ttu-id="ddcee-223">Добавянето на ключови взаимодействия с клиенти като уеб дневници, обслужване на клиенти дневници или история на програмите за награди може да подобри точността на прогнозите.</span><span class="sxs-lookup"><span data-stu-id="ddcee-223">Adding key customer interactions like web logs, customer service logs, or rewards program history can improve the accuracy of predictions.</span></span> <span data-ttu-id="ddcee-224">Изберете **Добавете данни**, за да включите повече данни за активността на клиентите.</span><span class="sxs-lookup"><span data-stu-id="ddcee-224">Select **Add data** to include more customer activity data.</span></span>

1. <span data-ttu-id="ddcee-225">Добавете обект на дейност на клиента и съпоставете имената на полетата му със съответните полета, изисквани от модела:</span><span class="sxs-lookup"><span data-stu-id="ddcee-225">Add the customer activity entity and map its fields names to the corresponding fields required by the model:</span></span>
   - <span data-ttu-id="ddcee-226">Субект на дейност на клиента: Reviews:Website</span><span class="sxs-lookup"><span data-stu-id="ddcee-226">Customer activity entity: Reviews:Website</span></span>
   - <span data-ttu-id="ddcee-227">Първичен ключ: Website.Reviews.ReviewId</span><span class="sxs-lookup"><span data-stu-id="ddcee-227">Primary key: Website.Reviews.ReviewId</span></span>
   - <span data-ttu-id="ddcee-228">Клеймо за време: Website.Reviews.ReviewDate</span><span class="sxs-lookup"><span data-stu-id="ddcee-228">Timestamp: Website.Reviews.ReviewDate</span></span>
   - <span data-ttu-id="ddcee-229">Събитие (име на активност): Website.Reviews.ActivityTypeDisplay</span><span class="sxs-lookup"><span data-stu-id="ddcee-229">Event (activity name): Website.Reviews.ActivityTypeDisplay</span></span>
   - <span data-ttu-id="ddcee-230">Подробности (сума или стойност): Website.Reviews.ReviewRating</span><span class="sxs-lookup"><span data-stu-id="ddcee-230">Details (amount or value): Website.Reviews.ReviewRating</span></span>

1. <span data-ttu-id="ddcee-231">Изберете **Следващия** и конфигурирайте дейността и връзката между данните за транзакциите и данните на клиента:</span><span class="sxs-lookup"><span data-stu-id="ddcee-231">Select **Next** and configure the activity and the relationship between the transaction data and the customer data:</span></span>  
   - <span data-ttu-id="ddcee-232">Тип дейност: Изберете съществуващ</span><span class="sxs-lookup"><span data-stu-id="ddcee-232">Activity type: Choose existing</span></span>
   - <span data-ttu-id="ddcee-233">Етикет на дейността: Преглед</span><span class="sxs-lookup"><span data-stu-id="ddcee-233">Activity label: Review</span></span>
   - <span data-ttu-id="ddcee-234">Съответстващ етикет: Website.Reviews.UserId</span><span class="sxs-lookup"><span data-stu-id="ddcee-234">Corresponding label: Website.Reviews.UserId</span></span>
   - <span data-ttu-id="ddcee-235">Обект на клиент: eCommerceContacts:eCommerce</span><span class="sxs-lookup"><span data-stu-id="ddcee-235">Customer entity: eCommerceContacts:eCommerce</span></span>
   - <span data-ttu-id="ddcee-236">Връзка: WebsiteReviews</span><span class="sxs-lookup"><span data-stu-id="ddcee-236">Relationship: WebsiteReviews</span></span>

1. <span data-ttu-id="ddcee-237">Изберете **Напред**, за да зададете графика на модела.</span><span class="sxs-lookup"><span data-stu-id="ddcee-237">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="ddcee-238">Моделът трябва да тренира редовно, за да научи нови модели, когато има погълнати нови данни.</span><span class="sxs-lookup"><span data-stu-id="ddcee-238">The model needs to train regularly to learn new patterns when there's new data ingested.</span></span> <span data-ttu-id="ddcee-239">За този пример изберете **Месечно**.</span><span class="sxs-lookup"><span data-stu-id="ddcee-239">For this example, choose **Monthly**.</span></span>

1. <span data-ttu-id="ddcee-240">След като прегледате всички подробности, изберете **Запазете и стартирайте**.</span><span class="sxs-lookup"><span data-stu-id="ddcee-240">After reviewing all the details, select  **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="ddcee-241">Задача 4 - Преглед на резултатите от модела и обяснения</span><span class="sxs-lookup"><span data-stu-id="ddcee-241">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="ddcee-242">Нека моделът завърши обучението и точкуването на данните.</span><span class="sxs-lookup"><span data-stu-id="ddcee-242">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="ddcee-243">След това можете да прегледате резултатите и обясненията на модела CLV.</span><span class="sxs-lookup"><span data-stu-id="ddcee-243">Next, you can review the CLV model results and explanations.</span></span> <span data-ttu-id="ddcee-244">За повече информация вижте [Прегледайте състоянието и резултатите на прогноза](predict-customer-lifetime-value.md#review-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="ddcee-244">For more information, see [Review a prediction status and results](predict-customer-lifetime-value.md#review-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-value-customers"></a><span data-ttu-id="ddcee-245">Задача 5 - Създайте сегмент от клиенти с висока стойност</span><span class="sxs-lookup"><span data-stu-id="ddcee-245">Task 5 - Create a segment of high value customers</span></span>

<span data-ttu-id="ddcee-246">Изпълнението на модела създава нов обект, който е включен в списъка **Данни** > **Субекти**.</span><span class="sxs-lookup"><span data-stu-id="ddcee-246">Running the model creates a new entity, which is listed on **Data** > **Entities**.</span></span> <span data-ttu-id="ddcee-247">Можете да създадете нов клиентски сегмент въз основа на обекта, създаден от модела.</span><span class="sxs-lookup"><span data-stu-id="ddcee-247">You can create a new customer segment based on the entity created by the model.</span></span>

1. <span data-ttu-id="ddcee-248">Към **Сегменти**.</span><span class="sxs-lookup"><span data-stu-id="ddcee-248">Go to **Segments**.</span></span> 

1. <span data-ttu-id="ddcee-249">Изберете **Създаване** и изберете **Създаване от** > **Разузнаване**.</span><span class="sxs-lookup"><span data-stu-id="ddcee-249">Select  **New** and choose **Create from** > **Intelligence**.</span></span>

   ![Създаване на сегмент с изхода на модела.](media/segment-intelligence.png)

1. <span data-ttu-id="ddcee-251">Изберете **OOBeCommerceCLVPrediction** обект и дефинирайте сегмента:</span><span class="sxs-lookup"><span data-stu-id="ddcee-251">Select the  **OOBeCommerceCLVPrediction** entity and define the segment:</span></span>
  - <span data-ttu-id="ddcee-252">Поле: CLVScore</span><span class="sxs-lookup"><span data-stu-id="ddcee-252">Field: CLVScore</span></span>
  - <span data-ttu-id="ddcee-253">Оператор: по-голямо от</span><span class="sxs-lookup"><span data-stu-id="ddcee-253">Operator: greater than</span></span>
  - <span data-ttu-id="ddcee-254">Стойност: 1500</span><span class="sxs-lookup"><span data-stu-id="ddcee-254">Value: 1500</span></span>

1. <span data-ttu-id="ddcee-255">Изберете **Преглед** и **Запазете** сегмента.</span><span class="sxs-lookup"><span data-stu-id="ddcee-255">Select **Review** and **Save** the segment.</span></span>

<span data-ttu-id="ddcee-256">Вече имате сегмент, който идентифицира клиенти, за които се очаква да генерират повече от $1500 приходи през следващите 12 месеца.</span><span class="sxs-lookup"><span data-stu-id="ddcee-256">You now have a segment that identifies customers who are predicted to generate more than $1500 of revenue in the next 12 months.</span></span> <span data-ttu-id="ddcee-257">Този сегмент се актуализира динамично, ако се погълнат повече данни.</span><span class="sxs-lookup"><span data-stu-id="ddcee-257">This segment gets updated dynamically if more data is ingested.</span></span>

<span data-ttu-id="ddcee-258">За повече информация вижте [Създаване и управление на сегменти](segments.md).</span><span class="sxs-lookup"><span data-stu-id="ddcee-258">For more information, see [Create and manage segments](segments.md).</span></span>
