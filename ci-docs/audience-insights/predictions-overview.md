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
ms.openlocfilehash: 69ae945b22819521db217508c6fc232876346747
ms.sourcegitcommit: 6b07c9c3102761be162e4842f3c9fbc19f948a9b
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 05/25/2021
ms.locfileid: "6095685"
---
# <a name="predictions-overview"></a><span data-ttu-id="add8d-103">Общ преглед на прогнози</span><span class="sxs-lookup"><span data-stu-id="add8d-103">Predictions overview</span></span>

<span data-ttu-id="add8d-104">Dynamics 365 Customer Insights идва с разнообразни опции, които използват AI и машинно обучение за прогнозиране на данни.</span><span class="sxs-lookup"><span data-stu-id="add8d-104">Dynamics 365 Customer Insights comes with a variety of options that leverage AI and machine learning to predict data.</span></span> 

## <a name="out-of-box-models"></a><span data-ttu-id="add8d-105">Предварително подготвени модели</span><span class="sxs-lookup"><span data-stu-id="add8d-105">Out-of-box models</span></span>

<span data-ttu-id="add8d-106">Най-лесният начин да започнете с прогнозиране на данни са предварително дефинираните модели, често наричани „готови модели“.</span><span class="sxs-lookup"><span data-stu-id="add8d-106">The easiest way to start with predicting data are predefined models, often referred to as out-of-box models.</span></span> <span data-ttu-id="add8d-107">Те изискват само определени данни и структура, за да генерират бързо прозрения.</span><span class="sxs-lookup"><span data-stu-id="add8d-107">They only require certain data and structure to generate insights quickly.</span></span> <span data-ttu-id="add8d-108">В момента се предлагат следните модели:</span><span class="sxs-lookup"><span data-stu-id="add8d-108">Currently, the following models are available:</span></span> 
- <span data-ttu-id="add8d-109">[Доживотна стойност на клиента](predict-customer-lifetime-value.md): Предсказва потенциалните приходи на клиент през цялото взаимодействие с бизнес.</span><span class="sxs-lookup"><span data-stu-id="add8d-109">[Customer lifetime value](predict-customer-lifetime-value.md): Predicts the potential revenue of a customer throughout the entire interaction with a business.</span></span> 
- <span data-ttu-id="add8d-110">[Препоръка за продукт](predict-product-recommendation.md): Предлага набори от предсказуеми препоръки за продукти, базирани на поведение при покупка и клиенти с подобни модели на покупка.</span><span class="sxs-lookup"><span data-stu-id="add8d-110">[Product recommendation](predict-product-recommendation.md): Suggests sets of predictive product recommendations based on purchase behavior and customers with similar purchase patterns.</span></span>
- <span data-ttu-id="add8d-111">[Оттегляне на абонаменти](predict-subscription-churn.md): Предвижда дали даден клиент е в риск да не използва повече продуктите или услугите от абонамента на фирмата.</span><span class="sxs-lookup"><span data-stu-id="add8d-111">[Subscription churn](predict-subscription-churn.md): Predicts whether a customer is at risk for no longer using your company’s subscription products or services.</span></span>
- <span data-ttu-id="add8d-112">[Транзакционен отбив](predict-transactional-churn.md): Предскажете дали клиентът вече няма да закупи вашите продукти или услуги в определен период от време.</span><span class="sxs-lookup"><span data-stu-id="add8d-112">[Transactional churn](predict-transactional-churn.md): Predict if a customer will no longer purchase your products or services in a certain time frame.</span></span>

## <a name="azure-machine-learning-integration"></a><span data-ttu-id="add8d-113">Интеграция на Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="add8d-113">Azure Machine Learning integration</span></span>

<span data-ttu-id="add8d-114">Ако дадена организация вече използва машинно обучение сценарии, базирани на Azure Machine Learning експерименти, функцията за персонализирани модели в Customer Insights помага за свързването на точките.</span><span class="sxs-lookup"><span data-stu-id="add8d-114">If an organization already uses machine learning scenarios based on Azure Machine Learning experiments, the custom models feature in Customer Insights helps to connect the dots.</span></span> <span data-ttu-id="add8d-115">Създайте работни потоци, които ви помагат да изберете данните, от които искате да генерирате прозрения, и да съпоставите резултатите с вашите унифицирани клиентски профили.</span><span class="sxs-lookup"><span data-stu-id="add8d-115">Create workflows that help you choose the data you want to generate insights from and map the results to your unified customer profiles.</span></span> <span data-ttu-id="add8d-116">За повече информация вижте [Персонализирани модели за машинно обучение](custom-models.md).</span><span class="sxs-lookup"><span data-stu-id="add8d-116">For more information, see [Custom machine learning models](custom-models.md).</span></span>

## <a name="ai-builder-prediction"></a><span data-ttu-id="add8d-117">Прогноза за AI Builder</span><span class="sxs-lookup"><span data-stu-id="add8d-117">AI Builder prediction</span></span>

<span data-ttu-id="add8d-118">Понякога наборите от данни са непълни и някои стойности липсват.</span><span class="sxs-lookup"><span data-stu-id="add8d-118">Sometimes, data sets are incomplete and some values are missing.</span></span> <span data-ttu-id="add8d-119">Customer Insights може да помогне за прогнозиране на липсващи стойности за обекта и сегментите на клиента.</span><span class="sxs-lookup"><span data-stu-id="add8d-119">Customer Insights can help to predict missing values for the Customer entity and segments.</span></span> <span data-ttu-id="add8d-120">За повече информация вижте [Попълнете частичните си данни с прогнози](predictions.md).</span><span class="sxs-lookup"><span data-stu-id="add8d-120">For more information, see [Complete your partial data with predictions](predictions.md).</span></span>
