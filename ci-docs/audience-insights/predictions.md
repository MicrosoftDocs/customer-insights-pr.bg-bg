---
title: Попълнете частични данни с помощта на прогнози
description: Използвайте прогнози за попълване на непълни клиентски данни.
ms.date: 05/05/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: zacook
manager: shellyha
ms.openlocfilehash: 66f0b16b5d05741ab98ca5ce2157da8c46b6d9e0
ms.sourcegitcommit: 5379c2b77d613d071a177f509e6417ebf3c47516
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 11/26/2020
ms.locfileid: "4648698"
---
# <a name="complete-your-partial-data-with-predictions"></a><span data-ttu-id="ffb29-103">Попълване на частичните данни с прогнози</span><span class="sxs-lookup"><span data-stu-id="ffb29-103">Complete your partial data with predictions</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="ffb29-104">Прогнозите ви позволяват лесно да създавате прогнозирани стойности, които могат да подобрят разбирането ви за клиент.</span><span class="sxs-lookup"><span data-stu-id="ffb29-104">Predictions lets you easily create predicted values that can enhance your understanding of a customer.</span></span> <span data-ttu-id="ffb29-105">На страницата **Разузнаване** > **Прогнози** можете да изберете **Моите прогнози**, за да видите прогнози, които сте конфигурирали в други части на статистика за аудиторията, и да ви позволи допълнително да ги персонализирате.</span><span class="sxs-lookup"><span data-stu-id="ffb29-105">On the **Intelligence** > **Predictions** page, you can select **My predictions** to see predictions that you've configured in other parts of audience insights, and allow you to further customize them.</span></span>

> [!NOTE]
> <span data-ttu-id="ffb29-106">Не можете да използвате тази функция, ако средата ви използва съхранение на Azure Data Lake Gen 2.</span><span class="sxs-lookup"><span data-stu-id="ffb29-106">You can't use this feature if your environment uses Azure Data Lake Gen 2 storage.</span></span>
>
> <span data-ttu-id="ffb29-107">Функцията за прогнози използва автоматизирани средства за оценка на данни и създаване на прогнози въз основа на тези данни и следователно има възможност да се използва като метод за профилиране съгласно определението на този термин в Общия регламент относно защитата на данните (GDPR).</span><span class="sxs-lookup"><span data-stu-id="ffb29-107">The predictions feature uses automated means to evaluate data and make predictions based on that data, and therefore has the capability to be used as a method of profiling, as that term is defined by the General Data Protection Regulation ("GDPR").</span></span> <span data-ttu-id="ffb29-108">Използването на тази функция от клиента за обработка на данни може да бъде предмет на GDPR или други закони или разпоредби.</span><span class="sxs-lookup"><span data-stu-id="ffb29-108">Customer's use of this feature to process data may be subject to GDPR or other laws or regulations.</span></span> <span data-ttu-id="ffb29-109">Вие носите отговорност за това, че използвате Dynamics 365 Customer Insights, включително прогнози, е в съответствие с всички приложими закони и разпоредби, включително закони, свързани с неприкосновеността на личния живот, личните данни, биометричните данни, защитата на данните и поверителността на комуникациите.</span><span class="sxs-lookup"><span data-stu-id="ffb29-109">You are responsible for ensuring that your use of Dynamics 365 Customer Insights, including predictions, complies with all applicable laws and regulations, including laws related to privacy, personal data, biometric data, data protection, and confidentiality of communications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ffb29-110">Предварителни изисквания</span><span class="sxs-lookup"><span data-stu-id="ffb29-110">Prerequisites</span></span>

<span data-ttu-id="ffb29-111">Преди организацията да може да използва функцията за прогнози, трябва да са изпълнени следните предварителни изисквания:</span><span class="sxs-lookup"><span data-stu-id="ffb29-111">Before your organization can use the predictions feature, the following prerequisites must be met:</span></span>

1. <span data-ttu-id="ffb29-112">Вашата организация има екземпляр [създаден в Common Data Service](https://docs.microsoft.com/ai-builder/build-model#prerequisites) и е в същата организация като Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="ffb29-112">Your organization has an instance [set up in the Common Data Service](https://docs.microsoft.com/ai-builder/build-model#prerequisites) and it's in the same organization as Customer Insights.</span></span>

2. <span data-ttu-id="ffb29-113">Вашата среда е привързана към вашия екземпляр на Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="ffb29-113">Your environment is attached to your Common Data Service instance.</span></span>

<span data-ttu-id="ffb29-114">Ако [създавате нова среда](manage-environments.md), конфигурирайте я в диалоговия прозорец **Създаване на среда** и изберете **Разширени**.</span><span class="sxs-lookup"><span data-stu-id="ffb29-114">If you're [creating a new environment](manage-environments.md), configure it in the **Create an environment** dialog and select **Advanced**.</span></span> <span data-ttu-id="ffb29-115">Ако вече сте създали среда, отидете в настройките и изберете **Разширени**.</span><span class="sxs-lookup"><span data-stu-id="ffb29-115">If you've already created an environment, go to its settings and select **Advanced**.</span></span> <span data-ttu-id="ffb29-116">Така или иначе, в секцията **Използване на прогнози** въведете URL адрес на екземпляр на Common Data Service, към който искате да прикачите вашата среда.</span><span class="sxs-lookup"><span data-stu-id="ffb29-116">Either way, in the **Use predictions** section, enter the Common Data Service instance URL to which you want to attach your environment.</span></span>

## <a name="create-a-prediction-in-the-customer-entity"></a><span data-ttu-id="ffb29-117">Създаване на прогноза в обекта на клиента</span><span class="sxs-lookup"><span data-stu-id="ffb29-117">Create a prediction in the Customer entity</span></span>

1. <span data-ttu-id="ffb29-118">В статията за аудиторията отидете на **Данни** > **Обекти**.</span><span class="sxs-lookup"><span data-stu-id="ffb29-118">In audience insights, go to **Data** > **Entities**.</span></span>

2. <span data-ttu-id="ffb29-119">Изберете обекта **Клиент**.</span><span class="sxs-lookup"><span data-stu-id="ffb29-119">Select the **Customer** entity.</span></span>

3. <span data-ttu-id="ffb29-120">В обекта **Клиент: CustomerInsights** изберете раздела **Полета**.</span><span class="sxs-lookup"><span data-stu-id="ffb29-120">In the **Customer:CustomerInsights** entity, select on the **Fields** tab.</span></span>

4. <span data-ttu-id="ffb29-121">Намерете името на атрибута, за който искате да прогнозирате стойности, след което изберете иконата **Преглед** в колоната **Обобщение**.</span><span class="sxs-lookup"><span data-stu-id="ffb29-121">Find the attribute name you wish to predict values for, then select the **Overview** icon in the **Summary** column.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ffb29-122">![Икона за преглед](media/intelligence-overviewicon.png "Икона за преглед")</span><span class="sxs-lookup"><span data-stu-id="ffb29-122">![Overview icon](media/intelligence-overviewicon.png "Overview icon")</span></span>

5. <span data-ttu-id="ffb29-123">Ако за атрибута ви има висок процент липсващи стойности, изберете **Прогнозиране на липсващи стойности**, за да продължите с прогнозирането.</span><span class="sxs-lookup"><span data-stu-id="ffb29-123">If there's a high rate of missing values for your attribute, select **Predict missing values** to continue with your prediction.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ffb29-124">![Преглед на състоянието с показан бутон за прогнозиране на липсващи стойности](media/intelligence-overviewpredictmissingvalues.png "Преглед на състоянието с показан бутон за прогнозиране на липсващи стойности")</span><span class="sxs-lookup"><span data-stu-id="ffb29-124">![Overview status with predict missing values button shown](media/intelligence-overviewpredictmissingvalues.png "Overview status with predict missing values button shown")</span></span>

6. <span data-ttu-id="ffb29-125">Въведете **Показвано име** и **Име на изходен обект** за резултатите от прогнозата.</span><span class="sxs-lookup"><span data-stu-id="ffb29-125">Provide a **Display name** and an **Output entity name** for the results of the prediction.</span></span>

7. <span data-ttu-id="ffb29-126">Предварително попълнен списък с опции ще покаже къде можете да нанесете стойностите с категория на прогнози.</span><span class="sxs-lookup"><span data-stu-id="ffb29-126">A pre-populated list of options will show where you can map the values to a predicted category.</span></span> <span data-ttu-id="ffb29-127">В този случай категорията може да бъде само 0 или 1, тъй като се нанася към вярно/невярно, т.е. двоичен вид на прогнозата.</span><span class="sxs-lookup"><span data-stu-id="ffb29-127">In this case, your only category options will be 0 or 1, as they map to the true/false or binary nature of the prediction.</span></span> <span data-ttu-id="ffb29-128">В колоната „Категория” нанесете стойностите на полето, които бихте искали да бъдат класифицирани като „0” в окончателната прогноза, като „0”, а елементите, които искате да бъдат класифицирани като „1” в окончателната прогноза, като „1”.</span><span class="sxs-lookup"><span data-stu-id="ffb29-128">In the Category column, map the field values you'd like to be classified as "0" in the final prediction to "0", and the items you'd like to be classified as "1" in the final prediction to "1".</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ffb29-129">![Пример, показващ нанесени стойности на поле с категории](media/intelligence-categorymapping.png "Пример, показващ нанесени стойности на поле с категории")</span><span class="sxs-lookup"><span data-stu-id="ffb29-129">![Example showing mapped field values to categories](media/intelligence-categorymapping.png "Example showing mapped field values to categories")</span></span>

8. <span data-ttu-id="ffb29-130">Изберете **Готово** и прогнозата ще бъде обработена.</span><span class="sxs-lookup"><span data-stu-id="ffb29-130">Select **Done** and the prediction will be processed.</span></span> <span data-ttu-id="ffb29-131">Обработката ще отнеме известно време, в зависимост от размера и сложността на данните.</span><span class="sxs-lookup"><span data-stu-id="ffb29-131">The processing will take some time, depending on the size and complexity of data.</span></span> <span data-ttu-id="ffb29-132">Резултатите ще бъдат достъпни в нов обект, базиран на **Име на изходен обект** на прогнозата, която създадохте.</span><span class="sxs-lookup"><span data-stu-id="ffb29-132">Results will be available in a new entity based on the **Output entity name** of the prediction you created.</span></span>

## <a name="create-a-prediction-while-creating-a-segment"></a><span data-ttu-id="ffb29-133">Създаване на прогноза при създаване на сегмент</span><span class="sxs-lookup"><span data-stu-id="ffb29-133">Create a prediction while creating a segment</span></span>

<span data-ttu-id="ffb29-134">Прогнозирането на липсващи стойности за определен атрибут по избор е възможно и при създаването на сегмент.</span><span class="sxs-lookup"><span data-stu-id="ffb29-134">Predicting missing values for a specific attribute of choice is also possible when creating a segment.</span></span> <span data-ttu-id="ffb29-135">По-конкретно, когато бързо създавате сегмент, базиран на унифицирания обект на клиент или обект Customer_Measure.</span><span class="sxs-lookup"><span data-stu-id="ffb29-135">Specifically, when you quickly create a segment based on either your unified Customer entity or Customer_Measure entity.</span></span>

<span data-ttu-id="ffb29-136">Като част от този поток избирате конкретен атрибут, върху който базирате сегмента, като например удовлетвореност на клиента или сума на покупка.</span><span class="sxs-lookup"><span data-stu-id="ffb29-136">As part of this flow, you'll choose a specific attribute to base your segment on, such as Customer Satisfaction or Purchase Amount.</span></span> <span data-ttu-id="ffb29-137">При създаването на сегмент системата ще предложи метод за прогнозиране на липсващи стойности за този атрибут.</span><span class="sxs-lookup"><span data-stu-id="ffb29-137">Upon segment creation, the system will suggest a method for predicting any missing values for this attribute.</span></span>

1. <span data-ttu-id="ffb29-138">В статията за аудиторията отидете на **Сегменти** и изберете плочката **Профили**.</span><span class="sxs-lookup"><span data-stu-id="ffb29-138">In audience insights, go to **Segments** and select the **Profiles** tile.</span></span>

2. <span data-ttu-id="ffb29-139">Изберете **Поле** за създаването на сегмента и изберете **Оператор**, след което изберете **Преглед**.</span><span class="sxs-lookup"><span data-stu-id="ffb29-139">Choose a **Field** to create a segment on and select an **Operator**, then select **Review**.</span></span>

3. <span data-ttu-id="ffb29-140">Въведете **Име** и **Показвано име** за сегмента.</span><span class="sxs-lookup"><span data-stu-id="ffb29-140">Provide a **Name** and a **Display name** for the segment.</span></span>

4. <span data-ttu-id="ffb29-141">Изберете **Записване**.</span><span class="sxs-lookup"><span data-stu-id="ffb29-141">Select **Save**.</span></span>

5. <span data-ttu-id="ffb29-142">Ако сегментът, който създадохте, съдържа непълни данни в изходното поле, можете да изберете прогнозиране на липсващите стойности.</span><span class="sxs-lookup"><span data-stu-id="ffb29-142">If the segment you created has incomplete data in the source field, you can choose to predict the missing values.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ffb29-143">![Бутон за прогноза](media/segments-predictoption.png "Бутон за прогноза")</span><span class="sxs-lookup"><span data-stu-id="ffb29-143">![Prediction button](media/segments-predictoption.png "Prediction button")</span></span>

6. <span data-ttu-id="ffb29-144">Въведете **Показвано име** и **Име на изходен обект** за резултатите от прогнозата.</span><span class="sxs-lookup"><span data-stu-id="ffb29-144">Provide a **Display name** and an **Output entity name** for the results of the prediction.</span></span>

7. <span data-ttu-id="ffb29-145">Изберете **Готово**.</span><span class="sxs-lookup"><span data-stu-id="ffb29-145">Select **Done**.</span></span> <span data-ttu-id="ffb29-146">Прогнозата ви ще бъде генерирана скоро в нов обект с името, което предоставихте за **Име на изходен обект**.</span><span class="sxs-lookup"><span data-stu-id="ffb29-146">Your prediction will be generated shortly in a new entity with the name you provided for the **Output entity name**.</span></span>

## <a name="view-a-prediction"></a><span data-ttu-id="ffb29-147">Преглед на прогноза</span><span class="sxs-lookup"><span data-stu-id="ffb29-147">View a prediction</span></span>

1. <span data-ttu-id="ffb29-148">В статията за аудиторията отидете на **Разузнаване** > **Прогнози** > **Моите прогнози**.</span><span class="sxs-lookup"><span data-stu-id="ffb29-148">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="ffb29-149">Изберете прогнозата, която искате да прегледате.</span><span class="sxs-lookup"><span data-stu-id="ffb29-149">Select the prediction you want to review.</span></span>

3. <span data-ttu-id="ffb29-150">Изберете многоточието в колоната **Действия** и изберете **Преглед**.</span><span class="sxs-lookup"><span data-stu-id="ffb29-150">Select the ellipsis in the **Actions** column and choose **View**.</span></span>

4. <span data-ttu-id="ffb29-151">В изгледа на прогнозата ще видите няколко точки от данни.</span><span class="sxs-lookup"><span data-stu-id="ffb29-151">You'll see a number of data points in the view of your prediction.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ffb29-152">![Страница с прогнози](media/intelligence-predictionsviewpage.png "Страница с прогнози")</span><span class="sxs-lookup"><span data-stu-id="ffb29-152">![Predictions page](media/intelligence-predictionsviewpage.png "Predictions page")</span></span>

   - <span data-ttu-id="ffb29-153">**Прогнозирани стойности** показва нанасянето, което създадохте във фазата на нанасяне на стойност на поле към категория.</span><span class="sxs-lookup"><span data-stu-id="ffb29-153">**Predicted values** shows the mapping you created during the Field value to Category mapping phase.</span></span> <span data-ttu-id="ffb29-154">Тези са стойностите в набора от данни, които са нанесени към конкретна категория.</span><span class="sxs-lookup"><span data-stu-id="ffb29-154">These are the values in your dataset that have been mapped to a specific category.</span></span>
   <span data-ttu-id="ffb29-155">-**Най-влиятелни** са факторите в набора от данни с най-голяма вероятност да повлияят върху достоверността на прогнозата за нанасяне на стойността на полето към конкретна категория.</span><span class="sxs-lookup"><span data-stu-id="ffb29-155">-**Top influencers** are the factors within your dataset that were most likely to influence the prediction's confidence of your Field value being mapped to a specific category.</span></span>
   - <span data-ttu-id="ffb29-156">**Представяне** показва как се представят прогнозите.</span><span class="sxs-lookup"><span data-stu-id="ffb29-156">**Performance** indicates how the predictions are doing.</span></span> <span data-ttu-id="ffb29-157">Изберете връзката, за да научите повече.</span><span class="sxs-lookup"><span data-stu-id="ffb29-157">Select the link to learn more.</span></span>
   - <span data-ttu-id="ffb29-158">**Преглед** показва примери за набора от изходни данни от прогнозата и вероятността или достоверността на прогнозираната стойност, като 0 е несигурна, а 1 е сигурна.</span><span class="sxs-lookup"><span data-stu-id="ffb29-158">**Preview** shows samples of the output dataset from your prediction and the likelihood, or our confidence, of the predicted value where 0 is uncertain, and 1 is certain.</span></span>

## <a name="update-a-prediction"></a><span data-ttu-id="ffb29-159">Актуализиране на прогноза</span><span class="sxs-lookup"><span data-stu-id="ffb29-159">Update a prediction</span></span>

1. <span data-ttu-id="ffb29-160">В статията за аудиторията отидете на **Разузнаване** > **Прогнози** > **Моите прогнози**.</span><span class="sxs-lookup"><span data-stu-id="ffb29-160">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="ffb29-161">Изберете прогнозата, която искате да актуализирате, и изберете иконата **Актуализиране**.</span><span class="sxs-lookup"><span data-stu-id="ffb29-161">Select the prediction you want to update and select the **Update** icon.</span></span>

3. <span data-ttu-id="ffb29-162">Прогнозата ще бъде планирана за обработка.</span><span class="sxs-lookup"><span data-stu-id="ffb29-162">The prediction will be scheduled for processing.</span></span> <span data-ttu-id="ffb29-163">Можете да видите времето на последната актуализация в колоната **Актуализирано** на страницата **Прогнози**.</span><span class="sxs-lookup"><span data-stu-id="ffb29-163">You can see the time it was last updated in the **Updated** column of the **Predictions** page.</span></span>

## <a name="edit-a-prediction"></a><span data-ttu-id="ffb29-164">Редактиране на прогноза</span><span class="sxs-lookup"><span data-stu-id="ffb29-164">Edit a prediction</span></span>

<span data-ttu-id="ffb29-165">След като сте създали прогноза, можете да персонализирате модела в AI Builder, за да увеличите ефективността му.</span><span class="sxs-lookup"><span data-stu-id="ffb29-165">After you've created a prediction, you can customize the model in the AI Builder to increase the effectiveness of your model.</span></span>  

1. <span data-ttu-id="ffb29-166">В статията за аудиторията отидете на **Разузнаване** > **Прогнози** > **Моите прогнози**.</span><span class="sxs-lookup"><span data-stu-id="ffb29-166">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="ffb29-167">Изберете прогнозата, която искате да редактирате.</span><span class="sxs-lookup"><span data-stu-id="ffb29-167">Select the prediction you want to edit.</span></span>

3. <span data-ttu-id="ffb29-168">Изберете многоточието в колоната **Действия** и изберете **Преглед**.</span><span class="sxs-lookup"><span data-stu-id="ffb29-168">Select the ellipsis in the **Actions** column and choose **View**.</span></span>

4. <span data-ttu-id="ffb29-169">Изберете **Персонализиране в AI Builder**.</span><span class="sxs-lookup"><span data-stu-id="ffb29-169">Select **Customize in AI Builder**.</span></span>

5. <span data-ttu-id="ffb29-170">Актуализирайте модела в AI Builder.</span><span class="sxs-lookup"><span data-stu-id="ffb29-170">Update your model in the AI Builder.</span></span> <span data-ttu-id="ffb29-171">[Научете повече за управлението на модели в AI Builder](https://docs.microsoft.com/ai-builder/manage-model#retrain-and-republish-existing-models).</span><span class="sxs-lookup"><span data-stu-id="ffb29-171">[Learn more about managing models in the AI builder](https://docs.microsoft.com/ai-builder/manage-model#retrain-and-republish-existing-models).</span></span>

<span data-ttu-id="ffb29-172">Следващото изпълнение на прогнозата ще използва създадения от вас актуализиран модел.</span><span class="sxs-lookup"><span data-stu-id="ffb29-172">The next run of your prediction will use the updated model you've created.</span></span>

> [!NOTE]
> <span data-ttu-id="ffb29-173">Новите модели, създадени в AI Builder, няма да се показват в статистика за аудиторията, освен ако моделът е създаден от изброените по-горе преживявания.</span><span class="sxs-lookup"><span data-stu-id="ffb29-173">New models created in AI Builder will not be displayed in audience insights unless the model was created from the experiences listed above.</span></span>

## <a name="remove-a-prediction"></a><span data-ttu-id="ffb29-174">Премахване на прогноза</span><span class="sxs-lookup"><span data-stu-id="ffb29-174">Remove a prediction</span></span>

1. <span data-ttu-id="ffb29-175">В статията за аудиторията отидете на **Разузнаване** > **Прогнози** > **Моите прогнози**.</span><span class="sxs-lookup"><span data-stu-id="ffb29-175">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="ffb29-176">Изберете прогнозата, който искате да изтриете.</span><span class="sxs-lookup"><span data-stu-id="ffb29-176">Select the prediction you want to delete.</span></span>

3. <span data-ttu-id="ffb29-177">Изберете многоточието в колоната **Действия** и изберете **Изтриване**.</span><span class="sxs-lookup"><span data-stu-id="ffb29-177">Select the ellipsis in the **Actions** column and choose **Delete**.</span></span>

4. <span data-ttu-id="ffb29-178">Потвърдете изтриването.</span><span class="sxs-lookup"><span data-stu-id="ffb29-178">Confirm the deletion.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="ffb29-179">Отстраняване на неизправности</span><span class="sxs-lookup"><span data-stu-id="ffb29-179">Troubleshooting</span></span>

<span data-ttu-id="ffb29-180">Ако не можете да завършите процеса на прикачване на Common Data Service поради грешка, можете да опитате да завършите процеса ръчно.</span><span class="sxs-lookup"><span data-stu-id="ffb29-180">If you can't complete the attach Common Data Service process due to an error, you can try to complete the process manually.</span></span> <span data-ttu-id="ffb29-181">Има два известни проблема, които могат да възникнат в процеса на прикачване:</span><span class="sxs-lookup"><span data-stu-id="ffb29-181">There are two known issues that can occur in the attach process:</span></span>

- <span data-ttu-id="ffb29-182">Решението за добавка на клиентска карта не е инсталирано.</span><span class="sxs-lookup"><span data-stu-id="ffb29-182">The Customer Card Add-in solution is not installed.</span></span>
    1. <span data-ttu-id="ffb29-183">Изпълнете инструкциите за [инсталиране и конфигуриране на решението](customer-card-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="ffb29-183">Complete the instructions to [install and configure the solution](customer-card-add-in.md).</span></span>

- <span data-ttu-id="ffb29-184">Разрешения за приложения не се предоставят.</span><span class="sxs-lookup"><span data-stu-id="ffb29-184">App permissions aren't granted.</span></span>
    1. <span data-ttu-id="ffb29-185">Отидете на [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="ffb29-185">Go to [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).</span></span>
    1. <span data-ttu-id="ffb29-186">Изберете **Среди**.</span><span class="sxs-lookup"><span data-stu-id="ffb29-186">Select **Environments**.</span></span>
    1. <span data-ttu-id="ffb29-187">Изберете многоточието до средата, към която искате да добавите разрешението, и изберете **Настройки**.</span><span class="sxs-lookup"><span data-stu-id="ffb29-187">Select the ellipsis next to the environment you want to add the permission to and select **Settings**.</span></span>
    1. <span data-ttu-id="ffb29-188">Разширете **Потребители + разрешения** и изберете **Потребители**.</span><span class="sxs-lookup"><span data-stu-id="ffb29-188">Expand **Users + permissions** and select **Users**.</span></span>
    1. <span data-ttu-id="ffb29-189">Изберете **+ Нов** и след това **Потребител**.</span><span class="sxs-lookup"><span data-stu-id="ffb29-189">Select **+ New** and select **User**.</span></span>
    1. <span data-ttu-id="ffb29-190">Изберете **Потребител на приложението**, ако все още не е избран и въведете следната информация:</span><span class="sxs-lookup"><span data-stu-id="ffb29-190">Select **Application User** if it's not already selected and enter the following information:</span></span>
        - <span data-ttu-id="ffb29-191">**Потребителско име:** cihelp@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="ffb29-191">**User Name:** cihelp@microsoft.com</span></span>
        - <span data-ttu-id="ffb29-192">**ИД на приложение:** 38c77d00-5fcb-4cce-9d93-af4738258e3c</span><span class="sxs-lookup"><span data-stu-id="ffb29-192">**Application ID:** 38c77d00-5fcb-4cce-9d93-af4738258e3c</span></span>
        - <span data-ttu-id="ffb29-193">**Собствено име:** Customer</span><span class="sxs-lookup"><span data-stu-id="ffb29-193">**First Name:** Customer</span></span>
        - <span data-ttu-id="ffb29-194">**Фамилно име:** Insights</span><span class="sxs-lookup"><span data-stu-id="ffb29-194">**Last Name:** Insights</span></span>
        - <span data-ttu-id="ffb29-195">**Основен имейл:** cihelp@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="ffb29-195">**Primary Email:** cihelp@microsoft.com</span></span>
    1. <span data-ttu-id="ffb29-196">Изберете **Записване и затваряне**.</span><span class="sxs-lookup"><span data-stu-id="ffb29-196">Select **Save & Close**.</span></span>
    1. <span data-ttu-id="ffb29-197">Изберете потребителя, който току-що сте създали.</span><span class="sxs-lookup"><span data-stu-id="ffb29-197">Select the user you just created.</span></span>
    1. <span data-ttu-id="ffb29-198">Изберете **Управление на роли** в горната лента с менюта.</span><span class="sxs-lookup"><span data-stu-id="ffb29-198">Select **Manage Roles** in the top menu bar.</span></span>
    1. <span data-ttu-id="ffb29-199">Изберете **Системен администратор**, след което изберете **OK**.</span><span class="sxs-lookup"><span data-stu-id="ffb29-199">Select **System Administrator**, then select **OK**.</span></span>
