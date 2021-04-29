---
title: Експортиране на данни от Customer Insights
description: Управлявайте експортирането, за да споделяте данни.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 354ce9ef30fe918975d06290430996c84f8bd3f7
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896130"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="ec111-103">Общ преглед на експортирания (преглед)</span><span class="sxs-lookup"><span data-stu-id="ec111-103">Exports (preview) overview</span></span>

<span data-ttu-id="ec111-104">Страницата **Експортиране** ви показва всички конфигурирани експортирания.</span><span class="sxs-lookup"><span data-stu-id="ec111-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="ec111-105">Експортирането споделя специфични данни с различни приложения.</span><span class="sxs-lookup"><span data-stu-id="ec111-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="ec111-106">Те могат да включват клиентски профили или обекти, схеми и подробности за съпоставяне.</span><span class="sxs-lookup"><span data-stu-id="ec111-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="ec111-107">Всяко експортиране изисква [връзка, настроена от администратор, за управление на удостоверяване и достъп](connections.md).</span><span class="sxs-lookup"><span data-stu-id="ec111-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

> [!NOTE]
> <span data-ttu-id="ec111-108">До март 2021 г. експортирането автоматично създаваше връзка със съответната услуга.</span><span class="sxs-lookup"><span data-stu-id="ec111-108">Until March 2021, exports created a connection to the corresponding service automatically.</span></span> <span data-ttu-id="ec111-109">Сега експортирането изисква [връзка, създадена и споделена от администратор](connections.md), преди да можете да го създадете.</span><span class="sxs-lookup"><span data-stu-id="ec111-109">Exports now require a [connection, created and shared by an administrator](connections.md) before you can create them.</span></span>

<span data-ttu-id="ec111-110">Отидете на **Данни** > **Експортиране**, за да видите страницата за експортиране.</span><span class="sxs-lookup"><span data-stu-id="ec111-110">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="ec111-111">Всички потребителски роли имат достъп за преглед на конфигурираното експортиране.</span><span class="sxs-lookup"><span data-stu-id="ec111-111">All user roles have access to view configured exports.</span></span> <span data-ttu-id="ec111-112">Използване на полето за търсене в командната лента за намиране на експортирания по тяхното име, името на връзката или типа връзка.</span><span class="sxs-lookup"><span data-stu-id="ec111-112">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="ec111-113">Настройване на ново експортиране</span><span class="sxs-lookup"><span data-stu-id="ec111-113">Set up a new export</span></span>

<span data-ttu-id="ec111-114">За да настроите или редактирате експортиране, трябва да имате налични връзки.</span><span class="sxs-lookup"><span data-stu-id="ec111-114">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="ec111-115">Връзките зависят от [потребителската роля](permissions.md):</span><span class="sxs-lookup"><span data-stu-id="ec111-115">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="ec111-116">Администраторите имат достъп до всички връзки.</span><span class="sxs-lookup"><span data-stu-id="ec111-116">Administrators have access to all connections.</span></span> <span data-ttu-id="ec111-117">Те също могат да създават нови връзки, когато настройват експортиране.</span><span class="sxs-lookup"><span data-stu-id="ec111-117">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="ec111-118">Сътрудниците могат да осъществяват достъп до конкретни връзки.</span><span class="sxs-lookup"><span data-stu-id="ec111-118">Contributors can have access to specific connections.</span></span> <span data-ttu-id="ec111-119">Те зависят от администраторите за конфигуриране и споделяне на връзки.</span><span class="sxs-lookup"><span data-stu-id="ec111-119">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="ec111-120">За повече информация вижте [Разрешаване на сътрудници да използват връзка за експортиране](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="ec111-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="ec111-121">Преглеждащите могат да виждат само съществуващи експортирания, но не и да ги създават.</span><span class="sxs-lookup"><span data-stu-id="ec111-121">Viewers can only view existing exports but not create them.</span></span>

1. <span data-ttu-id="ec111-122">Отидете на **Данни** > **Експортиране**.</span><span class="sxs-lookup"><span data-stu-id="ec111-122">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="ec111-123">Изберете **Добавяне на експортиране**, за да създадете ново местоназначение за експортиране.</span><span class="sxs-lookup"><span data-stu-id="ec111-123">Select **Add export** to create a new export destination.</span></span>

1. <span data-ttu-id="ec111-124">В прозореца **Настройване на експортиране** изберете коя връзка да използвате.</span><span class="sxs-lookup"><span data-stu-id="ec111-124">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="ec111-125">[Връзките](connections.md) се управляват от администратори.</span><span class="sxs-lookup"><span data-stu-id="ec111-125">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="ec111-126">Посочете необходимите подробности и изберете **Записване** за създаване на експортиране.</span><span class="sxs-lookup"><span data-stu-id="ec111-126">Provide the required details and select **Save** to create the export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="ec111-127">Редактиране на експортиране</span><span class="sxs-lookup"><span data-stu-id="ec111-127">Edit an export</span></span>

1. <span data-ttu-id="ec111-128">Изберете вертикалното многоточие за местоназначението за експортирането, което искате да редактирате.</span><span class="sxs-lookup"><span data-stu-id="ec111-128">Select the vertical ellipsis for the export destination you want to edit.</span></span>

1. <span data-ttu-id="ec111-129">Изберете **Редактиране** от падащото меню.</span><span class="sxs-lookup"><span data-stu-id="ec111-129">Select **Edit** from the drop-down menu.</span></span>

1. <span data-ttu-id="ec111-130">Променете стойностите, които искате да актуализирате, и изберете **Записване**.</span><span class="sxs-lookup"><span data-stu-id="ec111-130">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="ec111-131">Преглед на експортирания и подробностите за експортиране</span><span class="sxs-lookup"><span data-stu-id="ec111-131">View Exports and export details</span></span>

<span data-ttu-id="ec111-132">След създаването на местоназначение за експортиране, те са изброени в **Данни** > **Експортирания**.</span><span class="sxs-lookup"><span data-stu-id="ec111-132">After creating export destinations, they are listed on **Data** > **Exports**.</span></span> <span data-ttu-id="ec111-133">Всички потребители могат да видят кои данни се споделят и последното им състояние.</span><span class="sxs-lookup"><span data-stu-id="ec111-133">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="ec111-134">Отидете на **Данни** > **Експортиране**.</span><span class="sxs-lookup"><span data-stu-id="ec111-134">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="ec111-135">Потребителите без разрешения за редактиране избират **Преглед** вместо **Редактиране**, за да видят подробностите за експортирането.</span><span class="sxs-lookup"><span data-stu-id="ec111-135">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="ec111-136">Този страничен прозорец показва настройката на това експортиране.</span><span class="sxs-lookup"><span data-stu-id="ec111-136">This side pane shows the set up of this export.</span></span> <span data-ttu-id="ec111-137">Без разрешения за редактиране не можете да променяте стойности.</span><span class="sxs-lookup"><span data-stu-id="ec111-137">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="ec111-138">Изберете **Затваряне**, за да се върнете към страницата за експортиране.</span><span class="sxs-lookup"><span data-stu-id="ec111-138">Select **Close** to return to the exports page.</span></span>

## <a name="run-exports-on-demand"></a><span data-ttu-id="ec111-139">Изпълнение на експортиране при поискване</span><span class="sxs-lookup"><span data-stu-id="ec111-139">Run exports on demand</span></span>

<span data-ttu-id="ec111-140">След конфигуриране на експортиране то ще се изпълнява с всяко [планирано обновяване](system.md#schedule-tab), ако има работеща връзка.</span><span class="sxs-lookup"><span data-stu-id="ec111-140">After configuring an export, it will run with every [scheduled refresh](system.md#schedule-tab) as long as it has a working connection.</span></span>

<span data-ttu-id="ec111-141">За да експортирате данни, без да чакате планирано обновяване, отидете на **Данни** > **Експортиране**.</span><span class="sxs-lookup"><span data-stu-id="ec111-141">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span> <span data-ttu-id="ec111-142">Имате две опции:</span><span class="sxs-lookup"><span data-stu-id="ec111-142">You have two options:</span></span>

- <span data-ttu-id="ec111-143">За да стартирате всички експортирания, изберете **Изпълнение на всички** в командната лента.</span><span class="sxs-lookup"><span data-stu-id="ec111-143">To run all exports, select **Run all** in the command bar.</span></span> 
- <span data-ttu-id="ec111-144">За да стартирате едно експортиране, изберете многоточието (...) върху елемент от списъка и след това изберете **Изпълнение**.</span><span class="sxs-lookup"><span data-stu-id="ec111-144">To run a single export, select the ellipsis (...) on a list item and then choose **Run**.</span></span>

## <a name="remove-an-export"></a><span data-ttu-id="ec111-145">Премахване на експортиране</span><span class="sxs-lookup"><span data-stu-id="ec111-145">Remove an Export</span></span>

1. <span data-ttu-id="ec111-146">Отидете на **Данни** > **Експортиране**.</span><span class="sxs-lookup"><span data-stu-id="ec111-146">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="ec111-147">Изберете вертикалното многоточие за експортиране, което искате да премахнете.</span><span class="sxs-lookup"><span data-stu-id="ec111-147">Select the vertical ellipsis for the Export you want to remove.</span></span>

1. <span data-ttu-id="ec111-148">Изберете **Премахване** от падащото меню.</span><span class="sxs-lookup"><span data-stu-id="ec111-148">Select **Remove** from the dropdown menu.</span></span>

1. <span data-ttu-id="ec111-149">Потвърдете премахването, като изберете **Премахване** в екрана за потвърждение.</span><span class="sxs-lookup"><span data-stu-id="ec111-149">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
