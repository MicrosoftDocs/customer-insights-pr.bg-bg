---
title: Данни на Customer Insights в Microsoft Dataverse
description: Използвайте обекти на Customer Insights като таблици в Microsoft Dataverse.
ms.date: 04/05/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 1e629cd218b104b115f74f59a53a14e9d60fcc8a
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: MT
ms.contentlocale: bg-BG
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741352"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Работа с данни на Customer Insights в Microsoft Dataverse

Customer Insights предоставя опция за предоставяне на изходни обекти в [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). Тази интеграция дава възможност за лесно споделяне на данни и персонализирано развитие чрез подход с нисък код/без код. Изходните [обекти](#output-entities) са налични като таблици в Dataverse среда. Можете да използвате данните за всяко друго приложение въз основа на Dataverse таблици. Тези таблици дават възможност за сценарии като автоматизирани работни потоци през Power Automate или изграждане на приложения с Power Apps. Текущото внедряване поддържа главно справки, при които данните от наличните обекти "Аналитични данни за клиенти" могат да бъдат довладеени за даден Идентификационен номер на клиента.

## <a name="attach-a-dataverse-environment-to-customer-insights"></a>Прикачете Dataverse среда към Customer Insights

**Съществуваща организация**

Администраторите могат да конфигурират "Аналитични данни за клиенти" да [използват съществуваща Dataverse среда](create-environment.md), когато създават среда за аналитични данни за клиенти. Предоставяйки URL адреса на околната Dataverse среда, той се прикачва към новата им среда "Аналитични данни за клиенти". Клиентските аналитични данни и Dataverse среди трябва да се хостват в един и същ регион. 

Ако не искате да използвате съществуваща Dataverse среда, системата създава нова среда за данните "Аналитични данни за клиенти" във вашия наемател. 

> [!NOTE]
> Ако вашите организации вече използват в своя наемател, важно е да запомните Dataverse, че [Dataverse създаването на среда се контролира от администратор](/power-platform/admin/control-environment-creation). Например, ако настройвате нова среда на Customer Insights с организационния си акаунт и администраторът е забранил създаването на Dataverse пробни среди за всички, с изключение на администраторите, не можете да създадете нова пробна среда.
> 
> Пробните среди на Dataverse, създадени в Customer Insights, имат 3 GB място за съхранение, което няма да се брои за общия капацитет, който има право на наемателя. Платените абонаменти получават правомощие на Dataverse за 15 GB за база данни и 20 GB за съхранение на файлове.

**Нова организация**

Ако създавате нова организация при настройването на "Аналитични данни за клиенти", системата автоматично създава нова Dataverse среда във вашата организация вместо вас.

## <a name="output-entities"></a>Изходни обекти

Някои изходни обекти от "Аналитични данни за клиенти" се предлагат като таблици в Dataverse. Разделите по-долу описват очакваната схема на тези таблици.

- [CustomerProfile](#customerprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Обогатяване](#enrichment)
- [Прогноза](#prediction)
- [Членство в сегмент](#segment-membership)


### <a name="customerprofile"></a>CustomerProfile

Тази таблица съдържа единния потребителски профил от Customer Insights. Схемата за унифициран профил на клиент зависи от обектите и атрибутите, използвани в процеса на обединяване на данни. Схемата на потребителския профил обикновено съдържа подмножество на атрибутите от [Дефиниция на Common Data Model на CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile).

### <a name="alternatekey"></a>AlternateKey

Таблицата AlternateKey съдържа ключове на обектите, участвали в процеса на обединяване.

|Column  |Тип  |Описание  |
|---------|---------|---------|
|DataSourceName    |String         | Име на източник на данни. Например: `datasource5`        |
|EntityName        | String        | Име на обекта в "Аналитични данни за клиенти". Например: `contact1`        |
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

### <a name="segment-membership"></a>Членство в сегмент

Тази таблица съдържа информация за членство в сегмент на профилите на клиента.

| Column        | Вид | Описание                        |
|--------------------|--------------|-----------------------------|
| CustomerId        | String       | ИД на профил на клиент        |
| СегментПрочетир      | String       | Приложение, което публикува сегментите.      |
| СегментМембърствоТип | String       | Тип на клиента този запис на членство в сегмент. Поддържа няколко типа като "Клиент", "Контакт" или "Акаунт". По подразбиране: Клиент  |
| Сегменти       | Низ JSON  | Списък с уникални сегменти профилът на клиента е член на      |
| msdynci_identifier  | String   | Еднозначен идентификатор на записа за членство в сегмент. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | GUID      | Детерминистичен GUID, генериран от`msdynci_identifier`          |
