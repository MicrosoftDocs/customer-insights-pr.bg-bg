---
title: Експортирайте данни за Customer Insights в ActiveCampaign
description: Научете как да конфигурирате връзката и да експортирате в ActiveCampaign.
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d85fa9836618e27f7f3da6ce17c07b4bc89e187
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314578"
---
# <a name="export-segments-to-activecampaign-preview"></a><span data-ttu-id="8b857-103">Експортиране на сегменти в ActiveCampaign (преглед)</span><span class="sxs-lookup"><span data-stu-id="8b857-103">Export segments to ActiveCampaign (preview)</span></span>

<span data-ttu-id="8b857-104">Експортирайте сегменти от унифицирани клиентски профили в ActiveCampaign и ги използвайте за маркетингови дейности.</span><span class="sxs-lookup"><span data-stu-id="8b857-104">Export segments of unified customer profiles to ActiveCampaign and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8b857-105">Предварителни изисквания</span><span class="sxs-lookup"><span data-stu-id="8b857-105">Prerequisites</span></span>

-   <span data-ttu-id="8b857-106">Имате [Акаунт в ActiveCampaign](https://www.activecampaign.com/) и съответните идентификационни данни на администратора.</span><span class="sxs-lookup"><span data-stu-id="8b857-106">You have an [ActiveCampaign account](https://www.activecampaign.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="8b857-107">Имате [конфигурирани сегменти](segments.md) в аналитични данни за аудитория.</span><span class="sxs-lookup"><span data-stu-id="8b857-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="8b857-108">Единните потребителски профили в експортираните сегменти съдържат поле с имейл адрес.</span><span class="sxs-lookup"><span data-stu-id="8b857-108">Unified customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="8b857-109">Известни ограничения</span><span class="sxs-lookup"><span data-stu-id="8b857-109">Known limitations</span></span>

- <span data-ttu-id="8b857-110">Можете да експортирате до 1 милион профила на износ в ActiveCampaign и това може да отнеме до 90 минути, за да завършите.</span><span class="sxs-lookup"><span data-stu-id="8b857-110">You can export up to 1 million profiles per export to ActiveCampaign and it can take up to 90 minutes to complete.</span></span>
- <span data-ttu-id="8b857-111">Експортирането в ActiveCampaign е ограничено до сегменти.</span><span class="sxs-lookup"><span data-stu-id="8b857-111">Exporting to ActiveCampaign is limited to segments.</span></span>
- <span data-ttu-id="8b857-112">Броят на профилите, които можете да експортирате в ActiveCampaign, зависи от вашия договор с ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="8b857-112">The number of profiles that you can export to ActiveCampaign depends on your contract with ActiveCampaign.</span></span>

## <a name="set-up-connection-to-activecampaign"></a><span data-ttu-id="8b857-113">Настройване на връзка с ActiveCampaign</span><span class="sxs-lookup"><span data-stu-id="8b857-113">Set up connection to ActiveCampaign</span></span>

1. <span data-ttu-id="8b857-114">Отидете на **Администратор** > **Връзки**.</span><span class="sxs-lookup"><span data-stu-id="8b857-114">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="8b857-115">Изберете **Добавете връзка** и изберете **ActiveCampaign** за конфигуриране на връзката.</span><span class="sxs-lookup"><span data-stu-id="8b857-115">Select **Add connection** and choose **ActiveCampaign** to configure the connection.</span></span>

1. <span data-ttu-id="8b857-116">Въведете разпознаваемо име за връзката в полето **Показвано име**.</span><span class="sxs-lookup"><span data-stu-id="8b857-116">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="8b857-117">Показваното име и типът описват тази връзка.</span><span class="sxs-lookup"><span data-stu-id="8b857-117">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="8b857-118">Препоръчваме да изберете име, което обяснява целта на връзката.</span><span class="sxs-lookup"><span data-stu-id="8b857-118">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="8b857-119">Изберете кой може да използва тази връзка.</span><span class="sxs-lookup"><span data-stu-id="8b857-119">Choose who can use this connection.</span></span> <span data-ttu-id="8b857-120">По подразбиране това са само администратори.</span><span class="sxs-lookup"><span data-stu-id="8b857-120">By default, it's only administrators.</span></span> <span data-ttu-id="8b857-121">За повече информация вижте [Разрешаване на сътрудници да използват връзка за експортиране](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="8b857-121">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="8b857-122">Въведете своя [API ключ ActiveCampaign и име на хост REST Endpoint](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key).</span><span class="sxs-lookup"><span data-stu-id="8b857-122">Enter your [ActiveCampaign API Key and REST Endpoint Hostname](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key).</span></span> <span data-ttu-id="8b857-123">Името на хоста REST Endpoint е само името на хоста, без https://.</span><span class="sxs-lookup"><span data-stu-id="8b857-123">The REST Endpoint Hostname is the hostname only, without https://.</span></span> 

1. <span data-ttu-id="8b857-124">Изберете **Приемам**, за да потвърдите **Поверителност на данните и съответствие**.</span><span class="sxs-lookup"><span data-stu-id="8b857-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="8b857-125">Изберете **Свързване**, за да инициализирате връзка с ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="8b857-125">Select **Connect** to initialize the connection to ActiveCampaign.</span></span>

1. <span data-ttu-id="8b857-126">Изберете **Добавете себе си като потребител за експортиране** и предоставете вашите идентификационни данни на Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="8b857-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="8b857-127">Изберете **Записване**, за да завършите връзката.</span><span class="sxs-lookup"><span data-stu-id="8b857-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="8b857-128">Конфигуриране на експортиране</span><span class="sxs-lookup"><span data-stu-id="8b857-128">Configure an export</span></span>

<span data-ttu-id="8b857-129">Можете да конфигурирате експортиране, ако имате достъп до връзка от този тип.</span><span class="sxs-lookup"><span data-stu-id="8b857-129">You can configure an export if you have access to a connection of this type.</span></span> <span data-ttu-id="8b857-130">За повече информация вижте [Разрешения, необходими за конфигуриране на експортиране](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="8b857-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="8b857-131">Отидете на **Данни** > **Експортиране**.</span><span class="sxs-lookup"><span data-stu-id="8b857-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="8b857-132">За да създадете ново експортиране, изберете **Добавяне на местоназначение**.</span><span class="sxs-lookup"><span data-stu-id="8b857-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="8b857-133">В **Връзка за експортиране** поле, изберете връзка от раздела ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="8b857-133">In the **Connection for export** field, choose a connection from the ActiveCampaign section.</span></span> <span data-ttu-id="8b857-134">Ако не виждате името на тази секция, няма достъпни за вас връзки от този тип.</span><span class="sxs-lookup"><span data-stu-id="8b857-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="8b857-135">Въведете своя [**ИД на списък на ActiveCampaign**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).</span><span class="sxs-lookup"><span data-stu-id="8b857-135">Enter your [**ActiveCampaign List ID**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).</span></span>    

3. <span data-ttu-id="8b857-136">В секцията **Съвпадение на данни** в полето **Имейл** изберете полето във вашия унифициран потребителски профил, което представлява имейл адреса на клиента.</span><span class="sxs-lookup"><span data-stu-id="8b857-136">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="8b857-137">Изисква се да експортирате сегменти в ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="8b857-137">It's required to export segments to ActiveCampaign.</span></span> <span data-ttu-id="8b857-138">По желание можете да експортирате собствено име, фамилно име и Телефон за създаване на по-персонализирани имейли.</span><span class="sxs-lookup"><span data-stu-id="8b857-138">Optionally, you can export First name, Last name, and Phone to create more personalized emails.</span></span> <span data-ttu-id="8b857-139">Изберете Добавяне на атрибут за нанасяне на тези полета.</span><span class="sxs-lookup"><span data-stu-id="8b857-139">Select Add attribute to map these fields.</span></span>

1. <span data-ttu-id="8b857-140">Изберете **Записване**.</span><span class="sxs-lookup"><span data-stu-id="8b857-140">Select **Save**.</span></span>

<span data-ttu-id="8b857-141">Запазването на експортиране не го изпълнява незабавно.</span><span class="sxs-lookup"><span data-stu-id="8b857-141">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="8b857-142">Експортирането се изпълнява с всяко [планирано обновяване](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="8b857-142">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="8b857-143">Може също [да експортирате данни при поискване](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="8b857-143">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="8b857-144">Поверителност и съответствие на данните</span><span class="sxs-lookup"><span data-stu-id="8b857-144">Data privacy and compliance</span></span>

<span data-ttu-id="8b857-145">Когато активирате Dynamics 365 Customer Insights за предаване на данни на ActiveCampaign, разрешавате прехвърляне на данни извън границата за съответствие за Dynamics 365 Customer Insights, включително потенциално чувствителни данни като Лични данни.</span><span class="sxs-lookup"><span data-stu-id="8b857-145">When you enable Dynamics 365 Customer Insights to transmit data to ActiveCampaign, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="8b857-146">Microsoft ще прехвърли такива данни по ваше указание, но вие сте отговорни за това ActiveCampaign отговаря на всички задължения за поверителност или сигурност, които може да имате.</span><span class="sxs-lookup"><span data-stu-id="8b857-146">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that ActiveCampaign meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="8b857-147">За информация посетете [Декларация за поверителност Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="8b857-147">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="8b857-148">Вашият администратор на Dynamics 365 Customer Insights да премахнете това местоназначение за експортиране по всяко време, за да прекратите използването на тази функционалност.</span><span class="sxs-lookup"><span data-stu-id="8b857-148">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
