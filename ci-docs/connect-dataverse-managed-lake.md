---
title: Свързване с данни в управлявано от Microsoft Dataverse хранилище за необработени данни
description: Импортиране на данни от управлявано хранилище Data Lake в Microsoft Dataverse.
ms.date: 08/18/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: v-wendysmith
searchScope:
- ci-dataverse
- customerInsights
ms.openlocfilehash: 0d9612525344c8ac99b6e3edfe33a426dc0a474b
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: bg-BG
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609778"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Свързване с данни в управлявано от Microsoft Dataverse хранилище за необработени данни

Microsoft Dataverse Потребителите могат бързо да се свържат с аналитични обекти в управлявано Microsoft Dataverse езеро. Само един източник на данни от среда може едновременно да използва същото управлявано хранилище на Dataverse.

> [!NOTE]
> Трябва да сте администратор в организацията, за да продължите и да видите списъка на единиците, Dataverse налични в управляваното езеро.

## <a name="prerequisites"></a>Предварителни изисквания

- Данните, съхранявани в онлайн услуги като Azure Data Lake Storage може да се съхраняват на различно място от това, на което се обработват или съхраняват данни в Dynamics 365 Customer Insights.Чрез импортиране или свързване към данни, съхранявани в онлайн услуги, Вие се съгласявате, че данните могат да бъдат прехвърляни и съхранявани с Dynamics 365 Customer Insights. [Научете повече в Доверителния център на Microsoft](https://www.microsoft.com/trust-center).

- Видими са само Dataverse субекти с [активирано проследяване на](/power-platform/admin/enable-change-tracking-control-data-synchronization) промените. Тези субекти могат да бъдат експортирани в управляваното езеро за Dataverse данни и да се използват в Customer Insights. Таблиците извън кутията Dataverse са активирани по подразбиране за проследяване на промените. Трябва да включите проследяването на промените за персонализирани таблици. За да проверите дали Dataverse дадена таблица е разрешена за проследяване на промените, отидете в [Power Apps](https://make.powerapps.com) > **таблици с** > **данни**. Намерете таблицата на вашия интерес и го изберете. Отидете в Настройки **Разширени опции** > **и прегледайте настройката за промени** в **проследяването**.

## <a name="connect-to-a-dataverse-managed-lake"></a>Свържете се с управлявано от Dataverse хранилище

1. Отидете на **Данни** > **Източници на данни**.

1. Изберете **Добавяне на източник на данни**.

1. Изберете **Microsoft Dataverse**.

1. Въведете **име** за източник на данни и незадължително **описание**.

1. Въведете **адреса на сървъра** за организацията на Dataverse и изберете **Влизане**.

1. Изберете таблиците, които искате да поглъщате като същности към Клиентски прозрения от наличния списък.

   > [!NOTE]
   > Ако някои таблици вече са избрани, те може да се използват от други приложения на Dynamics 365 (като Dynamics 365 Sales Insights или Customer Service Insights). Не можете да променяте този избор. Тези таблици ще са достъпни като обекти след създаването на източник на данни.

    :::image type="content" source="media/select-dataverse-entities.png" alt-text="Диалогов прозорец, който показва списък с обекти в средата на Dataverse.":::

1. Запишете своя избор, за да започнете да синхронизирате избраните таблици от Dataverse. Ще намерите ново добавената връзка на страницата **Източници на данни**. Той ще се постави в опашката за обновяване и ще покаже броя на обектите като 0, докато всички избрани таблици се синхронизират.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Зареждането на данни може да отнеме време. След успешно обновяване, погълнатите данни могат да бъдат прегледани от страницата на Същностите [**·**](entities.md).

## <a name="edit-a-dataverse-managed-lake-data-source"></a>Редактиране на управляван от Dataverse източник на данни на хранилище

Вие редактирате избора на обекти само след като създадете източник на данни. Например, ако в Dataverse са добавени допълнителни обекти и вие също искате да ги импортирате.
За да се свържете с различен Data Lake на Dataverse, [създайте нов източник на данни](#connect-to-a-dataverse-managed-lake).

1. Отидете на **Данни** > **Източници на данни**.

1. До източник на данни, които искате да актуализирате, изберете **Редактиране**.

1. Изберете допълнителни субекти от наличния списък на субектите.

1. Щракнете върху Запиши **, за да приложите** промените си и да се върнете към страницата с източници **на** данни.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="common-reasons-for-ingestion-errors-or-corrupted-data"></a>Често срещани причини за грешки при поглъщане или повредени данни

Следните проверки се изпълняват върху приетите данни, за да се разкрият повредени записи:

- Стойността на полето не съвпада с типа данни на колоната.
- Полетата съдържат символи, заради които колоните не съответстват на очакваната схема. Например: неправилно форматирани кавички, непропуснати кавички или знаци за нов ред.
- Ако има колони за дата/дата/дата, форматът им трябва да бъде посочен в модела, ако не следва стандартния ISO формат.

### <a name="schema-or-data-type-mismatch"></a>Схема или несъответствие на типа данни

Ако данните не съответстват на схемата, записите се класифицират като повредени. Коригирайте или изходните данни, или схемата и повторно поглъщане на данните.

### <a name="datetime-fields-in-the-wrong-format"></a>Полета за дата в грешен формат

Полетата за дата в предприятието не са в ISO или en-US формати. Форматът по подразбиране за дата в Customer Insights е формат en-US. Всички полета за дата в предприятието трябва да бъдат в един и същ формат. Customer Insights поддържа други формати, при условие че анотации или черти са направени на ниво източник или субект в модела или manifest.json. Например:

**Модел.json**

   ```json
      "annotations": [
        {
          "name": "ci:CustomTimestampFormat",
          "value": "yyyy-MM-dd'T'HH:mm:ss:SSS"
        },
        {
          "name": "ci:CustomDateFormat",
          "value": "yyyy-MM-dd"
        }
      ]   
   ```

  В manifest.json форматът за дата може да бъде определен на ниво субект или на ниво атрибут. На ниво субект използвайте "експонатиЧерти" в предприятието в *.manifest.cdm.json, за да определите формата на времето за данни. На ниво атрибут използвайте "приложеничерти" в атрибута в името на предприятието.cdm.json.

**Manifest.json на ниво субект**

```json
"exhibitsTraits": [
    {
        "traitReference": "is.formatted.dateTime",
        "arguments": [
            {
                "name": "format",
                "value": "yyyy-MM-dd'T'HH:mm:ss"
            }
        ]
    },
    {
        "traitReference": "is.formatted.date",
        "arguments": [
            {
                "name": "format",
                "value": "yyyy-MM-dd"
            }
        ]
    }
]
```

**Entity.json на ниво атрибут**

```json
   {
      "name": "PurchasedOn",
      "appliedTraits": [
        {
          "traitReference": "is.formatted.date",
          "arguments" : [
            {
              "name": "format",
              "value": "yyyy-MM-dd"
            }
          ]
        },
        {
          "traitReference": "is.formatted.dateTime",
          "arguments" : [
            {
              "name": "format",
              "value": "yyyy-MM-ddTHH:mm:ss"
            }
          ]
        }
      ],
      "attributeContext": "POSPurchases/attributeContext/POSPurchases/PurchasedOn",
      "dataFormat": "DateTime"
    }
```

[!INCLUDE [footer-include](includes/footer-banner.md)]
