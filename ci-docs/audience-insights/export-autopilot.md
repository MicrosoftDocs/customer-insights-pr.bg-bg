---
title: Експортирайте данните от Customer Insights в Autopilot
description: Научете как да конфигурирате връзката и да експортирате в Autopilot.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e320a48d5b7c35b530e3a38567b226b804879e4e
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760084"
---
# <a name="export-segments-to-autopilot-preview"></a><span data-ttu-id="33d3e-103">Експортиране на сегменти в Autopilot (преглед)</span><span class="sxs-lookup"><span data-stu-id="33d3e-103">Export segments to Autopilot (preview)</span></span>

<span data-ttu-id="33d3e-104">Експортирайте сегменти от унифицирани клиентски профили в Autopilot и ги използвайте за маркетинг по имейл в Autopilot.</span><span class="sxs-lookup"><span data-stu-id="33d3e-104">Export segments of unified customer profiles to Autopilot and use them for email marketing in Autopilot.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="33d3e-105">Предварителни изисквания за връзка</span><span class="sxs-lookup"><span data-stu-id="33d3e-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="33d3e-106">Имате [Акаунт в Autopilot](https://www.autopilothq.com/) и съответните идентификационни данни на администратора.</span><span class="sxs-lookup"><span data-stu-id="33d3e-106">You have an [Autopilot account](https://www.autopilothq.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="33d3e-107">Имате [конфигурирани сегменти](segments.md) в аналитични данни за аудитория.</span><span class="sxs-lookup"><span data-stu-id="33d3e-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="33d3e-108">Единните клиентски профили в експортираните сегменти съдържат поле, представляващо имейл адрес.</span><span class="sxs-lookup"><span data-stu-id="33d3e-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="33d3e-109">Известни ограничения</span><span class="sxs-lookup"><span data-stu-id="33d3e-109">Known limitations</span></span>

- <span data-ttu-id="33d3e-110">Можете да експортирате до 100 000 профила общо в Autopilot.</span><span class="sxs-lookup"><span data-stu-id="33d3e-110">You can export up to 100'000 profiles in total to Autopilot.</span></span>
- <span data-ttu-id="33d3e-111">Експортирането в Autopilot е ограничено до сегменти.</span><span class="sxs-lookup"><span data-stu-id="33d3e-111">Exporting to Autopilot is limited to segments.</span></span>
- <span data-ttu-id="33d3e-112">Експортирането на до 100 000 профила в Autopilot може да отнеме до няколко часа.</span><span class="sxs-lookup"><span data-stu-id="33d3e-112">Exporting up to 100'000 profiles to Autopilot can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="33d3e-113">Броят на профилите, които можете да експортирате в Autopilot, зависи и е ограничен от вашия договор с Autopilot.</span><span class="sxs-lookup"><span data-stu-id="33d3e-113">The number of profiles that you can export to Autopilot is dependent and limited on your contract with Autopilot.</span></span>

## <a name="set-up-connection-to-autopilot"></a><span data-ttu-id="33d3e-114">Настройване на връзката с Autopilot</span><span class="sxs-lookup"><span data-stu-id="33d3e-114">Set up connection to Autopilot</span></span>

1. <span data-ttu-id="33d3e-115">Отидете на **Администратор** > **Връзки**.</span><span class="sxs-lookup"><span data-stu-id="33d3e-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="33d3e-116">Изберете **Добавяне на връзка** и изберете **Autopilot** за конфигуриране на връзката.</span><span class="sxs-lookup"><span data-stu-id="33d3e-116">Select **Add connection** and choose **Autopilot** to configure the connection.</span></span>

1. <span data-ttu-id="33d3e-117">Въведете разпознаваемо име за връзката в полето **Показвано име**.</span><span class="sxs-lookup"><span data-stu-id="33d3e-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="33d3e-118">Показваното име и типът описват тази връзка.</span><span class="sxs-lookup"><span data-stu-id="33d3e-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="33d3e-119">Препоръчваме да изберете име, което обяснява целта на връзката.</span><span class="sxs-lookup"><span data-stu-id="33d3e-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="33d3e-120">Изберете кой може да използва тази връзка.</span><span class="sxs-lookup"><span data-stu-id="33d3e-120">Choose who can use this connection.</span></span> <span data-ttu-id="33d3e-121">Ако не предприемете нищо, по подразбиране ще е Администратори.</span><span class="sxs-lookup"><span data-stu-id="33d3e-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="33d3e-122">За повече информация вижте [Разрешаване на сътрудници да използват връзка за експортиране](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="33d3e-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

3. <span data-ttu-id="33d3e-123">Въведете [ключа за API за Autopilot](https://autopilot.docs.apiary.io/#).</span><span class="sxs-lookup"><span data-stu-id="33d3e-123">Enter your [Autopilot API key](https://autopilot.docs.apiary.io/#).</span></span>

1. <span data-ttu-id="33d3e-124">Изберете **Приемам**, за да потвърдите **Поверителност на данните и съответствие**.</span><span class="sxs-lookup"><span data-stu-id="33d3e-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="33d3e-125">Изберете **Свържете** за инициализиране на връзката с Autopilot.</span><span class="sxs-lookup"><span data-stu-id="33d3e-125">Select **Connect** to initialize the connection to Autopilot.</span></span>

1. <span data-ttu-id="33d3e-126">Изберете **Добавете себе си като потребител за експортиране** и предоставете вашите идентификационни данни на Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="33d3e-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="33d3e-127">Изберете **Записване**, за да завършите връзката.</span><span class="sxs-lookup"><span data-stu-id="33d3e-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="33d3e-128">Конфигуриране на експортиране</span><span class="sxs-lookup"><span data-stu-id="33d3e-128">Configure an export</span></span>

<span data-ttu-id="33d3e-129">Можете да конфигурирате това експортиране, ако имате достъп до връзка от този тип.</span><span class="sxs-lookup"><span data-stu-id="33d3e-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="33d3e-130">За повече информация вижте [Разрешения, необходими за конфигуриране на експортиране](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="33d3e-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="33d3e-131">Отидете на **Данни** > **Експортиране**.</span><span class="sxs-lookup"><span data-stu-id="33d3e-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="33d3e-132">За да създадете ново експортиране, изберете **Добавяне на местоназначение**.</span><span class="sxs-lookup"><span data-stu-id="33d3e-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="33d3e-133">В полето **Връзка за експортиране** изберете връзка от секцията Autopilot.</span><span class="sxs-lookup"><span data-stu-id="33d3e-133">In the **Connection for export** field, choose a connection from the Autopilot section.</span></span> <span data-ttu-id="33d3e-134">Ако не виждате името на тази секция, няма достъпни за вас връзки от този тип.</span><span class="sxs-lookup"><span data-stu-id="33d3e-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

3. <span data-ttu-id="33d3e-135">В секцията **Съвпадение на данни** в полето **Имейл** изберете полето във вашия унифициран потребителски профил, което представлява имейл адреса на клиента.</span><span class="sxs-lookup"><span data-stu-id="33d3e-135">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="33d3e-136">Повторете същите стъпки за други незадължителни полета, като например **собствено име**, **фамилно име**.</span><span class="sxs-lookup"><span data-stu-id="33d3e-136">Repeat the same steps for other optional fields such as **First name**, **Last name**.</span></span>

1. <span data-ttu-id="33d3e-137">Изберете сегментите, които искате да експортирате.</span><span class="sxs-lookup"><span data-stu-id="33d3e-137">Select the segments you want to export.</span></span> <span data-ttu-id="33d3e-138">Ние силно **препоръчваме да не експортирате повече от 100 000 потребителски профила общо** към Autopilot.</span><span class="sxs-lookup"><span data-stu-id="33d3e-138">We strongly **recommend to not export more than 100'000 customer profiles in total** to Autopilot.</span></span> 

1. <span data-ttu-id="33d3e-139">Изберете **Записване**.</span><span class="sxs-lookup"><span data-stu-id="33d3e-139">Select **Save**.</span></span>

<span data-ttu-id="33d3e-140">Запазването на експортиране не го изпълнява незабавно.</span><span class="sxs-lookup"><span data-stu-id="33d3e-140">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="33d3e-141">Експортирането се изпълнява с всяко [планирано обновяване](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="33d3e-141">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="33d3e-142">Може също [да експортирате данни при поискване](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="33d3e-142">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="33d3e-143">Поверителност и съответствие на данните</span><span class="sxs-lookup"><span data-stu-id="33d3e-143">Data privacy and compliance</span></span>

<span data-ttu-id="33d3e-144">Когато активирате Dynamics 365 Customer Insights, за да предавате данни на Autopilot, разрешавате прехвърляне на данни извън границата за съответствие за Dynamics 365 Customer Insights, включително потенциално чувствителни данни като Лични данни.</span><span class="sxs-lookup"><span data-stu-id="33d3e-144">When you enable Dynamics 365 Customer Insights to transmit data to Autopilot, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="33d3e-145">Microsoft ще прехвърли такива данни по ваше указание, но вие носите отговорност да гарантирате, че Autopilot отговаря на всички задължения за поверителност или сигурност, които може да имате.</span><span class="sxs-lookup"><span data-stu-id="33d3e-145">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Autopilot meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="33d3e-146">За информация посетете [Декларация за поверителност Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="33d3e-146">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="33d3e-147">Вашият администратор на Dynamics 365 Customer Insights да премахнете това местоназначение за експортиране по всяко време, за да прекратите използването на тази функционалност.</span><span class="sxs-lookup"><span data-stu-id="33d3e-147">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
