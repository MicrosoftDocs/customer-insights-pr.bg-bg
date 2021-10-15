---
title: Започнете с възможностите за анализи на аудиторията в Dynamics 365 Customer Insights
description: Прегледът на статистиката за аудиторията помага на ресурсите да започнат бързо.
ms.reviewer: mhart
ms.author: mhart
author: m-hartmann
ms.date: 08/31/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: aaaf1848df175469d8af07754ac153b777781ffb
ms.sourcegitcommit: 971716c761871cee390519cacef617dac21ecd60
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 09/01/2021
ms.locfileid: "7466564"
---
# <a name="get-started-with-dynamics-365-customer-insights-audience-insights-capability"></a>Започнете с възможностите за анализи на аудиторията в Dynamics 365 Customer Insights

Аналитични данни за аудитория ви помагат да изградите по-задълбочено разбиране за клиентите. Свържете данни от различни източници, свързани с трансакции, поведение и наблюдение, за да създадете 360-градусов изглед на клиента. Използвайте тези аналитични данни, за да управлявате ориентираните към клиента преживявания и процеси. Обединете и разберете данните на клиентите и ги използвайте за интелигентни прозрения и действия.

## <a name="step-1-create-an-environment"></a>Стъпка 1: Създаване на нова среда

За да започнете, първо трябва да създадете среда, в която да работите. Ако вашата организация вече е закупила лиценз, вижте [Започнете с платен абонамент](get-started-paid.md). За да започнете пробен период за прозрения на аудиторията, вижте [Настройте пробна среда](get-started-trial.md). 

## <a name="step-2-explore-audience-insights"></a>Стъпка 2: Разглеждане на аналитичните данни за аудиторията

За първи път, когато влезете в Аналитични данни за аудитория, можете да конфигурирате настройки и да прегледате продукта.

1. [Влезте в Аналитични данни за аудиторията](https://home.ci.ai.dynamics.com), като използвате вашия Microsoft Azure Active Directory (AAD) потребителски акаунт.

1. [Променете средата](manage-environments.md#switch-environments), за да видите демо данни и [изследвайте Аналитични данни за аудитория](home.md).

##  <a name="step-3-ingest-unify-and-set-up-relationships-for-your-data"></a>Стъпка 3: Поглъщайте, унифицирайте и настройте взаимоотношения за вашите данни

Унифицираните профили са основата за получаване на информация и предприемане на действия по отношение на данните. Въведете данни от различни източници и стартирайте процеса на обединяване на данни, за да комбинирате унифицирани профили. Задайте взаимоотношения между погълнатите обекти, използвайте функции за обогатяване, за да добавите информация към профилите. 

1. Поглъщайте данни, като създавате източници на данни от множество опции. Изберете между [Power Query конектори](connect-power-query.md), [Папка Common Data Model](connect-common-data-model.md) или [Microsoft Dataverse](connect-common-data-service-lake.md). 

1. Стартирайте [процес на унифициране на данни](data-unification.md) като преминете през [нанасяне](map-entities.md), [съпоставяне](match-entities.md) и [сливане](merge-entities.md) фази.

1. Запознайте се с [обекти, които системата създава](entities.md) и създайте [взаимоотношения между погълнатите обекти](relationships.md).
    
## <a name="step-4-enhance-unified-profiles-with-predictions-activities-and-measures"></a>Стъпка 4: Подобрете унифицираните профили с прогнози, дейности и мерки

С създадени унифицирани профили можете да подобрите данните си и допълнително да увеличите информацията, която предоставят.

1. Изберете от разширяваща се библиотека от доставчици на обогатяване да [обогатите вашите клиентски данни](enrichment-hub.md).

1. Използвайте [предварително подготвени модели](predictions-overview.md) за прогнозиране на вероятността от отпадъци или очакваните приходи.

1. [Конфигурирайте дейности](activities.md) въз основа на погълнати данни и визуализиране на взаимодействията с вашите клиенти в хронологична хронология. 

1. [Изградете мерки](measures.md) за преценка на вашите бизнес цели и KPI.
 
## <a name="step-5-create-segments-and-activate-data-through-various-export-options"></a>Стъпка 5: Създайте сегменти и активирайте данни чрез различни опции за експортиране

Сега, когато вашите данни са пълни и съдържат широк спектър от информация за вашите клиенти, е време да потърсите начини да предприемете действия по тези данни. 

1. [Създайте сегменти](segments.md), подгрупи от вашата клиентска база, за да сте сигурни, че вашите действия са подходящи за целевите клиенти.

1. Разгледайте разширяващия се каталог на [опции за експортиране](export-destinations.md), където можете да използвате клиентски данни. Например можете да използвате данни за управление на промоции и контакт с дигитален маркетинг.

1. Прегледайте опциите за интеграция, например с [директна връзка с Аналитични данни за ангажираност](../engagement-insights/integrate-audience-insights-engagement-insights.md) или към други приложения на Dynamics 365 с [Добавка за клиентска карта](customer-card-add-in.md).  


[!INCLUDE[footer-include](../includes/footer-banner.md)]