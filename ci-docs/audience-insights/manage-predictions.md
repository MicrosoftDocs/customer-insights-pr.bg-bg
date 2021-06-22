---
title: Споделени задачи за сценарии на прогноза
description: Научете как да управлявате, отстранявате и прецизирате прогнози.
ms.date: 05/17/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: b935be08199f20e83bceb3317985b0e1dc120016
ms.sourcegitcommit: 6b07c9c3102761be162e4842f3c9fbc19f948a9b
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 05/25/2021
ms.locfileid: "6095686"
---
# <a name="manage-predictions"></a><span data-ttu-id="8e05f-103">Управление на прогнозите</span><span class="sxs-lookup"><span data-stu-id="8e05f-103">Manage predictions</span></span>

<span data-ttu-id="8e05f-104">Тази статия разглежда някои задачи, които повечето прогноза споделят.</span><span class="sxs-lookup"><span data-stu-id="8e05f-104">This article discusses some tasks that most prediction scenarios share.</span></span>

## <a name="troubleshoot-a-failed-prediction"></a><span data-ttu-id="8e05f-105">Отстраняване на проблеми с неуспешна прогноза</span><span class="sxs-lookup"><span data-stu-id="8e05f-105">Troubleshoot a failed prediction</span></span>

1. <span data-ttu-id="8e05f-106">Отидете на **Разузнаване** > **Прогнози** и изберете раздела **Моите прогнози**.</span><span class="sxs-lookup"><span data-stu-id="8e05f-106">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="8e05f-107">Изберете вертикалните елипси до прогноза, за които искате да видите регистрационните файлове за грешки.</span><span class="sxs-lookup"><span data-stu-id="8e05f-107">Select the vertical ellipses next to the prediction you want to view error logs for.</span></span>

1. <span data-ttu-id="8e05f-108">Изберете **регистрационни файлове**.</span><span class="sxs-lookup"><span data-stu-id="8e05f-108">Select **Logs**.</span></span>

1. <span data-ttu-id="8e05f-109">Прегледайте всички грешки.</span><span class="sxs-lookup"><span data-stu-id="8e05f-109">Review all the errors.</span></span> <span data-ttu-id="8e05f-110">Има няколко вида грешки, които могат да възникнат, и те описват кое състояние е причинило грешката.</span><span class="sxs-lookup"><span data-stu-id="8e05f-110">There are several types of errors that can occur, and they describe what condition caused the error.</span></span> <span data-ttu-id="8e05f-111">Например грешката, при която няма достатъчно данни за точна прогноза, обикновено се разрешава чрез зареждане на допълнителни данни в Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="8e05f-111">For example, an error that there's not enough data to accurately predict is typically resolved by loading additional data into Customer Insights.</span></span>

## <a name="input-data-usability-report"></a><span data-ttu-id="8e05f-112">Отчет за използваемост на входните данни</span><span class="sxs-lookup"><span data-stu-id="8e05f-112">Input data usability report</span></span>

<span data-ttu-id="8e05f-113">Отчетът за използваемост на входните данни предоставя консолидиран изглед на грешките и предупрежденията, които може да генерират вашите нестандартни прогнози.</span><span class="sxs-lookup"><span data-stu-id="8e05f-113">The input data usability report provides a consolidated view of the errors and warnings that your out-of-box predictions may be generating.</span></span> <span data-ttu-id="8e05f-114">Той също така дава препоръки как да подобрите производителността на модела.</span><span class="sxs-lookup"><span data-stu-id="8e05f-114">It also gives recommendations how to improve the model performance.</span></span>

<span data-ttu-id="8e05f-115">Отчетът е достъпен, след като моделът завърши своя тренировъчен процес.</span><span class="sxs-lookup"><span data-stu-id="8e05f-115">The report is available after a model has completed its training process.</span></span> <span data-ttu-id="8e05f-116">Създаден е за всеки модел поотделно, независимо дали е завършен успешно или не.</span><span class="sxs-lookup"><span data-stu-id="8e05f-116">It's created for each model separately, regardless if it completed successfully or not.</span></span>

> [!NOTE]
> <span data-ttu-id="8e05f-117">Понастоящем тази функция работи само за модела Transaction Churn.</span><span class="sxs-lookup"><span data-stu-id="8e05f-117">Currently, this feature only works for the Transaction Churn model.</span></span>

### <a name="view-the-input-data-usability-report"></a><span data-ttu-id="8e05f-118">Преглед на отчета за използваемост на входните данни</span><span class="sxs-lookup"><span data-stu-id="8e05f-118">View the input data usability report</span></span>

<span data-ttu-id="8e05f-119">След като излезлият от кутията модел завърши своята стъпка за обучение, вижте доклада:</span><span class="sxs-lookup"><span data-stu-id="8e05f-119">After an out-of-box model has completed its training step, view the report:</span></span>
- <span data-ttu-id="8e05f-120">Изберете многоточието до името на модела и изберете **Отчет за използваемост на входните данни**.</span><span class="sxs-lookup"><span data-stu-id="8e05f-120">Select the ellipses next to the model name and choose **Input data usability report**.</span></span>
- <span data-ttu-id="8e05f-121">Изберете състоянието на избрания модел **Вижте Отчет за използваемост на входните данни** в страничния прозорец.</span><span class="sxs-lookup"><span data-stu-id="8e05f-121">Select the status of a model select **See Input data usability report** in the side pane.</span></span>
- <span data-ttu-id="8e05f-122">Избиране на един от моделите в списъка и избор **Отчет за използваемост на входните данни** в командната лента.</span><span class="sxs-lookup"><span data-stu-id="8e05f-122">Selecting one of the models in the list and select **Input data usability report** in the command bar.</span></span>
- <span data-ttu-id="8e05f-123">Отворете страницата с резултати от модела и изберете **Отчет за използваемост на входните данни** в командната лента.</span><span class="sxs-lookup"><span data-stu-id="8e05f-123">Open the model results page and select **Input data usability report** in the command bar.</span></span>

### <a name="information-in-the-input-data-usability-report"></a><span data-ttu-id="8e05f-124">Информация в Отчета за използваемост на входните данни</span><span class="sxs-lookup"><span data-stu-id="8e05f-124">Information in the input data usability report</span></span>

<span data-ttu-id="8e05f-125">Следващите колони в отчета съдържат полезна информация за подобряване на данните за модела.</span><span class="sxs-lookup"><span data-stu-id="8e05f-125">The following columns in the report contain helpful information to improve the data for the model.</span></span>

:::image type="content" source="media/input-data-usability-report.png" alt-text="Пример за отчет за използваемост на входни данни, показващ таблица с грешки, предупреждения и препоръки.":::

- <span data-ttu-id="8e05f-127">Име: Описателно име на грешката, предупреждението или препоръката.</span><span class="sxs-lookup"><span data-stu-id="8e05f-127">Name: Descriptive name of the error, warning, or recommendation.</span></span>
- <span data-ttu-id="8e05f-128">Стъпка: Фаза на модел, тренировка или резултат, към която се отнася информацията.</span><span class="sxs-lookup"><span data-stu-id="8e05f-128">Step: Model phase, train or score, the information refers to.</span></span>
- <span data-ttu-id="8e05f-129">Състояние: Тежест на информацията (грешка, предупреждение, препоръка).</span><span class="sxs-lookup"><span data-stu-id="8e05f-129">State: Severity of the information (error, warning, recommendation).</span></span>
- <span data-ttu-id="8e05f-130">Име на колона: Колона в обект, който трябва да бъде модифициран, за да се подобри производителността на модела.</span><span class="sxs-lookup"><span data-stu-id="8e05f-130">Column name: Column in an entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="8e05f-131">Име на обект: Името на обекта, което трябва да бъде модифицирано, за да се подобри производителността на модела.</span><span class="sxs-lookup"><span data-stu-id="8e05f-131">Entity name: Name of the entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="8e05f-132">Подробности: Подробности за грешката, предупреждението или препоръката.</span><span class="sxs-lookup"><span data-stu-id="8e05f-132">Details: Details about the error, warning, or recommendation.</span></span>

## <a name="refresh-a-prediction"></a><span data-ttu-id="8e05f-133">Обновяване на прогноза</span><span class="sxs-lookup"><span data-stu-id="8e05f-133">Refresh a prediction</span></span>

<span data-ttu-id="8e05f-134">Прогнозите автоматично ще се обновяват по същия [график, по който се обновяват данните ви](system.md#schedule-tab), както е конфигурирано в настройките.</span><span class="sxs-lookup"><span data-stu-id="8e05f-134">Predictions will automatically refresh on the same [schedule your data refreshes](system.md#schedule-tab) as configured in settings.</span></span> <span data-ttu-id="8e05f-135">Можете да ги опресните и ръчно.</span><span class="sxs-lookup"><span data-stu-id="8e05f-135">You can refresh them manually too.</span></span>

1. <span data-ttu-id="8e05f-136">Отидете на **Разузнаване** > **Прогнози** и изберете раздела **Моите прогнози**.</span><span class="sxs-lookup"><span data-stu-id="8e05f-136">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="8e05f-137">Изберете вертикалното многоточие до прогнозата, която искате да обновите.</span><span class="sxs-lookup"><span data-stu-id="8e05f-137">Select the vertical ellipses next to the prediction you want to refresh.</span></span>

1. <span data-ttu-id="8e05f-138">Изберете **Обновяване**.</span><span class="sxs-lookup"><span data-stu-id="8e05f-138">Select **Refresh**.</span></span>

## <a name="delete-a-prediction"></a><span data-ttu-id="8e05f-139">Изтриване на прогноза</span><span class="sxs-lookup"><span data-stu-id="8e05f-139">Delete a prediction</span></span>

<span data-ttu-id="8e05f-140">Изтриването на прогноза също премахва неговия изходен обект.</span><span class="sxs-lookup"><span data-stu-id="8e05f-140">Deleting a prediction also removes its output entity.</span></span>

1. <span data-ttu-id="8e05f-141">Отидете на **Разузнаване** > **Прогнози** и изберете раздела **Моите прогнози**.</span><span class="sxs-lookup"><span data-stu-id="8e05f-141">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="8e05f-142">Изберете вертикалното многоточие до прогнозата, която искате да изтриете.</span><span class="sxs-lookup"><span data-stu-id="8e05f-142">Select the vertical ellipses next to the prediction you want to delete.</span></span>

1. <span data-ttu-id="8e05f-143">Изберете **Изтриване**.</span><span class="sxs-lookup"><span data-stu-id="8e05f-143">Select **Delete**.</span></span>
