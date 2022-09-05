---
title: OData примери за заявки за API за аналитични данни за клиенти
description: Често използвани примери за Протокола за отворени данни (OData) за заявка на API за аналитични данни на клиента за преглед на данни.
ms.date: 08/30/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 26e56a3bab01ba55284a52e72efbcbfbaadaad6f
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: MT
ms.contentlocale: bg-BG
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387189"
---
# <a name="odata-query-examples-for-customer-insights-apis"></a>OData примери за заявки за API за аналитични данни за клиенти

Протоколът за отворени данни (OData) е протокол за достъп до данни, изграден върху основни протоколи като HTTP. Той използва общоприети методологии като REST за мрежата. Има различни видове библиотеки и инструменти, които могат да се използват за консумиране на OData услуги.

За да ви помогне да изградите свои собствени внедрявания въз основа на API [на](apis.md) Customer Insights, прегледайте някои често искани примерни заявки.

Модифицирайте образците на заявките, за да ги накарате да работят върху целевите среди:

- {serviceRoot}: `https://api.ci.ai.dynamics.com/v1/instances/{instanceId}/data` къде {instanceId} е GUID на средата "Аналитични данни за клиенти", която искате да направите заявка. [Операцията](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) ListAllInstances ви позволява да намерите {InstanceId} достъп до вас.
- {CID}: GUID на унифициран клиентски запис. Пример: `ce759201f786d590bf2134bff576c369`.
- {AlternateKey}: Идентификатор на основния ключ на запис на клиент в източник на данни. Пример: `CNTID_1002`
- {DSname}: Низ с името на обекта на източник на данни, който се погръща в "Аналитични данни за клиенти". Пример: `Website_contacts`.
- {SegmentName}: Низ с името на изходния обект на сегмент в "Аналитични данни за клиенти". Пример: `Male_under_40`.

## <a name="customer"></a>Клиент

Примерни заявки за *обекта Клиент* .

|Тип заявка |Пример  | Бележка  |
|---------|---------|---------|
|Идентификационен номер на един клиент     | `{serviceRoot}/Customer?$filter=CustomerId eq '{CID}'`          |  |
|алтернативен ключ    | `{serviceRoot}/Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} eq '{AlternateKey}'`         |  Алтернативните ключове се запазват в унифицирания обект клиент       |
|Select   | `{serviceRoot}/Customer?$select=CustomerId,FullName&$filter=customerid eq '1'`        |         |
|След    | `{serviceRoot}/Customer?$filter=CustomerId in ('{CID1}',’{CID2}’)`        |         |
|алтернативен ключ + В   | `{serviceRoot}/Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} in ('{AlternateKey}','{AlternateKey}')`         |         |
|Търсете  | `{serviceRoot}/Customer?$top=10&$skip=0&$search="string"`        |   Връща топ 10 резултати за низ за търсене      |
|Членство в сегмент  | `{serviceRoot}/Customer?select=*&$filter=IsMemberOfSegment('{SegmentName}')&$top=10`     | Връща предварително зададен брой редове от обекта за сегментиране.      |
|Членство в сегмент за клиент | `{serviceRoot}/Customer?$filter=CustomerId eq '{CID}'&IsMemberOfSegment('{SegmentName}')`     | Връща потребителския профил на клиента, ако е член на дадения сегмент     |

## <a name="unified-activity"></a>Единна дейност

Примерни заявки за *обекта Унифициранаактивност* .

|Тип заявка |Пример  | Бележка  |
|---------|---------|---------|
|Дейност на CID     | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}'`          | Изброява дейности на конкретен профил на клиент |
|Времева рамка за активност    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityTime gt 2017-01-01T00:00:00.000Z and ActivityTime lt 2020-01-01T00:00:00.000Z`     |  Дейности на клиентски профил във времева рамка       |
|Тип дейност    |   `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityType eq '{ActivityName}'`        |         |
|Дейност по показвано име     | `{serviceRoot}/UnifiedActivity$filter=CustomerId eq ‘{CID}’ and ActivityTypeDisplay eq ‘{ActivityDisplayName}’`        | |
|Сортиране на дейности    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq ‘{CID}’ & $orderby=ActivityTime asc`     |  Сортиране на дейности възходящи или низходящи       |
|Активността е разширена от членството в сегмент  |   `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId eq '{CID}'`     |         |

## <a name="other-examples"></a>Други примери

Примерни заявки за други обекти.

|Тип заявка |Пример  | Бележка  |
|---------|---------|---------|
|Мерки на CID    | `{serviceRoot}/Customer_Measure?$filter=CustomerId eq '{CID}'`          |  |
|Обогатени марки на CID    | `{serviceRoot}/BrandShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`  |       |
|Обогатени интереси на CID    |   `{serviceRoot}/InterestShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`       |         |
|In-клауза + Разгъване     | `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId in ('{CID}', '{CID}')`         | |

## <a name="not-supported-odata-queries"></a>Не се поддържа OData заявки

Следните заявки не се поддържат от "Аналитични данни за клиенти":

- `$filter` относно субектите от най-много източници. Можете да изпълнявате само $filter заявки на системни обекти, които Customer Insights създава.
- `$expand` от `$search` заявка. Пример: `Customer?$expand=UnifiedActivity$top=10&$skip=0&$search="corey"`
- `$expand` от `$select` ако е избрано само подмножество от атрибути. Пример: `Customer?$select=CustomerId,FullName&$expand=UnifiedActivity&$filter=CustomerId eq '{CID}'`
- `$expand` обогатена марка или интерес афинитети за даден клиент. Пример: `Customer?$expand=BrandShareOfVoiceFromMicrosoft&$filter=CustomerId eq '518291faaa12f6d853c417835d40eb10'`
- Заявка прогноза обекти за изход на модел чрез алтернативен ключ. Пример: `OOBModelOutputEntity?$filter=HotelCustomerID eq '{AK}'`
