---
title: Експортиране на данни на Customer Insights в Constant Contact
description: Научете как да конфигурирате връзката и да експортирате в Constant Contact.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 29f4320c798db62609283e3c48f0b47a4f0b982f
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124260"
---
# <a name="export-segments-to-constant-contact-preview"></a><span data-ttu-id="9f60b-103">Експортиране на сегменти в Constant Contact (преглед)</span><span class="sxs-lookup"><span data-stu-id="9f60b-103">Export segments to Constant Contact (preview)</span></span>

<span data-ttu-id="9f60b-104">Експортирайте сегменти от унифицирани клиентски профили в Constant Contact и ги използвайте за маркетингови дейности.</span><span class="sxs-lookup"><span data-stu-id="9f60b-104">Export segments of unified customer profiles to Constant Contact and use them for marketing activities.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="9f60b-105">Предварителни изисквания за връзка</span><span class="sxs-lookup"><span data-stu-id="9f60b-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="9f60b-106">Имате [акаунт в Constant Contact](https://www.constantcontact.com/account-home) и съответните идентификационни данни на администратор.</span><span class="sxs-lookup"><span data-stu-id="9f60b-106">You have an [Constant Contact account](https://www.constantcontact.com/account-home) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="9f60b-107">Имате [конфигурирани сегменти](segments.md) в аналитични данни за аудитория.</span><span class="sxs-lookup"><span data-stu-id="9f60b-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="9f60b-108">Единните клиентски профили в експортираните сегменти съдържат поле, представляващо имейл адрес.</span><span class="sxs-lookup"><span data-stu-id="9f60b-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="9f60b-109">Известни ограничения</span><span class="sxs-lookup"><span data-stu-id="9f60b-109">Known limitations</span></span>

- <span data-ttu-id="9f60b-110">Можете да експортирате до 1 милион профила с всяко експортиране в Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="9f60b-110">You can export up to 1 million profiles per export to Constant Contact.</span></span>
- <span data-ttu-id="9f60b-111">Експортирането в Constant Contact е ограничено до сегменти.</span><span class="sxs-lookup"><span data-stu-id="9f60b-111">Exporting to Constant Contact is limited to segments.</span></span>
- <span data-ttu-id="9f60b-112">Експортирането на до 1 милион профила в Constant Contact може да отнеме до 1 час.</span><span class="sxs-lookup"><span data-stu-id="9f60b-112">Exporting up to 1 million profiles to Constant Contact can take up to 1 hour to complete.</span></span> 
- <span data-ttu-id="9f60b-113">Броят на профилите, които можете да експортирате в Constant Contact, зависи и е ограничен от вашия договор с Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="9f60b-113">The number of profiles that you can export to Constant Contact is dependent and limited on your contract with Constant Contact.</span></span>

## <a name="set-up-connection-to-constant-contact"></a><span data-ttu-id="9f60b-114">Задаване на връзка с Constant Contact</span><span class="sxs-lookup"><span data-stu-id="9f60b-114">Set up connection to Constant Contact</span></span>

1. <span data-ttu-id="9f60b-115">Отидете на **Администратор** > **Връзки**.</span><span class="sxs-lookup"><span data-stu-id="9f60b-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="9f60b-116">Изберете **Добавяне на връзка** и изберете **Constant Contact** за конфигуриране на връзката.</span><span class="sxs-lookup"><span data-stu-id="9f60b-116">Select **Add connection** and choose **Constant Contact** to configure the connection.</span></span>

1. <span data-ttu-id="9f60b-117">Въведете разпознаваемо име за връзката в полето **Показвано име**.</span><span class="sxs-lookup"><span data-stu-id="9f60b-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="9f60b-118">Показваното име и типът описват тази връзка.</span><span class="sxs-lookup"><span data-stu-id="9f60b-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="9f60b-119">Препоръчваме да изберете име, което обяснява целта на връзката.</span><span class="sxs-lookup"><span data-stu-id="9f60b-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="9f60b-120">Изберете кой може да използва тази връзка.</span><span class="sxs-lookup"><span data-stu-id="9f60b-120">Choose who can use this connection.</span></span> <span data-ttu-id="9f60b-121">Ако не предприемете нищо, по подразбиране ще е Администратори.</span><span class="sxs-lookup"><span data-stu-id="9f60b-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="9f60b-122">За повече информация вижте [Разрешаване на сътрудници да използват връзка за експортиране](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="9f60b-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="9f60b-123">Изберете **Приемам**, за да потвърдите **Поверителност на данните и съответствие**.</span><span class="sxs-lookup"><span data-stu-id="9f60b-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="9f60b-124">Изберете **Свързване** за инициализиране на връзката с Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="9f60b-124">Select **Connect** to initialize the connection to Constant Contact.</span></span>

1. <span data-ttu-id="9f60b-125">Изберете **Удостоверяване с AdRoll** и предоставете администраторските си данни за Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="9f60b-125">Select **Authenticate with AdRoll** and provide your admin credentials for Constant Contact.</span></span> 

1. <span data-ttu-id="9f60b-126">Изберете **Добавете себе си като потребител за експортиране** и предоставете вашите идентификационни данни на Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="9f60b-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="9f60b-127">Изберете **Записване**, за да завършите връзката.</span><span class="sxs-lookup"><span data-stu-id="9f60b-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="9f60b-128">Конфигуриране на експортиране</span><span class="sxs-lookup"><span data-stu-id="9f60b-128">Configure an export</span></span>

<span data-ttu-id="9f60b-129">Можете да конфигурирате това експортиране, ако имате достъп до връзка от този тип.</span><span class="sxs-lookup"><span data-stu-id="9f60b-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="9f60b-130">За повече информация вижте [Разрешения, необходими за конфигуриране на експортиране](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="9f60b-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="9f60b-131">Отидете на **Данни** > **Експортиране**.</span><span class="sxs-lookup"><span data-stu-id="9f60b-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="9f60b-132">За да създадете ново експортиране, изберете **Добавяне на местоназначение**.</span><span class="sxs-lookup"><span data-stu-id="9f60b-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="9f60b-133">В полето **Връзка за експортиране** изберете връзка от секцията Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="9f60b-133">In the **Connection for export** field, choose a connection from the Constant Contact section.</span></span> <span data-ttu-id="9f60b-134">Ако не виждате името на тази секция, няма достъпни за вас връзки от този тип.</span><span class="sxs-lookup"><span data-stu-id="9f60b-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="9f60b-135">Въведете [**ИД на списък в Constant Contact**](https://app.constantcontact.com/pages/contacts/ui#lists).</span><span class="sxs-lookup"><span data-stu-id="9f60b-135">Enter your [**Constant Contact List ID**](https://app.constantcontact.com/pages/contacts/ui#lists).</span></span> <span data-ttu-id="9f60b-136">Отворете списък в Constant Contact, за да намерите ИД на списъка в URL адреса.</span><span class="sxs-lookup"><span data-stu-id="9f60b-136">Open a list in Constant Contact to find the list ID in the URL.</span></span>

1. <span data-ttu-id="9f60b-137">В секцията **Съвпадение на данни** в полето **Имейл** изберете полето във вашия унифициран потребителски профил, което представлява имейл адреса на клиента.</span><span class="sxs-lookup"><span data-stu-id="9f60b-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="9f60b-138">Необходимо е да експортирате сегменти в Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="9f60b-138">It's required to export segments to Constant Contact.</span></span>

1. <span data-ttu-id="9f60b-139">По желание можете да експортирате Собствено име и Фамилно име като допълнителни полета за създаване на по-персонализирани имейли.</span><span class="sxs-lookup"><span data-stu-id="9f60b-139">Optionally, you can export First name and Last name as additional fields to create more personalized emails.</span></span> <span data-ttu-id="9f60b-140">Изберете **Добавяне на атрибут** за нанасяне на тези полета.</span><span class="sxs-lookup"><span data-stu-id="9f60b-140">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="9f60b-141">Изберете сегментите, които искате да експортирате.</span><span class="sxs-lookup"><span data-stu-id="9f60b-141">Select the segments you want to export.</span></span>

1. <span data-ttu-id="9f60b-142">Изберете **Записване**.</span><span class="sxs-lookup"><span data-stu-id="9f60b-142">Select **Save**.</span></span>

<span data-ttu-id="9f60b-143">Запазването на експортиране не го изпълнява незабавно.</span><span class="sxs-lookup"><span data-stu-id="9f60b-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="9f60b-144">Експортирането се изпълнява с всяко [планирано обновяване](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="9f60b-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="9f60b-145">Може също [да експортирате данни при поискване](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="9f60b-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="9f60b-146">Поверителност и съответствие на данните</span><span class="sxs-lookup"><span data-stu-id="9f60b-146">Data privacy and compliance</span></span>

<span data-ttu-id="9f60b-147">Когато активирате Dynamics 365 Customer Insights, за да предавате данни към Constant Contact, разрешавате прехвърляне на данни извън границата на съответствие на Dynamics 365 Customer Insights, включително потенциално чувствителни данни като лични данни.</span><span class="sxs-lookup"><span data-stu-id="9f60b-147">When you enable Dynamics 365 Customer Insights to transmit data to Constant Contact, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="9f60b-148">Microsoft ще предава такива данни по ваше разпореждане, но вие носите отговорност да гарантирате, че Constant Contact спазва задълженията за поверителност и сигурност, които може да имате.</span><span class="sxs-lookup"><span data-stu-id="9f60b-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Constant Contact meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="9f60b-149">За информация посетете [Декларация за поверителност Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="9f60b-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="9f60b-150">Вашият администратор на Dynamics 365 Customer Insights да премахнете това местоназначение за експортиране по всяко време, за да прекратите използването на тази функционалност.</span><span class="sxs-lookup"><span data-stu-id="9f60b-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
