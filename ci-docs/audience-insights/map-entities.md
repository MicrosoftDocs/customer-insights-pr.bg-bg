---
title: Нанасяне на обекти за обединяване на данни
description: Нанасяне на данни за създаване на унифицирани клиентски профили.
ms.date: 09/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 36b7f7b2fac9497245cf6759506c53753972f173
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595980"
---
# <a name="map-entities-and-attributes"></a><span data-ttu-id="d4db1-103">Обекти и атрибути на карта</span><span class="sxs-lookup"><span data-stu-id="d4db1-103">Map entities and attributes</span></span>

<span data-ttu-id="d4db1-104">**Нанасянето** е първият етап в процеса на обединяване на данни за прозрения на аудиторията.</span><span class="sxs-lookup"><span data-stu-id="d4db1-104">**Map** is the first stage in the data unification process of audience insights.</span></span> <span data-ttu-id="d4db1-105">Картографирането се състои от три фази:</span><span class="sxs-lookup"><span data-stu-id="d4db1-105">Mapping consists of three phases:</span></span>

- <span data-ttu-id="d4db1-106">*Избор на обект*: Определете възможните за комбиниране обекти, които водят до набор от данни с по-пълна информация за клиентите.</span><span class="sxs-lookup"><span data-stu-id="d4db1-106">*Entity selection*: Identify the combinable entities that lead to a dataset with more complete information about your customers.</span></span>
- <span data-ttu-id="d4db1-107">*Избор на атрибут*: За всеки обект определете колоните, които искате да комбинирате и съгласувате във фазите на *съвпадение* и *обединяване*.</span><span class="sxs-lookup"><span data-stu-id="d4db1-107">*Attribute selection*: For each entity, identify the columns you want to combine and reconcile in the *match* and *merge* phases.</span></span> <span data-ttu-id="d4db1-108">Тези колони се наричат *Атрибути*.</span><span class="sxs-lookup"><span data-stu-id="d4db1-108">These columns are called *Attributes*.</span></span>
- <span data-ttu-id="d4db1-109">*Избор на първичен ключ и семантичен тип*: За всеки обект идентифицирайте атрибут, който искате да дефинирате като първичен ключ за този обект, и за всеки атрибут идентифицирайте семантичен тип, който най-добре описва този атрибут.</span><span class="sxs-lookup"><span data-stu-id="d4db1-109">*Primary key and semantic type selection*: For each entity, identify an attribute you want to define as the primary key for that entity, and for each attribute, identify a semantic type that best describes that attribute.</span></span>

<span data-ttu-id="d4db1-110">За повече информация относно общия поток на унифициране на данни вж. [Унифициране](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="d4db1-110">For more information about the general flow of data unification, see [Unify](data-unification.md).</span></span>

## <a name="select-the-first-entities"></a><span data-ttu-id="d4db1-111">Избор на първите обекти</span><span class="sxs-lookup"><span data-stu-id="d4db1-111">Select the first entities</span></span>

1. <span data-ttu-id="d4db1-112">В статията за аудиторията отидете на **Данни** > **Обединете** > **Нанасяне**.</span><span class="sxs-lookup"><span data-stu-id="d4db1-112">In audience insights, go to **Data** > **Unify** > **Map**.</span></span>

2. <span data-ttu-id="d4db1-113">Започнете фазата на нанасяне,като изберете **Избор на обекти**.</span><span class="sxs-lookup"><span data-stu-id="d4db1-113">Start the map phase by selecting **Select entities**.</span></span>

3. <span data-ttu-id="d4db1-114">Изберете обектите и атрибутите, които искате да използвате в *съпоставяне* и *сливане* фази.</span><span class="sxs-lookup"><span data-stu-id="d4db1-114">Select the entities and attributes you want to use in the *match* and *merge* phases.</span></span> <span data-ttu-id="d4db1-115">Можете да изберете необходимите атрибути индивидуално от обект или да включите всички атрибути от обект, като изберете квадратче за отметка **Включете всички полета** на ниво обект.</span><span class="sxs-lookup"><span data-stu-id="d4db1-115">You can select the required attributes individually from an entity or include all attributes from an entity by selecting the **Include all fields** checkbox on the entity level.</span></span> <span data-ttu-id="d4db1-116">Препоръчваме да изберете поне два обекта, за да използвате процеса на унифициране на данни.</span><span class="sxs-lookup"><span data-stu-id="d4db1-116">We recommend selecting at least two entities to benefit from the data unification process.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d4db1-117">![Пример за добавяне на обекти](media/data-manager-configure-map-add-entities-example.png "Пример за добавяне на обекти")</span><span class="sxs-lookup"><span data-stu-id="d4db1-117">![Add entities example](media/data-manager-configure-map-add-entities-example.png "Add entities example")</span></span>

   <span data-ttu-id="d4db1-118">В този пример добавяме обектите **eCommerceContacts** и **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="d4db1-118">In this example, we're adding the **eCommerceContacts** and **loyCustomers** entities.</span></span> <span data-ttu-id="d4db1-119">Избирайки тези обекти, можете да получите представа за това кои от онлайн бизнес клиентите са членове на програмата за лоялност.</span><span class="sxs-lookup"><span data-stu-id="d4db1-119">By choosing these entities, you can derive insights on which of the online business customers are loyalty program members.</span></span>
   
   <span data-ttu-id="d4db1-120">Можете да търсите по ключови думи във всички атрибути и обекти, за да изберете необходимите атрибути, които искате да съпоставите.</span><span class="sxs-lookup"><span data-stu-id="d4db1-120">You can search on keywords across all attributes and entities to select the required attributes you want to map.</span></span>
   
     > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d4db1-121">![Пример за полета за търсене](media/data-manager-configure-map-search-fields-example.png "Пример за полета за търсене")</span><span class="sxs-lookup"><span data-stu-id="d4db1-121">![Search fields example](media/data-manager-configure-map-search-fields-example.png "Search fields example")</span></span>

4. <span data-ttu-id="d4db1-122">Изберете **Приложи**, за да потвърдите избора си.</span><span class="sxs-lookup"><span data-stu-id="d4db1-122">Select **Apply** to confirm your selections.</span></span>

## <a name="select-primary-key-and-semantic-type-for-attributes"></a><span data-ttu-id="d4db1-123">Изберете първичен ключ и семантичен тип за атрибути</span><span class="sxs-lookup"><span data-stu-id="d4db1-123">Select primary key and semantic type for attributes</span></span>

<span data-ttu-id="d4db1-124">След като изберете обектите си, страница **Карта** изброява избраните обекти за преглед.</span><span class="sxs-lookup"><span data-stu-id="d4db1-124">After selecting your entities, the **Map** page lists the selected entities for your review.</span></span> <span data-ttu-id="d4db1-125">Дефинирайте първичния ключ за обект и идентифицирайте семантичния тип за атрибут в обекта.</span><span class="sxs-lookup"><span data-stu-id="d4db1-125">Define the primary key for an entity and identify the semantic type for an attribute in the entity.</span></span>

- <span data-ttu-id="d4db1-126">**Първичен ключ**: Изберете един атрибут като първичен ключ за всеки от обектите.</span><span class="sxs-lookup"><span data-stu-id="d4db1-126">**Primary key**: Select one attribute as a primary key for each of your entities.</span></span> <span data-ttu-id="d4db1-127">За да бъде атрибутът валиден първичен ключ, той не трябва да включва дублирани стойности, липсващи стойности или нулеви стойности.</span><span class="sxs-lookup"><span data-stu-id="d4db1-127">For an attribute to be a valid primary key, it shouldn't include duplicate values, missing values, or null values.</span></span> <span data-ttu-id="d4db1-128">Атрибутите тип данни за низ, цяло число и GUID се поддържат като първични ключове и ще бъдат показани в поле, от което да избирате.</span><span class="sxs-lookup"><span data-stu-id="d4db1-128">String, integer, and GUID data type attributes are supported as primary keys and will be displayed in a field for you to select from.</span></span>

- <span data-ttu-id="d4db1-129">**Семантичен тип на атрибут**: Категории на атрибутите, като например имейл адрес или име.</span><span class="sxs-lookup"><span data-stu-id="d4db1-129">**Attribute semantic type**: Categories of your attributes, such as email address or name.</span></span> <span data-ttu-id="d4db1-130">За да използвате AI модели за интелигентни прогноза на семантиката, да спестите време и да подобрите точността, задайте **Интелигентно съпоставяне** на **ВКЛ.**.</span><span class="sxs-lookup"><span data-stu-id="d4db1-130">To use AI models for smart prediction of semantics, save time and improve accuracy, set **Intelligent mapping** to **ON**.</span></span> <span data-ttu-id="d4db1-131">Интелигентното съпоставяне маркира препоръките за семантика, базирани на AI, в полето **Тип**.</span><span class="sxs-lookup"><span data-stu-id="d4db1-131">Intelligent mapping highlights AI-based semantics recommendation in the **Type** field.</span></span> <span data-ttu-id="d4db1-132">Ако го зададете на **ИЗКЛ.**, ще виждате нашите обичайни препоръки за съпоставяне.</span><span class="sxs-lookup"><span data-stu-id="d4db1-132">If you set it to **OFF**, you will see our regular mapping recommendations.</span></span> <span data-ttu-id="d4db1-133">Можете да изберете всеки семантичен тип от наличния списък с опции и да замените предложената селекция.</span><span class="sxs-lookup"><span data-stu-id="d4db1-133">You can select any semantic type from the available list of options and override the suggested selection.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d4db1-134">![Тип атрибут и семантична прогноза](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Тип атрибут и семантична прогноза")</span><span class="sxs-lookup"><span data-stu-id="d4db1-134">![Attribute type and semantic prediction](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Attribute type and semantic prediction")</span></span>

<span data-ttu-id="d4db1-135">Възможно е също да се добави персонализиран семантичен тип.</span><span class="sxs-lookup"><span data-stu-id="d4db1-135">Adding a custom semantic type is also possible.</span></span> <span data-ttu-id="d4db1-136">Изберете полето за тип за атрибут и въведете името на типа на персонализирания семантичен тип.</span><span class="sxs-lookup"><span data-stu-id="d4db1-136">Select the type field for an attribute, and type your custom semantic type name.</span></span> <span data-ttu-id="d4db1-137">По този начин можете също да промените типовете атрибути, които са били идентифицирани от системата.</span><span class="sxs-lookup"><span data-stu-id="d4db1-137">This way, you can also change the attribute types that were identified by the system.</span></span>

<span data-ttu-id="d4db1-138">Всички атрибути, за които семантичен тип се идентифицира автоматично, са групирани в раздела **Преглед на картографираните полета**.</span><span class="sxs-lookup"><span data-stu-id="d4db1-138">All attributes for which a semantic type is automatically identified are grouped in the **Review mapped fields** section.</span></span> <span data-ttu-id="d4db1-139">Прегледайте тези атрибути и техните семантични типове, защото те ще бъдат използвани за комбиниране на вашите обекти в стъпката за обединяване на обединяването на данни.</span><span class="sxs-lookup"><span data-stu-id="d4db1-139">Review these attributes and their semantic types because they'll be used to combine your entities in the merge step of data unification.</span></span>

<span data-ttu-id="d4db1-140">Атрибутите, които не се преобразуват автоматично в семантичен тип, са групирани в раздел **Дефинирайте данните в некартографираните полета**.</span><span class="sxs-lookup"><span data-stu-id="d4db1-140">Attributes that aren't automatically mapped to a semantic type are grouped in the **Define the data in the unmapped fields** section.</span></span> <span data-ttu-id="d4db1-141">Изберете полето на семантичния тип за немартираните атрибути или въведете вашето име на персонализиран тип атрибут.</span><span class="sxs-lookup"><span data-stu-id="d4db1-141">Select the semantic type field for the unmapped attributes, or enter your custom attribute-type name.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d4db1-142">![Първичен ключ и тип атрибут](media/data-manager-configure-map-add-attributes.png "Първичен ключ и тип атрибут")</span><span class="sxs-lookup"><span data-stu-id="d4db1-142">![Primary key and attribute type](media/data-manager-configure-map-add-attributes.png "Primary key and attribute type")</span></span>

> [!NOTE]
> <span data-ttu-id="d4db1-143">Едно поле трябва да се преобразува в семантичния тип Person.FullName, за да попълни името на клиента в клиентска карта.</span><span class="sxs-lookup"><span data-stu-id="d4db1-143">One field should map to the semantic type Person.FullName to populate the customer name in customer card.</span></span> <span data-ttu-id="d4db1-144">В противен случай клиентските карти ще се показват без имена.</span><span class="sxs-lookup"><span data-stu-id="d4db1-144">Otherwise, the customer cards will appear nameless.</span></span> 

## <a name="add-and-remove-attributes-and-entities"></a><span data-ttu-id="d4db1-145">Добавяне и премахване на атрибути и обекти</span><span class="sxs-lookup"><span data-stu-id="d4db1-145">Add and remove attributes and entities</span></span>

1. <span data-ttu-id="d4db1-146">В **Обединяване** > **Карта**, изберете **Редактиране на полета**.</span><span class="sxs-lookup"><span data-stu-id="d4db1-146">On **Unify** > **Map**, select **Edit fields**.</span></span>

2. <span data-ttu-id="d4db1-147">В панела **Редактиране на полета** добавете или премахнете атрибути и обекти.</span><span class="sxs-lookup"><span data-stu-id="d4db1-147">In the **Edit fields** pane, add or remove attributes and entities.</span></span> <span data-ttu-id="d4db1-148">Използвайте търсенето или превъртете, за да намерите и изберете вашите атрибути и обекти, които представляват интерес.</span><span class="sxs-lookup"><span data-stu-id="d4db1-148">Use the search or scroll to find and select your attributes and entities of interest.</span></span> <span data-ttu-id="d4db1-149">Не можете да премахнете атрибут или обект, ако те вече са съвпаднали.</span><span class="sxs-lookup"><span data-stu-id="d4db1-149">You can't remove an attribute or an entity if they've already been matched.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d4db1-150">![Добавяне или премахване на атрибути](media/configure-data-map-edit.png "Добавяне или премахване на атрибути")</span><span class="sxs-lookup"><span data-stu-id="d4db1-150">![Add or remove attributes](media/configure-data-map-edit.png "Add or remove attributes")</span></span>

3. <span data-ttu-id="d4db1-151">Изберете **Прилагане**.</span><span class="sxs-lookup"><span data-stu-id="d4db1-151">Select **Apply**.</span></span>

## <a name="add-images-to-profiles"></a><span data-ttu-id="d4db1-152">Добавяне на изображения към профилите</span><span class="sxs-lookup"><span data-stu-id="d4db1-152">Add images to profiles</span></span>

<span data-ttu-id="d4db1-153">Ако дадено обект съдържа URL адреси за публично достъпни изображения на профили или емблеми, можете да ги добавите към унифицирания клиентски профил.</span><span class="sxs-lookup"><span data-stu-id="d4db1-153">If an entity contains URLs to publicly available profile images or logos, you can add them to the unified customer profile.</span></span>

<span data-ttu-id="d4db1-154">Изберете обекта и намерете полето, което съдържа URL адреса към изображението на профила.</span><span class="sxs-lookup"><span data-stu-id="d4db1-154">Select the entity and find the field that contains the URL to the profile image.</span></span> <span data-ttu-id="d4db1-155">В полето за въвеждане **Тип** въведете ръчно следната стойност:</span><span class="sxs-lookup"><span data-stu-id="d4db1-155">In the **Type** input field, manually enter the following value:</span></span> 
- <span data-ttu-id="d4db1-156">За лице: Person.ProfileImage</span><span class="sxs-lookup"><span data-stu-id="d4db1-156">For a person: Person.ProfileImage</span></span>
- <span data-ttu-id="d4db1-157">За организация: Organization.LogoImage</span><span class="sxs-lookup"><span data-stu-id="d4db1-157">For an organization: Organization.LogoImage</span></span>

<span data-ttu-id="d4db1-158">Продължете със стъпките за обединяване и се уверете, че атрибутът, който съдържа URL адреса на изображението, също е добавен в стъпката [Обединяване](merge-entities.md).</span><span class="sxs-lookup"><span data-stu-id="d4db1-158">Continue with the unification steps and ensure the attribute that contains the image URL is also added in the [Merge](merge-entities.md) step.</span></span>

## <a name="set-attributes-for-organizations"></a><span data-ttu-id="d4db1-159">Задаване на атрибути за организации</span><span class="sxs-lookup"><span data-stu-id="d4db1-159">Set attributes for organizations</span></span>

<span data-ttu-id="d4db1-160">За организации (преглед) типът атрибут трябва да бъде нанесен към "Organization.Name"</span><span class="sxs-lookup"><span data-stu-id="d4db1-160">For organizations (Preview), the attribute type should be mapped to "Organization.Name"</span></span>
> [!div class="mx-imgBorder"]
> <span data-ttu-id="d4db1-161">![Първичен ключ и тип атрибут B2B](media/configure-data-map-edit-b2b.png "Първичен ключ и тип атрибут B2B")</span><span class="sxs-lookup"><span data-stu-id="d4db1-161">![Primary key and attribute type B2B](media/configure-data-map-edit-b2b.png "Primary key and attribute type B2B")</span></span>

## <a name="next-step"></a><span data-ttu-id="d4db1-162">Следваща стъпка</span><span class="sxs-lookup"><span data-stu-id="d4db1-162">Next step</span></span>

<span data-ttu-id="d4db1-163">Като част от процеса на унифициране отидете на страницата **Съвпадение**.</span><span class="sxs-lookup"><span data-stu-id="d4db1-163">As part of the data unification process, go to the **Match** page.</span></span> <span data-ttu-id="d4db1-164">Посетете [**Съвпадение**](match-entities.md), за да научите повече за тази фаза.</span><span class="sxs-lookup"><span data-stu-id="d4db1-164">Visit [**Match**](match-entities.md) to learn about this phase.</span></span>

> [!TIP]
> <span data-ttu-id="d4db1-165">Вижте следния видеоклип: [Първи стъпки: Създаване на унифициран клиентски профил](https://youtu.be/oBfGEhucAxs).</span><span class="sxs-lookup"><span data-stu-id="d4db1-165">Check out the following video: [Getting Started: Creating a Unified Customer Profile](https://youtu.be/oBfGEhucAxs).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]