---
title: Свържете се с обекти в управлявано хранилище на Common Data Service
description: Импортиране на данни от управлявано хранилище Data Lake в Common Data Service.
ms.date: 09/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.reviewer: adkuppa
ms.openlocfilehash: 029857e2bbb5f6357a5c01138ceaad78887b7518
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643385"
---
# <a name="connect-to-data-in-a-common-data-service-managed-data-lake"></a><span data-ttu-id="c0471-103">Свързване с данни в управлявано от Common Data Service хранилище за необработени данни</span><span class="sxs-lookup"><span data-stu-id="c0471-103">Connect to data in a Common Data Service managed data lake</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="c0471-104">Тази статия предоставя информация за това как съществуващите клиенти на Dynamics 365 могат бързо да се свържат със своите аналитични обекти в управляваното хранилище в Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="c0471-104">This article provides information on how existing Dynamics 365 customers can quickly connect to their analytical entities in the Common Data Service managed lake.</span></span> <span data-ttu-id="c0471-105">Трябва да сте администратор на организация в Common Data Service, за да продължите и да видите списъка с обекти, налични в управляваното хранилище.</span><span class="sxs-lookup"><span data-stu-id="c0471-105">You must be an admin on the Common Data Service organization to proceed and see the list of entities available in the managed lake.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="c0471-106">Важни съображения</span><span class="sxs-lookup"><span data-stu-id="c0471-106">Important considerations</span></span>

<span data-ttu-id="c0471-107">Данните, съхранявани в онлайн услуги като Azure Data Lake Storage може да се съхраняват на различно място от това, на което се обработват или съхраняват данни в Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="c0471-107">Data stored in online services, such as Azure Data Lake Storage, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="c0471-108"> Чрез импортиране или свързване към данни, съхранявани в онлайн услуги, вие се съгласявате, че данните могат да се прехвърлят и съхраняват в Dynamics 365 Customer Insights. [Научете повече в центъра за сигурност на Microsoft.](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="c0471-108"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-service-managed-lake"></a><span data-ttu-id="c0471-109">Свържете се с управлявано от Common Data Service хранилище</span><span class="sxs-lookup"><span data-stu-id="c0471-109">Connect to a Common Data Service managed lake</span></span>

1. <span data-ttu-id="c0471-110">В статията за аудиторията отидете на **Данни** > **Източници на данни**.</span><span class="sxs-lookup"><span data-stu-id="c0471-110">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="c0471-111">Изберете **Добавяне на източник на данни**.</span><span class="sxs-lookup"><span data-stu-id="c0471-111">Select **Add data source**.</span></span>

3. <span data-ttu-id="c0471-112">Изберете **Свържете се с Common Data Service** и изберете **Напред**.</span><span class="sxs-lookup"><span data-stu-id="c0471-112">Select **Connect to Common Data Service** and select **Next**.</span></span>

4. <span data-ttu-id="c0471-113">Въведете **Име** за източника на данни и изберете **Напред**.</span><span class="sxs-lookup"><span data-stu-id="c0471-113">Enter a **Name** for the data source and select **Next**.</span></span>

5. <span data-ttu-id="c0471-114">Предоставете **Адрес на сървър** за организацията ви на Common Data Service и изберете **Вход**.</span><span class="sxs-lookup"><span data-stu-id="c0471-114">Provide the **Server address** for your Common Data Service organization, and select **Sign in**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c0471-115">![Диалогов прозорец за влизане на адрес на сървър на Common Data Service](media/enter-CDS-org-details.png)</span><span class="sxs-lookup"><span data-stu-id="c0471-115">![Dialog box to enter Common Data Service server address](media/enter-CDS-org-details.png)</span></span>

6. <span data-ttu-id="c0471-116">Изберете обектите, които искате да поемете от наличния списък.</span><span class="sxs-lookup"><span data-stu-id="c0471-116">Select the entities you want to ingest from the available list.</span></span>    

   > [!NOTE]
   > <span data-ttu-id="c0471-117">Ако някои обекти вече са избрани, те могат да бъдат използвани от други приложения на Dynamics 365 (като например Dynamics 365 Sales Insights или Customer Service Insights).</span><span class="sxs-lookup"><span data-stu-id="c0471-117">If some entities are already selected, they might be used by other Dynamics 365 applications (such as Dynamics 365 Sales Insights or Customer Service Insights).</span></span> <span data-ttu-id="c0471-118">Не можете да променяте този избор.</span><span class="sxs-lookup"><span data-stu-id="c0471-118">You can't change the selection.</span></span> <span data-ttu-id="c0471-119">Тези обекти ще бъдат достъпни след създаването на източника на данни.</span><span class="sxs-lookup"><span data-stu-id="c0471-119">These entities will be available once the data source is created.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c0471-120">![Диалогов прозорец, показващ списък с обекти в организация на Common Data Service](media/select-analytical-entities.png)</span><span class="sxs-lookup"><span data-stu-id="c0471-120">![Dialog box showing a list of entities in the Common Data Service org](media/select-analytical-entities.png)</span></span>

7. <span data-ttu-id="c0471-121">Запазете своя избор, за да започнете да синхронизирате избраните обекти с управлявано от Common Data Service хранилище.</span><span class="sxs-lookup"><span data-stu-id="c0471-121">Save your selection to start syncing the selected entities to the Common Data Service managed lake.</span></span> <span data-ttu-id="c0471-122">Ще намерите ново добавената връзка на страницата **Източници на данни**.</span><span class="sxs-lookup"><span data-stu-id="c0471-122">You'll find the newly added connection on the **Data sources** page.</span></span> <span data-ttu-id="c0471-123">Тя ще бъде поставена на опашка за опресняване и ще показва, че единиците се броят като 0, докато всички обекти не се синхронизират.</span><span class="sxs-lookup"><span data-stu-id="c0471-123">It will be queued for refresh and show the entities count as 0 until all the entities are synced.</span></span>

<span data-ttu-id="c0471-124">Само един източник на данни от среда може едновременно да използва същото управлявано хранилище на Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="c0471-124">Only one data source of an environment can simultaneously use the same Common Data Service managed lake.</span></span>

## <a name="edit-a-common-data-service-managed-lake-data-source"></a><span data-ttu-id="c0471-125">Редактиране на управляван от Common Data Service източник на данни на хранилище</span><span class="sxs-lookup"><span data-stu-id="c0471-125">Edit a Common Data Service managed lake data source</span></span>

<span data-ttu-id="c0471-126">Вие редактирате избора на обекти само след като създадете източник на данни.</span><span class="sxs-lookup"><span data-stu-id="c0471-126">You only edit the entity selection after creating the data source.</span></span> <span data-ttu-id="c0471-127">Например, ако в Common Data Service са добавени допълнителни обекти и вие също искате да ги импортирате.</span><span class="sxs-lookup"><span data-stu-id="c0471-127">For example, if additional entities were added to Common Data Service and you want to import them too.</span></span>    
<span data-ttu-id="c0471-128">За да свържете към различен Common Data Service, [създайте нов източник на данни](#connect-to-a-common-data-service-managed-lake).</span><span class="sxs-lookup"><span data-stu-id="c0471-128">To connect to a different Common Data Service, [create a new data source](#connect-to-a-common-data-service-managed-lake).</span></span>

1. <span data-ttu-id="c0471-129">В статията за аудиторията отидете на **Данни** > **Източници на данни**.</span><span class="sxs-lookup"><span data-stu-id="c0471-129">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="c0471-130">До източника на данни, който искате да актуализирате, изберете многоточието.</span><span class="sxs-lookup"><span data-stu-id="c0471-130">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="c0471-131">Изберете опцията **Редактиране** от списъка.</span><span class="sxs-lookup"><span data-stu-id="c0471-131">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="c0471-132">Изберете допълнителни обекти от наличния списък и изберете **Записване**.</span><span class="sxs-lookup"><span data-stu-id="c0471-132">Select additional entities from the available list of entities and select **Save**.</span></span>
