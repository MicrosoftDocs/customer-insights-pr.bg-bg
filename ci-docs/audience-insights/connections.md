---
title: Връзки с други услуги от Customer Insights.
description: Споделяйте данни с други услуги.
ms.date: 04/09/2021
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 17e04b243e9b3d4375c86f5a890a18be35956835
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304959"
---
# <a name="connections-preview-overview"></a><span data-ttu-id="06f92-103">Общ преглед на връзките (преглед)</span><span class="sxs-lookup"><span data-stu-id="06f92-103">Connections (preview) overview</span></span>

<span data-ttu-id="06f92-104">Връзките са основата на активирането на споделяне на данни със и от Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="06f92-104">Connections are the key to enable data sharing to and from Customer Insights.</span></span> <span data-ttu-id="06f92-105">Всяка връзка установява споделяне на данни с конкретна услуга.</span><span class="sxs-lookup"><span data-stu-id="06f92-105">Each connection establishes data sharing with a specific service.</span></span> <span data-ttu-id="06f92-106">Връзките са основата за [конфигуриране на допълване на трети страни](enrichment-hub.md) и [конфигуриране на експортиране](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="06f92-106">Connections are the foundation to [configure third-party enrichments](enrichment-hub.md) and [configure exports](export-destinations.md).</span></span> <span data-ttu-id="06f92-107">Една и съща връзка може да се използва няколко пъти.</span><span class="sxs-lookup"><span data-stu-id="06f92-107">The same connection can be used multiple times.</span></span> <span data-ttu-id="06f92-108">Например една връзка с Dynamics 365 Marketing работи за няколко експортирания и една връзка Leadspace може да се използва за няколко допълвания.</span><span class="sxs-lookup"><span data-stu-id="06f92-108">For example, one connection to Dynamics 365 Marketing works for multiple exports and one Leadspace connection can be used for several enrichments.</span></span>

<span data-ttu-id="06f92-109">Отидете на **Администратор** > **Връзки** за създаване и преглед на връзките.</span><span class="sxs-lookup"><span data-stu-id="06f92-109">Go to **Admin** > **Connections** to create and view connections.</span></span>

<span data-ttu-id="06f92-110">Разделът **Връзки** ви показва всички активни връзки.</span><span class="sxs-lookup"><span data-stu-id="06f92-110">The **Connections** tab shows you all active connections.</span></span> <span data-ttu-id="06f92-111">Списъкът показва ред за всяка връзка.</span><span class="sxs-lookup"><span data-stu-id="06f92-111">The list shows a row for each connection.</span></span> 

<span data-ttu-id="06f92-112">Вижте бърз преглед, описание и разберете какво можете да направите с всяка опция за разширяване в раздела **Откриване**.</span><span class="sxs-lookup"><span data-stu-id="06f92-112">Get a quick overview, description, and find out what you can do with each extensibility option on the **Discover** tab.</span></span>

### <a name="exports"></a><span data-ttu-id="06f92-113">Експортирания</span><span class="sxs-lookup"><span data-stu-id="06f92-113">Exports</span></span>

<span data-ttu-id="06f92-114">Само администраторите могат да конфигурират нови връзки, но те могат да предоставят достъп на сътрудници за използване на съществуващи връзки.</span><span class="sxs-lookup"><span data-stu-id="06f92-114">Only administrators can configure new connections but they can grant access to contributors to use existing connections.</span></span> <span data-ttu-id="06f92-115">Администраторите контролират къде могат да отидат данните, сътрудниците определят полезните данни и честотата, които отговарят на нуждите им.</span><span class="sxs-lookup"><span data-stu-id="06f92-115">Administrators control where data can go, contributors define the payload and frequency fitting their needs.</span></span> <span data-ttu-id="06f92-116">За повече информация вижте [Разрешаване на сътрудници да използват връзка за експортиране](#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="06f92-116">For more information, see [Allow contributors to use a connection for exports](#allow-contributors-to-use-a-connection-for-exports).</span></span>

### <a name="enrichments"></a><span data-ttu-id="06f92-117">Допълвания</span><span class="sxs-lookup"><span data-stu-id="06f92-117">Enrichments</span></span>

<span data-ttu-id="06f92-118">Само администраторите могат да конфигурират нови връзки, но създадените връзки са винаги достъпни както за администратори, така и за сътрудници.</span><span class="sxs-lookup"><span data-stu-id="06f92-118">Only administrators can configure new connections but the created connections are always available to both administrators and contributors.</span></span> <span data-ttu-id="06f92-119">Администраторите управляват идентификационните данни и дават съгласие за прехвърляне на данни.</span><span class="sxs-lookup"><span data-stu-id="06f92-119">Administrators manage credentials and give consent to data transfers.</span></span> <span data-ttu-id="06f92-120">След това връзките могат да се използват за допълване от администратори и от сътрудници.</span><span class="sxs-lookup"><span data-stu-id="06f92-120">The connections can then be used for enrichments by both administrators and contributors.</span></span>

## <a name="add-a-new-connection"></a><span data-ttu-id="06f92-121">Добавяне на нова връзка</span><span class="sxs-lookup"><span data-stu-id="06f92-121">Add a new connection</span></span>

<span data-ttu-id="06f92-122">За да добавите връзки, трябва да имате [разрешения на администратор](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="06f92-122">To add connections, you need to have [administrator permissions](permissions.md).</span></span> <span data-ttu-id="06f92-123">Ако се свържете с други услуги на Microsoft, предполагаме, че и двете услуги са в една и съща организация.</span><span class="sxs-lookup"><span data-stu-id="06f92-123">If you connect to other Microsoft services, we assume both services are in the same organization.</span></span>

1. <span data-ttu-id="06f92-124">Отидете на **Администратор** > **Връзки (преглед)**.</span><span class="sxs-lookup"><span data-stu-id="06f92-124">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="06f92-125">Отидете в раздела **Връзки**.</span><span class="sxs-lookup"><span data-stu-id="06f92-125">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="06f92-126">Изберете **Добавяне на връзка**, за да създадете нова връзка.</span><span class="sxs-lookup"><span data-stu-id="06f92-126">Select **Add connection** to create a new connection.</span></span> <span data-ttu-id="06f92-127">Изберете от падащото меню какъв тип връзка искате да създадете.</span><span class="sxs-lookup"><span data-stu-id="06f92-127">Choose from the dropdown menu what type of connection you want to create.</span></span>

1. <span data-ttu-id="06f92-128">В прозореца **Настройване на връзка** предоставете необходимите подробности.</span><span class="sxs-lookup"><span data-stu-id="06f92-128">In the **Set up connection** pane, provide the required details.</span></span> 
   1. <span data-ttu-id="06f92-129">**Показваното име** и типът описват връзката.</span><span class="sxs-lookup"><span data-stu-id="06f92-129">The **Display name** and the type of the connection describe a connection.</span></span> <span data-ttu-id="06f92-130">Препоръчваме да изберете име, което обяснява целта на тази връзка.</span><span class="sxs-lookup"><span data-stu-id="06f92-130">We recommend choosing a name that explains the purpose and target of this connection.</span></span>
   1. <span data-ttu-id="06f92-131">Точните полета зависят от това към коя услуга се свързвате.</span><span class="sxs-lookup"><span data-stu-id="06f92-131">The exact fields depend on what service you are connecting to.</span></span> <span data-ttu-id="06f92-132">Можете да научите за подробности за конкретен тип връзка в статията за целевата услуга.</span><span class="sxs-lookup"><span data-stu-id="06f92-132">You can learn about details of a specific connection type in the article about the target service.</span></span>

1. <span data-ttu-id="06f92-133">За да създадете връзка, изберете **Записване**.</span><span class="sxs-lookup"><span data-stu-id="06f92-133">To create the connection, select **Save**.</span></span>

<span data-ttu-id="06f92-134">Можете също да изберете **Настройка** върху плочка на раздела **Откриване**.</span><span class="sxs-lookup"><span data-stu-id="06f92-134">You can also select **Set up** on a tile on the **Discover** tab.</span></span>

### <a name="allow-contributors-to-use-a-connection-for-exports"></a><span data-ttu-id="06f92-135">Разрешаване на сътрудници да използват връзка за експортиране</span><span class="sxs-lookup"><span data-stu-id="06f92-135">Allow contributors to use a connection for exports</span></span>

<span data-ttu-id="06f92-136">Когато настройвате или редактирате връзка за експортиране, избирате кои потребители могат да използват тази конкретна връзка за дефиниране на [експортиране](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="06f92-136">When setting up or editing an export connection, you choose which users are allowed to use this specific connection to define [exports](export-destinations.md).</span></span> <span data-ttu-id="06f92-137">По подразбиране връзката е достъпна за потребители с роля на администратор.</span><span class="sxs-lookup"><span data-stu-id="06f92-137">By default a connection is available to users with an administrator role.</span></span> <span data-ttu-id="06f92-138">Можете да промените тази настройка под **Изберете кой може да използва тази връзка** и позволете на потребителите с роля на сътрудник да използват тази връзка.</span><span class="sxs-lookup"><span data-stu-id="06f92-138">You can change this setting under **Choose who can use this connection** and allow users with contributor role to use this connection.</span></span>

- <span data-ttu-id="06f92-139">Сътрудниците няма да могат да преглеждат или редактират връзката.</span><span class="sxs-lookup"><span data-stu-id="06f92-139">Contributors won't be able to view or edit the connection.</span></span> <span data-ttu-id="06f92-140">Те ще виждат показваното име и неговия тип само при създаване на експортиране.</span><span class="sxs-lookup"><span data-stu-id="06f92-140">They will only see the display name and its type when creating an export.</span></span>
- <span data-ttu-id="06f92-141">Като споделяте връзка, вие разрешавате на участниците да я използват.</span><span class="sxs-lookup"><span data-stu-id="06f92-141">By sharing a connection, you allow contributors to use a connection.</span></span> <span data-ttu-id="06f92-142">Сътрудниците ще виждат споделените връзки, когато настройват експортиране.</span><span class="sxs-lookup"><span data-stu-id="06f92-142">Contributors will see shared connections when they set up exports.</span></span> <span data-ttu-id="06f92-143">Те могат да управляват всяко експортиране, което използва тази специфична връзка.</span><span class="sxs-lookup"><span data-stu-id="06f92-143">They can manage every export that uses this specific connection.</span></span>
- <span data-ttu-id="06f92-144">Можете да промените тази настройка, като същевременно запазите експортиранията, които вече са дефинирани от сътрудници.</span><span class="sxs-lookup"><span data-stu-id="06f92-144">You can change this setting while keeping the exports that have already been defined by contributors.</span></span>

## <a name="edit-a-connection"></a><span data-ttu-id="06f92-145">Редактиране на връзка</span><span class="sxs-lookup"><span data-stu-id="06f92-145">Edit a connection</span></span>

1. <span data-ttu-id="06f92-146">Отидете на **Администратор** > **Връзки (преглед)**.</span><span class="sxs-lookup"><span data-stu-id="06f92-146">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="06f92-147">Отидете в раздела **Връзки**.</span><span class="sxs-lookup"><span data-stu-id="06f92-147">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="06f92-148">Изберете вертикалното многоточие за връзката, която искате да редактирате.</span><span class="sxs-lookup"><span data-stu-id="06f92-148">Select the vertical ellipsis for the connection you want to edit.</span></span>

1. <span data-ttu-id="06f92-149">Изберете **Редактиране**.</span><span class="sxs-lookup"><span data-stu-id="06f92-149">Select **Edit**.</span></span>

1. <span data-ttu-id="06f92-150">Променете стойностите, които искате да актуализирате, и изберете **Записване**.</span><span class="sxs-lookup"><span data-stu-id="06f92-150">Change the values you want to update and select **Save**.</span></span>

## <a name="remove-a-connection"></a><span data-ttu-id="06f92-151">Премахване на връзка</span><span class="sxs-lookup"><span data-stu-id="06f92-151">Remove a connection</span></span>

<span data-ttu-id="06f92-152">Ако връзката, която премахвате, се използва за допълване или експортиране, първо трябва да я отделите или премахнете.</span><span class="sxs-lookup"><span data-stu-id="06f92-152">If the connection you are removing is used by enrichments or exports, you first need to detach or remove them.</span></span> <span data-ttu-id="06f92-153">Диалоговият прозорец за премахване ще ви насочи към съответните допълвания или експортиране.</span><span class="sxs-lookup"><span data-stu-id="06f92-153">The remove dialog will guide you to the relevant enrichments or exports.</span></span> 

<span data-ttu-id="06f92-154">Отделените допълвания и експортирания стават неактивни.</span><span class="sxs-lookup"><span data-stu-id="06f92-154">Detached enrichments and exports become inactive.</span></span> <span data-ttu-id="06f92-155">Активирате ги повторно, като добавите друга връзка към тях на страницата [Допълвания](enrichment-hub.md) или [Експортиране](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="06f92-155">You reactivate them by adding another connection to them on the [Enrichments](enrichment-hub.md) or [Exports](export-destinations.md) page.</span></span>

1. <span data-ttu-id="06f92-156">Отидете на **Администратор** > **Връзки (преглед)**.</span><span class="sxs-lookup"><span data-stu-id="06f92-156">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="06f92-157">Отидете в раздела **Връзки**.</span><span class="sxs-lookup"><span data-stu-id="06f92-157">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="06f92-158">Изберете вертикалното многоточие за връзката, която искате да премахнете.</span><span class="sxs-lookup"><span data-stu-id="06f92-158">Select the vertical ellipsis for the connection you want to remove.</span></span>

1. <span data-ttu-id="06f92-159">Изберете **Премахване** от падащото меню.</span><span class="sxs-lookup"><span data-stu-id="06f92-159">Select **Remove** from the dropdown menu.</span></span> <span data-ttu-id="06f92-160">Показва се диалогов прозорец за потвърждение.</span><span class="sxs-lookup"><span data-stu-id="06f92-160">A confirmation dialog appears.</span></span>

   1. <span data-ttu-id="06f92-161">Ако допълване или експортиране използват тази връзка, изберете бутона, за да видите какво използва връзката.</span><span class="sxs-lookup"><span data-stu-id="06f92-161">If there are enrichments or exports using this connection, select the button to see what's using the connection.</span></span>
      - <span data-ttu-id="06f92-162">**Експортиране:** Може да изберете да премахнете или да прекъснете експортирането, за да можете да премахнете връзката.</span><span class="sxs-lookup"><span data-stu-id="06f92-162">**Exports:** You can choose to either remove or disconnect the exports to be able to remove the connection.</span></span> <span data-ttu-id="06f92-163">За да прекъснат експортиране, администраторите могат да използват действието **Прекъсване на връзка**.</span><span class="sxs-lookup"><span data-stu-id="06f92-163">To disconnect an export, administrators can use the **Disconnect** action.</span></span> <span data-ttu-id="06f92-164">Това действие е достъпно за отделни и няколко избрани експортирания.</span><span class="sxs-lookup"><span data-stu-id="06f92-164">This action is available for individual and multiple selected exports.</span></span> <span data-ttu-id="06f92-165">С прекъсването на връзката запазвате конфигурацията за експортиране, но тя няма да се изпълни, докато към нея не бъде добавена друга връзка.</span><span class="sxs-lookup"><span data-stu-id="06f92-165">By disconnecting you keep the export config, but it won't be run until another connection is added to it.</span></span>
      - <span data-ttu-id="06f92-166">**Допълване:** Може да изберете да премахнете или да дезактивирате допълването, за да можете да премахнете връзката.</span><span class="sxs-lookup"><span data-stu-id="06f92-166">**Enrichments:** You can choose to either remove or deactivate the enrichments to be able to remove the connection.</span></span> 
   1. <span data-ttu-id="06f92-167">След като връзката няма зависимости, върнете се към **Администратор** > **Връзки** и опитайте да премахнете връзката отново.</span><span class="sxs-lookup"><span data-stu-id="06f92-167">Once the connection has no more dependencies, go back to **Admin** > **Connections** and try removing the connection again.</span></span>

1. <span data-ttu-id="06f92-168">За да потвърдите изтриването, изберете **Премахване**.</span><span class="sxs-lookup"><span data-stu-id="06f92-168">To confirm the deletion, select **Remove**.</span></span>

