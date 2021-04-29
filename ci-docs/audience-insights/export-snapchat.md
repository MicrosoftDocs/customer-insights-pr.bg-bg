---
title: Експортиране на данни на Customer Insights в Snapchat
description: Научете как да конфигурирате връзката и да експортирате в Snapchat.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d3dae7f0fef1fc3792c90c8ac0d3b037f5c0923d
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760470"
---
# <a name="export-segment-lists-to-snapchat-preview"></a><span data-ttu-id="bc30e-103">Експортиране на списъци със сегменти в Snapchat (преглед)</span><span class="sxs-lookup"><span data-stu-id="bc30e-103">Export segment lists to Snapchat (preview)</span></span>

<span data-ttu-id="bc30e-104">Експортирайте сегменти от унифицирани клиентски профили в Snapchat и ги използвайте за реклама.</span><span class="sxs-lookup"><span data-stu-id="bc30e-104">Export segments of unified customer profiles to Snapchat and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="bc30e-105">Предварителни изисквания за връзка</span><span class="sxs-lookup"><span data-stu-id="bc30e-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="bc30e-106">Имате [бизнес акаунт в Snapchat](https://business.snapchat.com/), [акаунт в Snapchat Ads](https://ads.snapchat.com/) и съответните идентификационни данни на администратор.</span><span class="sxs-lookup"><span data-stu-id="bc30e-106">You have a [Snapchat Business account](https://business.snapchat.com/), a [Snapchat Ads account](https://ads.snapchat.com/), and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="bc30e-107">Имате [конфигурирани сегменти](segments.md) в аналитични данни за аудитория.</span><span class="sxs-lookup"><span data-stu-id="bc30e-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="bc30e-108">Единните клиентски профили в експортираните сегменти съдържат поле, представляващо имейл адрес.</span><span class="sxs-lookup"><span data-stu-id="bc30e-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="bc30e-109">Известни ограничения</span><span class="sxs-lookup"><span data-stu-id="bc30e-109">Known limitations</span></span>

- <span data-ttu-id="bc30e-110">Експортирането в Snapchat е ограничено до сегменти.</span><span class="sxs-lookup"><span data-stu-id="bc30e-110">Exporting to Snapchat is limited to segments.</span></span>
- <span data-ttu-id="bc30e-111">Експортирането на до 1 милион профила в Snapchat може да отнеме до 15 минути.</span><span class="sxs-lookup"><span data-stu-id="bc30e-111">Exporting up to 1 million profiles to Snapchat can take up to 15 minutes to complete.</span></span> 

## <a name="set-up-connection-to-snapchat"></a><span data-ttu-id="bc30e-112">Настройване на връзка към Snapchat</span><span class="sxs-lookup"><span data-stu-id="bc30e-112">Set up connection to Snapchat</span></span>

1. <span data-ttu-id="bc30e-113">Отидете на **Администратор** > **Връзки**.</span><span class="sxs-lookup"><span data-stu-id="bc30e-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="bc30e-114">Изберете **Добавяне на връзка** и изберете **Snapchat** за конфигуриране на връзката.</span><span class="sxs-lookup"><span data-stu-id="bc30e-114">Select **Add connection** and choose **Snapchat** to configure the connection.</span></span>

1. <span data-ttu-id="bc30e-115">Въведете разпознаваемо име за връзката в полето **Показвано име**.</span><span class="sxs-lookup"><span data-stu-id="bc30e-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="bc30e-116">Показваното име и типът описват тази връзка.</span><span class="sxs-lookup"><span data-stu-id="bc30e-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="bc30e-117">Препоръчваме да изберете име, което обяснява целта на връзката.</span><span class="sxs-lookup"><span data-stu-id="bc30e-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="bc30e-118">Изберете кой може да използва тази връзка.</span><span class="sxs-lookup"><span data-stu-id="bc30e-118">Choose who can use this connection.</span></span> <span data-ttu-id="bc30e-119">Ако не предприемете нищо, по подразбиране ще е Администратори.</span><span class="sxs-lookup"><span data-stu-id="bc30e-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="bc30e-120">За повече информация вижте [Разрешаване на сътрудници да използват връзка за експортиране](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="bc30e-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="bc30e-121">Изберете **Приемам**, за да потвърдите **Поверителност на данните и съответствие**.</span><span class="sxs-lookup"><span data-stu-id="bc30e-121">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="bc30e-122">Изберете **Свързване** за инициализиране на връзката със Snapchat.</span><span class="sxs-lookup"><span data-stu-id="bc30e-122">Select **Connect** to initialize the connection to Snapchat.</span></span>

1. <span data-ttu-id="bc30e-123">Изберете **Удостоверяване със Snapchat** и предоставете администраторските си данни за Snapchat.</span><span class="sxs-lookup"><span data-stu-id="bc30e-123">Select **Authenticate with Snapchat** and provide your admin credentials for Snapchat.</span></span> 

1. <span data-ttu-id="bc30e-124">Изберете **Добавете себе си като потребител за експортиране** и предоставете вашите идентификационни данни на Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="bc30e-124">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="bc30e-125">Изберете **Записване**, за да завършите връзката.</span><span class="sxs-lookup"><span data-stu-id="bc30e-125">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="bc30e-126">Конфигуриране на експортиране</span><span class="sxs-lookup"><span data-stu-id="bc30e-126">Configure an export</span></span>

<span data-ttu-id="bc30e-127">Можете да конфигурирате това експортиране, ако имате достъп до връзка от този тип.</span><span class="sxs-lookup"><span data-stu-id="bc30e-127">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="bc30e-128">За повече информация вижте [Разрешения, необходими за конфигуриране на експортиране](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="bc30e-128">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="bc30e-129">Отидете на **Данни** > **Експортиране**.</span><span class="sxs-lookup"><span data-stu-id="bc30e-129">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="bc30e-130">За да създадете ново експортиране, изберете **Добавяне на местоназначение**.</span><span class="sxs-lookup"><span data-stu-id="bc30e-130">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="bc30e-131">В полето **Връзка за експортиране** изберете връзка от секцията Snapchat.</span><span class="sxs-lookup"><span data-stu-id="bc30e-131">In the **Connection for export** field, choose a connection from the Snapchat section.</span></span> <span data-ttu-id="bc30e-132">Ако не виждате името на тази секция, няма достъпни за вас връзки от този тип.</span><span class="sxs-lookup"><span data-stu-id="bc30e-132">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="bc30e-133">Влезте в [**ИД на аудитория на Snapchat**](https://businesshelp.snapchat.com/s/article/custom-audiences).</span><span class="sxs-lookup"><span data-stu-id="bc30e-133">Enter the [**Snapchat Audience ID**](https://businesshelp.snapchat.com/s/article/custom-audiences).</span></span>

1. <span data-ttu-id="bc30e-134">В секцията **Съвпадение на данни** в полето **Имейл** изберете полето във вашия унифициран потребителски профил, което представлява имейл адреса на клиента.</span><span class="sxs-lookup"><span data-stu-id="bc30e-134">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="bc30e-135">Необходимо е да експортирате сегменти в Snapchat.</span><span class="sxs-lookup"><span data-stu-id="bc30e-135">It's required to export segments to Snapchat.</span></span>

1. <span data-ttu-id="bc30e-136">Изберете сегментите, които искате да експортирате.</span><span class="sxs-lookup"><span data-stu-id="bc30e-136">Select the segments you want to export.</span></span> 

1. <span data-ttu-id="bc30e-137">Изберете **Записване**.</span><span class="sxs-lookup"><span data-stu-id="bc30e-137">Select **Save**.</span></span>

<span data-ttu-id="bc30e-138">Запазването на експортиране не го изпълнява незабавно.</span><span class="sxs-lookup"><span data-stu-id="bc30e-138">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="bc30e-139">Експортирането се изпълнява с всяко [планирано обновяване](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="bc30e-139">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="bc30e-140">Може също [да експортирате данни при поискване](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="bc30e-140">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="bc30e-141">Поверителност и съответствие на данните</span><span class="sxs-lookup"><span data-stu-id="bc30e-141">Data privacy and compliance</span></span>

<span data-ttu-id="bc30e-142">Когато активирате Dynamics 365 Customer Insights, за да предавате данни към Snapchat, разрешавате прехвърляне на данни извън границата на съответствие на Dynamics 365 Customer Insights, включително потенциално чувствителни данни като лични данни.</span><span class="sxs-lookup"><span data-stu-id="bc30e-142">When you enable Dynamics 365 Customer Insights to transmit data to Snapchat, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="bc30e-143">Microsoft ще предава такива данни по ваше разпореждане, но вие носите отговорност да гарантирате, че Snapchat спазва задълженията за поверителност и сигурност, които може да имате.</span><span class="sxs-lookup"><span data-stu-id="bc30e-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Snapchat meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="bc30e-144">За информация посетете [Декларация за поверителност Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="bc30e-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="bc30e-145">Вашият администратор на Dynamics 365 Customer Insights да премахнете това местоназначение за експортиране по всяко време, за да прекратите използването на тази функционалност.</span><span class="sxs-lookup"><span data-stu-id="bc30e-145">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
