---
title: Първи стъпки с Dynamics 365 Customer Insights
description: Преглед на "Аналитични данни за клиенти" помага на ресурсите да започнат бързо.
ms.reviewer: v-wendysmith
ms.author: mhart
author: m-hartmann
ms.date: 04/12/2022
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: 68c26eb0ad0da787a9f594b4aebe679588b0d6bf
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: MT
ms.contentlocale: bg-BG
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833526"
---
# <a name="get-started-with-dynamics-365-customer-insights"></a>Първи стъпки с Dynamics 365 Customer Insights

Customer Insights може да ви помогне да изградите по-задълбочено разбиране за клиентите си. Свържете данни от различни източници, свързани с трансакции, поведение и наблюдение, за да създадете 360-градусов изглед на клиента. Използвайте тези аналитични данни, за да управлявате ориентираните към клиента преживявания и процеси. Обединете и разберете данните на клиентите и ги използвайте за интелигентни прозрения и действия.

## <a name="step-1-create-an-environment"></a>Стъпка 1: Създаване на нова среда

Първо, създайте среда, в която да работите. Ако вашата организация вече е закупила лиценз, вижте [Създайте среда](create-environment.md). За да стартирате пробна версия за "Аналитични данни за клиенти", вижте [Настройване на пробна среда](trial-signup.md).

## <a name="step-2-explore-customer-insights"></a>Стъпка 2: Разгледайте аналитичните данни на клиентите

Първият път, когато влезете в Customer Insights, конфигурирайте настройките и разгледайте продукта.

1. [влезте в "Аналитични данни за](https://home.ci.ai.dynamics.com) клиенти", като използвате потребителския си акаунт в Microsoft Azure Active Directory (AAD).

1. Променете средата, за да видите демо данни и [да проучите "Аналитични данни за клиенти"](home.md).

## <a name="step-3-ingest-unify-and-set-up-relationships-for-your-data"></a>Стъпка 3: Поглъщайте, унифицирайте и настройте взаимоотношения за вашите данни

Унифицираните профили са основата за получаване на информация и предприемане на действия по отношение на данните. Въведете данни от различни източници и стартирайте процеса на обединяване на данни, за да комбинирате унифицирани профили. Задайте релации между погълнените обекти и използвайте функции за обогатяване, за да добавите информация към профилите.

1. Поглъщайте данни, като създавате източници на данни от множество опции. Изберете между [Power Query конектори](connect-power-query.md), [папка](connect-common-data-model.md) "Общ модел данни" или [Microsoft Dataverse](connect-dataverse-managed-lake.md).

1. Изпълнете процеса [на обединяване на](data-unification.md) данни, като идентифицирате [полетата източник](map-entities.md), премахнете [дубликатите](remove-duplicates.md), [съответстващите](match-entities.md) условия и [унифициращите полета](merge-entities.md).

1. Запознайте се с [обекти, които системата създава](entities.md) и създайте [взаимоотношения между погълнатите обекти](relationships.md).

## <a name="step-4-enhance-unified-profiles-with-predictions-activities-and-measures"></a>Стъпка 4: Подобрете унифицираните профили с прогнози, дейности и мерки

С унифицираните профили, усили данните си и допълнително увеличи информацията, която предоставят.

1. Изберете от разширяваща се библиотека от доставчици на обогатяване да [обогатите вашите клиентски данни](enrichment-hub.md).

1. Използвайте [предварително подготвени модели](predictions-overview.md) за прогнозиране на вероятността от отпадъци или очакваните приходи.

1. [Конфигурирайте дейности](activities.md) въз основа на погълнати данни и визуализиране на взаимодействията с вашите клиенти в хронологична хронология.

1. [Изградете мерки](measures.md) за преценка на вашите бизнес цели и KPI.

## <a name="step-5-create-segments-and-activate-data-through-various-export-options"></a>Стъпка 5: Създайте сегменти и активирайте данни чрез различни опции за експортиране

Сега, когато вашите данни са пълни и съдържат широк набор от информация за вашите клиенти, потърсете начини да предприемете действия по тези данни.

1. [Създайте сегменти](segments.md), подгрупи от вашата клиентска база, за да сте сигурни, че вашите действия са подходящи за целевите клиенти.

1. Разгледайте разширяващия се каталог на [опции за експортиране](export-destinations.md), където можете да използвате клиентски данни. Например можете да използвате данни за управление на промоции и контакт с дигитален маркетинг.

1. Прегледайте опциите за интеграция, например към други приложения на Dynamics 365 с добавката [Карта на](customer-card-add-in.md) клиента.  


[!INCLUDE [footer-include](includes/footer-banner.md)]