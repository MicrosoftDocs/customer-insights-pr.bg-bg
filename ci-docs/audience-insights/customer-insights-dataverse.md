---
title: Данни на Customer Insights в Microsoft Dataverse
description: Използвайте обекти на Customer Insights като таблици в Microsoft Dataverse.
ms.date: 06/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 45535a7368b89e19a91f08fcd825bda9d57a8709653104bf4043c29ffa14d0b8
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032883"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Работа с данни на Customer Insights в Microsoft Dataverse

Customer Insights предоставя опция за предоставяне на изходни обекти в [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro.md). Тази интеграция позволява лесно споделяне на данни и разработка по поръчка чрез подход с нисък код / без код. Изходните обекти ще бъдат достъпни като таблици в Dataverse. Тези таблици позволяват сценарии като [автоматизирани работни потоци чрез Power Automate](/power-automate/getting-started), [приложения, управлявани от модел](/powerapps/maker/model-driven-apps/) и [приложения за платно](/powerapps/maker/canvas-apps/) чрез Power Apps. Можете да използвате данните за всяко друго приложение, базирано на Dataverse таблици. Текущата реализация поддържа главно справки, при които данните от наличните обекти с прозрения за аудиторията могат да бъдат извлечени за даден идентификатор на клиента.

## <a name="attach-a-dataverse-environment-to-customer-insights"></a>Прикачете Dataverse среда към Customer Insights

**Организации със съществуващи Dataverse среди**

Организации, които вече използват Dataverse могат да [използват един от съществуващите им Dataverse среди](get-started-paid.md) когато администратор задава статистика за аудиторията. Като предоставите URL адреса на Dataverse среда, тя се привързва към тяхната нова аудитория прозрения среда. За да се осигури възможно най-доброто представяне, Customer Insights и Dataverse средите трябва да бъдат хоствани в същия регион.

За да прикачите Dataverse среда, разширете **Разширени настройки** при създаване на среда за прозрения на публиката. Предоставете **Microsoft Dataverse URL адрес на средата** и поставете отметка в **Активирайте споделянето на данни**.

:::image type="content" source="media/Datasharing-with-DataverseMDL.png" alt-text="alt.":::

**Нова организация**

Ако създадете нова организация, когато настройвате Customer Insights, автоматично ще получите нова Dataverse среда.

> [!NOTE]
> Ако вашите организации вече използват Dataverse в техния наемател е важно да се помни това [Dataverse създаването на среда се контролира от администратор](/power-platform/admin/control-environment-creation.md). Например, ако създавате нова среда за прозрения за аудиторията с вашия организационен акаунт и администраторът е деактивирал създаването на Dataverse среда за всички, с изключение на администраторите, не можете да създадете нова пробна среда.
> 
> Пробните среди на Dataverse, създадени в Customer Insights, имат 3 GB място за съхранение, което няма да се брои за общия капацитет, който има право на наемателя. Платените абонаменти получават правомощие на Dataverse за 15 GB за база данни и 20 GB за съхранение на файлове.

## <a name="output-entities"></a>Изходни обекти

Някои изходни обекти от статистика за аудиторията са достъпни като таблици в Dataverse. Разделите по-долу описват очакваната схема на тези таблици.

- [CustomerProfile](#customerprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Обогатяване](#enrichment)
- [Прогноза](#prediction)


### <a name="customerprofile"></a>CustomerProfile

Тази таблица съдържа единния потребителски профил от Customer Insights. Схемата за унифициран клиентски профил зависи от обектите и атрибутите, използвани в процеса на обединяване. Схемата на потребителския профил обикновено съдържа подмножество на атрибутите от [Дефиниция на Common Data Model на CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile).

### <a name="alternatekey"></a>AlternateKey

Таблицата AlternateKey съдържа ключове на обектите, участвали в процеса на обединяване.

|Column  |Тип  |Описание  |
|---------|---------|---------|
|DataSourceName    |String         | Име на източник на данни. Например: `datasource5`        |
|EntityName        | String        | Име на обекта в статистика за аудиторията. Например: `contact1`        |
|AlternateValue    |String         |Алтернативен идентификатор, който се съпоставя с идентификатора на клиента. Пример: `cntid_1078`         |
|KeyRing           | Многоредов текст        | Стойност на JSON  </br> Пример: [{"dataSourceName":" datasource5 ",</br>"entityName":" contact1",</br>"preferredKey":" cntid_1078",</br>"keys":[" cntid_1078"]}]       |
|CustomerId         | String        | Идентификационен номер на унифицирания потребителски профил.         |
|AlternateKeyId     | GUID         |  Детерминиран GUID на AlternateKey, базиран на msdynci_identifier       |
|msdynci_identifier |   String      |   `DataSourceName|EntityName|AlternateValue`  </br> Пример: `testdatasource|contact1|cntid_1078`    |

### <a name="unifiedactivity"></a>UnifiedActivity

Тази таблица съдържа дейности от потребители, които са налични в Customer Insights.

| Column            | Тип        | Описание                                                                              |
|-------------------|-------------|------------------------------------------------------------------------------------------|
| CustomerId        | String      | ИД на профил на клиент                                                                      |
| ActivityId        | String      | Вътрешен идентификатор на активността на клиента (първичен ключ)                                       |
| SourceEntityName  | String      | Име на обекта-източник                                                                |
| SourceActivityId  | String      | Първичен ключ от изходния обект                                                       |
| ActivityType      | String      | Тип семантична дейност или име на персонализирана дейност                                        |
| ActivityTimeStamp | DATETIME    | Времево клеймо на дейността                                                                      |
| Заглавие             | String      | Заглавие или име на дейността                                                               |
| Описание       | String      | Описание на дейността                                                                     |
| URL адрес               | String      | Връзка към външен URL адрес, специфичен за дейността                                         |
| SemanticData      | Низ JSON | Включва списък на двойки ключови стойности за семантични полета за картографиране, специфични за вида дейност |
| RangeIndex        | String      | Отпечатъкът на Unix, използван за сортиране на времевата линия на дейността и ефективни заявки за диапазон |
| mydynci_unifiedactivityid   | GUID | Вътрешен идентификатор на активността на клиента (ActivityId) |

### <a name="customermeasure"></a>CustomerMeasure

Тази таблица съдържа изходни данни за базирани на атрибути на клиента мерки.

| Column             | Тип             | Описание                 |
|--------------------|------------------|-----------------------------|
| CustomerId         | String           | ИД на профил на клиент        |
| Мерки           | Низ JSON      | Включва списък с двойки ключови стойности за име на мярка и стойности за дадения клиент | 
| msdynci_identifier | String           | `Customer_Measure|CustomerId` |
| msdynci_customermeasureid | GUID      | ИД на профил на клиент |


### <a name="enrichment"></a>Обогатяване

Тази таблица съдържа резултатите от процеса на обогатяване.

| Column               | Тип             |  Описание                                          |
|----------------------|------------------|------------------------------------------------------|
| CustomerId           | String           | ИД на профил на клиент                                 |
| EnrichmentProvider   | String           | Имена доставчика за допълването                                  |
| EnrichmentType       | String           | Тип на обогатяване                                      |
| Стойности               | Низ JSON      | Списък на атрибутите, получени в процеса на обогатяване |
| msdynci_enrichmentid | GUID             | Детерминиран GUID, генериран от msdynci_identifier |
| msdynci_identifier   | String           | `EnrichmentProvider|EnrichmentType|CustomerId`         |

### <a name="prediction"></a>Прогноза

Тази таблица съдържа резултатите на предсказанията на модела.

| Column               | Тип        | Описание                                          |
|----------------------|-------------|------------------------------------------------------|
| CustomerId           | String      | ИД на профил на клиент                                  |
| ModelProvider        | String      | Имена доставчика на модела                                      |
| Модел                | String      | Име на модела                                                |
| Стойности               | Низ JSON | Списък на атрибутите, получени от модела |
| msdynci_predictionid | GUID        | Детерминиран GUID, генериран от msdynci_identifier | 
| msdynci_identifier   | String      |  `Model|ModelProvider|CustomerId`                      |
