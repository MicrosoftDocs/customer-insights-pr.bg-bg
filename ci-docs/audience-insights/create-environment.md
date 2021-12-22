---
title: Създаване на среди в Customer Insights
description: Стъпки за създаване на среди с лицензиран абонамент за Dynamics 365 Customer Insights.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 4f26220f6ba7f5b5ae00c11216129f9ad814b77d
ms.sourcegitcommit: 626d485dae1e001e63e4d4bf78f6770766822ba0
ms.translationtype: MT
ms.contentlocale: bg-BG
ms.lasthandoff: 12/06/2021
ms.locfileid: "7892325"
---
# <a name="create-an-environment-in-audience-insights"></a>Създаване на среда в аналитични данни за аудиторията

Тази статия обяснява как да създадете нова среда, след като организацията е закупила абонамент за Dynamics 365 Customer Insights. 

Организациите могат да създават *две* среди за всеки лиценз за Customer Insights. Ако вашата организация закупи повече от един лиценз, [свържете се с нашия екип за поддръжка](https://go.microsoft.com/fwlink/?linkid=2079641), за да увеличите броя на наличните среди. За повече информация относно капацитета и допълнителния капацитет изтеглете [ръководството за лицензиране на Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

> [!NOTE]
> Ако искате да опитате услугата, вижте [Настройте пробна среда](../trial-signup.md).

## <a name="create-a-new-environment"></a>Създаване на нова среда

След закупуване на лиценз за абонамент за Customer Insights, глобалният администратор на клиента на Microsoft 365 получава имейл с покана за създаване на среда. Отидете на [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start), за да започнете. 

Ръководеният опит ви помага през стъпките да съберете цялата необходима информация за нова среда. Имате нужда от [администраторски разрешения](permissions.md) в аналитични данни на аудиторията за създаване или управление на среди.

1. В аналитични данни за аудиторията отворете инструмента за избор на среда и изберете **+ Ново**.
  
   :::image type="content" source="../engagement-insights/media/environment-picker.png" alt-text="Изберете инструмента за избор на средата.":::

1. Следвайте направляваното изживяване, описано в следващите раздели.

### <a name="step-1-provide-environment-information"></a>Стъпка 1: Предоставете информация за околната среда

В **Основна информация** стъпка, изберете дали искате да създадете среда от нулата или [копирайте данни от друга среда](manage-environments.md#copy-the-environment-configuration).

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Диалогов прозорец за създаване на нова среда на Customer Insights.":::

Посочете следните подробности:
   - **Име**: Името за тази среда. Това поле вече е попълнено, ако сте копирали от съществуваща среда, но можете да го промените.
   - **Изберете бизнеса**: Изберете основната аудитория за новата среда. Може да работите с отделни потребители (B-to-C) или с [бизнес акаунти](work-with-business-accounts.md) (B-to-B).
   - **Тип**: Изберете дали искате да създадете производствена среда или среда в ограничителен режим. Средата в ограничителен режим не позволява планирано обновяване на данни и е предназначена за предварително внедряване и тестване. Средите с пясъчник използват същата основна аудитория като производствената среда, която е избрана в момента.
   - **Регион**: Регионът, в който е внедрена и хоствана услугата.

### <a name="step-2-configure-data-storage"></a>Стъпка 2: Конфигурирайте съхранение на данни

В стъпката **Хранилище за данни** изберете къде да съхранявате данните от статистика за аудиторията.

Ще имате две възможности: **Съхранение на Customer Insights** (хранилище за необработени данни на Azure, управлявано от екипа на Customer Insights) и **Azure Data Lake Storage** (собствено Azure Data Lake Storage). По подразбиране е избрана опцията за съхранение в Customer Insights.

:::image type="content" source="media/data-storage-environment.png" alt-text="Изберете Azure Data Lake Storage за съхраняване на данните за вашата аудитория.":::

Като запишете данни в Azure Data Lake Storage, вие се съгласявате, че данните ще бъдат прехвърляни и съхранявани в подходящото географско местоположение за този акаунт за съхранение в Azure. Това местоположение може да се различава от мястото, където се съхраняват данните Dynamics 365 Customer Insights. Научете повече в [центъра за сигурност на Microsoft](https://www.microsoft.com/trust-center).

> [!NOTE]
> Понастоящем Customer Insights поддържа следното:
> - Вградени обекти от Power BI потоци от данни, които се съхраняват в управляван от Microsoft Dataverse Data Lake.  
> - Акаунти в Azure Data Lake Storage от същия регион на Azure, който сте избрали при създаването на средата.
> - Акаунти в Azure Data Lake Storage, които имат активирано *йерархично пространство от имена*.

За опцията Azure Data Lake Storage, можете да избирате между базирана на ресурси опция и опция, базирана на абонамент за удостоверяване. За повече информация вижте [Свързване с акаунт на Azure Data Lake Storage с помощта на ръководител на услуга на Azure](connect-service-principal.md). Името на **Контейнер** ще бъде `customerinsights` и не може да се променя.

Когато системните процеси, като поглъщането на данни приключи, системата създава съответни папки в акаунта за съхранение, който сте посочили. Създават се файлове с данни и файлове *model.json* и се добавят към папки въз основа на името на процеса.

Ако създадете множество среди на Customer Insights и изберете да запишете изходните обекти от тези среди във вашия акаунт за съхранение, Customer Insights създава отделни папки за всяка среда с `ci_environmentID` в контейнера.

### <a name="step-3-connect-to-microsoft-dataverse"></a>Стъпка 3: Свързване към Microsoft Dataverse
   
Стъпката **Microsoft Dataverse** ви позволява да свържете Customer Insights с вашата среда на Dataverse.

За да използвате [подготвени модели на прогноза](predictions-overview.md#out-of-box-models), конфигурирайте споделянето на данни с Dataverse. Или можете да активирате поглъщането на данни от локален източници на данни, предоставяйки URL адрес на средата на Microsoft Dataverse, който администрира вашата организация. Изберете **Активиране на споделянето на данни** за споделяне на изходни данни на Customer Insights с управлявано от Dataverse хранилище за необработени данни.

> [!IMPORTANT]
> "Аналитични данни за клиенти" и Dataverse трябва да бъдат в същия регион, за да се даде възможност за споделяне на данни.

:::image type="content" source="media/dataverse-data-sharing.png" alt-text="Опции за конфигуриране, за да се даде възможност за споделяне на данни с Microsoft Dataverse.":::

> [!NOTE]
> Customer Insights не поддържа следните сценарии за споделяне на данни:
> - Ако запишете всички данни в собствено Azure Data Lake Storage, няма да можете да активирате споделянето на данни с управлявано от Dataverse хранилище за необработени данни.
> - Ако активирате споделянето на данни с Dataverse, няма да можете да [създавате предвидени или липсващи стойности в обект](predictions.md).

### <a name="step-4-finalize-the-settings"></a>Стъпка 4: Завършване на настройките

В стъпката **Преглед** преминете през всички посочени настройки. Когато всичко изглежда завършено, изберете **създаване** за създаване на среда. 

Можете също да промените повечето настройки по -късно. За повече информация вижте [Управление на среди](manage-environments.md).

## <a name="work-with-your-new-environment"></a>Работете с новата си среда

Прегледайте следващите статии, които ще ви помогнат да започнете с конфигурирането на Customer Insights: 

- [Добавяне на още потребители и присвояване на разрешения](permissions.md).
- [Приемете източниците на данни](data-sources.md) и ги изпълнете чрез [процеса на унифициране на данни](data-unification.md), за да получите [унифицирани клиентски профили](customer-profiles.md).
- [Обогатете унифицираните клиентски профили](enrichment-hub.md) или [изпълнете модели за прогнозиране](predictions-overview.md).
- [Създайте сегменти](segments.md), за да групирате клиенти, и [мерки](measures.md), за да преглеждате KPI.
- [Задайте връзки](connections.md) и [експортиране](export-destinations.md) за обработка на поднабори от данните в други приложения.