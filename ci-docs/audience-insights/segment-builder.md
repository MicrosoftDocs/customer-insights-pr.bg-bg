---
title: Създаване и управление на сегменти
description: Създайте сегменти с клиенти, за да ги групирате въз основа на различни атрибути.
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 550e509a24701fe5fcdeb9d54311872dc954156c
ms.sourcegitcommit: 72603fb39c4d5dbca71128815a2e1692542ea4dc
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 05/19/2021
ms.locfileid: "6064924"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="e449c-103">Създаване и управление на сегменти</span><span class="sxs-lookup"><span data-stu-id="e449c-103">Create and manage segments</span></span>

<span data-ttu-id="e449c-104">Дефинирайте сложни филтри около обединения клиентски обект и свързаните с него обекти.</span><span class="sxs-lookup"><span data-stu-id="e449c-104">Define complex filters around the unified customer entity and its related entities.</span></span> <span data-ttu-id="e449c-105">Всеки сегмент след обработка създава набор от клиентски записи, които можете да експортирате и да предприемете действия по тях.</span><span class="sxs-lookup"><span data-stu-id="e449c-105">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="e449c-106">Сегментите се управляват на страницата **Сегменти**.</span><span class="sxs-lookup"><span data-stu-id="e449c-106">Segments are managed on the **Segments** page.</span></span> 

<span data-ttu-id="e449c-107">Следващият пример илюстрира способността за сегментиране.</span><span class="sxs-lookup"><span data-stu-id="e449c-107">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="e449c-108">Определихме сегмент за клиенти, които са поръчали стоки за поне 500 долара през последните 90 дни *и* които са участвали в обаждане за обслужване на клиенти, което е ескалирало.</span><span class="sxs-lookup"><span data-stu-id="e449c-108">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

:::image type="content" source="media/segmentation-group1-2.png" alt-text="Екранна снимка на потребителския интерфейс на конструктора на сегменти с две групи, които определят клиентски сегмент.":::

## <a name="create-a-new-segment"></a><span data-ttu-id="e449c-110">Създаване на нов сегмент</span><span class="sxs-lookup"><span data-stu-id="e449c-110">Create a new segment</span></span>

<span data-ttu-id="e449c-111">Има няколко начина за създаване на нов сегмент.</span><span class="sxs-lookup"><span data-stu-id="e449c-111">There are multiple ways to create a new segment.</span></span> <span data-ttu-id="e449c-112">Този раздел описва как да създадете *празен сегмент* от нулата.</span><span class="sxs-lookup"><span data-stu-id="e449c-112">This section describes how to create a *blank segment* from scratch.</span></span> <span data-ttu-id="e449c-113">Можете също да създадете *бърз сегмент* въз основа на съществуващи обекти или използвайте машинно обучение модели, за да получите *предложени сегменти*.</span><span class="sxs-lookup"><span data-stu-id="e449c-113">You can also create a *quick segment* based on existing entities or make use of machine learning models to get *suggested segments*.</span></span> <span data-ttu-id="e449c-114">Повече информация: [Общ преглед на сегменти](segments.md).</span><span class="sxs-lookup"><span data-stu-id="e449c-114">More information: [Segments overview](segments.md).</span></span>

<span data-ttu-id="e449c-115">Докато създавате сегмент, можете да запазите чернова.</span><span class="sxs-lookup"><span data-stu-id="e449c-115">While creating a segment, you can save a draft.</span></span> <span data-ttu-id="e449c-116">Той ще бъде запазен като неактивен сегмент и не може да бъде активиран, завършен с валидна конфигурация.</span><span class="sxs-lookup"><span data-stu-id="e449c-116">It will be saved as an inactive segment, and can't be activated it finished with a valid configuration.</span></span>

1. <span data-ttu-id="e449c-117">Отидете на страницата **Сегменти**.</span><span class="sxs-lookup"><span data-stu-id="e449c-117">Go to the **Segments** page.</span></span>

1. <span data-ttu-id="e449c-118">Изберете **Нов** > **Празен сегмент**.</span><span class="sxs-lookup"><span data-stu-id="e449c-118">Select **New** > **Blank segment**.</span></span>

1. <span data-ttu-id="e449c-119">В **Нов сегмент** прозорец, изберете тип сегмент:</span><span class="sxs-lookup"><span data-stu-id="e449c-119">In the **New segment** pane, choose a segment type:</span></span>

   - <span data-ttu-id="e449c-120">**Динамични сегменти** [опресняване](segments.md#refresh-segments) по повтарящ се график.</span><span class="sxs-lookup"><span data-stu-id="e449c-120">**Dynamic segments** [refresh](segments.md#refresh-segments) on a recurring schedule.</span></span>
   - <span data-ttu-id="e449c-121">**Статични сегменти** стартирайте веднъж, когато го създадете.</span><span class="sxs-lookup"><span data-stu-id="e449c-121">**Static segments** run once when you create it.</span></span>

1. <span data-ttu-id="e449c-122">Предоставете **Име на изходния обект** за сегмента.</span><span class="sxs-lookup"><span data-stu-id="e449c-122">Provide an **Output entity name** for the segment.</span></span> <span data-ttu-id="e449c-123">По избор въведете показвано име и описание, които да помогнат за идентифицирането на сегмента.</span><span class="sxs-lookup"><span data-stu-id="e449c-123">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

1. <span data-ttu-id="e449c-124">Изберете **Напред**, за да преминете към страницата **Конструктор на сегменти**, където ще определите група.</span><span class="sxs-lookup"><span data-stu-id="e449c-124">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="e449c-125">Групата представлява набор от клиенти.</span><span class="sxs-lookup"><span data-stu-id="e449c-125">A group is a set of customers.</span></span>

1. <span data-ttu-id="e449c-126">Изберете обекта, който включва атрибута, по който искате да сегментирате.</span><span class="sxs-lookup"><span data-stu-id="e449c-126">Choose the entity that includes the attribute you want to segment by.</span></span>

1. <span data-ttu-id="e449c-127">Изберете атрибута, по който да се сегментира.</span><span class="sxs-lookup"><span data-stu-id="e449c-127">Choose the attribute to segment by.</span></span> <span data-ttu-id="e449c-128">Този атрибут може да има един от четирите типа стойности: числова, низ, дата или булева.</span><span class="sxs-lookup"><span data-stu-id="e449c-128">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

1. <span data-ttu-id="e449c-129">Изберете оператор и стойност за избрания атрибут.</span><span class="sxs-lookup"><span data-stu-id="e449c-129">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e449c-130">![Персонализиран филтър на група](media/customer-group-numbers.png "Филтър на група клиенти")</span><span class="sxs-lookup"><span data-stu-id="e449c-130">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="e449c-131">Число</span><span class="sxs-lookup"><span data-stu-id="e449c-131">Number</span></span> |<span data-ttu-id="e449c-132">Дефиниция</span><span class="sxs-lookup"><span data-stu-id="e449c-132">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="e449c-133">1</span><span class="sxs-lookup"><span data-stu-id="e449c-133">1</span></span>     |<span data-ttu-id="e449c-134">Entity</span><span class="sxs-lookup"><span data-stu-id="e449c-134">Entity</span></span>          |
   |<span data-ttu-id="e449c-135">2</span><span class="sxs-lookup"><span data-stu-id="e449c-135">2</span></span>     |<span data-ttu-id="e449c-136">Атрибут</span><span class="sxs-lookup"><span data-stu-id="e449c-136">Attribute</span></span>          |
   |<span data-ttu-id="e449c-137">3</span><span class="sxs-lookup"><span data-stu-id="e449c-137">3</span></span>    |<span data-ttu-id="e449c-138">Оператор</span><span class="sxs-lookup"><span data-stu-id="e449c-138">Operator</span></span>         |
   |<span data-ttu-id="e449c-139">4</span><span class="sxs-lookup"><span data-stu-id="e449c-139">4</span></span>    |<span data-ttu-id="e449c-140">Стойност</span><span class="sxs-lookup"><span data-stu-id="e449c-140">Value</span></span>         |

   1. <span data-ttu-id="e449c-141">За да добавите още условия към група, можете да използвате два логически оператора:</span><span class="sxs-lookup"><span data-stu-id="e449c-141">To add more conditions to a group, you can use two logical operators:</span></span>

      - <span data-ttu-id="e449c-142">Оператор **И**: И двете условия трябва да бъдат изпълнени като част от процеса на сегментиране.</span><span class="sxs-lookup"><span data-stu-id="e449c-142">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="e449c-143">Тази опция е най-полезна, когато дефинирате условия за различни обекти.</span><span class="sxs-lookup"><span data-stu-id="e449c-143">This option is most useful when you define conditions across different entities.</span></span>

      - <span data-ttu-id="e449c-144">Оператор **ИЛИ**: Едно от условията трябва да бъде изпълнено като част от процеса на сегментиране.</span><span class="sxs-lookup"><span data-stu-id="e449c-144">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="e449c-145">Тази опция е най-полезна, когато дефинирате няколко условия за един и същи обект.</span><span class="sxs-lookup"><span data-stu-id="e449c-145">This option is most useful when you define multiple conditions for the same entity.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="e449c-146">![Оператор ИЛИ, където трябва да бъде изпълнено едно от условията](media/segmentation-either-condition.png "Оператор ИЛИ, където трябва да бъде изпълнено едно от условията")</span><span class="sxs-lookup"><span data-stu-id="e449c-146">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

      <span data-ttu-id="e449c-147">В момента е възможно да се вложи оператор **ИЛИ** под оператор **И**, но не и обратното.</span><span class="sxs-lookup"><span data-stu-id="e449c-147">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

   1. <span data-ttu-id="e449c-148">Всяка група съвпада с набор от клиенти.</span><span class="sxs-lookup"><span data-stu-id="e449c-148">Each group matches set of customers.</span></span> <span data-ttu-id="e449c-149">Можете да комбинирате групи, за да включите клиентите, необходими за вашия бизнес случай.</span><span class="sxs-lookup"><span data-stu-id="e449c-149">You can combine groups to include the customers required for your business case.</span></span>    
   <span data-ttu-id="e449c-150">Изберете **Добавяне на група**.</span><span class="sxs-lookup"><span data-stu-id="e449c-150">Select **Add Group**.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="e449c-151">![Добавяне на група за група клиенти](media/customer-group-add-group.png "Добавяне на група за група клиенти")</span><span class="sxs-lookup"><span data-stu-id="e449c-151">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

   1. <span data-ttu-id="e449c-152">Изберете един от зададените оператори: **Съюз**, **Пресичане** или **С изключение**.</span><span class="sxs-lookup"><span data-stu-id="e449c-152">Select one of the set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e449c-153">![Добавяне на обединяване за група клиенти](media/customer-group-union.png "Добавяне на обединяване за група клиенти")</span><span class="sxs-lookup"><span data-stu-id="e449c-153">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   - <span data-ttu-id="e449c-154">**Обединяването** съединява двете групи.</span><span class="sxs-lookup"><span data-stu-id="e449c-154">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="e449c-155">**Пресичането** припокрива двете групи.</span><span class="sxs-lookup"><span data-stu-id="e449c-155">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="e449c-156">Само данни, които *са често срещани* в двете групи, се задържат в единната група.</span><span class="sxs-lookup"><span data-stu-id="e449c-156">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="e449c-157">**Освен** комбинира двете групи.</span><span class="sxs-lookup"><span data-stu-id="e449c-157">**Except** combines the two groups.</span></span> <span data-ttu-id="e449c-158">Само данни в група А, които *не са често срещани* за данните в група B, се задържат.</span><span class="sxs-lookup"><span data-stu-id="e449c-158">Only data in group A that *is not common* to data in group B is retained.</span></span>

1. <span data-ttu-id="e449c-159">Ако обекта е свързан с унифицирания обект на клиент чрез [релации](relationships.md), трябва да определите пътя на релацията, за да създадете валиден сегмент.</span><span class="sxs-lookup"><span data-stu-id="e449c-159">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="e449c-160">Добавяйте обектите от пътя на релацията, докато можете да изберете обекта **Клиент: CustomerInsights** от падащото меню.</span><span class="sxs-lookup"><span data-stu-id="e449c-160">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="e449c-161">След това изберете **Всички записи** за всяка стъпка.</span><span class="sxs-lookup"><span data-stu-id="e449c-161">Then, choose **All records** for each step.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e449c-162">![Път на релация по време на създаване на сегмент](media/segments-multiple-relationships.png "Път на релация по време на създаване на сегмент")</span><span class="sxs-lookup"><span data-stu-id="e449c-162">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

1. <span data-ttu-id="e449c-163">По подразбиране сегментите генерират изходен обект, който съдържа всички атрибути на клиентски профили, които съответстват на дефинираните филтри.</span><span class="sxs-lookup"><span data-stu-id="e449c-163">By default, segments generate an output entity that contains all attributes of customer profiles which match the defined filters.</span></span> <span data-ttu-id="e449c-164">Ако сегментът се основава на други обекти, различни от обект *Клиент*, можете да добавите още атрибути от тези обекти към изходния обект.</span><span class="sxs-lookup"><span data-stu-id="e449c-164">If a segment is based on other entities than the *Customer* entity, you can add more attributes from these entities to the output entity.</span></span> <span data-ttu-id="e449c-165">Изберете **Атрибути на проекта**, за да изберете атрибутите, които ще бъдат добавени към изходния обект.</span><span class="sxs-lookup"><span data-stu-id="e449c-165">Select **Project attributes** to choose the attributes that will be appended to the output entity.</span></span>  
  
   <span data-ttu-id="e449c-166">Пример: Сегментът се основава на обект, който съдържа данни за активността на клиентите, които са свързани с обект *Клиент*.</span><span class="sxs-lookup"><span data-stu-id="e449c-166">Example: A segment is based on an entity that contains customer activity data which is related to the *Customer* entity.</span></span> <span data-ttu-id="e449c-167">Сегментът търси всички клиенти, които са се обадили в бюрото за помощ през последните 60 дни.</span><span class="sxs-lookup"><span data-stu-id="e449c-167">The segment looks for all customers that called the help desk in the last 60 days.</span></span> <span data-ttu-id="e449c-168">Можете да изберете да добавите продължителността на разговора и броя на обажданията към всички съвпадащи клиентски записи в изходния обект.</span><span class="sxs-lookup"><span data-stu-id="e449c-168">You can choose to append the call duration and the number of calls to all matching customer records in the output entity.</span></span> <span data-ttu-id="e449c-169">Тази информация може да е полезна за изпращане на имейл с полезни връзки към онлайн помощни статии и често задавани въпроси на клиенти, които често са се обаждали.</span><span class="sxs-lookup"><span data-stu-id="e449c-169">This information might be useful to send an email with helpful links to online help articles and FAQs to customers who called frequently.</span></span>

   > [!NOTE]
   > - <span data-ttu-id="e449c-170">Проектираните атрибути работят само за обекти, които имат връзка едно към много с обекта на клиента.</span><span class="sxs-lookup"><span data-stu-id="e449c-170">Projected attributes only work for entities that have a one-to-many relationship with the customer entity.</span></span> <span data-ttu-id="e449c-171">Например, един клиент може да има няколко абонамента.</span><span class="sxs-lookup"><span data-stu-id="e449c-171">For example, one customer can have multiple subscriptions.</span></span>
   > - <span data-ttu-id="e449c-172">Можете да проектирате атрибути само от обект, който се използва във всяка група сегментни заявки, които изграждате.</span><span class="sxs-lookup"><span data-stu-id="e449c-172">You can only project attributes from an entity that is used in every group of segment query you are building.</span></span>
   > - <span data-ttu-id="e449c-173">Проектираните атрибути се вземат предвид, когато се използват оператори на множество.</span><span class="sxs-lookup"><span data-stu-id="e449c-173">Projected attributes are factored in when using set operators.</span></span>

1. <span data-ttu-id="e449c-174">Изберете **Записване**, за да запишете сегмента.</span><span class="sxs-lookup"><span data-stu-id="e449c-174">Select **Save** to save your segment.</span></span> <span data-ttu-id="e449c-175">Сегментът ще бъде записан и обработен, ако всички изисквания са потвърдени.</span><span class="sxs-lookup"><span data-stu-id="e449c-175">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="e449c-176">В противен случай ще бъде записан като чернова.</span><span class="sxs-lookup"><span data-stu-id="e449c-176">Otherwise, it will be saved as a draft.</span></span>

1. <span data-ttu-id="e449c-177">Изберете **Обратно към сегментите**, за да се върна на страницата **Сегменти**.</span><span class="sxs-lookup"><span data-stu-id="e449c-177">Select **Back to segments** to go back to the **Segments** page.</span></span>



## <a name="quick-segments"></a><span data-ttu-id="e449c-178">Бързи сегменти</span><span class="sxs-lookup"><span data-stu-id="e449c-178">Quick segments</span></span>

<span data-ttu-id="e449c-179">Бързите сегменти ви позволяват бързо да изграждате прости сегменти с един оператор за по-бърза информация.</span><span class="sxs-lookup"><span data-stu-id="e449c-179">Quick segments let you build simple segments with a single operator quickly for faster insights.</span></span>

1. <span data-ttu-id="e449c-180">На страницата **Сегменти** изберете **Създаване** > **сегмент от**.</span><span class="sxs-lookup"><span data-stu-id="e449c-180">On the **Segments** page, select **New** > **Create from**.</span></span>

   - <span data-ttu-id="e449c-181">Изберете опцията **Профили** за изграждане на сегмент, който се основава на обект на *унифициран клиент*.</span><span class="sxs-lookup"><span data-stu-id="e449c-181">Select the **Profiles** option to build a segment that is based on the *unified customer* entity.</span></span>
   - <span data-ttu-id="e449c-182">Изберете **Мерки** опция за изграждане на сегмент около мерки, които сте създали преди.</span><span class="sxs-lookup"><span data-stu-id="e449c-182">Select the **Measures** option to build a segment around  measures you have previously created.</span></span>
   - <span data-ttu-id="e449c-183">Изберете опцията **Разузнаване** за изграждане на сегмент по един от изходните обекти, който генерирахте чрез възможностите **Прогнози** или **Персонализирани модели**.</span><span class="sxs-lookup"><span data-stu-id="e449c-183">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="e449c-184">В диалоговия прозорец **Нов бърз сегмент** изберете атрибут от падащия списък **Поле**.</span><span class="sxs-lookup"><span data-stu-id="e449c-184">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="e449c-185">Системата ще предостави някои допълнителни аналитични данни, които ще ви помогнат да създадете по-добри сегменти за клиентите.</span><span class="sxs-lookup"><span data-stu-id="e449c-185">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="e449c-186">За полета на категории ще покажем 10-те най-добри клиенти.</span><span class="sxs-lookup"><span data-stu-id="e449c-186">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="e449c-187">Изберете **Стойност** и след това **Преглед**.</span><span class="sxs-lookup"><span data-stu-id="e449c-187">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="e449c-188">За числов атрибут системата ще покаже каква стойност на атрибута попада в рамките на процентила на всеки клиент.</span><span class="sxs-lookup"><span data-stu-id="e449c-188">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="e449c-189">Изберете **Оператор** и **Стойност**, след което изберете **Преглед**.</span><span class="sxs-lookup"><span data-stu-id="e449c-189">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="e449c-190">Системата ще ви предостави **Прогнозен размер на сегмента**.</span><span class="sxs-lookup"><span data-stu-id="e449c-190">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="e449c-191">Можете да изберете дали да генерирате определения от вас сегмент или първо да го преразгледате, за да получите различен размер на сегмента.</span><span class="sxs-lookup"><span data-stu-id="e449c-191">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="e449c-192">![Име и оценка за бърз сегмент](media/quick-segment-name.png "Име и оценка за бърз сегмент")</span><span class="sxs-lookup"><span data-stu-id="e449c-192">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="e449c-193">Посочете **Име** за сегмента.</span><span class="sxs-lookup"><span data-stu-id="e449c-193">Provide a **Name** for your segment.</span></span> <span data-ttu-id="e449c-194">По избор въведете **Показвано име**.</span><span class="sxs-lookup"><span data-stu-id="e449c-194">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="e449c-195">Изберете **Записване**, за да създадете сегмента.</span><span class="sxs-lookup"><span data-stu-id="e449c-195">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="e449c-196">След като обработката на сегмента завърши, можете да го прегледате като всеки друг сегмент, който сте създали.</span><span class="sxs-lookup"><span data-stu-id="e449c-196">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e449c-197">Следващи стъпки</span><span class="sxs-lookup"><span data-stu-id="e449c-197">Next steps</span></span>

<span data-ttu-id="e449c-198">[Експортирайте сегмент](export-destinations.md) и разгледайте [картата на клиента](customer-card-add-in.md) и [конекторите](export-power-bi.md), за да получите аналитични данни на ниво клиент.</span><span class="sxs-lookup"><span data-stu-id="e449c-198">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
