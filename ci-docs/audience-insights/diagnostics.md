---
title: Проверка Dynamics 365 Customer Insights с Монитор на Azure
description: Научете как да изпращате регистрационни файлове на Microsoft Azure Monitor.
ms.date: 12/14/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: article
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 18fc072d129be6b4fc5470b1057f592dc2638216
ms.sourcegitcommit: 5bd07f3a1288f003704acd576741cf6aedc1ac33
ms.translationtype: MT
ms.contentlocale: bg-BG
ms.lasthandoff: 03/31/2022
ms.locfileid: "8523655"
---
# <a name="log-forwarding-in-dynamics-365-customer-insights-with-azure-monitor-preview"></a>Влизане в препращане Dynamics 365 Customer Insights с Azure монитор (визуализация)

Dynamics 365 Customer Insights осигурява директна интеграция с Azure Монитор. Регистрационните файлове за ресурси на Azure Monitor ви позволяват да наблюдавате и изпращате регистрационни файлове в [Хранилище на Azure](https://azure.microsoft.com/services/storage/), [Azure Log Analytics](/azure/azure-monitor/logs/log-analytics-overview) или да ги предавате поточно в [центровете](https://azure.microsoft.com/services/event-hubs/) за събития в Azure.

"Аналитични данни за клиенти" изпраща следните регистрационни файлове за събития:

- **Одитни събития**
  - **APIEvent** - дава възможност за проследяване на промените, направено чрез Dynamics 365 Customer Insights ПИ.
- **Оперативни събития**
  - **WorkflowEvent** - Работният поток позволява на един да настроите [Източници на](data-sources.md) данни, [да унифицирате](data-unification.md) и обогатявате [и](enrichment-hub.md) накрая [да експортирате](export-destinations.md) данни в други системи. Всички тези стъпки могат да се направят индивидуално (например да предизвикат единен износ) или да бъдат оркестрирани (напр. опресняване на данните от източници на данни, които задействат процеса на обединение, който ще изтегли допълнителни обогатявания и след като бъде направен износ на данните в друга система). За повече подробности вижте [работния потокСъбитие схема](#workflow-event-schema).
  - **APIEvent** - всички API повиквания към екземпляра на клиентите да Dynamics 365 Customer Insights. За повече подробности вижте Схемата [на](#api-event-schema) APIEvent.

## <a name="set-up-the-diagnostic-settings"></a>Настройване на настройките за диагностика

### <a name="prerequisites"></a>Предварителни изисквания

За да конфигурирате диагностиката в "Статистика за клиенти", трябва да бъдат изпълнени следните предпоставки:

- Имате активен [абонамент](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/) за Azure.
- Имате [администраторски](permissions.md#admin) разрешения в "Аналитични данни за клиенти".
- Имате ролята на администратор на **сътрудник** и **потребителски достъп** на местоназначение ресурс на Azure. Ресурсът може да бъде акаунт за хранилище в Azure, център за събития в Azure или работна област на Azure Log Analytics. За повече информация вижте [Добавяне или премахване на присвоявания на роля на Azure с помощта на портала](/azure/role-based-access-control/role-assignments-portal) на Azure.
- [Изпълнени са изискванията](/azure/azure-monitor/platform/diagnostic-settings#destination-requirements) за местоназначение за хранилище в Azure, център за събития в Azure или Анализ на регистрационния файл на Azure.
- Имате поне ролята на **Reader** в групата ресурси, към която принадлежи ресурсът.

### <a name="set-up-diagnostics-with-azure-monitor"></a>Настройване на диагностиката с Azure монитор

1. В Статистика за клиенти изберете **SystemDiagnostics** > **·**, за да видите дестинациите за диагностика, конфигурирани този екземпляр.

1. Изберете **Добавяне на** местоназначение.

   > [!div class="mx-imgBorder"]
   > ![Връзка за диагностика](media/diagnostics-pane.png "Връзка за диагностика")

1. Предоставете име в полето **Име за местоназначение** за диагностика.

1. Изберете **наемателя** на абонамента за Azure с ресурса местоназначение и изберете **влизане**.

1. Изберете **типа** ресурс (Акаунт за съхранение, Център за събития или анализ на регистрационните файлове).

1. Изберете **абонамента** за ресурса местоназначение.

1. Изберете **групата** ресурси за ресурса местоназначение.

1. Изберете **ресурса**.

1. Потвърдете **декларацията за поверителност и съответствие с** Данните.

1. Изберете **Свързване със системата**, за да се свържете с ресурса местоназначение. Регистрационните файлове започват да се появяват в местоназначението след 15 минути, ако API се използва и генерира събития.

### <a name="remove-a-destination"></a>Премахване на дестинация

1. Отидете на **СистемаДиагносттика** > **·**.

1. Изберете дестинацията за диагностика в списъка.

1. В **колоната Действия** изберете иконата **Изтриване**.

1. Потвърдете изтриването, за да спрете препращането на регистрационния файл. Ресурсът в абонамента за Azure няма да бъде изтрит. Можете да изберете връзката в **колоната Действия,** за да отворите портала на Azure за избрания ресурс и да я изтриете там.

## <a name="log-categories-and-event-schemas"></a>Регистрационни категории и схеми на събития

В момента [се поддържат API събития](apis.md) и събития на работния поток и се прилагат следните категории и схеми.
Схемата на регистрационния файл следва общата схема на [Azure монитор](/azure/azure-monitor/platform/resource-logs-schema#top-level-common-schema).

### <a name="categories"></a>Категории

"Клиентски аналитични данни" предоставя две категории:

- **Проверка на събития**: [API събития](#api-event-schema) за проследяване на промените в конфигурацията на услугата. `POST|PUT|DELETE|PATCH` операциите влизат в тази категория.
- **Оперативни събития**: [API събития](#api-event-schema) или [събития](#workflow-event-schema) на работен поток, генерирани по време на използване на услугата.  Например `GET` заявки или събитията за изпълнение на работен поток.

## <a name="configuration-on-the-destination-resource"></a>Конфигурация на ресурса местоназначение

Въз основа на вашия избор на типа ресурс автоматично ще се прилагат следните стъпки:

### <a name="storage-account"></a>Акаунт на хранилище

Клиент insights услуга принципал получава **разрешение За съхранение сметка Сътрудник** на избрания ресурс и създава два контейнера под избраното пространство на имената:

- `insight-logs-audit` съдържащи **одитни събития**
- `insight-logs-operational` съдържащи **оперативни събития**

### <a name="event-hub"></a>Център за събития

Клиент прозрения услуга принципал получава **azure събитие центрове собственик на данни собственик** на ресурса и ще създаде два Центъра за събития под избраното пространство на имената:

- `insight-logs-audit` съдържащи **одитни събития**
- `insight-logs-operational` съдържащи **оперативни събития**

### <a name="log-analytics"></a>Регистрационен анализ

Директорът на услугата "Статистика за клиенти" получава **разрешението "Сътрудник в Log Analytics Contributor** " на ресурса. Регистрационните файлове ще бъдат достъпни под **LogsTablesLog** > **·** > **Управление** на избраната работна област на Log Analytics. Разгънете **решението за управление на** регистрационния файл и намерете таблиците `CIEventsAudit` и `CIEventsOperational` таблиците.

- `CIEventsAudit` съдържащи **одитни събития**
- `CIEventsOperational` съдържащи **оперативни събития**

Под прозореца **Заявки разгънете** решението проверка **и намерете примерните заявки, предоставени чрез търсене на**`CIEvents`.

## <a name="event-schemas"></a>Схеми на събития

API събитията и събитията на работния поток имат обща структура и подробности, където те се различават, вижте [API схема](#api-event-schema) на събитие или [схема](#workflow-event-schema) на събитие на работен поток.

### <a name="api-event-schema"></a>API схема на събитие

| Поле             | Тип данни  | Задължително/Незадължително | Описание       | Пример        |
| ----------------- | --------- | ----------------- | --------------------- | ------------------------ |
| `time`            | Времево клеймо | Необходимо          | Клеймо на събитието (UTC)       | `2020-09-08T09:48:14.8050869Z`         |
| `resourceId`      | String    | Необходимо          | ResourceId на екземпляра, който е излъчвал събитието         | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX`  |
| `operationName`   | String    | Необходимо          | Име на операцията, представена от това събитие.                                                                                                                | `Workflows.GetWorkFlowStatusAsync`                                                                                                                                       |
| `category`        | String    | Необходимо          | Регистрационна категория на събитието. Или `Operational` или `Audit`. Всички POST/PUT/PATCH/DELETE HTTP Заявки са маркирани с `Audit`, всичко останало с`Operational` | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resultType`      | String    | Необходимо          | Състояние на събитието. `Success`, `ClientError`, `Failure`                                                                                                        |                                                                                                                                                                          |
| `resultSignature` | String    | Незадължителен          | Състояние на резултата от събитието. Ако операцията съответства на REST API повикване, това е кода на състоянието на HTTP.        | `200`             |
| `durationMs`      | Дълъг      | Незадължителен          | Продължителност на операцията в милисекунди.     | `133`     |
| `callerIpAddress` | String    | Незадължителен          | IP адрес на обаждащ се, ако операцията съответства на API повикване, което идва от публично достъпен IP адрес.                                                 | `144.318.99.233`         |
| `identity`        | String    | Незадължителен          | JSON обект, описващ самоличността на потребителя или приложението, което е извършило операцията.       | Вижте [Секция "Самоличност](#identity-schema) ".     |  
| `properties`      | String    | Незадължителен          | JSON обект с повече свойства към конкретната категория събития.      | Вижте [Свойства](#api-properties-schema) раздел.    |
| `level`           | String    | Необходимо          | Ниво на тежест на събитието.    | `Informational`, `Warning`, `Error` или `Critical`.           |
| `uri`             | String    | Незадължителен          | Абсолютна заявка URI.    |               |

#### <a name="identity-schema"></a>Схема за самоличност

Обектът `identity` JSON има следната структура

```json
{
  "Authorization" : {
    "UserRole": "Admin",
    "RequiredRoles": [
      "Contributor",
      "Viewer"
      ]
    },
  "Claims" {
    "claimNameX" : "claimValueX",
    "claimNameY" : "claimValueY"
   }
}  
```

| Поле                         | Описание                                                                                                                          |
| ----------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| `Authorization.UserRole`      | Присвоена роля за потребителя или приложението. За повече информация вижте [потребителските](permissions.md) разрешения.                                     |
| `Authorization.RequiredRoles` | Необходими роли за извършване на операцията. `Admin` роля е позволено да се правят всички операции.                                                    |
| `Claims`                      | Претенции на потребителя или приложението JSON уеб маркер (JWT). Свойствата на претенцията варират за организация и конфигурацията Azure Active Directory. |

#### <a name="api-properties-schema"></a>Схема на свойствата на API

[API събитията](apis.md) имат следните свойства.

| Поле                        | Описание                                                                                                            |
| ---------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| `properties.eventType`       | Винаги `ApiEvent`, маркиране на регистрационното събитие като API събитие.                                                                 |
| `properties.userAgent`       | Агент на браузъра, изпращащ заявката или `unknown`.                                                                        |
| `properties.method`          | HTTP метод:`GET/POST/PUT/PATCH/HEAD`.                                                                                |
| `properties.path`            | Относителен път на искането.                                                                                          |
| `properties.origin`          | URI, показваща откъде идва допир или `unknown`.                                                                  |
| `properties.operationStatus` | `Success` за HTTP Код на състоянието < 400 <br> `ClientError` за HTTP Код на състоянието < 500 <br> `Error` за HTTP състояние >= 500 |
| `properties.tenantId`        | ИД на организация                                                                                                        |
| `properties.tenantName`      | Име на организацията.                                                                                              |
| `properties.callerObjectId`  | Azure Active Directory ObjectId на повикващия.                                                                         |
| `properties.instanceId`      | Аналитични данни за клиенти`instanceId`                                                                                         |

### <a name="workflow-event-schema"></a>Схема на събитие на работен поток

Работният поток съдържа няколко стъпки. [Въвеждане на източници на](data-sources.md) данни, [обединение](data-unification.md), [обогатяване](enrichment-hub.md) и [експортиране](export-destinations.md) на данни. Всички тези стъпки могат да се изпълняват индивидуално или оркестрирани със следните процеси. 

#### <a name="operation-types"></a>Типове операции

| OperationType     | Групов                                     |
| ----------------- | ----------------------------------------- |
| Поглъщане         | [Източници на данни](data-sources.md)           |
| Подготовка на данни   | [Източници на данни](data-sources.md)           |
| Картова               | [Обединяване на данни](data-unification.md)   |
| Съвпадение             | [Обединяване на данни](data-unification.md)   |
| Обедини             | [Обединяване на данни](data-unification.md)   |
| ПрофилСтор      | [Профили на клиент](customer-profiles.md) |
| Търсете            | [Профили на клиент](customer-profiles.md) |
| Дейност          | [Дейности](activities.md)                  |
| АтрибутМерения | [Сегменти и мерки](segments.md)      |
| ОбектМерения    | [Сегменти и мерки](segments.md)      |
| Мерки          | [Сегменти и мерки](segments.md)      |
| Сегментиране      | [Сегменти и мерки](segments.md)      |
| Допълване        | [Обогатяване](enrichment-hub.md)                                          |
| Разузнаване      | [Прогнози](predictions-overview.md)                                          |
| АйБилдър         | [Прогнози](predictions-overview.md)                                          |
| Прозрения          | [Прогнози](predictions-overview.md)                                          |
| Export            | [Експортирания](export-destinations.md)                                          |
| Управление на модели   | [Прогнози](custom-models.md)                                           |
| Релация      | [Обединяване на данни](relationships.md)                                           |

#### <a name="field-description"></a>Описание на полето

| Поле           | Тип данни  | Задължително/Незадължително | Описание                                                                                                                                                   | Пример                                                                                                                                                                  |
| --------------- | --------- | ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `time`          | Времево клеймо | Необходимо          | Клеймо на събитието (UTC).                                                                                                                                 | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resourceId`    | String    | Необходимо          | ResourceId на екземпляра, който е излъчвал събитието.                                                                                                            | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX` |
| `operationName` | String    | Необходимо          | Име на операцията, представена от това събитие. `{OperationType}.[WorkFlow|Task][Started|Completed]`. Вижте [Типове операции](#operation-types) за справка. | `Segmentation.WorkflowStarted`,<br> `Segmentation.TaskStarted`, <br> `Segmentation.TaskCompleted`, <br> `Segmentation.WorkflowCompleted`                                 |
| `category`      | String    | Необходимо          | Регистрационна категория на събитието. Винаги `Operational` за събития от работния поток                                                                                           | `Operational`                                                                                                                                                            | 
| `resultType`    | String    | Необходимо          | Състояние на събитието. `Running`, `Skipped`, `Successful`, `Failure`                                                                                            |                                                                                                                                                                          |
| `durationMs`    | Дълъг      | Незадължителен          | Продължителност на операцията в милисекунди.                                                                                                                    | `133`                                                                                                                                                                    |
| `properties`    | String    | Незадължителен          | JSON обект с повече свойства към конкретната категория събития.                                                                                        | Вижте под раздел [Свойства на работен поток](#workflow-properties-schema)                                                                                                       |
| `level`         | String    | Необходимо          | Ниво на тежест на събитието.                                                                                                                                  | `Informational`, `Warning` или `Error`                                                                                                                                   |
|                 |

#### <a name="workflow-properties-schema"></a>Схема на свойствата на работния поток

Събитията на работния поток имат следните свойства.

| Поле              | Workflow | Задача | Описание            |
| ------------------------------- | -------- | ---- | ----------- |
| `properties.eventType`                       | Да      | Да  | Винаги `WorkflowEvent`, маркиране на събитието като събитие на работен поток.                                                                                                                                                                                                |
| `properties.workflowJobId`                   | Да      | Да  | Идентификатор на изпълнението на работния поток. Всички събития на работния поток и задачите в рамките на изпълнението на работния поток имат еднакви `workflowJobId`.                                                                                                                                   |
| `properties.operationType`                   | Да      | Да  | Идентификатор на операцията вижте [Типове операции](#operation-types).                                                                                                                                                                               |
| `properties.tasksCount`                      | Да      | No   | Само работен поток. Брой задачи задейства работния поток.                                                                                                                                                                                                       |
| `properties.submittedBy`                     | Да      | No   | По избор. Само за събития от работния поток. Azure Active Directory [ObjectId на потребителя](/azure/marketplace/find-tenant-object-id#find-user-object-id), който е задействал работния поток, вижте също `properties.workflowSubmissionKind`.                                   |
| `properties.workflowType`                    | Да      | No   | `full` или `incremental` опресняване.                                                                                                                                                                                                                            |
| `properties.workflowSubmissionKind`          | Да      | No   | `OnDemand` или `Scheduled`.                                                                                                                                                                                                                                  |
| `properties.workflowStatus`                  | Да      | No   | `Running` или `Successful`.                                                                                                                                                                                                                                 |
| `properties.startTimestamp`                  | Да      | Да  | UTC Клеймо`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.endTimestamp`                    | Да      | Да  | UTC Клеймо`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.submittedTimestamp`              | Да      | Да  | UTC Клеймо`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.instanceId`                      | Да      | Да  | Аналитични данни за клиенти`instanceId`                                                                                                                                                                                                                              |  
| `properties.identifier`                      | No       | Да  | - За OperationType = `Export`, идентификаторът е ръководството на конфигурацията за експортиране. <br> - За OperationType = `Enrichment`, това е ръководството на обогатяването <br> - За OperationType `Measures` и `Segmentation`, идентификаторът е името на обекта. |
| `properties.friendlyName`                    | No       | Да  | Потребителско име на експортирането или обекта, който се обработва.                                                                                                                                                                                           |
| `properties.error`                           | No       | Да  | По избор. Съобщение за грешка с повече подробности.                                                                                                                                                                                                                  |
| `properties.additionalInfo.Kind`             | No       | Да  | По избор. Само за ОперацияТип `Export`. Идентифицира вида на експортирането. За повече информация вижте [общ преглед на дестинациите за](export-destinations.md) експортиране.                                                                                          |
| `properties.additionalInfo.AffectedEntities` | No       | Да  | По избор. Само за ОперацияТип `Export`. Съдържа списък с конфигурирани обекти в експортирането.                                                                                                                                                            |
| `properties.additionalInfo.MessageCode`      | No       | Да  | По избор. Само за ОперацияТип `Export`. Подробно съобщение за експортирането.                                                                                                                                                                                 |
| `properties.additionalInfo.entityCount`      | No       | Да  | По избор. Само за ОперацияТип `Segmentation`. Показва общите номера на членовете, които сегментът има.                                                                                                                                                    |
