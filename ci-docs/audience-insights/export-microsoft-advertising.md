---
title: Експортиране на данни от Customer Insights в Microsoft Advertising
description: Научете как да конфигурирате връзката и да експортирате в Microsoft Advertising.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c2ac92de2718cf7f0622b407bf198a7a7e50a37b
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124453"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a><span data-ttu-id="9ac9d-103">Експортиране на сегменти в Microsoft Advertising (преглед)</span><span class="sxs-lookup"><span data-stu-id="9ac9d-103">Export segments to Microsoft Advertising (preview)</span></span>

<span data-ttu-id="9ac9d-104">Експортирайте сегменти на Customer Insights в Microsoft Advertising, за да създадете аудитории за списъци с клиенти.</span><span class="sxs-lookup"><span data-stu-id="9ac9d-104">Export Customer Insights segments to Microsoft Advertising to create Customer Match audiences.</span></span> <span data-ttu-id="9ac9d-105">Използвайте тези аудитории за рекламните си кампании.</span><span class="sxs-lookup"><span data-stu-id="9ac9d-105">Use these audiences for your ad campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9ac9d-106">Предварителни изисквания</span><span class="sxs-lookup"><span data-stu-id="9ac9d-106">Prerequisites</span></span>

-   <span data-ttu-id="9ac9d-107">[Акаунт в Microsoft Advertising](https://ads.microsoft.com/) и съответните идентификационни данни на администратор.</span><span class="sxs-lookup"><span data-stu-id="9ac9d-107">An [Microsoft Advertising account](https://ads.microsoft.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="9ac9d-108">Вие приехте условията за използване на списъка с клиенти.</span><span class="sxs-lookup"><span data-stu-id="9ac9d-108">You've accepted the Customer Match terms of use.</span></span> 
-   <span data-ttu-id="9ac9d-109">[Конфигурирани сегменти](segments.md) в аналитични данни за аудитория.</span><span class="sxs-lookup"><span data-stu-id="9ac9d-109">[Configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="9ac9d-110">Единните потребителски профили в експортираните сегменти съдържат поле с имейл адрес.</span><span class="sxs-lookup"><span data-stu-id="9ac9d-110">Unified customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="9ac9d-111">Известни ограничения</span><span class="sxs-lookup"><span data-stu-id="9ac9d-111">Known limitations</span></span>

- <span data-ttu-id="9ac9d-112">Можете да експортирате до 500 хиляди профила с всяко експортиране в Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="9ac9d-112">You can export up to 500 K profiles per export to Microsoft Advertising.</span></span>
- <span data-ttu-id="9ac9d-113">Експортирането в Microsoft Advertising е ограничено до сегменти.</span><span class="sxs-lookup"><span data-stu-id="9ac9d-113">Exporting to Microsoft Advertising is limited to segments.</span></span>
- <span data-ttu-id="9ac9d-114">Експортирането на до 500 хиляди профила в Microsoft Advertising може да отнеме до 10 минути.</span><span class="sxs-lookup"><span data-stu-id="9ac9d-114">Exporting up to 500 K profiles to Microsoft Advertising can take up to 10 minutes to complete.</span></span> 


## <a name="set-up-the-connection-to-microsoft-advertising"></a><span data-ttu-id="9ac9d-115">Настройване на връзката с Microsoft Advertising</span><span class="sxs-lookup"><span data-stu-id="9ac9d-115">Set up the connection to Microsoft Advertising</span></span>

1. <span data-ttu-id="9ac9d-116">Отидете на **Администратор** > **Връзки**.</span><span class="sxs-lookup"><span data-stu-id="9ac9d-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="9ac9d-117">Изберете **Добавяне на връзка** и изберете **Microsoft Advertising** за конфигуриране на връзката.</span><span class="sxs-lookup"><span data-stu-id="9ac9d-117">Select **Add connection** and choose **Microsoft Advertising** to configure the connection.</span></span>

1. <span data-ttu-id="9ac9d-118">Въведете разпознаваемо име за връзката в полето **Показвано име**.</span><span class="sxs-lookup"><span data-stu-id="9ac9d-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="9ac9d-119">Показваното име и типът описват тази връзка.</span><span class="sxs-lookup"><span data-stu-id="9ac9d-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="9ac9d-120">Препоръчваме да изберете име, което обяснява целта на връзката.</span><span class="sxs-lookup"><span data-stu-id="9ac9d-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="9ac9d-121">Изберете кой може да използва тази връзка.</span><span class="sxs-lookup"><span data-stu-id="9ac9d-121">Choose who can use this connection.</span></span> <span data-ttu-id="9ac9d-122">По подразбиране са администратори.</span><span class="sxs-lookup"><span data-stu-id="9ac9d-122">The default is administrators.</span></span> <span data-ttu-id="9ac9d-123">За повече информация вижте [Разрешаване на сътрудници да използват връзка за експортиране](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="9ac9d-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="9ac9d-124">Изберете **Приемам**, за да потвърдите **Поверителност на данните и съответствие**.</span><span class="sxs-lookup"><span data-stu-id="9ac9d-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="9ac9d-125">Изберете **Свързване** за инициализиране на връзката с Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="9ac9d-125">Select **Connect** to initialize the connection to Microsoft Advertising.</span></span>

1. <span data-ttu-id="9ac9d-126">Изберете **Удостоверяване с Microsoft Advertising** и предоставете администраторските си данни за Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="9ac9d-126">Select **Authenticate with Microsoft Advertising** and provide your admin credentials for Microsoft Advertising.</span></span>

1. <span data-ttu-id="9ac9d-127">Изберете **Добавете себе си като потребител за експортиране** и предоставете вашите идентификационни данни на Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="9ac9d-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="9ac9d-128">Изберете **Записване**, за да завършите връзката.</span><span class="sxs-lookup"><span data-stu-id="9ac9d-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="9ac9d-129">Конфигуриране на експортиране</span><span class="sxs-lookup"><span data-stu-id="9ac9d-129">Configure an export</span></span>

<span data-ttu-id="9ac9d-130">Можете да конфигурирате това експортиране, ако имате достъп до връзка от този тип.</span><span class="sxs-lookup"><span data-stu-id="9ac9d-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="9ac9d-131">За повече информация вижте [Разрешения, необходими за конфигуриране на експортиране](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="9ac9d-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="9ac9d-132">Отидете на **Данни** > **Експортиране**.</span><span class="sxs-lookup"><span data-stu-id="9ac9d-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="9ac9d-133">За да създадете ново експортиране, изберете **Добавяне на местоназначение**.</span><span class="sxs-lookup"><span data-stu-id="9ac9d-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="9ac9d-134">В полето **Връзка за експортиране** изберете връзка от секцията Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="9ac9d-134">In the **Connection for export** field, choose a connection from the Microsoft Advertising section.</span></span> <span data-ttu-id="9ac9d-135">Ако не виждате името на тази секция, няма достъпни за вас връзки от този тип.</span><span class="sxs-lookup"><span data-stu-id="9ac9d-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="9ac9d-136">Изберете сегменти за експортиране.</span><span class="sxs-lookup"><span data-stu-id="9ac9d-136">Select the segments to export.</span></span> <span data-ttu-id="9ac9d-137">Аудиториите за съвпадение на клиенти в Microsoft Advertising се създават автоматично с името на сегментите, избрани за експортиране.</span><span class="sxs-lookup"><span data-stu-id="9ac9d-137">The Customer Match audiences in Microsoft Advertising are automatically created with the name of the segments selected for export.</span></span> <span data-ttu-id="9ac9d-138">Всеки сегмент ще доведе до отделна аудитория за списъци с клиенти.</span><span class="sxs-lookup"><span data-stu-id="9ac9d-138">Each segment will result in a separate Customer Match audience.</span></span> 

1. <span data-ttu-id="9ac9d-139">Въведете своя **Идентификационен номер на клиент на Microsoft Advertising и идентификатор на акаунт**.</span><span class="sxs-lookup"><span data-stu-id="9ac9d-139">Enter your **Microsoft Advertising Customer ID and Account ID**.</span></span> <span data-ttu-id="9ac9d-140">Можете да намерите идентификатора на клиента (`cid`) и идентификационен номер на акаунт (`aid`) в параметрите на URL адреса, когато сте влезли в Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="9ac9d-140">You can find the Customer ID (`cid`) and Account ID (`aid`) in the parameters of the URL when you're signed in Microsoft Advertising.</span></span>

1. <span data-ttu-id="9ac9d-141">В секцията **Съвпадение на данни** в полето **електронна поща**, изберете полето във вашия унифициран потребителски профил с имейл адрес на клиента.</span><span class="sxs-lookup"><span data-stu-id="9ac9d-141">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile with a customer's email address.</span></span> <span data-ttu-id="9ac9d-142">Необходимо е да експортирате сегменти в Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="9ac9d-142">It's required to export segments to Microsoft Advertising.</span></span>

1. <span data-ttu-id="9ac9d-143">Изберете **Записване**.</span><span class="sxs-lookup"><span data-stu-id="9ac9d-143">Select **Save**.</span></span>

<span data-ttu-id="9ac9d-144">Запазването на експортиране не го изпълнява незабавно.</span><span class="sxs-lookup"><span data-stu-id="9ac9d-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="9ac9d-145">Експортирането се изпълнява с всяко [планирано обновяване](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="9ac9d-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="9ac9d-146">Може също [да експортирате данни при поискване](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="9ac9d-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="9ac9d-147">Поверителност и съответствие на данните</span><span class="sxs-lookup"><span data-stu-id="9ac9d-147">Data privacy and compliance</span></span>

<span data-ttu-id="9ac9d-148">Когато активирате Dynamics 365 Customer Insights, за да предавате данни към Microsoft Advertising, разрешавате прехвърляне на данни извън границата на съответствие на Dynamics 365 Customer Insights, включително потенциално чувствителни данни като лични данни.</span><span class="sxs-lookup"><span data-stu-id="9ac9d-148">When you enable Dynamics 365 Customer Insights to transmit data to Microsoft Advertising, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="9ac9d-149">Microsoft ще предава такива данни по ваше разпореждане, но вие носите отговорност да гарантирате, че Microsoft Advertising спазва задълженията за поверителност и сигурност, които може да имате.</span><span class="sxs-lookup"><span data-stu-id="9ac9d-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Microsoft Advertising meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="9ac9d-150">За информация посетете [Декларация за поверителност Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="9ac9d-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="9ac9d-151">Вашият администратор на Dynamics 365 Customer Insights може да премахнете това местоназначение за експортиране по всяко време, за да прекратите използването на тази функционалност.</span><span class="sxs-lookup"><span data-stu-id="9ac9d-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to stop use of this functionality.</span></span>
