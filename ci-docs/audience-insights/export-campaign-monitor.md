---
title: Експортиране на данни на Customer Insights в Campaign Monitor
description: Научете как да конфигурирате връзката и да експортирате в Campaign Monitor.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 7fd6af37b40e21d030a1ace0cd5f8fcc7861c3fa
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760472"
---
# <a name="export-segment-lists-to-campaign-monitor-preview"></a><span data-ttu-id="bfe63-103">Експортиране на списъци със сегменти в Campaign Monitor (преглед)</span><span class="sxs-lookup"><span data-stu-id="bfe63-103">Export segment lists to Campaign Monitor (preview)</span></span>

<span data-ttu-id="bfe63-104">Експортирайте сегменти от унифицирани клиентски профили в Campaign Monitor и ги използвайте за маркетингови дейности.</span><span class="sxs-lookup"><span data-stu-id="bfe63-104">Export segments of unified customer profiles to Campaign Monitor and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="bfe63-105">Предварителни изисквания</span><span class="sxs-lookup"><span data-stu-id="bfe63-105">Prerequisites</span></span>

-   <span data-ttu-id="bfe63-106">Имате [акаунт в Campaign Monitor](https://www.campaignmonitor.com/) и съответните идентификационни данни на администратор.</span><span class="sxs-lookup"><span data-stu-id="bfe63-106">You have an [Campaign Monitor account](https://www.campaignmonitor.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="bfe63-107">Имате [конфигурирани сегменти](segments.md) в аналитични данни за аудитория.</span><span class="sxs-lookup"><span data-stu-id="bfe63-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="bfe63-108">Единните клиентски профили в експортираните сегменти съдържат поле, представляващо имейл адрес.</span><span class="sxs-lookup"><span data-stu-id="bfe63-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="bfe63-109">Известни ограничения</span><span class="sxs-lookup"><span data-stu-id="bfe63-109">Known limitations</span></span>

- <span data-ttu-id="bfe63-110">Можете да експортирате до 1 милион профила с всяко експортиране в Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="bfe63-110">You can export up to 1 million profiles per export to Campaign Monitor.</span></span>
- <span data-ttu-id="bfe63-111">Експортирането в Campaign Monitor е ограничено до сегменти.</span><span class="sxs-lookup"><span data-stu-id="bfe63-111">Exporting to Campaign Monitor is limited to segments.</span></span>
- <span data-ttu-id="bfe63-112">Експортирането на до 1 милион профила в Campaign Monitor може да отнеме до 20 минути.</span><span class="sxs-lookup"><span data-stu-id="bfe63-112">Exporting up to 1 million profiles to Campaign Monitor can take up to 20 minutes to complete.</span></span> 
- <span data-ttu-id="bfe63-113">Броят на профилите, които можете да експортирате в Campaign Monitor, зависи и е ограничен от вашия договор с Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="bfe63-113">The number of profiles that you can export to Campaign Monitor is dependent and limited on your contract with Campaign Monitor.</span></span>

## <a name="set-up-connection-to-campaign-monitor"></a><span data-ttu-id="bfe63-114">Задаване на връзка с Campaign Monitor</span><span class="sxs-lookup"><span data-stu-id="bfe63-114">Set up connection to Campaign Monitor</span></span>

1. <span data-ttu-id="bfe63-115">Отидете на **Администратор** > **Връзки**.</span><span class="sxs-lookup"><span data-stu-id="bfe63-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="bfe63-116">Изберете **Добавяне на връзка** и изберете **Campaign Monitor** за конфигуриране на връзката.</span><span class="sxs-lookup"><span data-stu-id="bfe63-116">Select **Add connection** and choose **Campaign Monitor** to configure the connection.</span></span>

1. <span data-ttu-id="bfe63-117">Въведете разпознаваемо име за връзката в полето **Показвано име**.</span><span class="sxs-lookup"><span data-stu-id="bfe63-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="bfe63-118">Показваното име и типът описват тази връзка.</span><span class="sxs-lookup"><span data-stu-id="bfe63-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="bfe63-119">Препоръчваме да изберете име, което обяснява целта на връзката.</span><span class="sxs-lookup"><span data-stu-id="bfe63-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="bfe63-120">Изберете кой може да използва тази връзка.</span><span class="sxs-lookup"><span data-stu-id="bfe63-120">Choose who can use this connection.</span></span> <span data-ttu-id="bfe63-121">Ако не предприемете нищо, по подразбиране ще е Администратори.</span><span class="sxs-lookup"><span data-stu-id="bfe63-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="bfe63-122">За повече информация вижте [Разрешаване на сътрудници да използват връзка за експортиране](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="bfe63-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="bfe63-123">Изберете **Приемам**, за да потвърдите **Поверителност на данните и съответствие**.</span><span class="sxs-lookup"><span data-stu-id="bfe63-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="bfe63-124">Изберете **Свързване** за инициализиране на връзката с Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="bfe63-124">Select **Connect** to initialize the connection to Campaign Monitor.</span></span>

1. <span data-ttu-id="bfe63-125">Изберете **Удостоверяване с Campaign Monitor** и предоставете администраторските си данни за Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="bfe63-125">Select **Authenticate with Campaign Monitor** and provide your admin credentials for Campaign Monitor.</span></span>

1. <span data-ttu-id="bfe63-126">Изберете **Добавете себе си като потребител за експортиране** и предоставете вашите идентификационни данни на Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="bfe63-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="bfe63-127">Изберете **Записване**, за да завършите връзката.</span><span class="sxs-lookup"><span data-stu-id="bfe63-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="bfe63-128">Конфигуриране на експортиране</span><span class="sxs-lookup"><span data-stu-id="bfe63-128">Configure an export</span></span>

<span data-ttu-id="bfe63-129">Можете да конфигурирате това експортиране, ако имате достъп до връзка от този тип.</span><span class="sxs-lookup"><span data-stu-id="bfe63-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="bfe63-130">За повече информация вижте [Разрешения, необходими за конфигуриране на експортиране](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="bfe63-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="bfe63-131">Отидете на **Данни** > **Експортиране**.</span><span class="sxs-lookup"><span data-stu-id="bfe63-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="bfe63-132">За да създадете ново експортиране, изберете **Добавяне на местоназначение**.</span><span class="sxs-lookup"><span data-stu-id="bfe63-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="bfe63-133">В полето **Връзка за експортиране** изберете връзка от секцията Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="bfe63-133">In the **Connection for export** field, choose a connection from the Campaign Monitor section.</span></span> <span data-ttu-id="bfe63-134">Ако не виждате името на тази секция, няма достъпни за вас връзки от този тип.</span><span class="sxs-lookup"><span data-stu-id="bfe63-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="bfe63-135">Въведете [**ИД на списък в Campaign Monitor**](https://www.campaignmonitor.com/api/getting-started/#your-list-id).</span><span class="sxs-lookup"><span data-stu-id="bfe63-135">Enter your [**Campaign Monitor List ID**](https://www.campaignmonitor.com/api/getting-started/#your-list-id).</span></span>    
   <span data-ttu-id="bfe63-136">Първо [Генерирайте API ключа](https://www.campaignmonitor.com/api/getting-started/) от **Настройки на акаунт** в Campaign Monitor, за да видите ИД на API списъка.</span><span class="sxs-lookup"><span data-stu-id="bfe63-136">[Generate the API key](https://www.campaignmonitor.com/api/getting-started/) from **Account Settings** in Campaign Monitor first to view the API list ID.</span></span>  

3. <span data-ttu-id="bfe63-137">В секцията **Съвпадение на данни** в полето **Имейл** изберете полето във вашия унифициран потребителски профил, което представлява имейл адреса на клиента.</span><span class="sxs-lookup"><span data-stu-id="bfe63-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="bfe63-138">Необходимо е да експортирате сегменти в Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="bfe63-138">It's required to export segments to Campaign Monitor.</span></span>

1. <span data-ttu-id="bfe63-139">Изберете **Записване**.</span><span class="sxs-lookup"><span data-stu-id="bfe63-139">Select **Save**.</span></span>

<span data-ttu-id="bfe63-140">Запазването на експортиране не го изпълнява незабавно.</span><span class="sxs-lookup"><span data-stu-id="bfe63-140">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="bfe63-141">Експортирането се изпълнява с всяко [планирано обновяване](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="bfe63-141">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="bfe63-142">Може също [да експортирате данни при поискване](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="bfe63-142">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="bfe63-143">Поверителност и съответствие на данните</span><span class="sxs-lookup"><span data-stu-id="bfe63-143">Data privacy and compliance</span></span>

<span data-ttu-id="bfe63-144">Когато активирате Dynamics 365 Customer Insights, за да предавате данни към Campaign Monitor, разрешавате прехвърляне на данни извън границата на съответствие на Dynamics 365 Customer Insights, включително потенциално чувствителни данни като лични данни.</span><span class="sxs-lookup"><span data-stu-id="bfe63-144">When you enable Dynamics 365 Customer Insights to transmit data to Campaign Monitor, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="bfe63-145">Microsoft ще предава такива данни по ваше разпореждане, но вие носите отговорност да гарантирате, че Campaign Monitor спазва задълженията за поверителност и сигурност, които може да имате.</span><span class="sxs-lookup"><span data-stu-id="bfe63-145">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Campaign Monitor meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="bfe63-146">За информация посетете [Декларация за поверителност Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="bfe63-146">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="bfe63-147">Вашият администратор на Dynamics 365 Customer Insights да премахнете това местоназначение за експортиране по всяко време, за да прекратите използването на тази функционалност.</span><span class="sxs-lookup"><span data-stu-id="bfe63-147">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
