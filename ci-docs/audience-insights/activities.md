---
title: Дейности на клиент
description: Дефинирайте дейностите на клиентите и ги прегледайте в хронологията на клиентите.
ms.date: 04/07/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: 0c728fad4ed00d1bf085fed60057211861b3a195
ms.sourcegitcommit: f0855bd7762b1f0a1d3dd5259e23c95e1b0a6a93
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 04/07/2021
ms.locfileid: "5866394"
---
# <a name="customer-activities"></a><span data-ttu-id="156de-103">Дейности на клиент</span><span class="sxs-lookup"><span data-stu-id="156de-103">Customer activities</span></span>

<span data-ttu-id="156de-104">Комбинирайте дейностите на клиентите от [различни източници на данни](data-sources.md) в Dynamics 365 Customer Insights, за да създадете времева линия, която изброява дейностите в хронологичен ред.</span><span class="sxs-lookup"><span data-stu-id="156de-104">Combine customer activities from [various data sources](data-sources.md) in Dynamics 365 Customer Insights to create a timeline that lists the activities chronologically.</span></span> <span data-ttu-id="156de-105">Включете вревата линия в приложенията на Dynamics 365 с решението [Добавка за карта на клиент](customer-card-add-in.md) или в таблото на Power BI.</span><span class="sxs-lookup"><span data-stu-id="156de-105">Include the timeline in Dynamics 365 apps with the [Customer Card add-in](customer-card-add-in.md) solution, or in a Power BI dashboard.</span></span>

## <a name="define-an-activity"></a><span data-ttu-id="156de-106">Определяне на дейност</span><span class="sxs-lookup"><span data-stu-id="156de-106">Define an activity</span></span>

<span data-ttu-id="156de-107">Източниците на данни може да включват обекти с данни за трансакции и дейности от множество източници на данни.</span><span class="sxs-lookup"><span data-stu-id="156de-107">Your data sources can include entities with transactional and activity data from multiple data sources.</span></span> <span data-ttu-id="156de-108">Идентифицирайте тези обекти и изберете дейностите, които искате да видите на времевата линия на клиента.</span><span class="sxs-lookup"><span data-stu-id="156de-108">Identify these entities and select the activities you want to view on the customer's timeline.</span></span> <span data-ttu-id="156de-109">Изберете обекта, който включва целевата дейност или дейности.</span><span class="sxs-lookup"><span data-stu-id="156de-109">Choose the entity that includes your target activity or activities.</span></span>

> [!NOTE]
> <span data-ttu-id="156de-110">Обектът трябва да има поне един атрибут от тип **Дата**, за да бъде включен във времевата линия на клиент, и не можете да добавяте обекти без полета **Дата**.</span><span class="sxs-lookup"><span data-stu-id="156de-110">An entity must have at least one attribute of type **Date** to be included in a customer timeline and you can't add entities without **Date** fields.</span></span> <span data-ttu-id="156de-111">Контролата **Добавяне на дейност** се деактивира, ако не се намери такъв обект.</span><span class="sxs-lookup"><span data-stu-id="156de-111">The **Add activity** control is disabled if no such entity is found.</span></span>

1. <span data-ttu-id="156de-112">В статията за аудиторията отидете на **Данни** > **Дейности**.</span><span class="sxs-lookup"><span data-stu-id="156de-112">In audience insights, go to **Data** > **Activities**.</span></span>

1. <span data-ttu-id="156de-113">Изберете **Добавяне на дейност**, за да стартирате ръководството за процеса на настройка на дейността.</span><span class="sxs-lookup"><span data-stu-id="156de-113">Select **Add activity** to start the guided experience for the activity setup process.</span></span>

1. <span data-ttu-id="156de-114">В стъпката **Данни за дейността** задайте стойностите за следните полета:</span><span class="sxs-lookup"><span data-stu-id="156de-114">In the **Activity data** step, set the values for the following fields:</span></span>

   - <span data-ttu-id="156de-115">**Име на дейност**: Изберете име за дейността.</span><span class="sxs-lookup"><span data-stu-id="156de-115">**Activity name**: Select a name for your activity.</span></span>
   - <span data-ttu-id="156de-116">**Обект**: Изберете обект, който включва данни за трансакции или дейности.</span><span class="sxs-lookup"><span data-stu-id="156de-116">**Entity**: Select an entity that includes transactional or activity data.</span></span>
   - <span data-ttu-id="156de-117">**Първичен ключ**: Изберете полето, което еднозначно идентифицира запис.</span><span class="sxs-lookup"><span data-stu-id="156de-117">**Primary key**: Select the field that uniquely identifies a record.</span></span> <span data-ttu-id="156de-118">Не трябва да съдържа дублирани стойности, празни стойности или липсващи стойности.</span><span class="sxs-lookup"><span data-stu-id="156de-118">It shouldn't contain any duplicate values, empty values, or missing values.</span></span>

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Настройте данните за дейността с име, обект и първичен ключ.":::

1. <span data-ttu-id="156de-120">Изберете **Напред**, за да преминете към следващата стъпка.</span><span class="sxs-lookup"><span data-stu-id="156de-120">Select **Next** to go to the next step.</span></span>

1. <span data-ttu-id="156de-121">В стъпката **Релация** конфигурирайте подробностите за свързване на данните за дейността със съответния клиент.</span><span class="sxs-lookup"><span data-stu-id="156de-121">In the **Relationship** step, configure the details to connect your activity data to its corresponding customer.</span></span> <span data-ttu-id="156de-122">Тази стъпка визуализира връзката между обектите.</span><span class="sxs-lookup"><span data-stu-id="156de-122">This step visualizes the connection between entities.</span></span>  

   - <span data-ttu-id="156de-123">**Първо**: Външно поле в обекта на дейността, което ще се използва за установяване на релация с друг обект.</span><span class="sxs-lookup"><span data-stu-id="156de-123">**First**: Foreign field in your activity entity that will be used to establish a relationship with another entity.</span></span>
   - <span data-ttu-id="156de-124">**Второ**: Съответен изходен обект на клиент, с който обектът на дейността ще има релация.</span><span class="sxs-lookup"><span data-stu-id="156de-124">**Second**: Corresponding source customer entity with which your activity entity will be in relationship.</span></span> <span data-ttu-id="156de-125">Може да се свържете само с изходни обекти на клиенти, които се използват в процеса на обединяване на данни.</span><span class="sxs-lookup"><span data-stu-id="156de-125">You can only relate to source customer entities that are used in the data unification process.</span></span>
   - <span data-ttu-id="156de-126">**Трето**: Ако връзка между този обект на дейност и избрания изходен обект на клиент вече съществува, името на връзката ще е в режим само за четене.</span><span class="sxs-lookup"><span data-stu-id="156de-126">**Third**: If a relationship between this activity entity and the selected source customer entity already exists, the relationship name will be in read-only mode.</span></span> <span data-ttu-id="156de-127">Ако такава връзка не съществува, ще се създаде нова връзка с името, което сте посочили в това поле.</span><span class="sxs-lookup"><span data-stu-id="156de-127">If there no such relationship exists, a new relationship will be created with the name you provide in this box.</span></span>

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Дефиниране на релация към обект.":::

1. <span data-ttu-id="156de-129">Изберете **Напред**, за да преминете към следващата стъпка.</span><span class="sxs-lookup"><span data-stu-id="156de-129">Select **Next** to go to the next step.</span></span> 

1. <span data-ttu-id="156de-130">В стъпката **Обединяване на дейност** изберете събитието на дейността и началния час на дейността.</span><span class="sxs-lookup"><span data-stu-id="156de-130">In the **Activity unification** step, choose the activity event and the start time of your activity.</span></span> 
   - <span data-ttu-id="156de-131">**Задължителни полета**</span><span class="sxs-lookup"><span data-stu-id="156de-131">**Required fields**</span></span>
      1. <span data-ttu-id="156de-132">**Събитие на дейност**: Поле, което представя събитието за тази дейност</span><span class="sxs-lookup"><span data-stu-id="156de-132">**Event activity**: Field that is the event for this activity</span></span>
      2. <span data-ttu-id="156de-133">**Времево клеймо**: Поле, което представя началния час на дейността.</span><span class="sxs-lookup"><span data-stu-id="156de-133">**Timestamp**: Field that represents the start time of your activity.</span></span>

   - <span data-ttu-id="156de-134">**Полета по избор**</span><span class="sxs-lookup"><span data-stu-id="156de-134">**Optional fields**</span></span>
      1. <span data-ttu-id="156de-135">**Допълнителни подробности**: Поле със съответната информация за тази дейност.</span><span class="sxs-lookup"><span data-stu-id="156de-135">**Additional detail**: Field with relevant information for this activity.</span></span>
      2. <span data-ttu-id="156de-136">**Икона**: Икона, която най-добре представя този тип дейност.</span><span class="sxs-lookup"><span data-stu-id="156de-136">**Icon**: Icon that best represents this activity type.</span></span>
      3. <span data-ttu-id="156de-137">**Уеб адрес**: Поле, съдържащо URL адрес с информация за тази дейност.</span><span class="sxs-lookup"><span data-stu-id="156de-137">**Web address**: Field containing a URL with information about this activity.</span></span> <span data-ttu-id="156de-138">Например системата за транзакции, която захранва тази дейност.</span><span class="sxs-lookup"><span data-stu-id="156de-138">For example, the transactional system that sources this activity.</span></span> <span data-ttu-id="156de-139">Този URL адрес може да бъде всяко поле от източника на данни или може да бъде конструиран като ново поле с помощта на трансформация на Power Query.</span><span class="sxs-lookup"><span data-stu-id="156de-139">This URL can be any field from the data source, or it can be constructed as a new field using a Power Query transformation.</span></span> <span data-ttu-id="156de-140">Данните за URL адресите ще се съхраняват в обекта *Обединена дейност*, който може да се използва надолу по веригата с помощта на [API](apis.md).</span><span class="sxs-lookup"><span data-stu-id="156de-140">The URL data will be stored in the *Unified Activity* entity, which can be consumed downstream using [APIs](apis.md).</span></span>
   
   :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="Посочете данните за дейността на клиента в обекта на обединена дейност.":::

1. <span data-ttu-id="156de-142">Изберете **Напред**, за да преминете към следващата стъпка.</span><span class="sxs-lookup"><span data-stu-id="156de-142">Select **Next** to move to the next step.</span></span> <span data-ttu-id="156de-143">Можете да изберете **Завършване и преглед**, за да запишете дейността веднага с тип дейност, зададен на **Други**.</span><span class="sxs-lookup"><span data-stu-id="156de-143">You can select **Finish and review** to save the activity now with the activity type set to **Other**.</span></span> 

1. <span data-ttu-id="156de-144">В стъпката **Тип дейност** изберете типа дейност и по желание изберете дали искате семантично да съпоставите някои от типовете дейности за използване в други области на Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="156de-144">In the **Activity Type** step, choose the activity type and optionally select if you want to semantically map some of the activity types for use in other areas of Customer Insights.</span></span> <span data-ttu-id="156de-145">В момента типовете дейност *Абонамент* & *SalesOrderLine* могат да се съпоставят семантично, след като се съгласите да съпоставите полетата.</span><span class="sxs-lookup"><span data-stu-id="156de-145">Currently, *Subscription* & *SalesOrderLine* activity types can be semantically mapped after agreeing to map the fields.</span></span> <span data-ttu-id="156de-146">Ако тип дейност не е подходящ за новата дейност, може да изберете *Други* или *Създаване на нова* за персонализиран тип дейност.</span><span class="sxs-lookup"><span data-stu-id="156de-146">If an activity type isn't relevant for the new activity, you can choose *Other* or *Create new* for a custom activity type.</span></span>

1. <span data-ttu-id="156de-147">Изберете **Напред**, за да преминете към следващата стъпка.</span><span class="sxs-lookup"><span data-stu-id="156de-147">Select **Next** to move to the next step.</span></span> 

1. <span data-ttu-id="156de-148">В стъпката **Преглед** проверете избора си.</span><span class="sxs-lookup"><span data-stu-id="156de-148">In the **Review** step, verify your selections.</span></span> <span data-ttu-id="156de-149">Върнете се към някоя от предишните стъпки и актуализирате информацията, ако е необходимо.</span><span class="sxs-lookup"><span data-stu-id="156de-149">You go back to any of the previous steps and update the information if necessary.</span></span>

   :::image type="content" source="media/Activity_Wizard5.PNG" alt-text="Прегледайте посочените полета за дейност.":::
   
1. <span data-ttu-id="156de-151">Изберете **Записване на дейността**, за да приложите промените, и изберете **Готово**, за да се върнете към **Данни** > **Дейности**.</span><span class="sxs-lookup"><span data-stu-id="156de-151">Select **Save activity** to apply your changes and select **Done** to go back to **Data** > **Activities**.</span></span> <span data-ttu-id="156de-152">Тук виждате кои дейности са зададени да се показват във времевата линия.</span><span class="sxs-lookup"><span data-stu-id="156de-152">Here you see which activities are set to show in the timeline.</span></span> 

1. <span data-ttu-id="156de-153">На страницата **Дейности** изберете **Изпълнение** за обработка на дейността.</span><span class="sxs-lookup"><span data-stu-id="156de-153">On the **Activities** page, select **Run** to process the activity.</span></span> 

> [!TIP]
> <span data-ttu-id="156de-154">Съществуват [шест вида статус](system.md#status-types) на задачите/процесите.</span><span class="sxs-lookup"><span data-stu-id="156de-154">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="156de-155">Освен това повечето процеси [зависят от други процеси надолу по веригата](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="156de-155">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="156de-156">Можете да изберете състоянието на процес, за да видите подробности за напредъка на цялата задача.</span><span class="sxs-lookup"><span data-stu-id="156de-156">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="156de-157">След като изберете **Вижте подробности** за една от задачите на заданието, ще намерите допълнителна информация: време за обработка, дата на последната обработка и всички грешки и предупреждения, свързани със задачата.</span><span class="sxs-lookup"><span data-stu-id="156de-157">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>


## <a name="manage-existing-activities"></a><span data-ttu-id="156de-158">Управление на съществуващи дейности</span><span class="sxs-lookup"><span data-stu-id="156de-158">Manage existing activities</span></span>

<span data-ttu-id="156de-159">В **Данни** > **Дейности** можете да видите всички записани дейности и да ги управлявате.</span><span class="sxs-lookup"><span data-stu-id="156de-159">On **Data** > **Activities**, you can view all your saved activities, and manage them.</span></span> <span data-ttu-id="156de-160">Всяка дейност е представена от ред, който също включва подробности за източника, обекта и типа дейност.</span><span class="sxs-lookup"><span data-stu-id="156de-160">Each activity is represented by a row that also includes details about the source, the entity, and the activity type.</span></span>

<span data-ttu-id="156de-161">Следните действия са налични, когато изберете дейност.</span><span class="sxs-lookup"><span data-stu-id="156de-161">The following actions are available when you select an activity.</span></span> 

- <span data-ttu-id="156de-162">**Редактиране**: Отваря настройката на дейността в стъпката за преглед.</span><span class="sxs-lookup"><span data-stu-id="156de-162">**Edit**: Opens the activity setup on the review step.</span></span> <span data-ttu-id="156de-163">Можете да промените всяка или цялата текуща конфигурация от тази стъпка.</span><span class="sxs-lookup"><span data-stu-id="156de-163">You can change any or all of the current configuration from this step.</span></span> <span data-ttu-id="156de-164">След като промените конфигурацията, изберете **Записване на дейност** и след това изберете **Изпълнение** за обработка на промените.</span><span class="sxs-lookup"><span data-stu-id="156de-164">After changing the configuration, select **Save activity** and then select **Run** to process the changes.</span></span>

- <span data-ttu-id="156de-165">**Преименуване**: Отваря диалогов прозорец, където да въведете друго име за избраната дейност.</span><span class="sxs-lookup"><span data-stu-id="156de-165">**Rename**: Opens a dialog where to enter a different name for the selected activity.</span></span> <span data-ttu-id="156de-166">Изберете **Записване**, за да приложите промените.</span><span class="sxs-lookup"><span data-stu-id="156de-166">Select **Save** to apply your changes.</span></span>

- <span data-ttu-id="156de-167">**Изтриване**: Отваря диалогов прозорец за потвърждение на изтриването на избраната дейност.</span><span class="sxs-lookup"><span data-stu-id="156de-167">**Delete**: Opens a dialog to confirm the deletion of the selected activity.</span></span> <span data-ttu-id="156de-168">Може също така да изтриете повече от една дейност наведнъж, като изберете дейностите и след това изберете иконата за изтриване.</span><span class="sxs-lookup"><span data-stu-id="156de-168">You can also delete more than one activity at once by selecting the activities and then selecting the delete icon.</span></span> <span data-ttu-id="156de-169">За да потвърдите изтриването, изберете **Изтриване**.</span><span class="sxs-lookup"><span data-stu-id="156de-169">Select **Delete** to confirm the deletion.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
