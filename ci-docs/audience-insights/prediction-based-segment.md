---
title: Сегменти, базирани на изходни данни на прогноза
description: Създайте сегменти въз основа на изходния обект на модел на прогноза.
ms.date: 03/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 488db1af865ce600ec012716327d053bee33aff8
ms.sourcegitcommit: a95c82f46c23f625cb34fceba021ccc70d4b1df6
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 03/30/2021
ms.locfileid: "5741416"
---
# <a name="create-a-segment-based-on-a-prediction-model-preview"></a><span data-ttu-id="d0619-103">Създайте сегмент въз основа на модел на прогноза (преглед)</span><span class="sxs-lookup"><span data-stu-id="d0619-103">Create a segment based on a prediction model (preview)</span></span>

<span data-ttu-id="d0619-104">Резултатите от прогнозите понякога се отнасят само за поднабори от клиенти.</span><span class="sxs-lookup"><span data-stu-id="d0619-104">The results of predictions sometimes only apply to a subset of your customers.</span></span> <span data-ttu-id="d0619-105">Увеличете персонализирането на препоръките, като създадете сегменти от резултатите на модели на прогноза.</span><span class="sxs-lookup"><span data-stu-id="d0619-105">Increase the personalization of recommendations by creating segments from results of prediction models.</span></span> <span data-ttu-id="d0619-106">Например може да поискате да дадете конкретни препоръки на клиенти, които предпочитат определен тип услуга.</span><span class="sxs-lookup"><span data-stu-id="d0619-106">For example, you may want to give specific recommendations to customers that prefer a certain type of service.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="d0619-107">Предварителни изисквания</span><span class="sxs-lookup"><span data-stu-id="d0619-107">Prerequisites</span></span>

- <span data-ttu-id="d0619-108">Поне [Разрешения на сътрудник](permissions.md) в Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="d0619-108">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>

- <span data-ttu-id="d0619-109">Препоръка за продукт, оттегляне на трансакция, оттегляне на абонамент или модел на стойност на жизнения цикъл на клиент, конфигурирани в Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="d0619-109">A product recommendation, transactional churn, subscription churn, or customer lifetime value model configured in Customer Insights.</span></span> <span data-ttu-id="d0619-110">Прегледайте изискванията за настройка на различните модели:</span><span class="sxs-lookup"><span data-stu-id="d0619-110">Review the requirements to set up the different models:</span></span>

  - [<span data-ttu-id="d0619-111">Модел на препоръка за продукт</span><span class="sxs-lookup"><span data-stu-id="d0619-111">Product recommendation model</span></span>](predict-product-recommendation.md)
  - [<span data-ttu-id="d0619-112">Модел на оттегляне на абонамент</span><span class="sxs-lookup"><span data-stu-id="d0619-112">Subscription churn model</span></span>](predict-subscription-churn.md)
  - [<span data-ttu-id="d0619-113">Модел на оттегляне на трансакция</span><span class="sxs-lookup"><span data-stu-id="d0619-113">Transactional churn model</span></span>](predict-transactional-churn.md)
  - [<span data-ttu-id="d0619-114">Модел на стойност на жизнения цикъл на клиента</span><span class="sxs-lookup"><span data-stu-id="d0619-114">Customer lifetime value model</span></span>](predict-customer-lifetime-value.md)

## <a name="create-a-customer-segment-based-on-predictions"></a><span data-ttu-id="d0619-115">Създаване на сегмент на клиент въз основа на прогнози</span><span class="sxs-lookup"><span data-stu-id="d0619-115">Create a customer segment based on predictions</span></span>

1. <span data-ttu-id="d0619-116">Отидете на **Разузнаване** > **Прогнози** и изберете раздела **Моите прогнози**.</span><span class="sxs-lookup"><span data-stu-id="d0619-116">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="d0619-117">Изберете вертикалното многоточие до модела, който искате да прегледате, и изберете **Преглед**.</span><span class="sxs-lookup"><span data-stu-id="d0619-117">Select the vertical ellipses next to the model you want to review and select **View**.</span></span>

1. <span data-ttu-id="d0619-118">На страницата с резултати изберете **Създаване на сегмент**.</span><span class="sxs-lookup"><span data-stu-id="d0619-118">On the results page, select **Create segment**.</span></span> <span data-ttu-id="d0619-119">За повече информация относно страницата с резултати прегледайте статията за модела.</span><span class="sxs-lookup"><span data-stu-id="d0619-119">For more information about the results page, review the article about the model.</span></span>

   :::image type="content" source="media/prediction-create-segment.png" alt-text="Екранна снимка на страницата с резултати от прогноза с маркирано действие за създаване на сегмент.":::

1. <span data-ttu-id="d0619-121">Създайте нов сегмент въз основа на изходния обект на избрания модел.</span><span class="sxs-lookup"><span data-stu-id="d0619-121">Create a new segment based on the output entity of the selected model.</span></span> <span data-ttu-id="d0619-122">За повече информация вижте [Създаване и управление на сегменти](segments.md).</span><span class="sxs-lookup"><span data-stu-id="d0619-122">For more information, see [Create and manage segments](segments.md).</span></span>