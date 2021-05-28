---
title: Експортиране на данни от Customer Insights
description: Управлявайте експортирането, за да споделяте данни.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c1078ed0ba259a6e9cde3c7ede3570890ae48e67
ms.sourcegitcommit: 33a8e21b3bf6521bdb8346f81f79fce88091ddfd
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 05/10/2021
ms.locfileid: "6016601"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="d8ae4-103">Общ преглед на експортирания (преглед)</span><span class="sxs-lookup"><span data-stu-id="d8ae4-103">Exports (preview) overview</span></span>

<span data-ttu-id="d8ae4-104">Страницата **Експортиране** ви показва всички конфигурирани експортирания.</span><span class="sxs-lookup"><span data-stu-id="d8ae4-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="d8ae4-105">Експортирането споделя специфични данни с различни приложения.</span><span class="sxs-lookup"><span data-stu-id="d8ae4-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="d8ae4-106">Те могат да включват клиентски профили или обекти, схеми и подробности за съпоставяне.</span><span class="sxs-lookup"><span data-stu-id="d8ae4-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="d8ae4-107">Всяко експортиране изисква [връзка, настроена от администратор, за управление на удостоверяване и достъп](connections.md).</span><span class="sxs-lookup"><span data-stu-id="d8ae4-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

<span data-ttu-id="d8ae4-108">Отидете на **Данни** > **Експортиране**, за да видите страницата за експортиране.</span><span class="sxs-lookup"><span data-stu-id="d8ae4-108">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="d8ae4-109">Всички потребителски роли имат достъп за преглед на конфигурираното експортиране.</span><span class="sxs-lookup"><span data-stu-id="d8ae4-109">All user roles have access to view configured exports.</span></span> <span data-ttu-id="d8ae4-110">Използване на полето за търсене в командната лента за намиране на експортирания по тяхното име, името на връзката или типа връзка.</span><span class="sxs-lookup"><span data-stu-id="d8ae4-110">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="d8ae4-111">Настройване на ново експортиране</span><span class="sxs-lookup"><span data-stu-id="d8ae4-111">Set up a new export</span></span>

<span data-ttu-id="d8ae4-112">За да настроите или редактирате експортиране, трябва да имате налични връзки.</span><span class="sxs-lookup"><span data-stu-id="d8ae4-112">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="d8ae4-113">Връзките зависят от [потребителската роля](permissions.md):</span><span class="sxs-lookup"><span data-stu-id="d8ae4-113">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="d8ae4-114">Администраторите имат достъп до всички връзки.</span><span class="sxs-lookup"><span data-stu-id="d8ae4-114">Administrators have access to all connections.</span></span> <span data-ttu-id="d8ae4-115">Те също могат да създават нови връзки, когато настройват експортиране.</span><span class="sxs-lookup"><span data-stu-id="d8ae4-115">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="d8ae4-116">Сътрудниците могат да осъществяват достъп до конкретни връзки.</span><span class="sxs-lookup"><span data-stu-id="d8ae4-116">Contributors can have access to specific connections.</span></span> <span data-ttu-id="d8ae4-117">Те зависят от администраторите за конфигуриране и споделяне на връзки.</span><span class="sxs-lookup"><span data-stu-id="d8ae4-117">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="d8ae4-118">За повече информация вижте [Разрешаване на сътрудници да използват връзка за експортиране](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="d8ae4-118">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="d8ae4-119">Преглеждащите могат да виждат само съществуващи експортирания, но не и да ги създават.</span><span class="sxs-lookup"><span data-stu-id="d8ae4-119">Viewers can only view existing exports but not create them.</span></span>

1. <span data-ttu-id="d8ae4-120">Отидете на **Данни** > **Експортиране**.</span><span class="sxs-lookup"><span data-stu-id="d8ae4-120">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="d8ae4-121">Изберете **Добавяне на експортиране**, за да създадете ново местоназначение за експортиране.</span><span class="sxs-lookup"><span data-stu-id="d8ae4-121">Select **Add export** to create a new export destination.</span></span>

1. <span data-ttu-id="d8ae4-122">В прозореца **Настройване на експортиране** изберете коя връзка да използвате.</span><span class="sxs-lookup"><span data-stu-id="d8ae4-122">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="d8ae4-123">[Връзките](connections.md) се управляват от администратори.</span><span class="sxs-lookup"><span data-stu-id="d8ae4-123">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="d8ae4-124">Посочете необходимите подробности и изберете **Записване** за създаване на експортиране.</span><span class="sxs-lookup"><span data-stu-id="d8ae4-124">Provide the required details and select **Save** to create the export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="d8ae4-125">Редактиране на експортиране</span><span class="sxs-lookup"><span data-stu-id="d8ae4-125">Edit an export</span></span>

1. <span data-ttu-id="d8ae4-126">Изберете вертикалното многоточие за местоназначението за експортирането, което искате да редактирате.</span><span class="sxs-lookup"><span data-stu-id="d8ae4-126">Select the vertical ellipsis for the export destination you want to edit.</span></span>

1. <span data-ttu-id="d8ae4-127">Изберете **Редактиране** от падащото меню.</span><span class="sxs-lookup"><span data-stu-id="d8ae4-127">Select **Edit** from the drop-down menu.</span></span>

1. <span data-ttu-id="d8ae4-128">Променете стойностите, които искате да актуализирате, и изберете **Записване**.</span><span class="sxs-lookup"><span data-stu-id="d8ae4-128">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="d8ae4-129">Преглед на експортирания и подробностите за експортиране</span><span class="sxs-lookup"><span data-stu-id="d8ae4-129">View Exports and export details</span></span>

<span data-ttu-id="d8ae4-130">След създаването на местоназначение за експортиране, те са изброени в **Данни** > **Експортирания**.</span><span class="sxs-lookup"><span data-stu-id="d8ae4-130">After creating export destinations, they are listed on **Data** > **Exports**.</span></span> <span data-ttu-id="d8ae4-131">Всички потребители могат да видят кои данни се споделят и последното им състояние.</span><span class="sxs-lookup"><span data-stu-id="d8ae4-131">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="d8ae4-132">Отидете на **Данни** > **Експортиране**.</span><span class="sxs-lookup"><span data-stu-id="d8ae4-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="d8ae4-133">Потребителите без разрешения за редактиране избират **Преглед** вместо **Редактиране**, за да видят подробностите за експортирането.</span><span class="sxs-lookup"><span data-stu-id="d8ae4-133">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="d8ae4-134">Този страничен прозорец показва настройката на това експортиране.</span><span class="sxs-lookup"><span data-stu-id="d8ae4-134">This side pane shows the set up of this export.</span></span> <span data-ttu-id="d8ae4-135">Без разрешения за редактиране не можете да променяте стойности.</span><span class="sxs-lookup"><span data-stu-id="d8ae4-135">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="d8ae4-136">Изберете **Затваряне**, за да се върнете към страницата за експортиране.</span><span class="sxs-lookup"><span data-stu-id="d8ae4-136">Select **Close** to return to the exports page.</span></span>

## <a name="run-exports-on-demand"></a><span data-ttu-id="d8ae4-137">Изпълнение на експортиране при поискване</span><span class="sxs-lookup"><span data-stu-id="d8ae4-137">Run exports on demand</span></span>

<span data-ttu-id="d8ae4-138">След конфигуриране на експортиране то ще се изпълнява с всяко [планирано обновяване](system.md#schedule-tab), ако има работеща връзка.</span><span class="sxs-lookup"><span data-stu-id="d8ae4-138">After configuring an export, it will run with every [scheduled refresh](system.md#schedule-tab) as long as it has a working connection.</span></span>

<span data-ttu-id="d8ae4-139">За да експортирате данни, без да чакате планирано обновяване, отидете на **Данни** > **Експортиране**.</span><span class="sxs-lookup"><span data-stu-id="d8ae4-139">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span> <span data-ttu-id="d8ae4-140">Имате две опции:</span><span class="sxs-lookup"><span data-stu-id="d8ae4-140">You have two options:</span></span>

- <span data-ttu-id="d8ae4-141">За да стартирате всички експортирания, изберете **Изпълнение на всички** в командната лента.</span><span class="sxs-lookup"><span data-stu-id="d8ae4-141">To run all exports, select **Run all** in the command bar.</span></span> 
- <span data-ttu-id="d8ae4-142">За да стартирате едно експортиране, изберете многоточието (...) върху елемент от списъка и след това изберете **Изпълнение**.</span><span class="sxs-lookup"><span data-stu-id="d8ae4-142">To run a single export, select the ellipsis (...) on a list item and then choose **Run**.</span></span>

## <a name="remove-an-export"></a><span data-ttu-id="d8ae4-143">Премахване на експортиране</span><span class="sxs-lookup"><span data-stu-id="d8ae4-143">Remove an Export</span></span>

1. <span data-ttu-id="d8ae4-144">Отидете на **Данни** > **Експортиране**.</span><span class="sxs-lookup"><span data-stu-id="d8ae4-144">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="d8ae4-145">Изберете вертикалното многоточие за експортиране, което искате да премахнете.</span><span class="sxs-lookup"><span data-stu-id="d8ae4-145">Select the vertical ellipsis for the Export you want to remove.</span></span>

1. <span data-ttu-id="d8ae4-146">Изберете **Премахване** от падащото меню.</span><span class="sxs-lookup"><span data-stu-id="d8ae4-146">Select **Remove** from the dropdown menu.</span></span>

1. <span data-ttu-id="d8ae4-147">Потвърдете премахването, като изберете **Премахване** в екрана за потвърждение.</span><span class="sxs-lookup"><span data-stu-id="d8ae4-147">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
