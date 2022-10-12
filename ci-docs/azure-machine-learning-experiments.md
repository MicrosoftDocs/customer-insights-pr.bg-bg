---
title: Използвайте базирани на Azure Machine Learning модели
description: Използвайте базирани на Azure Machine Learning модели в Dynamics 365 Customer Insights.
ms.date: 09/22/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: naravill
ms.author: naravill
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 8d9c9324ea4840b585b9af1a58d505ccaea6f18e
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: bg-BG
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609733"
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

Azure машинно обучение дизайнер осигурява визуално платно, където можете да плъзнете и пуснете набори от данни и модули. Партиден конвейер, създаден от дизайнера, може да бъде интегриран в Customer Insights, ако те са конфигурирани по съответния начин. 

## <a name="working-with-azure-machine-learning-sdk"></a>Работа с SDK Azure Machine Learning

Изследователите на данни и разработчиците на AI използват [Azure Machine Learning SDK](/python/api/overview/azure/ml/?preserve-view=true&view=azure-ml-py) за изграждане на машинно обучение работни потоци. Понастоящем модели, обучени с помощта на SDK, не могат да бъдат интегрирани директно с Customer Insights. Конвейер за групово извеждане, който консумира този модел, е необходим за интеграция с Customer Insights.

## <a name="batch-pipeline-requirements-to-integrate-with-customer-insights"></a>Изисквания за пакетен конвейер за интегриране с Customer Insights

### <a name="dataset-configuration"></a>Конфигурация на набор от данни

Създаване на набори от данни, за да използвате данни на предприятието от Customer Insights за вашия тръбопровод за партиден извод. Регистрирайте тези набори от данни в работното пространство. В момента поддържаме само [таблични набори от данни](/azure/machine-learning/how-to-create-register-datasets#tabulardataset) във формат .csv. Параметризирайте наборите от данни, които съответстват на данните на предприятието като параметър на тръбопровода.

- Параметри на набора от данни в Designer

  В дизайнера, отворете **Изберете Колони в набора от данни** и изберете **Задайте като параметър на конвейера**, където предоставяте име за параметъра.

  :::image type="content" source="media/intelligence-designer-dataset-parameters.png" alt-text="Задаване на параметри на набора от данни в дизайнера.":::

- Параметър на набора от данни в SDK (Python)

   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a>Конвейер за извод на партиди
  
- В дизайнера използвайте тренировъчен тръбопровод, за да създадете или актуализирате тръбопровод за извод. Понастоящем се поддържат само конвейери за групово извеждане.

- Използвайки SDK, публикувайте тръбопровода до крайна точка. Понастоящем Customer Insights се интегрира с конвейера по подразбиране в крайна точка на пакетния конвейер в работното пространство машинно обучение.

   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a>Импортирайте данните от конвейера в Customer Insights

- Дизайнерът предоставя [Модул за експортиране на данни](/azure/machine-learning/algorithm-module-reference/export-data), който позволява изхода на конвейер да бъде експортиран в хранилището на Azure. Понастоящем модулът трябва да използва типа хранилище на данни **Хранилище за BLOB на Azure** и да параметъризираме **Хранилището за данни** и относителен **Път**. Customer Insights замества и двата параметъра по време на изпълнение на тръбопровода с хранилище за данни и път, който е достъпен за продукта.

  :::image type="content" source="media/intelligence-designer-importdata.png" alt-text="Експортиране на конфигурация на модул на данни.":::

- Когато пишете изхода на заключението с помощта на код, качете изхода на път в регистриран магазин *за* данни в работното пространство. Ако пътят и хранилището за данни са параметризирани в конвейера, Customer Insights ще може да чете и импортира изхода за извод. В момента се поддържа единичен табличен изход във формат csv. Пътят трябва да включва директорията и името на файла.

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


[!INCLUDE [footer-include](includes/footer-banner.md)]