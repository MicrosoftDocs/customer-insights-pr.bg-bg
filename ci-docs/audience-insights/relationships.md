---
title: Релации между обекти и пътища на обект
description: Създавайте и управлявайте връзки между обекти от множество източници на данни.
ms.date: 06/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: d5b9566ec88096fec31d8e164a51598159ec26d4
ms.sourcegitcommit: ece48f80a7b470fb33cd36e3096b4f1e9190433a
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 06/03/2021
ms.locfileid: "6171151"
---
# <a name="relationships-between-entities"></a><span data-ttu-id="14ea0-103">Релации между обекти</span><span class="sxs-lookup"><span data-stu-id="14ea0-103">Relationships between entities</span></span>

<span data-ttu-id="14ea0-104">Връзките свързват обекти и дефинират графика на вашите данни, когато обектите споделят общ идентификатор, външен ключ.</span><span class="sxs-lookup"><span data-stu-id="14ea0-104">Relationships connect entities and define a graph of your data when entities share a common identifier, a foreign key.</span></span> <span data-ttu-id="14ea0-105">Този външен ключ може да се препраща от един обект към друг.</span><span class="sxs-lookup"><span data-stu-id="14ea0-105">This foreign key can be referenced from one entity to another.</span></span> <span data-ttu-id="14ea0-106">Свързаните обекти ви позволяват дефинирането на сегменти и мерки въз основа на няколко източника на данни.</span><span class="sxs-lookup"><span data-stu-id="14ea0-106">Connected entities enable the definition of segments and measures based on multiple data sources.</span></span>

<span data-ttu-id="14ea0-107">Има три типа взаимоотношения:</span><span class="sxs-lookup"><span data-stu-id="14ea0-107">There are three types of relationships:</span></span> 
- <span data-ttu-id="14ea0-108">Нередактируеми системни взаимоотношения, създадени от системата като част от процеса на обединяване на данните</span><span class="sxs-lookup"><span data-stu-id="14ea0-108">Non-editable system relationships, created by the system as part of the data unification process</span></span>
- <span data-ttu-id="14ea0-109">Нередактируеми наследени връзки, които се създават автоматично от поглъщането на източници на данни</span><span class="sxs-lookup"><span data-stu-id="14ea0-109">Non-editable inherited relationships, which are created automatically from ingesting data sources</span></span> 
- <span data-ttu-id="14ea0-110">Редактируеми персонализирани взаимоотношения, създадени и конфигурирани от потребители</span><span class="sxs-lookup"><span data-stu-id="14ea0-110">Editable custom relationships, created and configured by users</span></span>

## <a name="non-editable-system-relationships"></a><span data-ttu-id="14ea0-111">Нередактируеми системни взаимоотношения</span><span class="sxs-lookup"><span data-stu-id="14ea0-111">Non-editable system relationships</span></span>

<span data-ttu-id="14ea0-112">По време на обединяването на данните системните взаимоотношения се създават автоматично въз основа на интелигентно съвпадение.</span><span class="sxs-lookup"><span data-stu-id="14ea0-112">During data unification, system relationships are created automatically based on intelligent matching.</span></span> <span data-ttu-id="14ea0-113">Тези релации помагат да се свържат записите на клиентски профил с други съответстващи записи.</span><span class="sxs-lookup"><span data-stu-id="14ea0-113">These relationships help relate the customer profile records with corresponding records.</span></span> <span data-ttu-id="14ea0-114">Следващата диаграма илюстрира създаването на три базирани на системата взаимоотношения.</span><span class="sxs-lookup"><span data-stu-id="14ea0-114">The following diagram illustrates the creation of three system-based relationships.</span></span> <span data-ttu-id="14ea0-115">Клиентският обект се съпоставя с други обекти, за да се получи унифицираният обект *Клиент*.</span><span class="sxs-lookup"><span data-stu-id="14ea0-115">The customer entity is matched with other entities to produce the unified *Customer* entity.</span></span>

:::image type="content" source="media/relationships-entities-merge.png" alt-text="Диаграма с пътища на взаимоотношения за обекта на клиента с три 1-n връзки.":::

- <span data-ttu-id="14ea0-117">**Релацията *CustomerToContact*** е създадена между обекта на *клиент* и обекта на *контакт*.</span><span class="sxs-lookup"><span data-stu-id="14ea0-117">***CustomerToContact* relationship** was created between the *Customer* entity and the *Contact* entity.</span></span> <span data-ttu-id="14ea0-118">Обектът на *клиент* получава полето за ключ **Contact_contactID** за свързване с полето за ключ на *контакт* **contactID**.</span><span class="sxs-lookup"><span data-stu-id="14ea0-118">The *Customer* entity gets the key field **Contact_contactID** to relate to the *Contact* entity key field **contactID**.</span></span>
- <span data-ttu-id="14ea0-119">**Релацията *CustomerToAccount*** е създадена между обекта на *клиент* и обекта на *акаунт*.</span><span class="sxs-lookup"><span data-stu-id="14ea0-119">***CustomerToAccount* relationship** was created between the *Customer* entity and the *Account* entity.</span></span> <span data-ttu-id="14ea0-120">Обектът на *клиент* получава полето за ключ **Account_accountID** за свързване с полето за ключ на *акаунт* **accountID**.</span><span class="sxs-lookup"><span data-stu-id="14ea0-120">The *Customer* entity gets the key field **Account_accountID** to relate to the *Account* entity key field **accountID**.</span></span>
- <span data-ttu-id="14ea0-121">**Релацията *CustomerToWebAccount*** е създадена между обекта на *клиент* и обекта на *WebAccount*.</span><span class="sxs-lookup"><span data-stu-id="14ea0-121">***CustomerToWebAccount* relationship** was created between the *Customer* entity and the *WebAccount* entity.</span></span> <span data-ttu-id="14ea0-122">Обектът на *клиент* получава полето за ключ **WebAccount_webaccountID** за свързване с полето за ключ на обект *WebAccount* **webaccountID**.</span><span class="sxs-lookup"><span data-stu-id="14ea0-122">The *Customer* entity gets the key field **WebAccount_webaccountID** to relate to the *WebAccount* entity key field **webaccountID**.</span></span>

## <a name="non-editable-inherited-relationships"></a><span data-ttu-id="14ea0-123">Нередактируеми наследени релации</span><span class="sxs-lookup"><span data-stu-id="14ea0-123">Non-editable inherited relationships</span></span>

<span data-ttu-id="14ea0-124">По време на процеса на поглъщане на данни системата проверява източниците на данни за съществуващи връзки.</span><span class="sxs-lookup"><span data-stu-id="14ea0-124">During the data ingestion process, the system checks data sources for existing relationships.</span></span> <span data-ttu-id="14ea0-125">Ако не съществува връзка, системата автоматично ги създава.</span><span class="sxs-lookup"><span data-stu-id="14ea0-125">If no relationship exists, the system automatically creates them.</span></span> <span data-ttu-id="14ea0-126">Тези взаимоотношения се използват и в процесите надолу по веригата.</span><span class="sxs-lookup"><span data-stu-id="14ea0-126">These relationships are also used in downstream processes.</span></span>

## <a name="create-a-custom-relationship"></a><span data-ttu-id="14ea0-127">Създаване на персонализирана релация</span><span class="sxs-lookup"><span data-stu-id="14ea0-127">Create a custom relationship</span></span>

<span data-ttu-id="14ea0-128">Връзката се състои от *субект източник* съдържащ външния ключ и *целеви обект* към който сочи външният ключ на субекта източник.</span><span class="sxs-lookup"><span data-stu-id="14ea0-128">Relationship consists of a *source entity* containing the foreign key and a *target entity* that the source entity's foreign key points to.</span></span> 

1. <span data-ttu-id="14ea0-129">В статията за аудиторията отидете на **Данни** > **Релации**.</span><span class="sxs-lookup"><span data-stu-id="14ea0-129">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="14ea0-130">Изберете **Нова релация**.</span><span class="sxs-lookup"><span data-stu-id="14ea0-130">Select **New relationship**.</span></span>

3. <span data-ttu-id="14ea0-131">В екрана **Нова релация** посочете следната информация:</span><span class="sxs-lookup"><span data-stu-id="14ea0-131">In the **New relationship** pane, provide the following information:</span></span>

   :::image type="content" source="media/relationship-add.png" alt-text="Нов страничен прозорец на връзката с празни полета за въвеждане.":::

   - <span data-ttu-id="14ea0-133">**Име на връзката**: Име, което отразява целта на връзката.</span><span class="sxs-lookup"><span data-stu-id="14ea0-133">**Relationship name**: Name that reflects the purpose of the relationship.</span></span> <span data-ttu-id="14ea0-134">Пример: CustomerToSupportCase.</span><span class="sxs-lookup"><span data-stu-id="14ea0-134">Example: CustomerToSupportCase.</span></span>
   - <span data-ttu-id="14ea0-135">**Описание**: Описание на релацията.</span><span class="sxs-lookup"><span data-stu-id="14ea0-135">**Description**: Description of the relationship.</span></span>
   - <span data-ttu-id="14ea0-136">**Обект източник**: Обект, който се използва като източник във връзката.</span><span class="sxs-lookup"><span data-stu-id="14ea0-136">**Source entity**: Entity that is used as a source in the relationship.</span></span> <span data-ttu-id="14ea0-137">Пример: SupportCase.</span><span class="sxs-lookup"><span data-stu-id="14ea0-137">Example: SupportCase.</span></span>
   - <span data-ttu-id="14ea0-138">**Целеви обект**: Обект, който се използва като цел във връзката.</span><span class="sxs-lookup"><span data-stu-id="14ea0-138">**Target entity**: Entity that is used as a target in the relationship.</span></span> <span data-ttu-id="14ea0-139">Пример: Клиент.</span><span class="sxs-lookup"><span data-stu-id="14ea0-139">Example: Customer.</span></span>
   - <span data-ttu-id="14ea0-140">**Изходна кардиналност**: Посочете кардиналността на обекта източник.</span><span class="sxs-lookup"><span data-stu-id="14ea0-140">**Source cardinality**: Specify the cardinality of the source entity.</span></span> <span data-ttu-id="14ea0-141">Кардиналността описва броя на възможните елементи в даден набор.</span><span class="sxs-lookup"><span data-stu-id="14ea0-141">Cardinality describes the number of possible elements in a set.</span></span> <span data-ttu-id="14ea0-142">Винаги се отнася до целевата кардиналност.</span><span class="sxs-lookup"><span data-stu-id="14ea0-142">It always relates to the target cardinality.</span></span> <span data-ttu-id="14ea0-143">Можете да избирате между **Едно** и **Много**.</span><span class="sxs-lookup"><span data-stu-id="14ea0-143">You can choose between **One** and **Many**.</span></span> <span data-ttu-id="14ea0-144">Поддържат се само релации „много към един” и „един към един”.</span><span class="sxs-lookup"><span data-stu-id="14ea0-144">Only many-to-one and one-to-one relationships are supported.</span></span>  
     - <span data-ttu-id="14ea0-145">Много към едно: множество записи на източника могат да се отнасят до един целеви запис.</span><span class="sxs-lookup"><span data-stu-id="14ea0-145">Many-to-one: Multiple source records can relate to one target record.</span></span> <span data-ttu-id="14ea0-146">Пример: Множество случаи за поддръжка от един клиент.</span><span class="sxs-lookup"><span data-stu-id="14ea0-146">Example: Multiple support cases from a single customer.</span></span>
     - <span data-ttu-id="14ea0-147">Един към един: Записът от един източник се отнася до запис от една цел.</span><span class="sxs-lookup"><span data-stu-id="14ea0-147">One-to-one: A single source record relates to a one target record.</span></span> <span data-ttu-id="14ea0-148">Пример: Един идентификатор за лоялност за един клиент.</span><span class="sxs-lookup"><span data-stu-id="14ea0-148">Example: One loyalty ID for a single customer.</span></span>

     > [!NOTE]
     > <span data-ttu-id="14ea0-149">Връзките много към много могат да бъдат създадени с помощта на две връзки много към едно и свързващ обект, който свързва изходния обект и целевия обект.</span><span class="sxs-lookup"><span data-stu-id="14ea0-149">Many-to-many relationships can be created using two many-to-one relationships and a linking entity, which connects the source entity and the target entity.</span></span>

   - <span data-ttu-id="14ea0-150">**Целева важност** : Изберете важността на записите на целеви обект.</span><span class="sxs-lookup"><span data-stu-id="14ea0-150">**Target cardinality**: Select the cardinality of the target entity records.</span></span> 
   - <span data-ttu-id="14ea0-151">**Ключово поле на източника**: Полето за външния ключ в обекта източник.</span><span class="sxs-lookup"><span data-stu-id="14ea0-151">**Source key field**: The foreign key field in the source entity.</span></span> <span data-ttu-id="14ea0-152">Пример: SupportCase може да използва CaseID като поле за външен ключ.</span><span class="sxs-lookup"><span data-stu-id="14ea0-152">Example: SupportCase could use CaseID as a foreign key field.</span></span>
   - <span data-ttu-id="14ea0-153">**Целево поле за ключ**: Ключовото поле на целевия обект.</span><span class="sxs-lookup"><span data-stu-id="14ea0-153">**Target key field**: The key field of the target entity.</span></span> <span data-ttu-id="14ea0-154">Пример Клиентът може да използва **CustomerID** ключово поле.</span><span class="sxs-lookup"><span data-stu-id="14ea0-154">Example Customer could use the **CustomerID** key field.</span></span>

4. <span data-ttu-id="14ea0-155">За да създадете персонализирана връзка, изберете **Записване**.</span><span class="sxs-lookup"><span data-stu-id="14ea0-155">Select **Save** to create the custom relationship.</span></span>

## <a name="view-relationships"></a><span data-ttu-id="14ea0-156">Преглед на релациите</span><span class="sxs-lookup"><span data-stu-id="14ea0-156">View relationships</span></span>

<span data-ttu-id="14ea0-157">Страницата Връзки изброява всички създадени връзки.</span><span class="sxs-lookup"><span data-stu-id="14ea0-157">The Relationships page lists all the relationships that have been created.</span></span> <span data-ttu-id="14ea0-158">Всеки ред представлява връзка, която също включва подробности за обекта източник, целевия обект и мощността.</span><span class="sxs-lookup"><span data-stu-id="14ea0-158">Each row represents a relationship, which also includes details about the source entity, the target entity, and the cardinality.</span></span> 

:::image type="content" source="media/relationships-list.png" alt-text="Списък на връзките и опциите в лентата за действие на страницата „Връзки“.":::

<span data-ttu-id="14ea0-160">Тази страница предлага набор от опции за съществуващи и нови взаимоотношения:</span><span class="sxs-lookup"><span data-stu-id="14ea0-160">This page offers a set of options for existing and new relationships:</span></span> 
- <span data-ttu-id="14ea0-161">**Нова релация:** Изберете [Създаване на персонализирана релация](#create-a-custom-relationship).</span><span class="sxs-lookup"><span data-stu-id="14ea0-161">**New Relationship**: [Create a custom relationship](#create-a-custom-relationship).</span></span>
- <span data-ttu-id="14ea0-162">**Визуализатор**: [Разгледайте визуализатора на връзката](#explore-the-relationship-visualizer) за да видите мрежова диаграма на съществуващите взаимоотношения и тяхната същественост.</span><span class="sxs-lookup"><span data-stu-id="14ea0-162">**Visualizer**: [Explore the relationship visualizer](#explore-the-relationship-visualizer) to see a network diagram of the existing relationships and their cardinality.</span></span>
- <span data-ttu-id="14ea0-163">**Филтрирайте по**: Изберете типа връзки, които да се показват в списъка.</span><span class="sxs-lookup"><span data-stu-id="14ea0-163">**Filter by**: Choose the type of relationships to show in the list.</span></span>
- <span data-ttu-id="14ea0-164">**Търсене на релации**: Използвайте текстово търсене на свойствата на връзките.</span><span class="sxs-lookup"><span data-stu-id="14ea0-164">**Search relationships**: Use a text-based search on properties of the relationships.</span></span>

### <a name="explore-the-relationship-visualizer"></a><span data-ttu-id="14ea0-165">Разгледайте визуализатора на връзката</span><span class="sxs-lookup"><span data-stu-id="14ea0-165">Explore the relationship visualizer</span></span>

<span data-ttu-id="14ea0-166">Визуализаторът на релации показва мрежова диаграма на съществуващите взаимоотношения между свързаните обекти и тяхната кардиналност.</span><span class="sxs-lookup"><span data-stu-id="14ea0-166">The relationship visualizer shows a network diagram of the existing relationships between connected entities and their cardinality.</span></span>

<span data-ttu-id="14ea0-167">За да персонализирате изгледа, можете да промените позицията на полетата, като ги плъзнете върху платното.</span><span class="sxs-lookup"><span data-stu-id="14ea0-167">To customize the view, you can change the position of the boxes by dragging them on the canvas.</span></span>

:::image type="content" source="media/relationship-visualizer.png" alt-text="Екранна снимка на мрежовата диаграма на визуализатора на връзки с връзки между свързани обекти.":::

<span data-ttu-id="14ea0-169">Налични опции:</span><span class="sxs-lookup"><span data-stu-id="14ea0-169">Available options:</span></span> 
- <span data-ttu-id="14ea0-170">**Експортиране като изображение**: Запазване на текущия изглед като файл с изображение.</span><span class="sxs-lookup"><span data-stu-id="14ea0-170">**Export as image**: Save the current view as an image file.</span></span>
- <span data-ttu-id="14ea0-171">**Промяна на хоризонтално/вертикално оформление**: Променете подравняването на обектите и връзките.</span><span class="sxs-lookup"><span data-stu-id="14ea0-171">**Change to horizontal/vertical layout**: Change the alignment of the entities and relationships.</span></span>
- <span data-ttu-id="14ea0-172">**Редактиране**: Актуализирайте свойствата на персонализираните връзки в екрана за редактиране и запазете промените.</span><span class="sxs-lookup"><span data-stu-id="14ea0-172">**Edit**: Update properties of custom relationships in the edit pane and save changes.</span></span>

## <a name="manage-existing-relationships"></a><span data-ttu-id="14ea0-173">Управление на съществуващи релации</span><span class="sxs-lookup"><span data-stu-id="14ea0-173">Manage existing relationships</span></span> 

<span data-ttu-id="14ea0-174">На страницата „Връзки“ всяка връзка е представена с ред.</span><span class="sxs-lookup"><span data-stu-id="14ea0-174">On the Relationships page, each relationship is represented by a row.</span></span> 

<span data-ttu-id="14ea0-175">Изберете връзка и изберете една от следните опции:</span><span class="sxs-lookup"><span data-stu-id="14ea0-175">Select a relationship and choose one of the following options:</span></span> 
 
- <span data-ttu-id="14ea0-176">**Редактиране**: Актуализирайте свойствата на персонализираните връзки в екрана за редактиране и запазете промените.</span><span class="sxs-lookup"><span data-stu-id="14ea0-176">**Edit**: Update properties of custom relationships in the edit pane and save changes.</span></span>
- <span data-ttu-id="14ea0-177">**Изтриване**: Изтриване на персонализирани връзки.</span><span class="sxs-lookup"><span data-stu-id="14ea0-177">**Delete**: Delete custom relationships.</span></span>
- <span data-ttu-id="14ea0-178">**Изглед**: Преглед на създадени от системата и наследени връзки.</span><span class="sxs-lookup"><span data-stu-id="14ea0-178">**View**: View system-created and inherited relationships.</span></span> 

## <a name="next-step"></a><span data-ttu-id="14ea0-179">Следваща стъпка</span><span class="sxs-lookup"><span data-stu-id="14ea0-179">Next step</span></span>

<span data-ttu-id="14ea0-180">Системните и персонализираните релации се използват за [създаване на сегменти](segments.md) на базата на множество източници на данни, които вече не са в силози.</span><span class="sxs-lookup"><span data-stu-id="14ea0-180">System and custom relationships are used to [create segments](segments.md) based on multiple data sources that are no longer siloed.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
