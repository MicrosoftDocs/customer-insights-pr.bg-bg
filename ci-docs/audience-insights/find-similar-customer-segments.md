---
title: Търсене на сходни клиенти с помощта на AI
description: Намиране на сходни клиентски сегменти с изкуствен интелект.
ms.date: 06/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: b9b2e7fa862b595c6a364a7208e42295b4f9df83
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268857"
---
# <a name="similar-customers-preview"></a><span data-ttu-id="b38ef-103">Сходни клиенти (преглед)</span><span class="sxs-lookup"><span data-stu-id="b38ef-103">Similar Customers (preview)</span></span>

<span data-ttu-id="b38ef-104">Тази функция ви позволява да намирате сходни клиенти в клиентската си база с помощта на изкуствен интелект.</span><span class="sxs-lookup"><span data-stu-id="b38ef-104">This feature lets you find similar customers in your customer base using artificial intelligence.</span></span> <span data-ttu-id="b38ef-105">Трябва да имате създаден поне един сегмент, за да използвате тази функция.</span><span class="sxs-lookup"><span data-stu-id="b38ef-105">You need to have at least one segment created to use this feature.</span></span> <span data-ttu-id="b38ef-106">Разширяването на критериите на съществуващ сегмент помага да се намерят клиенти, които са сходни на този сегмент.</span><span class="sxs-lookup"><span data-stu-id="b38ef-106">Expanding the criteria of an existing segment help find customers that are similar to that segment.</span></span>

> [!NOTE]
> <span data-ttu-id="b38ef-107">*Намиране на сходни клиенти* използва автоматизирани средства за оценка на данни и прави прогнози въз основа на тези данни, поради това има възможността да се използва като метод за профилиране, както този термин е определен от Общия регламент относно защитата на данните („GDPR“).</span><span class="sxs-lookup"><span data-stu-id="b38ef-107">*Find similar customers* uses automated means to evaluate data and make predictions based on that data, and therefore has the capability to be used as a method of profiling, as that term is defined by the General Data Protection Regulation (“GDPR”).</span></span> <span data-ttu-id="b38ef-108">Използването на тази функция от клиента за обработка на данни може да бъде предмет на GDPR или други закони или разпоредби.</span><span class="sxs-lookup"><span data-stu-id="b38ef-108">Customer’s use of this feature to process data may be subject to GDPR or other laws or regulations.</span></span> <span data-ttu-id="b38ef-109">Вие носите отговорност за това, че използвате Dynamics 365 Customer Insights, включително прогнози, е в съответствие с всички приложими закони и разпоредби, включително закони, свързани с неприкосновеността на личния живот, личните данни, биометричните данни, защитата на данните и поверителността на комуникациите.</span><span class="sxs-lookup"><span data-stu-id="b38ef-109">You are responsible for ensuring that your use of Dynamics 365 Customer Insights, including predictions, complies with all applicable laws and regulations, including laws related to privacy, personal data, biometric data, data protection, and confidentiality of communications.</span></span>

## <a name="finding-similar-customers"></a><span data-ttu-id="b38ef-110">Намиране на сходни клиенти</span><span class="sxs-lookup"><span data-stu-id="b38ef-110">Finding similar customers</span></span>

1. <span data-ttu-id="b38ef-111">В статията за аудиторията отидете на **Сегменти** и изберете сегмента, на който искате да базирате новия си сегмент.</span><span class="sxs-lookup"><span data-stu-id="b38ef-111">In audience insights, go to **Segments** and select the segment you want to base your new segment on.</span></span> <span data-ttu-id="b38ef-112">Това е вашият *изходен сегмент*.</span><span class="sxs-lookup"><span data-stu-id="b38ef-112">That's your *source segment*.</span></span>

1. <span data-ttu-id="b38ef-113">В лентата за действия изберете **Намиране на сходни клиенти**.</span><span class="sxs-lookup"><span data-stu-id="b38ef-113">In the action bar, select **Find similar customers**.</span></span>

1. <span data-ttu-id="b38ef-114">Прегледайте предложеното име за вашия нов сегмент и го променете, ако е необходимо.</span><span class="sxs-lookup"><span data-stu-id="b38ef-114">Review the suggested name for your new segment and change it if necessary.</span></span>

1. <span data-ttu-id="b38ef-115">Прегледайте полетата, които определят вашия нов сегмент.</span><span class="sxs-lookup"><span data-stu-id="b38ef-115">Review the fields that define your new segment.</span></span> <span data-ttu-id="b38ef-116">Тези полета определят основата, на която системата ще се опита да намери сходни клиенти на вашия изходен сегмент.</span><span class="sxs-lookup"><span data-stu-id="b38ef-116">These fields define the basis on which the system will try to find similar customers to your source segment.</span></span> <span data-ttu-id="b38ef-117">Системата ще избере препоръчаните полета по подразбиране.</span><span class="sxs-lookup"><span data-stu-id="b38ef-117">The system will select recommended fields by default.</span></span>
  <span data-ttu-id="b38ef-118">Полетата, които могат значително да намалят производителността на модела, се изключват автоматично:</span><span class="sxs-lookup"><span data-stu-id="b38ef-118">Fields that can significantly reduce the model performance are automatically excluded:</span></span>
  
   - <span data-ttu-id="b38ef-119">Полета със следните типове данни: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType</span><span class="sxs-lookup"><span data-stu-id="b38ef-119">Fields with the following data types: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType</span></span>
   - <span data-ttu-id="b38ef-120">Полета с множество (броят на елементите в поле) по-малко от 2 или повече от 30</span><span class="sxs-lookup"><span data-stu-id="b38ef-120">Fields with a cardinality (the number of elements in a field) of less than 2 or more than 30</span></span>

1. <span data-ttu-id="b38ef-121">Изберете дали искате да включите **Всички клиенти** или само клиенти в **Конкретен съществуващ сегмент** във вашия нов сегмент.</span><span class="sxs-lookup"><span data-stu-id="b38ef-121">Choose if you want to include **All customers** or only customers in a **Specific existing segment** in your new segment.</span></span>

1. <span data-ttu-id="b38ef-122">Изключете клиентите във вашия изходен сегмент, като поставите отметка в квадратчето **Изключване на всички в изходния сегмент**.</span><span class="sxs-lookup"><span data-stu-id="b38ef-122">Exclude customers in your source segment by selecting the **Exclude everyone in source segment** checkbox.</span></span>

1. <span data-ttu-id="b38ef-123">По подразбиране системата предлага да включите само 20% от размера на целевата аудитория във вашите резултати.</span><span class="sxs-lookup"><span data-stu-id="b38ef-123">By default, the system suggests including only 20% of the target audience size in your output.</span></span> <span data-ttu-id="b38ef-124">Редактирайте този праг според нуждите.</span><span class="sxs-lookup"><span data-stu-id="b38ef-124">Edit this threshold as needed.</span></span> <span data-ttu-id="b38ef-125">Увеличаването на прага ще намали точността.</span><span class="sxs-lookup"><span data-stu-id="b38ef-125">Increasing the threshold will reduce the precision.</span></span>

1. <span data-ttu-id="b38ef-126">Изберете **Изпълнение** в долната част на страницата, за да стартирате задача за двоична класификация (метод на машинно обучение), която анализира набора от данни.</span><span class="sxs-lookup"><span data-stu-id="b38ef-126">Select **Run** at the bottom of the page to start a binary classification task (a method of machine learning) which analyzes the dataset.</span></span>

## <a name="view-the-similar-segment"></a><span data-ttu-id="b38ef-127">Преглед на сходния сегмент</span><span class="sxs-lookup"><span data-stu-id="b38ef-127">View the similar segment</span></span>

<span data-ttu-id="b38ef-128">След като обработите сходния сегмент, ще намерите новия сегмент, посочен в страницата **Сегменти**.</span><span class="sxs-lookup"><span data-stu-id="b38ef-128">After processing the similar segment, you'll find the new segment listed on the **Segments** page.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b38ef-129">![Сходен клиентски сегмент](media/expanded-segment.png "Сходен клиентски сегмент")</span><span class="sxs-lookup"><span data-stu-id="b38ef-129">![Similar customers segment](media/expanded-segment.png "Similar customers segment")</span></span>

<span data-ttu-id="b38ef-130">Изберете **Преглед** в лентата за действия, за да отворите подробностите за сегмента.</span><span class="sxs-lookup"><span data-stu-id="b38ef-130">Select **View** in the action bar to open the segment detail.</span></span> <span data-ttu-id="b38ef-131">Този преглед съдържа информация за разпределението на резултатите във всички [оценки за сходство](#about-similarity-scores).</span><span class="sxs-lookup"><span data-stu-id="b38ef-131">This view contains information about the result distribution across [similarity scores](#about-similarity-scores).</span></span> <span data-ttu-id="b38ef-132">Също така ще намерите стойностите на оценките за сходство в **Преглед на членове на сегмента**.</span><span class="sxs-lookup"><span data-stu-id="b38ef-132">You'll also find the similarity score values in the **Segment members preview**.</span></span>

## <a name="use-the-output-of-a-similar-segment"></a><span data-ttu-id="b38ef-133">Използване на резултата от сходен сегмент</span><span class="sxs-lookup"><span data-stu-id="b38ef-133">Use the output of a similar segment</span></span>

<span data-ttu-id="b38ef-134">Можете да [работите с резултата от сходен сегмент](segments.md), както правите с други сегменти.</span><span class="sxs-lookup"><span data-stu-id="b38ef-134">You can [work with the output of a similar segment](segments.md) as you do with other segments.</span></span> <span data-ttu-id="b38ef-135">Например да експортирате сегмента или да създадете мярка.</span><span class="sxs-lookup"><span data-stu-id="b38ef-135">For example, export the segment or build a measure.</span></span>

## <a name="refresh-and-edit-a-similar-segment"></a><span data-ttu-id="b38ef-136">Обновяване и редактиране на сходен сегмент</span><span class="sxs-lookup"><span data-stu-id="b38ef-136">Refresh and edit a similar segment</span></span>

<span data-ttu-id="b38ef-137">За да опресните сходен сегмент, изберете го в страницата **Сегменти** и изберете **Обновяване** в лентата за действия.</span><span class="sxs-lookup"><span data-stu-id="b38ef-137">To refresh a similar segment, select it on the **Segments** page and select **Refresh** in the action bar.</span></span>

<span data-ttu-id="b38ef-138">Редактирането на сходен сегмент ще обработи отново вашите данни.</span><span class="sxs-lookup"><span data-stu-id="b38ef-138">Editing a similar segment will reprocess your data.</span></span> <span data-ttu-id="b38ef-139">Създаденият преди това сегмент се актуализира с обновени данни.</span><span class="sxs-lookup"><span data-stu-id="b38ef-139">The previously created segment gets updated with refreshed data.</span></span>    
<span data-ttu-id="b38ef-140">За да редактирате сходен сегмент, изберете го в страницата **Сегменти** и изберете **Редактиране** в лентата за действия.</span><span class="sxs-lookup"><span data-stu-id="b38ef-140">To edit a similar segment, select it on the **Segments** page and select **Edit** in the action bar.</span></span> <span data-ttu-id="b38ef-141">Приложете промените и изберете **Изпълнение**, за да започне обработката.</span><span class="sxs-lookup"><span data-stu-id="b38ef-141">Apply your changes and select **Run** to start the processing.</span></span>

## <a name="delete-a-similar-segment"></a><span data-ttu-id="b38ef-142">Изтриване на сходен сегмент</span><span class="sxs-lookup"><span data-stu-id="b38ef-142">Delete a similar segment</span></span>

<span data-ttu-id="b38ef-143">Изберете сегмента в страницата **Сегменти** и изберете **Изтриване** в лентата за действия.</span><span class="sxs-lookup"><span data-stu-id="b38ef-143">Select the segment on the **Segments** page and select **Delete** in the action bar.</span></span> <span data-ttu-id="b38ef-144">След това потвърдете изтриването.</span><span class="sxs-lookup"><span data-stu-id="b38ef-144">Then, confirm your deletion.</span></span>

## <a name="about-similarity-scores"></a><span data-ttu-id="b38ef-145">Относно оценките за сходство</span><span class="sxs-lookup"><span data-stu-id="b38ef-145">About similarity scores</span></span>

<span data-ttu-id="b38ef-146">Моделът за машинно обучение с двоична класификация присвоява резултат на клиентите в сходен сегмент.</span><span class="sxs-lookup"><span data-stu-id="b38ef-146">The binary classification machine learning model assigns a score to customers in the similar segment.</span></span> <span data-ttu-id="b38ef-147">Оценката се основава на сходството с клиентите в изходния сегмент.</span><span class="sxs-lookup"><span data-stu-id="b38ef-147">The score is based on the similarity to customers in the source segment.</span></span>

- <span data-ttu-id="b38ef-148">Оценките за сходство под 0,55 са клиенти, които са класифицирани от системата, че *не са сходни* на клиентите в изходния сегмент</span><span class="sxs-lookup"><span data-stu-id="b38ef-148">Similarity scores below 0.55 are customers the system classified as *not similar* to customers in the source segment</span></span>
- <span data-ttu-id="b38ef-149">Оценките за сходство 0,55 – 0,7 се класифицират като *донякъде сходни*</span><span class="sxs-lookup"><span data-stu-id="b38ef-149">Similarity scores between 0.55 – 0.7 are classified as *somewhat similar*</span></span>
- <span data-ttu-id="b38ef-150">Оценките за сходство 0,7 – 0,85 се класифицират като *сходни*</span><span class="sxs-lookup"><span data-stu-id="b38ef-150">Similarity scores between 0.7 – 0.85 are classified as *similar*</span></span>
- <span data-ttu-id="b38ef-151">Оценките за сходство 0,85 – 1 са клиенти, класифицирани от системата като *много сходни*</span><span class="sxs-lookup"><span data-stu-id="b38ef-151">Similarity scores between 0.85 – 1 are customers the system classified as *very similar*</span></span>

<span data-ttu-id="b38ef-152">Клиентите с оценки за сходство под 0,4 не се включват в резултата от модела.</span><span class="sxs-lookup"><span data-stu-id="b38ef-152">Customers with similarity scores below 0.4 aren't included in the model output.</span></span> <span data-ttu-id="b38ef-153">Системата не ги счита за достатъчно сходни с изходния сегмент.</span><span class="sxs-lookup"><span data-stu-id="b38ef-153">The system doesn't consider them similar enough to the source segment.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]