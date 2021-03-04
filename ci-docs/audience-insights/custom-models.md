---
title: Персонализирани модели за машинно обучение | Microsoft Docs
description: Работа с персонализирани модели от Azure Machine Learning в Dynamics 365 Customer Insights.
ms.date: 11/19/2020
ms.reviewer: zacook
ms.service: dynamics-365-ai
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 34489faaecc5da1ce3dd68d799b3e0e0d9672ab7
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267221"
---
# <a name="custom-machine-learning-models"></a><span data-ttu-id="199d9-103">Персонализирани модели за машинно обучение</span><span class="sxs-lookup"><span data-stu-id="199d9-103">Custom machine learning models</span></span>

<span data-ttu-id="199d9-104">**Разузнаване** > **Персонализирани модели** ви позволява да управлявате работни потоци въз основа на модели на Azure Machine Learning.</span><span class="sxs-lookup"><span data-stu-id="199d9-104">**Intelligence** > **Custom models** lets you manage workflows based on Azure Machine Learning models.</span></span> <span data-ttu-id="199d9-105">Работните процеси ви помагат да изберете данните, от които искате да генерирате прозрения, и да съпоставите резултатите с вашите унифицирани клиентски данни.</span><span class="sxs-lookup"><span data-stu-id="199d9-105">Workflows help you choose the data you want to generate insights from and map the results to your unified customer data.</span></span> <span data-ttu-id="199d9-106">За повече информация относно изграждането на персонализирани модели ML, вижте [Използвайте модели, базирани на Azure Machine Learning](azure-machine-learning-experiments.md).</span><span class="sxs-lookup"><span data-stu-id="199d9-106">For more information about building custom ML models, see [Use Azure Machine Learning-based models](azure-machine-learning-experiments.md).</span></span>

## <a name="responsible-ai"></a><span data-ttu-id="199d9-107">Отговорен AI</span><span class="sxs-lookup"><span data-stu-id="199d9-107">Responsible AI</span></span>

<span data-ttu-id="199d9-108">Прогнозите предлагат възможности за създаване на по-добро преживяване на клиентите, подобряване на бизнес възможностите и потоци от приходи.</span><span class="sxs-lookup"><span data-stu-id="199d9-108">Predictions offer capabilities to create better customer experiences, improve business capabilities, and revenue streams.</span></span> <span data-ttu-id="199d9-109">Силно препоръчваме да балансирате стойността на вашия прогноза спрямо въздействието, което има и пристрастия, които могат да бъдат въведени по етичен начин.</span><span class="sxs-lookup"><span data-stu-id="199d9-109">We strongly recommend you balance the value of your prediction against the impact it has and biases that may be introduced in an ethical manner.</span></span> <span data-ttu-id="199d9-110">Научете повече за това как Microsoft се [справя с Отговорен AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span><span class="sxs-lookup"><span data-stu-id="199d9-110">Learn more about how Microsoft is [addressing Responsible AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span></span> <span data-ttu-id="199d9-111">Можете също така да научите за [техники и процеси за отговорни машинно обучение](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml), специфични за Azure Machine Learning.</span><span class="sxs-lookup"><span data-stu-id="199d9-111">You can also learn about [techniques and processes for responsible machine learning](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) specific to Azure Machine Learning.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="199d9-112">Предварителни изисквания</span><span class="sxs-lookup"><span data-stu-id="199d9-112">Prerequisites</span></span>

- <span data-ttu-id="199d9-113">Понастоящем тази функция поддържа уеб услуги, публикувани чрез [Machine Learning Studio (classic)](https://studio.azureml.net) и [пакетни конвейери на Azure Machine Learning](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).</span><span class="sxs-lookup"><span data-stu-id="199d9-113">Currently, this feature supports web services published through [Machine Learning Studio (classic)](https://studio.azureml.net) and [Azure Machine Learning batch pipelines](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).</span></span>

- <span data-ttu-id="199d9-114">За да използвате тази функция, ви е необходим акаунт за съхранение в Azure Data Lake Gen2, свързан с вашия екземпляр на Azure Studio.</span><span class="sxs-lookup"><span data-stu-id="199d9-114">You need an Azure Data Lake Gen2 storage account associated with your Azure Studio instance to use this feature.</span></span> <span data-ttu-id="199d9-115">За повече информация вижте [Създаване на акаунт за съхранение в Azure Data Lake Storage Gen2](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)</span><span class="sxs-lookup"><span data-stu-id="199d9-115">For more information, see [Create an Azure Data Lake Storage Gen2 storage account](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)</span></span>

## <a name="add-a-new-workflow"></a><span data-ttu-id="199d9-116">Добавяне на нов работен поток</span><span class="sxs-lookup"><span data-stu-id="199d9-116">Add a new workflow</span></span>

1. <span data-ttu-id="199d9-117">Отидете на **Разузнаване** > **Персонализирани модели** и изберете **Нов работен поток**.</span><span class="sxs-lookup"><span data-stu-id="199d9-117">Go to **Intelligence** > **Custom models** and select **New workflow**.</span></span>

1. <span data-ttu-id="199d9-118">Въведете разпознаваемо име за персонализирания модел в полето **Име**.</span><span class="sxs-lookup"><span data-stu-id="199d9-118">Give your custom model a recognizable name in the **Name** field.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="199d9-119">![Екранна снимка на прозореца „Нов работен поток“](media/new-workflowv2.png "Екранна снимка на прозореца „Нов работен поток“")</span><span class="sxs-lookup"><span data-stu-id="199d9-119">![Screenshot of the New workflow pane](media/new-workflowv2.png "Screenshot of the New workflow pane")</span></span>

1. <span data-ttu-id="199d9-120">Изберете организацията, която съдържа уеб услугата в **Клиент, който съдържа вашата уеб услуга**.</span><span class="sxs-lookup"><span data-stu-id="199d9-120">Select the organization that contains the web service in **Tenant that contains your web service**.</span></span>

1. <span data-ttu-id="199d9-121">Ако абонаментът ви за Azure Machine Learning е в клиент, който е различен от този на Customer Insights, изберете **Влизане** с вашите идентификационни данни за избраната организация.</span><span class="sxs-lookup"><span data-stu-id="199d9-121">If your Azure Machine Learning subscription is in a different tenant than Customer Insights, select **Sign in** with your credentials for the selected organization.</span></span>

1. <span data-ttu-id="199d9-122">Изберете **Работни пространства**, свързани с вашата уеб услуга.</span><span class="sxs-lookup"><span data-stu-id="199d9-122">Select the **Workspaces** associated with your web service.</span></span> <span data-ttu-id="199d9-123">Изброени са два раздела, един за Azure Machine Learning v1 (Machine Learning Studio (classic)) i Azure Machine Learning v2 (Azure Machine Learning).</span><span class="sxs-lookup"><span data-stu-id="199d9-123">There are two sections listed, one for Azure Machine Learning v1 (Machine Learning Studio (classic)) and Azure Machine Learning v2 (Azure Machine Learning).</span></span> <span data-ttu-id="199d9-124">Ако не сте сигурни кое работно пространство е подходящо за вашата уеб услуга Machine Learning Studio (classic), изберете **Всякакви**.</span><span class="sxs-lookup"><span data-stu-id="199d9-124">If you're not sure which workspace is the right one for your Machine Learning Studio (classic) web service, select **Any**.</span></span>

1. <span data-ttu-id="199d9-125">Изберете уеб услугата Machine Learning Studio (classic) или конвейера Azure Machine Learning в **Уеб услуга, която съдържа вашия модел** падащо меню.</span><span class="sxs-lookup"><span data-stu-id="199d9-125">Choose the Machine Learning Studio (classic) web service or Azure Machine Learning pipeline in the **Web service that contains your model** dropdown.</span></span> <span data-ttu-id="199d9-126">След това изберете **Напред**.</span><span class="sxs-lookup"><span data-stu-id="199d9-126">Then, select **Next**.</span></span>
   - <span data-ttu-id="199d9-127">Научете повече за [публикуване на уеб услуга в Machine Learning Studio (classic)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span><span class="sxs-lookup"><span data-stu-id="199d9-127">Learn more about [publishing a web service in Machine Learning Studio (classic)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span></span>
   - <span data-ttu-id="199d9-128">Научете повече за [публикуване на конвейер в Azure Machine Learning с помощта на дизайнера](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) или [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span><span class="sxs-lookup"><span data-stu-id="199d9-128">Learn more about [publishing a pipeline in Azure Machine Learning using the designer](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) or [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span></span> <span data-ttu-id="199d9-129">Вашият конвейер трябва да бъде публикуван под [крайна точка на конвейер](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span><span class="sxs-lookup"><span data-stu-id="199d9-129">Your pipeline must be published under a [pipeline endpoint](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span></span>

1. <span data-ttu-id="199d9-130">За всички **Входни данни на уеб услуга** изберете съответния **Обект** от аналитични данни за аудитория и изберете **Напред**.</span><span class="sxs-lookup"><span data-stu-id="199d9-130">For each **Web service input**, select the matching **Entity** from audience insights and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="199d9-131">Персонализираният работен поток на модела ще приложи евристика за картографиране на полетата за въвеждане на уеб услугата към атрибутите на обекта въз основа на името и типа данни на полето.</span><span class="sxs-lookup"><span data-stu-id="199d9-131">The custom model workflow will apply heuristics to map the web service input fields to the entity attributes based on the name and data type of the field.</span></span> <span data-ttu-id="199d9-132">Ще видите грешка, ако полето на уеб услуга не може да бъде съпоставено с обект.</span><span class="sxs-lookup"><span data-stu-id="199d9-132">You'll see an error if a web service field can't be mapped to an entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="199d9-133">![Конфигуриране на работен поток](media/intelligence-screen2-updated.png "Конфигуриране на работен поток")</span><span class="sxs-lookup"><span data-stu-id="199d9-133">![Configure a workflow](media/intelligence-screen2-updated.png "Configure a workflow")</span></span>
   
1. <span data-ttu-id="199d9-134">В **Изходни параметри на модела** стъпка, задайте следните свойства:</span><span class="sxs-lookup"><span data-stu-id="199d9-134">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="199d9-135">Machine Learning Studio (classic)</span><span class="sxs-lookup"><span data-stu-id="199d9-135">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="199d9-136">Въведете изхода **Име на обекта**, в който искате да изтичат резултатите от уеб услугата.</span><span class="sxs-lookup"><span data-stu-id="199d9-136">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="199d9-137">Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="199d9-137">Azure Machine Learning</span></span>
      1. <span data-ttu-id="199d9-138">Въведете **Име на обекта** на изхода, в който искате да изтичат резултатите от конвейера.</span><span class="sxs-lookup"><span data-stu-id="199d9-138">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="199d9-139">Изберете **Изход хранилище на данни име на параметъра** на вашия пакетен конвейер от падащото меню.</span><span class="sxs-lookup"><span data-stu-id="199d9-139">Select the **Output data store parameter name** of your batch pipeline from the dropdown.</span></span>
      1. <span data-ttu-id="199d9-140">Изберете **Изход име на параметъра на път** на вашия пакетен конвейер от падащото меню.</span><span class="sxs-lookup"><span data-stu-id="199d9-140">Select the **Output Path parameter name** of your batch pipeline from the dropdown.</span></span>
      
      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="199d9-141">![Екран на параметър на изход на модел](media/intelligence-screen3-outputparameters.png "Екран на параметър на изход на модел")</span><span class="sxs-lookup"><span data-stu-id="199d9-141">![Model Output Parameter Pane](media/intelligence-screen3-outputparameters.png "Model Output Parameter Pane")</span></span>

1. <span data-ttu-id="199d9-142">Изберете съвпадащия атрибут от падащия списък **ИД на клиент в резултатите**, който идентифицира клиентите, и изберете **записване**.</span><span class="sxs-lookup"><span data-stu-id="199d9-142">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="199d9-143">![Свързване на резултатите с екран за данните на клиентите](media/intelligence-screen4-relatetocustomer.png "Свързване на резултатите с екран за данните на клиентите")</span><span class="sxs-lookup"><span data-stu-id="199d9-143">![Relate results to Customer data pane](media/intelligence-screen4-relatetocustomer.png "Relate results to Customer data pane")</span></span>

1. <span data-ttu-id="199d9-144">Ще видите екрана **Работният поток е запазен** с подробности за работния поток.</span><span class="sxs-lookup"><span data-stu-id="199d9-144">You'll see the **Workflow Saved** screen with details about the workflow.</span></span>    
   <span data-ttu-id="199d9-145">Ако сте конфигурирали работен поток за конвейер на Azure Machine Learning, статистика за аудиторията ще се прикачи към работното пространство, което съдържа конвейера.</span><span class="sxs-lookup"><span data-stu-id="199d9-145">If you configured a workflow for an Azure Machine Learning pipeline, audience insights will attach to the workspace that contains the pipeline.</span></span> <span data-ttu-id="199d9-146">Данните за публиката ще получат **Сътрудник** роля в работното пространство на Azure.</span><span class="sxs-lookup"><span data-stu-id="199d9-146">Audience insights will get a **Contributor** role on the Azure workspace.</span></span>

1. <span data-ttu-id="199d9-147">Изберете **Готово**.</span><span class="sxs-lookup"><span data-stu-id="199d9-147">Select **Done**.</span></span>

1. <span data-ttu-id="199d9-148">Вече можете да стартирате работния процес от страницата **Персонализирани модели**.</span><span class="sxs-lookup"><span data-stu-id="199d9-148">You can now run the workflow from the **Custom Models** page.</span></span>

## <a name="edit-a-workflow"></a><span data-ttu-id="199d9-149">Редактиране на работен поток</span><span class="sxs-lookup"><span data-stu-id="199d9-149">Edit a workflow</span></span>

1. <span data-ttu-id="199d9-150">На страницата **Персонализирани модели**, изберете вертикалното многоточие в **Дейности** колоната до работен поток, който сте създали преди това и изберете **Редактиране**.</span><span class="sxs-lookup"><span data-stu-id="199d9-150">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created and select **Edit**.</span></span>

1. <span data-ttu-id="199d9-151">Можете да актуализирате разпознаваемото име на вашия работен поток в полето **Показвано име**, но не можете да промените конфигурираната уеб услуга или конвейер.</span><span class="sxs-lookup"><span data-stu-id="199d9-151">You can update your workflow's recognizable name in the **Display name** field, but you can't change the configured web service or pipeline.</span></span> <span data-ttu-id="199d9-152">Изберете **Напред**.</span><span class="sxs-lookup"><span data-stu-id="199d9-152">Select **Next**.</span></span>

1. <span data-ttu-id="199d9-153">За всички **Входни данни на уеб услуга** можете да актуализирате съответния **Обект** от аналитични данни за аудитория.</span><span class="sxs-lookup"><span data-stu-id="199d9-153">For each **Web service input**, you can update the matching **Entity** from audience insights.</span></span> <span data-ttu-id="199d9-154">След това изберете **Напред**.</span><span class="sxs-lookup"><span data-stu-id="199d9-154">Then, select **Next**.</span></span>

1. <span data-ttu-id="199d9-155">В **Изходни параметри на модела** стъпка, задайте следните свойства:</span><span class="sxs-lookup"><span data-stu-id="199d9-155">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="199d9-156">Machine Learning Studio (classic)</span><span class="sxs-lookup"><span data-stu-id="199d9-156">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="199d9-157">Въведете изхода **Име на обекта**, в който искате да изтичат резултатите от уеб услугата.</span><span class="sxs-lookup"><span data-stu-id="199d9-157">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="199d9-158">Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="199d9-158">Azure Machine Learning</span></span>
      1. <span data-ttu-id="199d9-159">Въведете **Име на обекта** на изхода, в който искате да изтичат резултатите от конвейера.</span><span class="sxs-lookup"><span data-stu-id="199d9-159">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="199d9-160">Изберете **Изход хранилище на данни име на параметъра** за вашия тестов конвейер.</span><span class="sxs-lookup"><span data-stu-id="199d9-160">Select the **Output data store parameter name** for your test pipeline.</span></span>
      1. <span data-ttu-id="199d9-161">Изберете **Име на параметъра на път на изход** за вашия тестов конвейер.</span><span class="sxs-lookup"><span data-stu-id="199d9-161">Select the **Output Path parameter name** for your test pipeline.</span></span>

1. <span data-ttu-id="199d9-162">Изберете съвпадащия атрибут от падащия списък **ИД на клиент в резултатите**, който идентифицира клиентите, и изберете **записване**.</span><span class="sxs-lookup"><span data-stu-id="199d9-162">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   <span data-ttu-id="199d9-163">Трябва да изберете атрибут от извода за извод със стойности, подобни на колоната на идентификатора на клиента на обекта на клиента.</span><span class="sxs-lookup"><span data-stu-id="199d9-163">You need to choose an attribute from the inference output with values similar to the Customer ID column of the Customer entity.</span></span> <span data-ttu-id="199d9-164">Ако нямате такава колона във вашия набор от данни, изберете атрибут, който идентифицира уникално реда.</span><span class="sxs-lookup"><span data-stu-id="199d9-164">If don't have such a column in your data set, choose an attribute that uniquely identifies the row.</span></span>

## <a name="run-a-workflow"></a><span data-ttu-id="199d9-165">Изпълняване на работен поток</span><span class="sxs-lookup"><span data-stu-id="199d9-165">Run a workflow</span></span>

1. <span data-ttu-id="199d9-166">На страницата **Персонализирани модели**, изберете вертикалното многоточие в **Дейности** колоната до работен поток, който сте създали преди това.</span><span class="sxs-lookup"><span data-stu-id="199d9-166">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="199d9-167">Изберете **Изпълнение**.</span><span class="sxs-lookup"><span data-stu-id="199d9-167">Select **Run**.</span></span>

<span data-ttu-id="199d9-168">Вашият работен поток се изпълнява автоматично и с всяко планирано обновяване.</span><span class="sxs-lookup"><span data-stu-id="199d9-168">Your workflow also runs automatically with every scheduled refresh.</span></span> <span data-ttu-id="199d9-169">Научете повече за [настройката на планирано обновяване](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="199d9-169">Learn more about [setting up scheduled refreshes](system.md#schedule-tab).</span></span>

## <a name="delete-a-workflow"></a><span data-ttu-id="199d9-170">Изтриване на работен поток</span><span class="sxs-lookup"><span data-stu-id="199d9-170">Delete a workflow</span></span>

1. <span data-ttu-id="199d9-171">На страницата **Персонализирани модели**, изберете вертикалното многоточие в **Дейности** колоната до работен поток, който сте създали преди това.</span><span class="sxs-lookup"><span data-stu-id="199d9-171">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="199d9-172">Изберете **Изтриване** и потвърдете изтриването.</span><span class="sxs-lookup"><span data-stu-id="199d9-172">Select **Delete** and confirm your deletion.</span></span>

<span data-ttu-id="199d9-173">Работният поток ще бъде изтрит.</span><span class="sxs-lookup"><span data-stu-id="199d9-173">Your workflow will be deleted.</span></span> <span data-ttu-id="199d9-174">[Обектът](entities.md), създаден при създаването на работния поток, се запазва и може да бъде прегледан от страницата **Обекти**.</span><span class="sxs-lookup"><span data-stu-id="199d9-174">The [entity](entities.md) that was created when you created the workflow persists, and can be viewed from the **Entities** page.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]