---
title: Експортиране на данни на Customer Insights в RollWorks
description: Научете как да конфигурирате връзката и да експортирате в RollWorks.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: dce5d51ca4587b4d7a0644cc701c1826854882b5
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124076"
---
# <a name="export-segments-to-rollworks-preview"></a><span data-ttu-id="56c98-103">Експортиране на сегменти в RollWorks (преглед)</span><span class="sxs-lookup"><span data-stu-id="56c98-103">Export segments to RollWorks (preview)</span></span>

<span data-ttu-id="56c98-104">Експортирайте сегменти от унифицирани клиентски профили в RollWorks и ги използвайте за реклама.</span><span class="sxs-lookup"><span data-stu-id="56c98-104">Export segments of unified customer profiles to RollWorks and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="56c98-105">Предварителни изисквания за връзка</span><span class="sxs-lookup"><span data-stu-id="56c98-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="56c98-106">Имате [акаунт в RollWorks](https://www.rollworks.com/) и съответните идентификационни данни на администратор.</span><span class="sxs-lookup"><span data-stu-id="56c98-106">You have an [RollWorks account](https://www.rollworks.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="56c98-107">Имате [конфигурирани сегменти](segments.md) в аналитични данни за аудитория.</span><span class="sxs-lookup"><span data-stu-id="56c98-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="56c98-108">Единните клиентски профили в експортираните сегменти съдържат поле, представляващо имейл адрес.</span><span class="sxs-lookup"><span data-stu-id="56c98-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="56c98-109">Известни ограничения</span><span class="sxs-lookup"><span data-stu-id="56c98-109">Known limitations</span></span>

- <span data-ttu-id="56c98-110">Можете да експортирате до 250 000 профила с всяко експортиране в RollWorks.</span><span class="sxs-lookup"><span data-stu-id="56c98-110">You can export up to 250'000 profiles in per export to RollWorks.</span></span>
- <span data-ttu-id="56c98-111">Не можете да експортирате сегменти с по-малко от 100 профила в RollWorks.</span><span class="sxs-lookup"><span data-stu-id="56c98-111">You can't export segments with fewer than 100 profiles to RollWorks.</span></span> 
- <span data-ttu-id="56c98-112">Експортирането в RollWorks е ограничено до сегменти.</span><span class="sxs-lookup"><span data-stu-id="56c98-112">Exporting to RollWorks is limited to segments.</span></span>
- <span data-ttu-id="56c98-113">Експортирането на до 250 000 профила в RollWorks може да отнеме до 10 минути.</span><span class="sxs-lookup"><span data-stu-id="56c98-113">Exporting up to 250'000 profiles to RollWorks can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="56c98-114">Броят на профилите, които можете да експортирате в RollWorks, зависи и е ограничен от вашия договор с RollWorks.</span><span class="sxs-lookup"><span data-stu-id="56c98-114">The number of profiles that you can export to RollWorks is dependent and limited on your contract with RollWorks.</span></span>

## <a name="set-up-connection-to-rollworks"></a><span data-ttu-id="56c98-115">Настройване на връзката с RollWorks</span><span class="sxs-lookup"><span data-stu-id="56c98-115">Set up connection to RollWorks</span></span>

1. <span data-ttu-id="56c98-116">Отидете на **Администратор** > **Връзки**.</span><span class="sxs-lookup"><span data-stu-id="56c98-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="56c98-117">Изберете **Добавяне на връзка** и изберете **RollWorks** за конфигуриране на връзката.</span><span class="sxs-lookup"><span data-stu-id="56c98-117">Select **Add connection** and choose **RollWorks** to configure the connection.</span></span>

1. <span data-ttu-id="56c98-118">Въведете разпознаваемо име за връзката в полето **Показвано име**.</span><span class="sxs-lookup"><span data-stu-id="56c98-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="56c98-119">Показваното име и типът описват тази връзка.</span><span class="sxs-lookup"><span data-stu-id="56c98-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="56c98-120">Препоръчваме да изберете име, което обяснява целта на връзката.</span><span class="sxs-lookup"><span data-stu-id="56c98-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="56c98-121">Изберете кой може да използва тази връзка.</span><span class="sxs-lookup"><span data-stu-id="56c98-121">Choose who can use this connection.</span></span> <span data-ttu-id="56c98-122">Ако не предприемете нищо, по подразбиране ще е Администратори.</span><span class="sxs-lookup"><span data-stu-id="56c98-122">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="56c98-123">За повече информация вижте [Разрешаване на сътрудници да използват връзка за експортиране](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="56c98-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="56c98-124">Изберете **Приемам**, за да потвърдите **Поверителност на данните и съответствие**.</span><span class="sxs-lookup"><span data-stu-id="56c98-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="56c98-125">Изберете **Свързване** за инициализиране на връзката с RollWorks.</span><span class="sxs-lookup"><span data-stu-id="56c98-125">Select **Connect** to initialize the connection to RollWorks.</span></span>

1. <span data-ttu-id="56c98-126">Изберете **Удостоверяване с RollWorks** и предоставете администраторските си данни за RollWorks.</span><span class="sxs-lookup"><span data-stu-id="56c98-126">Select **Authenticate with RollWorks** and provide your admin credentials for RollWorks.</span></span>

1. <span data-ttu-id="56c98-127">Изберете **Добавете себе си като потребител за експортиране** и предоставете вашите идентификационни данни на Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="56c98-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="56c98-128">Изберете **Записване**, за да завършите връзката.</span><span class="sxs-lookup"><span data-stu-id="56c98-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="56c98-129">Конфигуриране на експортиране</span><span class="sxs-lookup"><span data-stu-id="56c98-129">Configure an export</span></span>

<span data-ttu-id="56c98-130">Можете да конфигурирате това експортиране, ако имате достъп до връзка от този тип.</span><span class="sxs-lookup"><span data-stu-id="56c98-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="56c98-131">За повече информация вижте [Разрешения, необходими за конфигуриране на експортиране](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="56c98-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="56c98-132">Отидете на **Данни** > **Експортиране**.</span><span class="sxs-lookup"><span data-stu-id="56c98-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="56c98-133">За да създадете ново експортиране, изберете **Добавяне на местоназначение**.</span><span class="sxs-lookup"><span data-stu-id="56c98-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="56c98-134">В полето **Връзка за експортиране** изберете връзка от секцията RollWorks.</span><span class="sxs-lookup"><span data-stu-id="56c98-134">In the **Connection for export** field, choose a connection from the RollWorks section.</span></span> <span data-ttu-id="56c98-135">Ако не виждате името на тази секция, няма достъпни за вас връзки от този тип.</span><span class="sxs-lookup"><span data-stu-id="56c98-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="56c98-136">Въведете **ИД на рекламодател в RollWorks** [Възможност за реклами в RollWorks](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="56c98-136">Enter your **RollWorks Advertiser ID** [RollWorks Advertisable](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span></span>

3. <span data-ttu-id="56c98-137">В секцията **Съвпадение на данни** в полето **Имейл** изберете полето във вашия унифициран потребителски профил, което представлява имейл адреса на клиента.</span><span class="sxs-lookup"><span data-stu-id="56c98-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="56c98-138">Необходимо е да експортирате сегменти в RollWorks.</span><span class="sxs-lookup"><span data-stu-id="56c98-138">It's required to export segments to RollWorks.</span></span>

1. <span data-ttu-id="56c98-139">Изберете сегментите, които искате да експортирате.</span><span class="sxs-lookup"><span data-stu-id="56c98-139">Select the segments you want to export.</span></span> <span data-ttu-id="56c98-140">Изберете сегмент с поне 100 членове.</span><span class="sxs-lookup"><span data-stu-id="56c98-140">Select a segment with a least 100 members.</span></span> <span data-ttu-id="56c98-141">Не можете да експортирате по-малки сегменти.</span><span class="sxs-lookup"><span data-stu-id="56c98-141">You can't export smaller segments.</span></span> <span data-ttu-id="56c98-142">Освен това максималният размер на сегмент за експортиране е 250 000 членове на експортиране.</span><span class="sxs-lookup"><span data-stu-id="56c98-142">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="56c98-143">Изберете **Записване**.</span><span class="sxs-lookup"><span data-stu-id="56c98-143">Select **Save**.</span></span>

<span data-ttu-id="56c98-144">Запазването на експортиране не го изпълнява незабавно.</span><span class="sxs-lookup"><span data-stu-id="56c98-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="56c98-145">Експортирането се изпълнява с всяко [планирано обновяване](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="56c98-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="56c98-146">Може също [да експортирате данни при поискване](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="56c98-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="56c98-147">Поверителност и съответствие на данните</span><span class="sxs-lookup"><span data-stu-id="56c98-147">Data privacy and compliance</span></span>

<span data-ttu-id="56c98-148">Когато активирате Dynamics 365 Customer Insights, за да предавате данни към RollWorks, разрешавате прехвърляне на данни извън границата на съответствие на Dynamics 365 Customer Insights, включително потенциално чувствителни данни като лични данни.</span><span class="sxs-lookup"><span data-stu-id="56c98-148">When you enable Dynamics 365 Customer Insights to transmit data to RollWorks, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="56c98-149">Microsoft ще предава такива данни по ваше разпореждане, но вие носите отговорност да гарантирате, че RollWorks спазва задълженията за поверителност и сигурност, които може да имате.</span><span class="sxs-lookup"><span data-stu-id="56c98-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that RollWorks meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="56c98-150">За информация посетете [Декларация за поверителност Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="56c98-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="56c98-151">Вашият администратор на Dynamics 365 Customer Insights да премахнете това местоназначение за експортиране по всяко време, за да прекратите използването на тази функционалност.</span><span class="sxs-lookup"><span data-stu-id="56c98-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
