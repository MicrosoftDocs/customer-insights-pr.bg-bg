---
title: Преглед на поддържаните сценарии за прогноза
description: Сценарии и опции за прогнози, обхванати от Dynamics 365 Customer Insights приложение.
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: get-started
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: b73046844f6009a2b163b5eaadf5f63f75cda1d8
ms.sourcegitcommit: b78c9680b213204e6b0ed47f0147205083f6a98f
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 07/12/2021
ms.locfileid: "6539148"
---
# <a name="predictions-overview"></a>Общ преглед на прогнози

Dynamics 365 Customer Insights идва с разнообразни опции, които използват AI и машинно обучение за прогнозиране на данни. 

## <a name="out-of-box-models"></a>Предварително подготвени модели

Най-лесният начин да започнете с прогнозиране на данни са предварително дефинираните модели, често наричани „готови модели“. Те изискват само определени данни и структура, за да генерират бързо прозрения. В момента се предлагат следните модели: 
- [Доживотна стойност на клиента](predict-customer-lifetime-value.md): Предсказва потенциалните приходи на клиент през цялото взаимодействие с бизнес. 
- [Препоръка за продукт](predict-product-recommendation.md): Предлага набори от предсказуеми препоръки за продукти, базирани на поведение при покупка и клиенти с подобни модели на покупка.
- [Оттегляне на абонаменти](predict-subscription-churn.md): Предвижда дали даден клиент е в риск да не използва повече продуктите или услугите от абонамента на фирмата.
- [Транзакционен отбив](predict-transactional-churn.md): Предскажете дали клиентът вече няма да закупи вашите продукти или услуги в определен период от време.

## <a name="azure-machine-learning-integration"></a>Интеграция на Azure Machine Learning

Ако дадена организация вече използва машинно обучение сценарии, базирани на Azure Machine Learning експерименти, функцията за персонализирани модели в Customer Insights помага за свързването на точките. Създайте работни потоци, които ви помагат да изберете данните, от които искате да генерирате прозрения, и да съпоставите резултатите с вашите унифицирани клиентски профили. За повече информация вижте [Персонализирани модели за машинно обучение](custom-models.md).

## <a name="ai-builder-prediction"></a>Прогноза за AI Builder

Понякога наборите от данни са непълни и някои стойности липсват. Customer Insights може да помогне за прогнозиране на липсващи стойности за обекта и сегментите на клиента. За повече информация вижте [Попълнете частичните си данни с прогнози](predictions.md).