---
title: Експортирайте данните от Customer Insights в AdRoll
description: Научете как да конфигурирате връзката и да експортирате в AdRoll.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 67bfa23d56b26ae592efa4d7197713664bb02623
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304788"
---
# <a name="export-segments-to-adroll-preview"></a><span data-ttu-id="ee60b-103">Експортиране със сегменти в AdRoll (преглед)</span><span class="sxs-lookup"><span data-stu-id="ee60b-103">Export segments to AdRoll (preview)</span></span>

<span data-ttu-id="ee60b-104">Експортирайте сегменти от унифицирани клиентски профили в AdRoll и ги използвайте за реклама.</span><span class="sxs-lookup"><span data-stu-id="ee60b-104">Export segments of unified customer profiles to AdRoll and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="ee60b-105">Предварителни изисквания за връзка</span><span class="sxs-lookup"><span data-stu-id="ee60b-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="ee60b-106">Имате [Акаунт в AdRoll](https://www.adroll.com/) и съответните идентификационни данни на администратора.</span><span class="sxs-lookup"><span data-stu-id="ee60b-106">You have an [AdRoll account](https://www.adroll.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="ee60b-107">Имате [конфигурирани сегменти](segments.md) в аналитични данни за аудитория.</span><span class="sxs-lookup"><span data-stu-id="ee60b-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="ee60b-108">Единните клиентски профили в експортираните сегменти съдържат поле, представляващо имейл адрес.</span><span class="sxs-lookup"><span data-stu-id="ee60b-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="ee60b-109">Известни ограничения</span><span class="sxs-lookup"><span data-stu-id="ee60b-109">Known limitations</span></span>

- <span data-ttu-id="ee60b-110">Едновременно можете да експортирате до 250 000 профила в AdRoll.</span><span class="sxs-lookup"><span data-stu-id="ee60b-110">You can export up to 250,000 profiles at a time to AdRoll.</span></span>
- <span data-ttu-id="ee60b-111">Не можете да експортирате сегменти с по-малко от 100 профила в AdRoll.</span><span class="sxs-lookup"><span data-stu-id="ee60b-111">You can't export segments with fewer than 100 profiles to AdRoll.</span></span> 
- <span data-ttu-id="ee60b-112">Експортирането в AdRoll е ограничено до сегменти.</span><span class="sxs-lookup"><span data-stu-id="ee60b-112">Exporting to AdRoll is limited to segments.</span></span>
- <span data-ttu-id="ee60b-113">Експортирането на до 250 000 профила в AdRoll може да отнеме до 10 минути.</span><span class="sxs-lookup"><span data-stu-id="ee60b-113">Exporting up to 250,000 profiles to AdRoll can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="ee60b-114">Броят на профилите, които можете да експортирате в AdRoll, зависи от вашия договор с AdRoll.</span><span class="sxs-lookup"><span data-stu-id="ee60b-114">The number of profiles that you can export to AdRoll is dependent on your contract with AdRoll.</span></span>

## <a name="set-up-connection-to-adroll"></a><span data-ttu-id="ee60b-115">Настройване на връзка към AdRoll</span><span class="sxs-lookup"><span data-stu-id="ee60b-115">Set up connection to AdRoll</span></span>

1. <span data-ttu-id="ee60b-116">Отидете на **Администратор** > **Връзки**.</span><span class="sxs-lookup"><span data-stu-id="ee60b-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="ee60b-117">Изберете **Добавяне на връзка** и изберете **AdRoll** за конфигуриране на връзката.</span><span class="sxs-lookup"><span data-stu-id="ee60b-117">Select **Add connection** and choose **AdRoll** to configure the connection.</span></span>

1. <span data-ttu-id="ee60b-118">Въведете разпознаваемо име за връзката в полето **Показвано име**.</span><span class="sxs-lookup"><span data-stu-id="ee60b-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="ee60b-119">Показваното име и типът описват тази връзка.</span><span class="sxs-lookup"><span data-stu-id="ee60b-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="ee60b-120">Препоръчваме да изберете име, което обяснява целта на връзката.</span><span class="sxs-lookup"><span data-stu-id="ee60b-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="ee60b-121">Изберете кой може да използва тази връзка.</span><span class="sxs-lookup"><span data-stu-id="ee60b-121">Choose who can use this connection.</span></span> <span data-ttu-id="ee60b-122">Ако не предприемете нищо, по подразбиране ще е Администратори.</span><span class="sxs-lookup"><span data-stu-id="ee60b-122">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="ee60b-123">За повече информация вижте [Разрешаване на сътрудници да използват връзка за експортиране](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="ee60b-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="ee60b-124">Изберете **Приемам**, за да потвърдите **Поверителност на данните и съответствие**.</span><span class="sxs-lookup"><span data-stu-id="ee60b-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="ee60b-125">Изберете **Свържете** за инициализиране на връзката с AdRoll.</span><span class="sxs-lookup"><span data-stu-id="ee60b-125">Select **Connect** to initialize the connection to AdRoll.</span></span>

1. <span data-ttu-id="ee60b-126">Изберете **Удостоверете с AdRoll** и предоставете вашите идентификационни данни на администратор за AdRoll.</span><span class="sxs-lookup"><span data-stu-id="ee60b-126">Select **Authenticate with AdRoll** and provide your admin credentials for AdRoll.</span></span> 

1. <span data-ttu-id="ee60b-127">Изберете **Добавете себе си като потребител за експортиране** и предоставете вашите идентификационни данни на Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="ee60b-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="ee60b-128">Изберете **Записване**, за да завършите връзката.</span><span class="sxs-lookup"><span data-stu-id="ee60b-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="ee60b-129">Конфигуриране на експортиране</span><span class="sxs-lookup"><span data-stu-id="ee60b-129">Configure an export</span></span>

<span data-ttu-id="ee60b-130">Можете да конфигурирате това експортиране, ако имате достъп до връзка от този тип.</span><span class="sxs-lookup"><span data-stu-id="ee60b-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="ee60b-131">За повече информация вижте [Разрешения, необходими за конфигуриране на експортиране](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="ee60b-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="ee60b-132">Отидете на **Данни** > **Експортиране**.</span><span class="sxs-lookup"><span data-stu-id="ee60b-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="ee60b-133">За да създадете ново експортиране, изберете **Добавяне на местоназначение**.</span><span class="sxs-lookup"><span data-stu-id="ee60b-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="ee60b-134">В полето **Връзка за експортиране** изберете връзка от секцията AdRoll.</span><span class="sxs-lookup"><span data-stu-id="ee60b-134">In the **Connection for export** field, choose a connection from the AdRoll section.</span></span> <span data-ttu-id="ee60b-135">Ако не виждате името на този раздел, тогава няма налични връзки от този тип.</span><span class="sxs-lookup"><span data-stu-id="ee60b-135">If you don't see this section name, then no connections of this type are available to you.</span></span>

1. <span data-ttu-id="ee60b-136">Въведете своя **ИД на рекламодателя на AdRoll**.</span><span class="sxs-lookup"><span data-stu-id="ee60b-136">Enter your **AdRoll Advertiser ID**.</span></span> <span data-ttu-id="ee60b-137">За повече информация вижте [Профили на рекламодатели на AdRoll](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="ee60b-137">For more information, see [AdRoll Advertiser Profiles](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span></span>

3. <span data-ttu-id="ee60b-138">В секцията **Съвпадение на данни** в полето **Имейл** изберете полето във вашия унифициран потребителски профил, което представлява имейл адреса на клиента.</span><span class="sxs-lookup"><span data-stu-id="ee60b-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="ee60b-139">Необходимо е да експортирате сегменти в AdRoll.</span><span class="sxs-lookup"><span data-stu-id="ee60b-139">It's required to export segments to AdRoll.</span></span>

1. <span data-ttu-id="ee60b-140">Изберете сегментите, които искате да експортирате.</span><span class="sxs-lookup"><span data-stu-id="ee60b-140">Select the segments you want to export.</span></span> <span data-ttu-id="ee60b-141">Изберете сегмент с поне 100 членове.</span><span class="sxs-lookup"><span data-stu-id="ee60b-141">Select a segment with a least 100 members.</span></span> <span data-ttu-id="ee60b-142">Не можете да експортирате по-малки сегменти.</span><span class="sxs-lookup"><span data-stu-id="ee60b-142">You can't export smaller segments.</span></span> <span data-ttu-id="ee60b-143">Освен това максималният размер на сегмент за експортиране е 250 000 членове на експортиране.</span><span class="sxs-lookup"><span data-stu-id="ee60b-143">Additionally the maximum size of a segment to export is 250,000 members per export.</span></span> 

1. <span data-ttu-id="ee60b-144">Изберете **Записване**.</span><span class="sxs-lookup"><span data-stu-id="ee60b-144">Select **Save**.</span></span>

<span data-ttu-id="ee60b-145">Запазването на експортиране не го изпълнява незабавно.</span><span class="sxs-lookup"><span data-stu-id="ee60b-145">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="ee60b-146">Експортирането се изпълнява с всяко [планирано обновяване](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="ee60b-146">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> 

<span data-ttu-id="ee60b-147">Може също [да експортирате данни при поискване](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="ee60b-147">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="ee60b-148">Поверителност и съответствие на данните</span><span class="sxs-lookup"><span data-stu-id="ee60b-148">Data privacy and compliance</span></span>

<span data-ttu-id="ee60b-149">Когато активирате Dynamics 365 Customer Insights, за да предавате данни на AdRoll, разрешавате прехвърляне на данни извън границата за съответствие за Dynamics 365 Customer Insights, включително потенциално чувствителни данни като Лични данни.</span><span class="sxs-lookup"><span data-stu-id="ee60b-149">When you enable Dynamics 365 Customer Insights to transmit data to AdRoll, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="ee60b-150">Microsoft ще прехвърли такива данни по ваше указание, но вие носите отговорност да гарантирате, че AdRoll отговаря на всички задължения за поверителност или сигурност, които може да имате.</span><span class="sxs-lookup"><span data-stu-id="ee60b-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that AdRoll meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="ee60b-151">За информация посетете [Декларация за поверителност Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="ee60b-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="ee60b-152">Вашият администратор на Dynamics 365 Customer Insights да премахнете това местоназначение за експортиране по всяко време, за да прекратите използването на тази функционалност.</span><span class="sxs-lookup"><span data-stu-id="ee60b-152">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
