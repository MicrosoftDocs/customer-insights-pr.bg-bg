---
title: Релации между обекти и пътища на обект
description: Създавайте и управлявайте връзки между обекти от множество източници на данни.
ms.date: 04/14/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: c25bfcb8e2a8223498dd1a5e8cfb3712a40ab85e
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595199"
---
# <a name="relationships-between-entities"></a><span data-ttu-id="8f0cf-103">Релации между обекти</span><span class="sxs-lookup"><span data-stu-id="8f0cf-103">Relationships between entities</span></span>

<span data-ttu-id="8f0cf-104">Релациите ви помагат да свържете обекти и да генерирате графика на данните, когато обектите споделят общ идентификатор (външен ключ), който може да бъде препратен от един обект към друг.</span><span class="sxs-lookup"><span data-stu-id="8f0cf-104">Relationships help you connect entities and generate a graph of your data when entities share a common identifier (foreign key) that can be referenced from one entity to another.</span></span> <span data-ttu-id="8f0cf-105">Свързаните обекти ви позволяват да дефинирате сегменти и мерки въз основа на няколко източника на данни.</span><span class="sxs-lookup"><span data-stu-id="8f0cf-105">Connected entities enable you to define segments and measures based on multiple data sources.</span></span>

<span data-ttu-id="8f0cf-106">Съществуват два типа релации:</span><span class="sxs-lookup"><span data-stu-id="8f0cf-106">There are two types of relationships.</span></span> <span data-ttu-id="8f0cf-107">Системни връзки, които не могат да се редактират, създадени автоматично, и персонализирани релации, създадени и конфигурирани от потребителите.</span><span class="sxs-lookup"><span data-stu-id="8f0cf-107">Non-editable system relationships, which are created automatically, and custom relationships created and configured by users.</span></span>

<span data-ttu-id="8f0cf-108">По време на процесите на съвпадение и обединяване системните релации се създават във фонов режим на базата на интелигентното съвпадение.</span><span class="sxs-lookup"><span data-stu-id="8f0cf-108">During the match and merge processes, system relationships are created behind the scenes based on intelligent matching.</span></span> <span data-ttu-id="8f0cf-109">Тези релации помагат да се свържат записите на клиентски профил с други съответстващи записи на обекти.</span><span class="sxs-lookup"><span data-stu-id="8f0cf-109">These relationships help relate the Customer Profile records with other corresponding entities' records.</span></span> <span data-ttu-id="8f0cf-110">Следващата диаграма илюстрира създаването на три системни релации, когато обекта на клиент е съпоставен с допълнителни обекти, за да се създаде окончателния обект на клиентски профил.</span><span class="sxs-lookup"><span data-stu-id="8f0cf-110">The following diagram illustrates the creation of three system relationships when the customer entity is matched with additional entities to produce the final Customer Profile entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="8f0cf-111">![Създаване на релация](media/relationships-entities-merge.png "Създаване на релация")</span><span class="sxs-lookup"><span data-stu-id="8f0cf-111">![Relationship creation](media/relationships-entities-merge.png "Relationship creation")</span></span>

- <span data-ttu-id="8f0cf-112">**Релацията *CustomerToContact*** е създадена между обекта на клиент и обекта на контакт.</span><span class="sxs-lookup"><span data-stu-id="8f0cf-112">***CustomerToContact* relationship** was created between the Customer entity and the Contact entity.</span></span> <span data-ttu-id="8f0cf-113">Обектът на клиент получава полето за ключ **Contact_contactId** за свързване с полето за ключ на контакт **contactId**.</span><span class="sxs-lookup"><span data-stu-id="8f0cf-113">The Customer entity gets the key field **Contact_contactId** to relate to the Contact entity key field **contactId**.</span></span>
- <span data-ttu-id="8f0cf-114">**Релацията *CustomerToAccount*** е създадена между обекта на клиент и обекта на акаунт.</span><span class="sxs-lookup"><span data-stu-id="8f0cf-114">***CustomerToAccount* relationship** was created between the Customer entity and the Account entity.</span></span> <span data-ttu-id="8f0cf-115">Обектът на клиент получава полето за ключ **Account_accountId** за свързване с полето за ключ на акаунт **accountId**.</span><span class="sxs-lookup"><span data-stu-id="8f0cf-115">The Customer entity gets the key field **Account_accountId** to relate to the Account entity key field **accountId**.</span></span>
- <span data-ttu-id="8f0cf-116">**Релацията *CustomerToWebAccount*** е създадена между обекта на клиент и обекта на WebAccount.</span><span class="sxs-lookup"><span data-stu-id="8f0cf-116">***CustomerToWebAccount* relationship** was created between the Customer entity and the WebAccount entity.</span></span> <span data-ttu-id="8f0cf-117">Обектът на клиент получава полето за ключ **WebAccount_webaccountId** за свързване с полето за ключ на обект WebAccount **webaccountId**.</span><span class="sxs-lookup"><span data-stu-id="8f0cf-117">The Customer entity gets the key field **WebAccount_webaccountId** to relate to the WebAccount entity key field **webaccountId**.</span></span>

## <a name="create-a-relationship"></a><span data-ttu-id="8f0cf-118">Създаване на релация</span><span class="sxs-lookup"><span data-stu-id="8f0cf-118">Create a relationship</span></span>

<span data-ttu-id="8f0cf-119">Определете персонализирани релации на страницата **Релации**.</span><span class="sxs-lookup"><span data-stu-id="8f0cf-119">Define custom relationships on the **Relationships** page.</span></span> <span data-ttu-id="8f0cf-120">Всяка релация се състои от изходен обект (обект, който съхранява външния ключ) и целеви обект (обект, към който посочва външният ключ на изходния обект).</span><span class="sxs-lookup"><span data-stu-id="8f0cf-120">Each relationship consists of a Source entity (the entity that holds the foreign key) and a Target entity (the entity that the source entity's foreign key points to).</span></span>

1. <span data-ttu-id="8f0cf-121">В статията за аудиторията отидете на **Данни** > **Релации**.</span><span class="sxs-lookup"><span data-stu-id="8f0cf-121">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="8f0cf-122">Изберете **Нова релация**.</span><span class="sxs-lookup"><span data-stu-id="8f0cf-122">Select **New relationship**.</span></span>

3. <span data-ttu-id="8f0cf-123">В прозореца **Добавяне на релация** въведете следната информация:</span><span class="sxs-lookup"><span data-stu-id="8f0cf-123">In the **Add relationship** pane, provide the following information:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8f0cf-124">![Въвеждане на подробности за релация](media/relationships-add.png "Въвеждане на подробности за релация")</span><span class="sxs-lookup"><span data-stu-id="8f0cf-124">![Enter relationship details](media/relationships-add.png "Enter relationship details")</span></span>

   - <span data-ttu-id="8f0cf-125">**Име на релация**: Име, което отразява целта на релацията (например **AccountWebLogs**).</span><span class="sxs-lookup"><span data-stu-id="8f0cf-125">**Relationship name**: Name that reflects the purpose of the relationship (for example, **AccountWebLogs**).</span></span>
   - <span data-ttu-id="8f0cf-126">**Описание**: Описание на релацията.</span><span class="sxs-lookup"><span data-stu-id="8f0cf-126">**Description**: Description of the relationship.</span></span>
   - <span data-ttu-id="8f0cf-127">**Изходен обект**: Изберете обекта, който се използва като източник в релацията (например WebLog).</span><span class="sxs-lookup"><span data-stu-id="8f0cf-127">**Source entity**: Select the entity that is used as a source in the relationship (for example, WebLog).</span></span>
   - <span data-ttu-id="8f0cf-128">**Важност** : Изберете важността на записите на изходен обект.</span><span class="sxs-lookup"><span data-stu-id="8f0cf-128">**Cardinality**: Select the cardinality of the source entity records.</span></span> <span data-ttu-id="8f0cf-129">Например „много“ означава, че множество записи Weblog са свързани с един WebAccount.</span><span class="sxs-lookup"><span data-stu-id="8f0cf-129">For example, "many" means that multiple Weblog records are related to one WebAccount.</span></span>
   - <span data-ttu-id="8f0cf-130">**Изходно поле за ключ**: Това представлява полето за външен ключ в изходния обект.</span><span class="sxs-lookup"><span data-stu-id="8f0cf-130">**Source key field**: This represents the foreign key field in the source entity.</span></span> <span data-ttu-id="8f0cf-131">Например WebLog има поле за външен ключ **accountId**.</span><span class="sxs-lookup"><span data-stu-id="8f0cf-131">For example, WebLog has the **accountId** foreign key field.</span></span>
   - <span data-ttu-id="8f0cf-132">**Целеви обект**: Изберете обекта, който се използва като цел в релацията (например WebAccount).</span><span class="sxs-lookup"><span data-stu-id="8f0cf-132">**Target entity**: Select the entity that is used as a target in the relationship (for example, WebAccount).</span></span>
   - <span data-ttu-id="8f0cf-133">**Целева важност** : Изберете важността на записите на целеви обект.</span><span class="sxs-lookup"><span data-stu-id="8f0cf-133">**Target cardinality**: Select the cardinality of the target entity records.</span></span> <span data-ttu-id="8f0cf-134">Например „един“ означава, че множество записи Weblog са свързани с един WebAccount.</span><span class="sxs-lookup"><span data-stu-id="8f0cf-134">For example, "one" means that multiple Weblog records are related to one WebAccount.</span></span>
   - <span data-ttu-id="8f0cf-135">**Целево поле за ключ**: Това поле представлява полето за ключ на целевия обект.</span><span class="sxs-lookup"><span data-stu-id="8f0cf-135">**Target key field**: This field represents the key field of target entity.</span></span> <span data-ttu-id="8f0cf-136">Например WebAccount има поле за ключ **accountId**.</span><span class="sxs-lookup"><span data-stu-id="8f0cf-136">For example, WebAccount has the **accountId** key field.</span></span>

> [!NOTE]
> <span data-ttu-id="8f0cf-137">Поддържат се само релации „много към един” и „един към един”.</span><span class="sxs-lookup"><span data-stu-id="8f0cf-137">Only many-to-one and one-to-one relationships are supported.</span></span> <span data-ttu-id="8f0cf-138">Могат да се създадат релации „много към много”, като се използват две релации „много към един” и обект на връзка (обект, който се използва за свързване на изходния и целевия обект).</span><span class="sxs-lookup"><span data-stu-id="8f0cf-138">Many-to-many relationships can be created using two many-to-one relationships and a link entity (an entity that is used to connect the source entity and the target entity).</span></span>

## <a name="delete-a-relationship"></a><span data-ttu-id="8f0cf-139">Изтриване на релация</span><span class="sxs-lookup"><span data-stu-id="8f0cf-139">Delete a relationship</span></span>

1. <span data-ttu-id="8f0cf-140">В статията за аудиторията отидете на **Данни** > **Релации**.</span><span class="sxs-lookup"><span data-stu-id="8f0cf-140">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="8f0cf-141">Поставете отметка в квадратчетата за релациите, които искате да изтриете.</span><span class="sxs-lookup"><span data-stu-id="8f0cf-141">Select check boxes for the relationships you want to delete.</span></span>

3. <span data-ttu-id="8f0cf-142">Изберете **Изтриване** в горната част на таблицата **Релации**.</span><span class="sxs-lookup"><span data-stu-id="8f0cf-142">Select **Delete** at the top of the **Relationships** table.</span></span>

4. <span data-ttu-id="8f0cf-143">Потвърдете изтриването.</span><span class="sxs-lookup"><span data-stu-id="8f0cf-143">Confirm your deletion.</span></span>

## <a name="next-step"></a><span data-ttu-id="8f0cf-144">Следваща стъпка</span><span class="sxs-lookup"><span data-stu-id="8f0cf-144">Next step</span></span>

<span data-ttu-id="8f0cf-145">Системните и персонализираните релации се използват за създаване на сегменти на базата на множество източници на данни, които вече не са в силози.</span><span class="sxs-lookup"><span data-stu-id="8f0cf-145">System and custom relationships are used to create segments based on multiple data sources that are no longer siloed.</span></span> <span data-ttu-id="8f0cf-146">За повече информация вижте [Сегменти](segments.md).</span><span class="sxs-lookup"><span data-stu-id="8f0cf-146">For more information, see [Segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]