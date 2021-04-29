---
title: Експортирайте данните от Customer Insights в Mailchimp
description: Научете как да конфигурирате връзката и да експортирате в Mailchimp.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b94a8e8b6bb867ca04a64007d592b22fbd700618
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759865"
---
# <a name="export-segment-lists-to-mailchimp-preview"></a><span data-ttu-id="bcc62-103">Експортиране на списъци със сегменти в Mailchimp (преглед)</span><span class="sxs-lookup"><span data-stu-id="bcc62-103">Export segment lists to Mailchimp (preview)</span></span>

<span data-ttu-id="bcc62-104">Експортирайте сегменти от унифицирани клиентски профили в Mailchimp, за да създавате бюлетини и имейл кампании.</span><span class="sxs-lookup"><span data-stu-id="bcc62-104">Export segments of unified customer profiles to Mailchimp to create newsletters and email campaigns.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="bcc62-105">Предварителни изисквания за връзка</span><span class="sxs-lookup"><span data-stu-id="bcc62-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="bcc62-106">Имате [Акаунт в Mailchimp](https://mailchimp.com/) и съответните идентификационни данни на администратора.</span><span class="sxs-lookup"><span data-stu-id="bcc62-106">You have a [Mailchimp account](https://mailchimp.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="bcc62-107">В Mailchimp има съществуващи аудитории и съответните идентификатори.</span><span class="sxs-lookup"><span data-stu-id="bcc62-107">There are existing audiences in Mailchimp and the corresponding IDs.</span></span> <span data-ttu-id="bcc62-108">За повече информация вижте [Аудитории на Mailchimp](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="bcc62-108">For more information, see [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>
-   <span data-ttu-id="bcc62-109">Имате [конфигурирани сегменти](segments.md)</span><span class="sxs-lookup"><span data-stu-id="bcc62-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="bcc62-110">Единните клиентски профили в експортираните сегменти съдържат поле, представляващо имейл адрес.</span><span class="sxs-lookup"><span data-stu-id="bcc62-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="bcc62-111">Известни ограничения</span><span class="sxs-lookup"><span data-stu-id="bcc62-111">Known limitations</span></span>

- <span data-ttu-id="bcc62-112">До 1 милион профила на износ към Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="bcc62-112">Up to 1 million profiles per export to Mailchimp.</span></span>
- <span data-ttu-id="bcc62-113">Експортирането в Mailchimp е ограничено до сегменти.</span><span class="sxs-lookup"><span data-stu-id="bcc62-113">Exporting to Mailchimp is limited to segments.</span></span>
- <span data-ttu-id="bcc62-114">Експортирането на сегменти с 1 милион профила може да отнеме до три часа.</span><span class="sxs-lookup"><span data-stu-id="bcc62-114">Exporting segments with 1 million profiles can take up to three hours.</span></span> 
- <span data-ttu-id="bcc62-115">Броят на профилите, които можете да експортирате в Mailchimp, зависи и е ограничен от вашия договор с Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="bcc62-115">The number of profiles that you can export to Mailchimp is dependent and limited on your contract with Mailchimp.</span></span>

## <a name="set-up-connection-to-mailchimp"></a><span data-ttu-id="bcc62-116">Настройване на връзката с Mailchimp</span><span class="sxs-lookup"><span data-stu-id="bcc62-116">Set up connection to Mailchimp</span></span>

1. <span data-ttu-id="bcc62-117">Отидете на **Администратор** > **Връзки**.</span><span class="sxs-lookup"><span data-stu-id="bcc62-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="bcc62-118">Изберете **Добавяне на връзка** и изберете **Autopilot** за конфигуриране на връзката.</span><span class="sxs-lookup"><span data-stu-id="bcc62-118">Select **Add connection** and choose **Autopilot** to configure the connection.</span></span>

1. <span data-ttu-id="bcc62-119">Въведете разпознаваемо име за връзката в полето **Показвано име**.</span><span class="sxs-lookup"><span data-stu-id="bcc62-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="bcc62-120">Показваното име и типът описват тази връзка.</span><span class="sxs-lookup"><span data-stu-id="bcc62-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="bcc62-121">Препоръчваме да изберете име, което обяснява целта на връзката.</span><span class="sxs-lookup"><span data-stu-id="bcc62-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="bcc62-122">Изберете кой може да използва тази връзка.</span><span class="sxs-lookup"><span data-stu-id="bcc62-122">Choose who can use this connection.</span></span> <span data-ttu-id="bcc62-123">Ако не предприемете нищо, по подразбиране ще е Администратори.</span><span class="sxs-lookup"><span data-stu-id="bcc62-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="bcc62-124">За повече информация вижте [Разрешаване на сътрудници да използват връзка за експортиране](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="bcc62-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="bcc62-125">Изберете **Приемам**, за да потвърдите **Поверителност на данните и съответствие**.</span><span class="sxs-lookup"><span data-stu-id="bcc62-125">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="bcc62-126">Изберете **Свързване** за инициализиране на връзката с Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="bcc62-126">Select **Connect** to initialize the connection to Mailchimp.</span></span>

1. <span data-ttu-id="bcc62-127">Изберете **Удостоверете с Mailchimp** и предоставете вашите идентификационни данни на Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="bcc62-127">Select **Authenticate with Mailchimp** and provide your Mailchimp credentials.</span></span>

1. <span data-ttu-id="bcc62-128">Изберете **Добавете себе си като потребител за експортиране** и предоставете вашите идентификационни данни на Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="bcc62-128">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="bcc62-129">Изберете **Записване**, за да завършите връзката.</span><span class="sxs-lookup"><span data-stu-id="bcc62-129">Select **Save** to complete the connection.</span></span> 

## <a name="configure-the-connector"></a><span data-ttu-id="bcc62-130">Конфигуриране на конектор</span><span class="sxs-lookup"><span data-stu-id="bcc62-130">Configure the connector</span></span>

<span data-ttu-id="bcc62-131">Можете да конфигурирате това експортиране, ако имате достъп до връзка от този тип.</span><span class="sxs-lookup"><span data-stu-id="bcc62-131">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="bcc62-132">За повече информация вижте [Разрешения, необходими за конфигуриране на експортиране](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="bcc62-132">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="bcc62-133">Отидете на **Данни**> **Експортиране**.</span><span class="sxs-lookup"><span data-stu-id="bcc62-133">Go to **Data**> **Exports**.</span></span>

1. <span data-ttu-id="bcc62-134">За да създадете ново експортиране, изберете **Добавяне на местоназначение**.</span><span class="sxs-lookup"><span data-stu-id="bcc62-134">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="bcc62-135">В полето **Връзка за експортиране** изберете връзка от секцията Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="bcc62-135">In the **Connection for export** field, choose a connection from the Mailchimp section.</span></span> <span data-ttu-id="bcc62-136">Ако не виждате името на тази секция, няма достъпни за вас връзки от този тип.</span><span class="sxs-lookup"><span data-stu-id="bcc62-136">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="bcc62-137">Въведете **[ИД на аудитория на Mailchimp](https://mailchimp.com/help/find-audience-id/)**</span><span class="sxs-lookup"><span data-stu-id="bcc62-137">Enter your **[Mailchimp audience ID](https://mailchimp.com/help/find-audience-id/)**</span></span>

3. <span data-ttu-id="bcc62-138">В секцията **Съвпадение на данни** в полето **Имейл** изберете полето във вашия унифициран потребителски профил, което представлява имейл адреса на клиента.</span><span class="sxs-lookup"><span data-stu-id="bcc62-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="bcc62-139">По желание можете да експортирате **Собствено име** и **Фамилно име** за създаване на по-персонализирани имейли.</span><span class="sxs-lookup"><span data-stu-id="bcc62-139">Optionally, you can export **First name** and **Last name** to create more personalized emails.</span></span> <span data-ttu-id="bcc62-140">Изберете **Добавяне на атрибут** за нанасяне на тези полета.</span><span class="sxs-lookup"><span data-stu-id="bcc62-140">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="bcc62-141">Изберете сегментите, които искате да експортирате.</span><span class="sxs-lookup"><span data-stu-id="bcc62-141">Select the segments you want to export.</span></span> <span data-ttu-id="bcc62-142">Можете да експортирате до 1 милион потребителски профила общо в Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="bcc62-142">You can export up to 1 million customer profiles in total to Mailchimp.</span></span>

1. <span data-ttu-id="bcc62-143">Изберете **Записване**.</span><span class="sxs-lookup"><span data-stu-id="bcc62-143">Select **Save**.</span></span>

<span data-ttu-id="bcc62-144">Запазването на експортиране не го изпълнява незабавно.</span><span class="sxs-lookup"><span data-stu-id="bcc62-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="bcc62-145">Експортирането се изпълнява с всяко [планирано обновяване](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="bcc62-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="bcc62-146">Може също [да експортирате данни при поискване](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="bcc62-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="bcc62-147">Поверителност и съответствие на данните</span><span class="sxs-lookup"><span data-stu-id="bcc62-147">Data privacy and compliance</span></span>

<span data-ttu-id="bcc62-148">Когато активирате Dynamics 365 Customer Insights, за да предавате данни на Mailchimp, разрешавате прехвърляне на данни извън границата за съответствие за Dynamics 365 Customer Insights, включително потенциално чувствителни данни като Лични данни.</span><span class="sxs-lookup"><span data-stu-id="bcc62-148">When you enable Dynamics 365 Customer Insights to transmit data to Mailchimp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="bcc62-149">Microsoft ще прехвърли такива данни по ваше указание, но вие носите отговорност да гарантирате, че Mailchimp отговаря на всички задължения за поверителност или сигурност, които може да имате.</span><span class="sxs-lookup"><span data-stu-id="bcc62-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Mailchimp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="bcc62-150">За информация посетете [Декларация за поверителност Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="bcc62-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="bcc62-151">Вашият администратор на Dynamics 365 Customer Insights да премахнете това местоназначение за експортиране по всяко време, за да прекратите използването на тази функционалност.</span><span class="sxs-lookup"><span data-stu-id="bcc62-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
