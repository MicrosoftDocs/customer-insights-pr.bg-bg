---
title: Дейности на клиент
description: Дефинирайте дейностите на клиентите и ги прегледайте в хронологията на клиентите.
ms.date: 10/13/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: fbfa9d7e00859cc80c24b98bd2dc806f1fda7803
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596716"
---
# <a name="customer-activities"></a><span data-ttu-id="665c1-103">Дейности на клиент</span><span class="sxs-lookup"><span data-stu-id="665c1-103">Customer activities</span></span>

<span data-ttu-id="665c1-104">Комбинирайте дейностите на клиентите от [различни източници на данни](data-sources.md) в Dynamics 365 Customer Insights за създаване на клиентска хронология, която изброява дейностите в хронологичен ред.</span><span class="sxs-lookup"><span data-stu-id="665c1-104">Combine customer activities from [various data sources](data-sources.md) in Dynamics 365 Customer Insights to create a customer timeline that lists the activities in chronological order.</span></span> <span data-ttu-id="665c1-105">Можете да включите времевата линия в приложения за ангажиране на клиенти в Dynamics 365 чрез [Добавка за клиентска карта](customer-card-add-in.md) или в Power BI табло.</span><span class="sxs-lookup"><span data-stu-id="665c1-105">You can include the timeline in customer engagement apps in Dynamics 365 via the [Customer Card add-in](customer-card-add-in.md), or in a Power BI dashboard.</span></span>

## <a name="define-an-activity"></a><span data-ttu-id="665c1-106">Определяне на дейност</span><span class="sxs-lookup"><span data-stu-id="665c1-106">Define an activity</span></span>

<span data-ttu-id="665c1-107">Източниците на данни включват обекти с данни за трансакции и дейности от множество източници на данни.</span><span class="sxs-lookup"><span data-stu-id="665c1-107">Your data sources include entities with transactional and activity data from multiple data sources.</span></span> <span data-ttu-id="665c1-108">Идентифицирайте тези обекти и изберете дейностите, които искате да видите на времевата линия на клиента.</span><span class="sxs-lookup"><span data-stu-id="665c1-108">Identify these entities and select the activities you want to view on the customer's timeline.</span></span> <span data-ttu-id="665c1-109">Изберете обекта, който включва целевата дейност или дейности.</span><span class="sxs-lookup"><span data-stu-id="665c1-109">Choose the entity that includes your target activity or activities.</span></span>

1. <span data-ttu-id="665c1-110">В статията за аудиторията отидете на **Данни** > **Дейности**.</span><span class="sxs-lookup"><span data-stu-id="665c1-110">In audience insights, go to **Data** > **Activities**.</span></span>

1. <span data-ttu-id="665c1-111">Изберете **Добавяне на дейност**.</span><span class="sxs-lookup"><span data-stu-id="665c1-111">Select **Add activity**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="665c1-112">Обектът трябва да има поне един атрибут от тип **Дата**, за да бъде включен във времевата линия на клиент, и не можете да добавяте обекти без полета **Дата**.</span><span class="sxs-lookup"><span data-stu-id="665c1-112">An entity must have at least one attribute of type **Date** to be included in a customer timeline and you can't add entities without **Date** fields.</span></span> <span data-ttu-id="665c1-113">Контролата **Добавяне на дейност** се деактивира, ако не се намери такъв обект.</span><span class="sxs-lookup"><span data-stu-id="665c1-113">The **Add activity** control is disabled if no such entity is found.</span></span>

1. <span data-ttu-id="665c1-114">В прозореца **Добавяне на дейност** задайте стойностите за следните полета:</span><span class="sxs-lookup"><span data-stu-id="665c1-114">In the **Add activity** pane, set the values for the following fields:</span></span>

   - <span data-ttu-id="665c1-115">**Обект**: Изберете обект, който включва данни за трансакции или дейности.</span><span class="sxs-lookup"><span data-stu-id="665c1-115">**Entity**: Select an entity that includes transactional or activity data.</span></span>
   - <span data-ttu-id="665c1-116">**Първичен ключ**: Изберете полето, което еднозначно идентифицира запис.</span><span class="sxs-lookup"><span data-stu-id="665c1-116">**Primary key**: Select the field that uniquely identifies a record.</span></span> <span data-ttu-id="665c1-117">Не трябва да съдържа дублирани стойности, празни стойности или липсващи стойности.</span><span class="sxs-lookup"><span data-stu-id="665c1-117">It shouldn't contain any duplicate values, empty values, or missing values.</span></span>
   - <span data-ttu-id="665c1-118">**Времево клеймо**: Изберете полето, което представлява началния час на дейността.</span><span class="sxs-lookup"><span data-stu-id="665c1-118">**Timestamp**: Select the field that represents the start time of your activity.</span></span>
   - <span data-ttu-id="665c1-119">**Събитие**: Изберете полето, което представлява събитието за дейността.</span><span class="sxs-lookup"><span data-stu-id="665c1-119">**Event**: Select the field that is the event for the activity.</span></span>
   - <span data-ttu-id="665c1-120">**Уеб адрес**: Изберете полето, което представлява URL адрес, предоставящ допълнителна информация за тази дейност.</span><span class="sxs-lookup"><span data-stu-id="665c1-120">**Web address**: Select the field that represents a URL providing additional information about this activity.</span></span> <span data-ttu-id="665c1-121">Например системата за транзакции, която захранва тази дейност.</span><span class="sxs-lookup"><span data-stu-id="665c1-121">For example, the transactional system that sources this activity.</span></span> <span data-ttu-id="665c1-122">Този URL адрес може да бъде всяко поле от източника на данни или може да бъде конструиран като ново поле с помощта на трансформация на Power Query.</span><span class="sxs-lookup"><span data-stu-id="665c1-122">This URL can be any field from the data source, or it can be constructed as a new field using a Power Query transformation.</span></span> <span data-ttu-id="665c1-123">Данните за този URL адрес ще се съхраняват в обекта „Унифицирана дейност“, който може да се изразходва надолу по веригата с помощта на API.</span><span class="sxs-lookup"><span data-stu-id="665c1-123">This URL data will be stored in the Unified Activity entity, which can be consumed downstream using APIs.</span></span>
   - <span data-ttu-id="665c1-124">**Подробности**: По желание изберете полето, което се добавя за допълнителни подробности.</span><span class="sxs-lookup"><span data-stu-id="665c1-124">**Details**: Optionally, select the field that is added for additional details.</span></span>
   - <span data-ttu-id="665c1-125">**Икона**: По желание изберете иконата, която представлява тази дейност.</span><span class="sxs-lookup"><span data-stu-id="665c1-125">**Icon**: Optionally, select the icon that represents this activity.</span></span>
   - <span data-ttu-id="665c1-126">**Тип дейност**: Определете препратката за типа дейност към Common Data Model, която най-добре описва семантичното определение на дейността.</span><span class="sxs-lookup"><span data-stu-id="665c1-126">**Activity Type**: Define the activity type reference to Common Data Model that best describes the semantic definition of the activity.</span></span>

1. <span data-ttu-id="665c1-127">В раздела **Настройване на релация** конфигурирайте подробностите, за да свържете данните за дейността със съответния клиент.</span><span class="sxs-lookup"><span data-stu-id="665c1-127">In the **Set up relationship** section, configure the details to connect your activity data to its corresponding customer.</span></span>

    - <span data-ttu-id="665c1-128">**Поле на обект на дейност**: Изберете полето в обекта на дейност, което ще се използва за установяване на релация с друг обект.</span><span class="sxs-lookup"><span data-stu-id="665c1-128">**Activity entity field**: Select the field in your activity entity that will be used to establish a relationship with another entity.</span></span>
    - <span data-ttu-id="665c1-129">**Обект на клиент**: Изберете съответния обект източник на клиент, с който обекта на дейност ще има релация.</span><span class="sxs-lookup"><span data-stu-id="665c1-129">**Customer entity**: Select the corresponding source customer entity with which your activity entity will be in relationship.</span></span> <span data-ttu-id="665c1-130">Можете да свържете само с тези обекти източници на клиент, които се използват в процеса на обединяване на данни.</span><span class="sxs-lookup"><span data-stu-id="665c1-130">You can relate to only those source customer entities that are used in the data unification process.</span></span>
    - <span data-ttu-id="665c1-131">**Поле на обект на клиент**: Това поле показва първичния ключ на обекта източник на клиент, както е избран в процеса на карта.</span><span class="sxs-lookup"><span data-stu-id="665c1-131">**Customer entity field**: This field shows the primary key of the source customer entity as selected in the map process.</span></span> <span data-ttu-id="665c1-132">Това поле за първичен ключ в обекта източник на клиент се използва за установяване на релация с обекта на дейността.</span><span class="sxs-lookup"><span data-stu-id="665c1-132">This primary key field in the source customer entity is used to establish a relationship with the activity entity.</span></span>
    - <span data-ttu-id="665c1-133">**Име**: Ако вече съществува релация между този обект на дейност и избрания обект източник на клиент, името на релацията ще бъде в режим само за четене.</span><span class="sxs-lookup"><span data-stu-id="665c1-133">**Name**: If a relationship between this activity entity and the selected source customer entity already exists, the relationship name will be in read-only mode.</span></span> <span data-ttu-id="665c1-134">Ако няма такава релация, ще се създаде нова релация с предоставеното тук име.</span><span class="sxs-lookup"><span data-stu-id="665c1-134">If there no such relationship exists, a new relationship will be created with the name provided here.</span></span>
   
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="665c1-135">![Дефиниране на релация към обект](media/activities-entities-define.png "Дефиниране на релация към обект")</span><span class="sxs-lookup"><span data-stu-id="665c1-135">![Define the entity relationship](media/activities-entities-define.png "Define the entity relationship")</span></span>

1. <span data-ttu-id="665c1-136">Изберете **Записване**, за да приложите промените.</span><span class="sxs-lookup"><span data-stu-id="665c1-136">Select **Save** to apply your changes.</span></span>

1. <span data-ttu-id="665c1-137">В страницата **Дейности** изберете **Изпълнение**.</span><span class="sxs-lookup"><span data-stu-id="665c1-137">On the **Activities** page, select **Run**.</span></span>

> [!TIP]
> <span data-ttu-id="665c1-138">Съществуват [шест вида статус](system.md#status-types) на задачите/процесите.</span><span class="sxs-lookup"><span data-stu-id="665c1-138">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="665c1-139">Освен това повечето процеси [зависят от други процеси надолу по веригата](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="665c1-139">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="665c1-140">Можете да изберете състоянието на процес, за да видите подробности за напредъка на цялата задача.</span><span class="sxs-lookup"><span data-stu-id="665c1-140">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="665c1-141">След като изберете **Вижте подробности** за една от задачите на заданието, ще намерите допълнителна информация: време за обработка, дата на последната обработка и всички грешки и предупреждения, свързани със задачата.</span><span class="sxs-lookup"><span data-stu-id="665c1-141">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="edit-an-activity"></a><span data-ttu-id="665c1-142">Редактиране на дейност</span><span class="sxs-lookup"><span data-stu-id="665c1-142">Edit an activity</span></span>

1. <span data-ttu-id="665c1-143">В статията за аудиторията отидете на **Данни** > **Дейности**.</span><span class="sxs-lookup"><span data-stu-id="665c1-143">In audience insights, go to **Data** > **Activities**.</span></span>

2. <span data-ttu-id="665c1-144">Изберете обекта на дейност, който искате да редактирате и изберете **Редактиране**.</span><span class="sxs-lookup"><span data-stu-id="665c1-144">Select the activity entity you want to edit and select **Edit**.</span></span> <span data-ttu-id="665c1-145">Или можете да посочите с мишката реда на обекта и да изберете иконата **Редактиране**.</span><span class="sxs-lookup"><span data-stu-id="665c1-145">Or, you can hover over the entity row and select the **Edit** icon.</span></span>

3. <span data-ttu-id="665c1-146">Щракнете върху иконата **Редактиране**.</span><span class="sxs-lookup"><span data-stu-id="665c1-146">Click on the **Edit** icon.</span></span>

4. <span data-ttu-id="665c1-147">В прозореца **Редактиране на дейност** актуализирайте стойностите и изберете **Записване**.</span><span class="sxs-lookup"><span data-stu-id="665c1-147">In the **Edit activity** pane, update the values and select **Save**.</span></span>

5. <span data-ttu-id="665c1-148">В страницата **Дейности** изберете **Изпълнение**.</span><span class="sxs-lookup"><span data-stu-id="665c1-148">On the **Activities** page, select **Run**.</span></span>

## <a name="delete-an-activity"></a><span data-ttu-id="665c1-149">Изтриване на дейност</span><span class="sxs-lookup"><span data-stu-id="665c1-149">Delete an activity</span></span>

1. <span data-ttu-id="665c1-150">В статията за аудиторията отидете на **Данни** > **Дейности**.</span><span class="sxs-lookup"><span data-stu-id="665c1-150">In audience insights, go to **Data** > **Activities**.</span></span>

2. <span data-ttu-id="665c1-151">Изберете обекта на дейност, който искате да премахнете и изберете **Изтриване**.</span><span class="sxs-lookup"><span data-stu-id="665c1-151">Select the activity entity you want to remove and select **Delete**.</span></span> <span data-ttu-id="665c1-152">Или можете да посочите с мишката реда на обекта и да изберете иконата **Изтриване**.</span><span class="sxs-lookup"><span data-stu-id="665c1-152">Or, you can hover over the entity row and select the **Delete** icon.</span></span> <span data-ttu-id="665c1-153">Освен това можете да изберете няколко обекта на дейност, които да бъдат изтрити наведнъж.</span><span class="sxs-lookup"><span data-stu-id="665c1-153">Additionally, you can select multiple activity entities to be deleted at once.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="665c1-154">![Редактиране или изтриване на релациите към обекта](media/activities-entities-edit-delete.png "Редактиране или изтриване на релациите към обекта")</span><span class="sxs-lookup"><span data-stu-id="665c1-154">![Edit or delete the entity relationship](media/activities-entities-edit-delete.png "Edit or delete the entity relationship")</span></span>

3. <span data-ttu-id="665c1-155">Изберете иконата **Изтриване**.</span><span class="sxs-lookup"><span data-stu-id="665c1-155">Select on the **Delete** icon.</span></span>

4. <span data-ttu-id="665c1-156">Потвърдете изтриването.</span><span class="sxs-lookup"><span data-stu-id="665c1-156">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]