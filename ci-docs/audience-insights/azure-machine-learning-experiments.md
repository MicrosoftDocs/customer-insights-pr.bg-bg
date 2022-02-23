---
title: Експерименти на Azure Machine Learning
description: Използвайте базирани на Azure Machine Learning модели в Dynamics 365 Customer Insights.
ms.date: 12/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: naravill
ms.author: naravill
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: e37eec503c9df83ef72497e22afa1266296e642c
ms.sourcegitcommit: 58651d33e0a7d438a2587c9ceeaf7ff58ae3b648
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 12/02/2021
ms.locfileid: "7881725"
---
# <a name="use-azure-machine-learning-based-models"></a>Използвайте базирани на Azure Machine Learning модели

Единните данни в Dynamics 365 Customer Insights са източник за изграждане на модели на машинно обучение, които могат да генерират допълнителни бизнес прозрения. Customer Insights се интегрират с Azure Machine Learning, за да използват вашите собствени персонализирани модели.

## <a name="prerequisites"></a>Предварителни изисквания

- Достъп до Customer Insights
- Активен корпоративен абонамент за Azure
- [Унифицирани клиентски профили](data-unification.md)
- [Експорт на обект в хранилище за BLOB на Azure](export-azure-blob-storage.md) е конфигуриран

## <a name="set-up-azure-machine-learning-workspace"></a>Настройване на работна област на Azure Machine Learning

1. Вижте [Създаване на работна област на Azure Machine Learning](/azure/machine-learning/concept-workspace#-create-a-workspace) за различни опции за създаване на работното пространство. За най-добра производителност създайте работното пространство в регион на Azure, който е географски най-близо до вашата среда на Customer Insights.

1. Достъп до работното ви пространство чрез [Azure Machine Learning Studio](https://ml.azure.com/). Има няколко [начини за взаимодействие](/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) с вашето работно пространство.

## <a name="work-with-azure-machine-learning-designer"></a>Работете с дизайнера на Azure Machine Learning

Дизайнерът на Azure машинно обучение предоставя визуално платно, където можете да плъзгате и пускате набори от данни и модули. Партиден конвейер, създаден от дизайнера, може да бъде интегриран в Customer Insights, ако те са конфигурирани по съответния начин. 
   
## <a name="working-with-azure-machine-learning-sdk"></a>Работа с SDK Azure Machine Learning

Изследователите на данни и разработчиците на AI използват [Azure Machine Learning SDK](/python/api/overview/azure/ml/?preserve-view=true&view=azure-ml-py) за изграждане на машинно обучение работни потоци. Понастоящем модели, обучени с помощта на SDK, не могат да бъдат интегрирани директно с Customer Insights. Конвейер за групово извеждане, който консумира този модел, е необходим за интеграция с Customer Insights.

## <a name="batch-pipeline-requirements-to-integrate-with-customer-insights"></a>Изисквания за пакетен конвейер за интегриране с Customer Insights

### <a name="dataset-configuration"></a>Конфигурация на набор от данни

Трябва да създадете набори от данни, за да използвате данни от обекти от Customer Insights към вашия конвейер за групово извеждане. Тези набори от данни трябва да бъдат регистрирани в работното пространство. В момента поддържаме само [таблични набори от данни](/azure/machine-learning/how-to-create-register-datasets#tabulardataset) във формат .csv. Наборите от данни, които съответстват на данните на обекта, трябва да бъдат параметризирани като параметър на тръбопровода.
   
* Параметри на набора от данни в Designer
   
     В дизайнера, отворете **Изберете Колони в набора от данни** и изберете **Задайте като параметър на конвейера**, където предоставяте име за параметъра.

     > [!div class="mx-imgBorder"]
     > ![Задаване на параметри на набора от данни в дизайнера.](media/intelligence-designer-dataset-parameters.png "Задаване на параметри на набора от данни в дизайнера")
   
* Параметър на набора от данни в SDK (Python)
   
   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a>Конвейер за извод на партиди
  
* В конструктора може да се използва тръбопровод за обучение, за да се създаде или актуализира извод. Понастоящем се поддържат само конвейери за групово извеждане.

* Използвайки SDK, можете да публикувате конвейера до крайна точка. Понастоящем Customer Insights се интегрира с конвейера по подразбиране в крайна точка на пакетния конвейер в работното пространство машинно обучение.
   
   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a>Импортирайте данните от конвейера в Customer Insights

* Дизайнерът предоставя [Модул за експортиране на данни](/azure/machine-learning/algorithm-module-reference/export-data), който позволява изхода на конвейер да бъде експортиран в хранилището на Azure. Понастоящем модулът трябва да използва типа хранилище на данни **Хранилище за BLOB на Azure** и да параметъризираме **Хранилището за данни** и относителен **Път**. Customer Insights замества и двата параметъра по време на изпълнение на тръбопровода с хранилище за данни и път, който е достъпен за продукта.
   > [!div class="mx-imgBorder"]
   > ![Експортиране на конфигурация на модул на данни.](media/intelligence-designer-importdata.png "Експортиране на конфигурация на модул на данни")
   
* Когато пишете извода за извод с помощта на код, можете да качите изхода в пътя в рамките на *регистрирана база данни* в работното пространство. Ако пътят и хранилището за данни са параметризирани в конвейера, Customer Insights ще може да чете и импортира изхода за извод. В момента се поддържа единичен табличен изход във формат csv. Пътят трябва да включва директорията и името на файла.

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


[!INCLUDE[footer-include](../includes/footer-banner.md)]