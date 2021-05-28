---
title: Предложения за сегменти, базирани на дейност.
description: Нека машинно обучение ви помогне да намерите нови и интересни сегменти въз основа на активността на клиентите.
ms.date: 05/11/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
ms.openlocfilehash: 14d9d4f0df6b5835f21fb63447d05853ee98a757
ms.sourcegitcommit: 8341fa964365c185b65bc4b71fc0c695ea127dc0
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 05/14/2021
ms.locfileid: "6034049"
---
# <a name="suggested-segments-based-on-activity-data-preview"></a><span data-ttu-id="e845d-103">Предложения за сегменти, базирани на данни за дейност (преглед)</span><span class="sxs-lookup"><span data-stu-id="e845d-103">Suggested segments based on activity data (preview)</span></span>

<span data-ttu-id="e845d-104">Открийте интересни сегменти от клиентите си въз основа на данни за активността на клиентите, които се поглъщат в Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="e845d-104">Discover interesting segments of your customers based on customer activity data that is ingested to Customer Insights.</span></span> <span data-ttu-id="e845d-105">Примери за данни за активност са транзакции, продължителност на разговора в подкрепа, покупки или връщания.</span><span class="sxs-lookup"><span data-stu-id="e845d-105">Examples of activity data are transactions, support call duration, purchases, or returns.</span></span> <span data-ttu-id="e845d-106">За да предложат сегменти, данните за дейността се анализират за актуалност, честота и парична стойност (или продължителност).</span><span class="sxs-lookup"><span data-stu-id="e845d-106">To suggest segments, activity data gets analyzed for recency, frequency, and monetary value (or duration).</span></span> <span data-ttu-id="e845d-107">Като алтернатива можете да генерирате [предложени сегменти, за да се подобри мярка или да се разбере по-добре какво влияе на даден атрибут](suggested-segments.md).</span><span class="sxs-lookup"><span data-stu-id="e845d-107">Alternatively, you can generate [suggested segments to improve a measure or better understand what influences an attribute](suggested-segments.md).</span></span>

:::image type="content" source="media/suggested-segments-tab.png" alt-text="Раздел „Предложени сегменти“, показващ предложения за сегменти за базирани на дейности и базирани на атрибути сегменти.":::

## <a name="categorize-customers-by-activity"></a><span data-ttu-id="e845d-109">Класифицирайте клиентите по дейности</span><span class="sxs-lookup"><span data-stu-id="e845d-109">Categorize customers by activity</span></span>

<span data-ttu-id="e845d-110">С [данни за дейността](activities.md) налични в Customer Insights, можем да генерираме предложения, които представляват групи клиенти:</span><span class="sxs-lookup"><span data-stu-id="e845d-110">With [activity data](activities.md) available in Customer Insights, we can generate suggestions that represent customer groups:</span></span>

- <span data-ttu-id="e845d-111">повечето активни клиенти</span><span class="sxs-lookup"><span data-stu-id="e845d-111">most active customers</span></span> 
- <span data-ttu-id="e845d-112">клиенти, които са направили най-много покупки</span><span class="sxs-lookup"><span data-stu-id="e845d-112">customers that have made the most purchases</span></span> 
- <span data-ttu-id="e845d-113">клиенти, които са генерирали най-много приходи</span><span class="sxs-lookup"><span data-stu-id="e845d-113">customers that generated the most revenue</span></span> 
- <span data-ttu-id="e845d-114">клиенти, които не са активни напоследък</span><span class="sxs-lookup"><span data-stu-id="e845d-114">customers who haven’t been active lately</span></span> 
- <span data-ttu-id="e845d-115">клиенти, които често взаимодействат с вашия бизнес</span><span class="sxs-lookup"><span data-stu-id="e845d-115">customers who frequently interact with your business</span></span>  

<span data-ttu-id="e845d-116">Ако имате бизнес на дребно, можете да разберете кои клиенти генерират най-много приходи и да ги възнаградите с купон.</span><span class="sxs-lookup"><span data-stu-id="e845d-116">If you have a retail business, you could find out which customers generate the most revenue and reward them with a coupon.</span></span> <span data-ttu-id="e845d-117">Или можете да идентифицирате случайни клиенти и да им предложите да се присъединят към програма за награди, така че те да посещават вашия бизнес по-често.</span><span class="sxs-lookup"><span data-stu-id="e845d-117">Or you can identify occasional customers and offer them to join a rewards program so they visit your business more often.</span></span>
<span data-ttu-id="e845d-118">Ако се занимавате със здравен бизнес, предоставящ обществено здравеопазване и вашата цел е да сведете до минимум разходите за отделни пациенти.</span><span class="sxs-lookup"><span data-stu-id="e845d-118">If you're in the healthcare business providing public healthcare and your goal is to minimize the expenses for individual patients.</span></span> <span data-ttu-id="e845d-119">Начин за това може да бъде намаляване на повтарящите се посещения чрез осигуряване на възможно най-добри грижи при възможно най-малко посещения.</span><span class="sxs-lookup"><span data-stu-id="e845d-119">A way to do so could be to reduce recurring visits by providing best possible care in as few visits as possible.</span></span> <span data-ttu-id="e845d-120">В този случай вашата цел е да поддържате ниската честота на посещенията и да сведете до минимум повтарящите се разходи за пациентите.</span><span class="sxs-lookup"><span data-stu-id="e845d-120">In this case, your goal is to keep the visit frequency low and minimize recurring cost for the patients.</span></span> <span data-ttu-id="e845d-121">Или можете да идентифицирате сегменти от пациенти, които имат чести срещи и високи повтарящи се разходи, и да анализирате тези случаи, за да подобрите лечението на индивида.</span><span class="sxs-lookup"><span data-stu-id="e845d-121">Or you can identify segments of patients who have frequent appointments and high recurring costs and analyze these cases to improve the treatment of the individual.</span></span> 

## <a name="required-data"></a><span data-ttu-id="e845d-122">Задължителни данни</span><span class="sxs-lookup"><span data-stu-id="e845d-122">Required data</span></span>

<span data-ttu-id="e845d-123">Предложенията се генерират въз основа на избраните входни данни.</span><span class="sxs-lookup"><span data-stu-id="e845d-123">Suggestions are generated based on the selected input data.</span></span> 

- <span data-ttu-id="e845d-124">Профили на клиенти: Всички клиенти или членове на определен сегмент.</span><span class="sxs-lookup"><span data-stu-id="e845d-124">Customer profiles: All customers or members of a specific segment.</span></span> 

- <span data-ttu-id="e845d-125">Период от време: Миналият месец, миналата година или всяка персонализирана времева рамка.</span><span class="sxs-lookup"><span data-stu-id="e845d-125">Time period: Last month, last year, or any custom time frame.</span></span>

- <span data-ttu-id="e845d-126">Тип дейност: покупки, транзакции на дребно, онлайн транзакции, случаи на поддръжка на клиенти, абонаменти и т.н.</span><span class="sxs-lookup"><span data-stu-id="e845d-126">Activity type: purchases, retail transactions, online transactions, customer support cases, subscriptions, and so on.</span></span>  

- <span data-ttu-id="e845d-127">Обект в Customer Insights, който съдържа данните за дейността: Обектът UnifiedActivity или обектът за конкретна дейност.</span><span class="sxs-lookup"><span data-stu-id="e845d-127">Entity in Customer Insights that contains the activity data: The UnifiedActivity entity or the entity for a specific activity.</span></span> 

- <span data-ttu-id="e845d-128">Размери, които да включват: Актуалност, честота или парично измерение, в зависимост от вашите бизнес изисквания.</span><span class="sxs-lookup"><span data-stu-id="e845d-128">Dimensions to include: Recency, frequency, or monetary dimension, depending on your business requirements.</span></span>

## <a name="generate-suggested-segments"></a><span data-ttu-id="e845d-129">Генериране на предложени сегменти</span><span class="sxs-lookup"><span data-stu-id="e845d-129">Generate suggested segments</span></span>

1. <span data-ttu-id="e845d-130">Към **Сегменти**.</span><span class="sxs-lookup"><span data-stu-id="e845d-130">Go to **Segments**.</span></span>

1. <span data-ttu-id="e845d-131">Изберете раздела **Предложения (визуализация)**.</span><span class="sxs-lookup"><span data-stu-id="e845d-131">Select the **Suggestions (preview)** tab.</span></span>

1. <span data-ttu-id="e845d-132">Изберете **Намерете нови предложения** и изберете **Вижте или предвидете поведението на клиентите**.</span><span class="sxs-lookup"><span data-stu-id="e845d-132">Select **Find new suggestions** and choose **See or anticipate customer behavior**.</span></span> <span data-ttu-id="e845d-133">Изберете **Започнете**, за да стартирате направляваното преживяване.</span><span class="sxs-lookup"><span data-stu-id="e845d-133">Select **Start** to run the guided experience.</span></span>

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="Първа стъпка от съветника за конфигуриране за предложен сегмент въз основа на активност.":::

1. <span data-ttu-id="e845d-135">Предоставете необходимите входни данни и изберете **Напред**, за да продължите.</span><span class="sxs-lookup"><span data-stu-id="e845d-135">Provide the required input data and select **Next** proceed.</span></span>

   - <span data-ttu-id="e845d-136">Изберете клиенти: Включете всички клиенти или определен сегмент.</span><span class="sxs-lookup"><span data-stu-id="e845d-136">Choose customers: Include all customers or a specific segment.</span></span>
   - <span data-ttu-id="e845d-137">Изберете дейност: Изберете вида на дейността и обектите, които описват дейността.</span><span class="sxs-lookup"><span data-stu-id="e845d-137">Choose activity: Select the activity type and the entities that describe the activity.</span></span>
   - <span data-ttu-id="e845d-138">Предпочитания: Задайте периода от време, който да разгледате, факторите за предложения и картографирайте атрибутите.</span><span class="sxs-lookup"><span data-stu-id="e845d-138">Preferences: Set the time period to consider, the factors for suggestions, and map the attributes.</span></span>

1. <span data-ttu-id="e845d-139">Прегледайте въведеното и изберете **Изпълнение**, за да стартирате модела и да генерирате предложения.</span><span class="sxs-lookup"><span data-stu-id="e845d-139">Review your input and select **Run** to run the model and generate suggestions.</span></span>

1. <span data-ttu-id="e845d-140">В зависимост от броя на потребителските профили и избраните дейности може да отнеме няколко минути.</span><span class="sxs-lookup"><span data-stu-id="e845d-140">Depending on the number of customer profiles and selected activities, it can take a few minutes to complete.</span></span> 

<span data-ttu-id="e845d-141">След генериране на предложенията можете да ги филтрирате по измерението или стойността, които ви интересуват най-много.</span><span class="sxs-lookup"><span data-stu-id="e845d-141">After generating the suggestions, you can filter them by the dimension or value you're most interested in.</span></span> 

## <a name="view-details-of-a-suggested-segment"></a><span data-ttu-id="e845d-142">Преглед на подробности на препоръчан сегмент</span><span class="sxs-lookup"><span data-stu-id="e845d-142">View details of a suggested segment</span></span>

<span data-ttu-id="e845d-143">След като предложенията бъдат генерирани, ще ги намерите в списъка **Сегменти** > **Предложения (преглед)** в **Предложения, основани на дейности** раздел.</span><span class="sxs-lookup"><span data-stu-id="e845d-143">Once the suggestions are generated, you'll find them listed on **Segments** > **Suggestions (preview)** in the **Activity-based suggestions** section.</span></span>

:::image type="content" source="media/suggested-segments-details.png" alt-text="Разгънат страничен прозорец, показващ подробни данни за предложен сегмент.":::

<span data-ttu-id="e845d-145">Изберете **Вижте предложението** върху предложен сегмент, за да видите подробностите за този сегмент.</span><span class="sxs-lookup"><span data-stu-id="e845d-145">Select **See suggestion** on a suggested segment to view the details of that segment.</span></span> <span data-ttu-id="e845d-146">Страничният прозорец предоставя подробности като степента на всяко измерение в сравнение с целевата група.</span><span class="sxs-lookup"><span data-stu-id="e845d-146">The side pane provides details like the extent of each dimension in comparison to the target group.</span></span> <span data-ttu-id="e845d-147">Той също така подчертава броя на потенциалните членове в сегмента и съответния процент от общия брой клиенти.</span><span class="sxs-lookup"><span data-stu-id="e845d-147">It also highlights the number of potential members in the segment and the corresponding percentage of the total customers.</span></span> <span data-ttu-id="e845d-148">Ако искате да запазите предложението като сегмент, изберете **Създаване на сегмент**.</span><span class="sxs-lookup"><span data-stu-id="e845d-148">If you want to keep the suggestion as a segment, select **Create segment**.</span></span>    

## <a name="save-a-suggestion-as-a-segment"></a><span data-ttu-id="e845d-149">Записване на предложение като сегмент</span><span class="sxs-lookup"><span data-stu-id="e845d-149">Save a suggestion as a segment</span></span>

1. <span data-ttu-id="e845d-150">Отидете на **Сегменти** > **Предложения (преглед)**.</span><span class="sxs-lookup"><span data-stu-id="e845d-150">Go to **Segments** > **Suggestions (preview)**.</span></span>

1. <span data-ttu-id="e845d-151">Изберете сегмента, който искате да запишете.</span><span class="sxs-lookup"><span data-stu-id="e845d-151">Select the segment you want to save.</span></span> 

1. <span data-ttu-id="e845d-152">В страничния прозорец изберете **Създаване на сегмент**.</span><span class="sxs-lookup"><span data-stu-id="e845d-152">In the side pane, select **Create segment**.</span></span> 

1. <span data-ttu-id="e845d-153">След като запазите сегмента, той ще се покаже в списъка със сегменти в **Всички сегменти** раздел. Сега може да бъде [обновен или изтрит като всеки друг сегмент](segments.md).</span><span class="sxs-lookup"><span data-stu-id="e845d-153">After saving the segment, it will show in the list of segments on the **All segments** tab. It can now be [refreshed or deleted like any other segment](segments.md).</span></span> <span data-ttu-id="e845d-154">Не можете да редактирате подробности за сегмента.</span><span class="sxs-lookup"><span data-stu-id="e845d-154">You can't edit the segment details.</span></span> <span data-ttu-id="e845d-155">Можете обаче да промените критериите за въвеждане на предложенията и да генерирате различни предложения.</span><span class="sxs-lookup"><span data-stu-id="e845d-155">However, you can change the input criteria for the suggestions and generate different suggestions.</span></span>

## <a name="refresh-or-edit-a-set-of-suggestions"></a><span data-ttu-id="e845d-156">Опреснете или редактирайте набор от предложения</span><span class="sxs-lookup"><span data-stu-id="e845d-156">Refresh or edit a set of suggestions</span></span>

1. <span data-ttu-id="e845d-157">Отидете на **Сегменти** > **Предложения (преглед)** и потърсете сегмента в **Предложения, основани на дейности** раздел.</span><span class="sxs-lookup"><span data-stu-id="e845d-157">Go to **Segments** > **Suggestions (preview)** and look for the segment in the **Activity-based suggestions** section.</span></span>

1. <span data-ttu-id="e845d-158">Изберете **Предложения за опресняване**, за да обновите предложенията, като същевременно запазите конфигурирани атрибути.</span><span class="sxs-lookup"><span data-stu-id="e845d-158">Select **Refresh suggestions** to refresh the suggestions while keeping configured attributes.</span></span> <span data-ttu-id="e845d-159">Или изберете **Редактиране на предложения** за промяна на конфигурираните атрибути.</span><span class="sxs-lookup"><span data-stu-id="e845d-159">Or select **Edit suggestions** to modify the configured attributes.</span></span> <span data-ttu-id="e845d-160">Системата ще повтори процеса, ще генерира предложения за сегменти въз основа на най-новите данни и ще замени текущите предложения.</span><span class="sxs-lookup"><span data-stu-id="e845d-160">The system will rerun the process, generate segment suggestions based on the latest data, and replace the current suggestions.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
