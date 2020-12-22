---
title: Експерименти на Azure Machine Learning
description: Използвайте базирани на Azure Machine Learning модели в Dynamics 365 Customer Insights.
ms.date: 11/30/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: naravill
ms.author: mhart
ms.reviewer: m-hartmann
manager: shellyha
ms.openlocfilehash: 6f00d3202dc29d810bdd218d06c7d04e551846e8
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668755"
---
# <a name="use-azure-machine-learning-based-models"></a><span data-ttu-id="3accb-103">Използвайте базирани на Azure Machine Learning модели</span><span class="sxs-lookup"><span data-stu-id="3accb-103">Use Azure Machine Learning-based models</span></span>

<span data-ttu-id="3accb-104">Единните данни в Dynamics 365 Customer Insights са източник за изграждане на модели на машинно обучение, които могат да генерират допълнителни бизнес прозрения.</span><span class="sxs-lookup"><span data-stu-id="3accb-104">The unified data in Dynamics 365 Customer Insights is a source for building machine learning models that can generate additional business insights.</span></span> <span data-ttu-id="3accb-105">Customer Insights се интегрира с Machine Learning Studio (classic) и Azure Machine Learning, за да използва вашите собствени персонализирани модели.</span><span class="sxs-lookup"><span data-stu-id="3accb-105">Customer Insights integrates with Machine Learning Studio (classic) and Azure Machine Learning to use your own custom models.</span></span> <span data-ttu-id="3accb-106">Вижте [Експерименти в Machine Learning Studio (classic)](machine-learning-studio-experiments.md) за примери за експерименти, изградени върху Machine Learning Studio (classic).</span><span class="sxs-lookup"><span data-stu-id="3accb-106">Refer to [Machine Learning Studio (classic) experiments](machine-learning-studio-experiments.md) for examples of experiments built on Machine Learning Studio (classic).</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="3accb-107">Предварителни изисквания</span><span class="sxs-lookup"><span data-stu-id="3accb-107">Prerequisites</span></span>

- <span data-ttu-id="3accb-108">Достъп до Customer Insights</span><span class="sxs-lookup"><span data-stu-id="3accb-108">Access to Customer Insights</span></span>
- <span data-ttu-id="3accb-109">Активен корпоративен абонамент за Azure</span><span class="sxs-lookup"><span data-stu-id="3accb-109">Active Azure Enterprise subscription</span></span>
- [<span data-ttu-id="3accb-110">Унифицирани клиентски профили</span><span class="sxs-lookup"><span data-stu-id="3accb-110">Unified customer profiles</span></span>](data-unification.md)
- <span data-ttu-id="3accb-111">[Експорт на обект в хранилище за BLOB на Azure](export-azure-blob-storage.md) е конфигуриран</span><span class="sxs-lookup"><span data-stu-id="3accb-111">[Entity export to Azure Blob storage](export-azure-blob-storage.md) configured</span></span>

## <a name="set-up-azure-machine-learning-workspace"></a><span data-ttu-id="3accb-112">Настройване на работна област на Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="3accb-112">Set up Azure Machine Learning workspace</span></span>

1. <span data-ttu-id="3accb-113">Вижте [Създаване на работна област на Azure Machine Learning](https://docs.microsoft.com/azure/machine-learning/concept-workspace#-create-a-workspace) за различни опции за създаване на работното пространство.</span><span class="sxs-lookup"><span data-stu-id="3accb-113">See [create a Azure Machine Learning workspace](https://docs.microsoft.com/azure/machine-learning/concept-workspace#-create-a-workspace) for different options to create the workspace.</span></span> <span data-ttu-id="3accb-114">За най-добра производителност създайте работното пространство в регион на Azure, който е географски най-близо до вашата среда на Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="3accb-114">For best performance, create the workspace in an Azure region that is geographically closest to your Customer Insights environment.</span></span>

1. <span data-ttu-id="3accb-115">Достъп до работното ви пространство чрез [Azure Machine Learning Studio](https://ml.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="3accb-115">Access your workspace through the [Azure Machine Learning Studio](https://ml.azure.com/).</span></span> <span data-ttu-id="3accb-116">Има няколко [начини за взаимодействие](https://docs.microsoft.com/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) с вашето работно пространство.</span><span class="sxs-lookup"><span data-stu-id="3accb-116">There are several [ways to interact](https://docs.microsoft.com/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) with your workspace.</span></span>

## <a name="work-with-azure-machine-learning-designer"></a><span data-ttu-id="3accb-117">Работете с дизайнера на Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="3accb-117">Work with Azure Machine Learning designer</span></span>

<span data-ttu-id="3accb-118">Дизайнерът на Azure Machine Learning предоставя визуално платно, където можете да плъзгате и пускате набори от данни и модули, подобно на Machine Learning Studio (classic).</span><span class="sxs-lookup"><span data-stu-id="3accb-118">Azure Machine Learning designer provides a visual canvas where you can drag and drop datasets and modules, similar to Machine Learning Studio (classic).</span></span> <span data-ttu-id="3accb-119">Партиден конвейер, създаден от дизайнера, може да бъде интегриран в Customer Insights, ако те са конфигурирани по съответния начин.</span><span class="sxs-lookup"><span data-stu-id="3accb-119">A batch pipeline created from the designer can be integrated into Customer Insights if they are configured accordingly.</span></span> 
   
## <a name="working-with-azure-machine-learning-sdk"></a><span data-ttu-id="3accb-120">Работа с SDK Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="3accb-120">Working with Azure Machine Learning SDK</span></span>

<span data-ttu-id="3accb-121">Изследователите на данни и разработчиците на AI използват [Azure Machine Learning SDK](https://docs.microsoft.com/python/api/overview/azure/ml/?view=azure-ml-py&preserve-view=true) за изграждане на машинно обучение работни потоци.</span><span class="sxs-lookup"><span data-stu-id="3accb-121">Data scientists and AI developers use the [Azure Machine Learning SDK](https://docs.microsoft.com/python/api/overview/azure/ml/?view=azure-ml-py&preserve-view=true) to build machine learning workflows.</span></span> <span data-ttu-id="3accb-122">Понастоящем модели, обучени с помощта на SDK, не могат да бъдат интегрирани директно с Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="3accb-122">Currently, models trained using the SDK can't be integrated directly with Customer Insights.</span></span> <span data-ttu-id="3accb-123">Конвейер за групово извеждане, който консумира този модел, е необходим за интеграция с Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="3accb-123">A batch inference pipeline that consumes that model is required for integration with Customer Insights.</span></span>

## <a name="batch-pipeline-requirements-to-integrate-with-customer-insights"></a><span data-ttu-id="3accb-124">Изисквания за пакетен конвейер за интегриране с Customer Insights</span><span class="sxs-lookup"><span data-stu-id="3accb-124">Batch pipeline requirements to integrate with Customer Insights</span></span>

### <a name="dataset-configuration"></a><span data-ttu-id="3accb-125">Конфигурация на набор от данни</span><span class="sxs-lookup"><span data-stu-id="3accb-125">Dataset Configuration</span></span>

<span data-ttu-id="3accb-126">Трябва да създадете набори от данни, за да използвате данни от обекти от Customer Insights към вашия конвейер за групово извеждане.</span><span class="sxs-lookup"><span data-stu-id="3accb-126">You need to create datasets to use entity data from Customer Insights to your batch inference pipeline.</span></span> <span data-ttu-id="3accb-127">Тези набори от данни трябва да бъдат регистрирани в работното пространство.</span><span class="sxs-lookup"><span data-stu-id="3accb-127">These datasets need to be registered in the workspace.</span></span> <span data-ttu-id="3accb-128">В момента поддържаме само [таблични набори от данни](https://docs.microsoft.com/azure/machine-learning/how-to-create-register-datasets#tabulardataset) във формат .csv.</span><span class="sxs-lookup"><span data-stu-id="3accb-128">Currently, we only support [tabular datasets](https://docs.microsoft.com/azure/machine-learning/how-to-create-register-datasets#tabulardataset) in .csv format.</span></span> <span data-ttu-id="3accb-129">Наборите от данни, които съответстват на данните на обекта, трябва да бъдат параметризирани като параметър на тръбопровода.</span><span class="sxs-lookup"><span data-stu-id="3accb-129">The datasets that correspond to entity data need to be parameterized as a pipeline parameter.</span></span>
   
* <span data-ttu-id="3accb-130">Параметри на набора от данни в Designer</span><span class="sxs-lookup"><span data-stu-id="3accb-130">Dataset parameters in Designer</span></span>
   
     <span data-ttu-id="3accb-131">В дизайнера, отворете **Изберете Колони в набора от данни** и изберете **Задайте като параметър на конвейера**, където предоставяте име за параметъра.</span><span class="sxs-lookup"><span data-stu-id="3accb-131">In the designer, open **Select Columns in Dataset** and select **Set as pipeline parameter** where you provide a name for the parameter.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="3accb-132">![Задаване на параметри на набора от данни в дизайнера](media/intelligence-designer-dataset-parameters.png "Задаване на параметри на набора от данни в дизайнера")</span><span class="sxs-lookup"><span data-stu-id="3accb-132">![Dataset parameterization in designer](media/intelligence-designer-dataset-parameters.png "Dataset parameterization in designer")</span></span>
   
* <span data-ttu-id="3accb-133">Параметър на набора от данни в SDK (Python)</span><span class="sxs-lookup"><span data-stu-id="3accb-133">Dataset parameter in SDK (Python)</span></span>
   
   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a><span data-ttu-id="3accb-134">Конвейер за извод на партиди</span><span class="sxs-lookup"><span data-stu-id="3accb-134">Batch inference pipeline</span></span>
  
* <span data-ttu-id="3accb-135">В конструктора може да се използва тръбопровод за обучение, за да се създаде или актуализира извод.</span><span class="sxs-lookup"><span data-stu-id="3accb-135">In the designer, a training pipeline can be used to create or update an inference pipeline.</span></span> <span data-ttu-id="3accb-136">Понастоящем се поддържат само конвейери за групово извеждане.</span><span class="sxs-lookup"><span data-stu-id="3accb-136">Currently, only batch inference pipelines are supported.</span></span>

* <span data-ttu-id="3accb-137">Използвайки SDK, можете да публикувате конвейера до крайна точка.</span><span class="sxs-lookup"><span data-stu-id="3accb-137">Using the SDK, you can publish the pipeline to an endpoint.</span></span> <span data-ttu-id="3accb-138">Понастоящем Customer Insights се интегрира с конвейера по подразбиране в крайна точка на пакетния конвейер в работното пространство машинно обучение.</span><span class="sxs-lookup"><span data-stu-id="3accb-138">Currently, Customer Insights integrates with the default pipeline in a batch pipeline endpoint in the Machine Learning workspace.</span></span>
   
   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a><span data-ttu-id="3accb-139">Импортирайте данните от конвейера в Customer Insights</span><span class="sxs-lookup"><span data-stu-id="3accb-139">Import pipeline data into Customer Insights</span></span>

* <span data-ttu-id="3accb-140">Дизайнерът предоставя [Модул за експортиране на данни](https://docs.microsoft.com/azure/machine-learning/algorithm-module-reference/export-data), който позволява изхода на конвейер да бъде експортиран в хранилището на Azure.</span><span class="sxs-lookup"><span data-stu-id="3accb-140">The designer provides the [Export Data module](https://docs.microsoft.com/azure/machine-learning/algorithm-module-reference/export-data) that allows the output of a pipeline to be exported to Azure storage.</span></span> <span data-ttu-id="3accb-141">Понастоящем модулът трябва да използва типа хранилище на данни **Хранилище за BLOB на Azure** и да параметъризираме **Хранилището за данни** и относителен **Път**.</span><span class="sxs-lookup"><span data-stu-id="3accb-141">Currently, the module must use the datastore type **Azure Blob Storage** and parameterize the **Datastore** and relative **Path**.</span></span> <span data-ttu-id="3accb-142">Customer Insights замества и двата параметъра по време на изпълнение на тръбопровода с хранилище за данни и път, който е достъпен за продукта.</span><span class="sxs-lookup"><span data-stu-id="3accb-142">Customer Insights overrides both these parameters during pipeline execution with a datastore and path that is accessible to the product.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3accb-143">![Експортиране на конфигурация на модул на данни](media/intelligence-designer-importdata.png "Експортиране на конфигурация на модул на данни")</span><span class="sxs-lookup"><span data-stu-id="3accb-143">![Export Data Module Configuration](media/intelligence-designer-importdata.png "Export Data Module Configuration")</span></span>
   
* <span data-ttu-id="3accb-144">Когато пишете извода за извод с помощта на код, можете да качите изхода в пътя в рамките на *регистрирана база данни* в работното пространство.</span><span class="sxs-lookup"><span data-stu-id="3accb-144">When writing the inference output using code, you can upload the output to the a path within a *registered datastore* in the workspace.</span></span> <span data-ttu-id="3accb-145">Ако пътят и хранилището за данни са параметризирани в конвейера, Customer Insights ще може да чете и импортира изхода за извод.</span><span class="sxs-lookup"><span data-stu-id="3accb-145">If the path and datastore are parameterized in the pipeline, Customer insights will be able to read and import the inference output.</span></span> <span data-ttu-id="3accb-146">В момента се поддържа единичен табличен изход във формат csv.</span><span class="sxs-lookup"><span data-stu-id="3accb-146">Currently, a single tabular output in csv format is supported.</span></span> <span data-ttu-id="3accb-147">Пътят трябва да включва директорията и името на файла.</span><span class="sxs-lookup"><span data-stu-id="3accb-147">The path must include the directory and filename.</span></span>

   ```python
   # In Pipeline setup script
      OutputPathParameter = PipelineParameter(name="output_path", default_value="HotelChurnOutput/HotelChurnOutput.csv")
      OutputDatastoreParameter = PipelineParameter(name="output_datastore", default_value="workspaceblobstore")
   ...
   # In pipeline execution script
      run = Run.get_context()
      ws = run.experiment.workspace
      datastore = Datastore.get(ws, output_datastore) # output_datastore is parameterized
      directory_name =  os.path.dirname(output_path)  # output_path is parameterized.
      
      # Datastore.upload() or Dataset.File.upload_directory() are supported methods to uplaod the data
      # datastore.upload(src_dir=<<working directory>>, target_path=directory_name, overwrite=False, show_progress=True)
      output_dataset = Dataset.File.upload_directory(src_dir=<<working directory>>, target = (datastore, directory_name)) # Remove trailing "/" from directory_name
   ```
