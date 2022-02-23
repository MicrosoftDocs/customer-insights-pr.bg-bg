---
title: Данни от "Аналитични данни за клиенти" в Microsoft Dataverse
description: Използвайте обектите "Аналитични данни за клиенти" като таблици в Microsoft Dataverse.
ms.date: 11/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 6f74559b34a95ed976a4e353c2dbabe59e1a8839
ms.sourcegitcommit: 9558ff772ee6c944fcb8db4bfc8cda13b38a1bff
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 11/29/2021
ms.locfileid: "7866921"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Работа с данни от "Аналитични данни за клиенти" в Microsoft Dataverse

"Аналитични данни за клиенти" предоставя възможност за предоставяне на изходни обекти в [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro.md). Тази интеграция позволява лесно споделяне на данни и разработка по поръчка чрез подход с нисък код / без код. Изходните обекти ще бъдат достъпни като таблици в Dataverse. Тези таблици дават възможност за сценарии като [автоматизирани работни потоци чрез Power Automate](/power-automate/getting-started), [приложения, задвижвани от модел](/powerapps/maker/model-driven-apps/), и [приложения за платно](/powerapps/maker/canvas-apps/) чрез Power Apps. Можете да използвате данните за всяко друго приложение, което се основава на Dataverse таблици. Текущата реализация поддържа главно справки, при които данните от наличните обекти с прозрения за аудиторията могат да бъдат извлечени за даден идентификатор на клиента.

## <a name="attach-a-dataverse-environment-to-customer-insights"></a>Прикачване на Dataverse среда към "Аналитични данни за клиенти"

**Организации със съществуващи Dataverse среди**

Организациите, които вече използват Dataverse, могат да [използват една от съществуващите си Dataverse среди, когато администратор настрои аналитични данни за](create-environment.md) аудиторията. Предоставяйки URL адреса на Dataverse среда, той се прикрепя към новата им среда за прозрения на аудиторията. За да се гарантира възможно най-добра производителност, В един и същи регион трябва да се хостват Клиентски аналитични данни и Dataverse среди.

**Нова организация**

Ако създадете нова организация при настройването на "Аналитични данни за клиенти", автоматично ще получите нова среда за Dataverse.

> [!NOTE]
> Ако вашите организации вече използват Dataverse в своя наемател, важно е да запомните, че [създаването на Dataverse среда се контролира от администратор](/power-platform/admin/control-environment-creation.md) . Например, ако настройвате нова среда за прозрения на аудиторията с организационния си профил и администраторът е забранил създаването на Dataverse пробни среди за всички, с изключение на администраторите, не можете да създадете нова пробна среда.
> 
> Средите на Dataverse пробни версии, създадени в Customer Insights, имат 3 ГБ място за съхранение, което няма да се брои за общия капацитет, който има право на наемателя. Платените абонаменти получават Dataverse право на 15 GB за база данни и 20 GB за съхранение на файлове.

## <a name="output-entities"></a>Изходни обекти

Някои изходни обекти от аналитични данни за аудитории се предлагат като таблици в Dataverse. Разделите по-долу описват очакваната схема на тези таблици.

- [CustomerProfile](#customerprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Обогатяване](#enrichment)
- [Прогноза](#prediction)
- [Членство в сегмент](#segment-membership)


### <a name="customerprofile"></a>CustomerProfile

Тази таблица съдържа единния потребителски профил от Customer Insights. Схемата за унифициран клиентски профил зависи от обектите и атрибутите, използвани в процеса на обединяване. Схемата на потребителския профил обикновено съдържа подмножество на атрибутите от [Дефиниция на Common Data Model на CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile).

### <a name="alternatekey"></a>AlternateKey

Таблицата AlternateKey съдържа ключове на обектите, участвали в процеса на обединяване.

|Column  |Тип  |Описание  |
|---------|---------|---------|
|DataSourceName    |String         | Име на източник на данни. Например: `datasource5`        |
|EntityName        | String        | Име на обекта в статистика за аудиторията. Например: `contact1`        |
|AlternateValue    |String         |Алтернативен идентификатор, който се съпоставя с идентификатора на клиента. Пример: `cntid_1078`         |
|KeyRing           | Многоредов текст        | Стойност на JSON  </br> Извадка: [{"данниИзточникИме":" datasource5 ",</br>"entityName":" contact1",</br>"preferredKey":" cntid_1078",</br>"ключове":[" cntid_1078"]}]       |
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
| СегментПрочетир      | String       | Приложение, което публикува сегментите. По подразбиране: Прозрения на аудиторията         |
| СегментМембърствоТип | String       | Тип на клиента този запис на членство в сегмент. Поддържа няколко типа като "Клиент", "Контакт" или "Акаунт". По подразбиране: Клиент  |
| Сегменти       | Низ JSON  | Списък с уникални сегменти профилът на клиента е член на      |
| msdynci_identifier  | String   | Еднозначен идентификатор на записа за членство в сегмент. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | GUID      | Детерминистичен GUID, генериран от`msdynci_identifier`          |
