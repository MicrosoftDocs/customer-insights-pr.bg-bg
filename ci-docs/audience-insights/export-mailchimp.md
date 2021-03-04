---
title: Експортирайте данните от Customer Insights в Mailchimp
description: Научете как да конфигурирате връзката с Mailchimp.
ms.date: 10/26/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 2b465b32fa956e3f45a23f471dc3a3183def16ef
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267160"
---
# <a name="connector-for-mailchimp-preview"></a><span data-ttu-id="f5e87-103">Конектор за Mailchimp (преглед)</span><span class="sxs-lookup"><span data-stu-id="f5e87-103">Connector for Mailchimp (preview)</span></span>

<span data-ttu-id="f5e87-104">Експортирайте сегменти от унифицирани клиентски профили в Mailchimp, за да създавате бюлетини и имейл кампании.</span><span class="sxs-lookup"><span data-stu-id="f5e87-104">Export segments of unified customer profiles to Mailchimp to create newsletters and email campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f5e87-105">Предварителни изисквания</span><span class="sxs-lookup"><span data-stu-id="f5e87-105">Prerequisites</span></span>

-   <span data-ttu-id="f5e87-106">Имате [Акаунт в Mailchimp](https://mailchimp.com/) и съответните идентификационни данни на администратора.</span><span class="sxs-lookup"><span data-stu-id="f5e87-106">You have a [Mailchimp account](https://mailchimp.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="f5e87-107">В Mailchimp има съществуващи аудитории и съответните идентификатори.</span><span class="sxs-lookup"><span data-stu-id="f5e87-107">There are existing audiences in Mailchimp and the corresponding IDs.</span></span> <span data-ttu-id="f5e87-108">За повече информация вижте [Аудитории на Mailchimp](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="f5e87-108">For more information, see [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>
-   <span data-ttu-id="f5e87-109">Имате [конфигурирани сегменти](segments.md)</span><span class="sxs-lookup"><span data-stu-id="f5e87-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="f5e87-110">Единните клиентски профили в експортираните сегменти съдържат поле, представляващо имейл адрес.</span><span class="sxs-lookup"><span data-stu-id="f5e87-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-mailchimp"></a><span data-ttu-id="f5e87-111">Свързване с Mailchimp</span><span class="sxs-lookup"><span data-stu-id="f5e87-111">Connect to Mailchimp</span></span>

1. <span data-ttu-id="f5e87-112">Отидете на **Администратор** > **Експортиране на дестинации**.</span><span class="sxs-lookup"><span data-stu-id="f5e87-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="f5e87-113">Под **Mailchimp** изберете **Настройка**.</span><span class="sxs-lookup"><span data-stu-id="f5e87-113">Under **Mailchimp**, select **Set up**.</span></span>

1. <span data-ttu-id="f5e87-114">Въведете разпознаваемо име за местоназначението за експортиране в полето **Показвано име**.</span><span class="sxs-lookup"><span data-stu-id="f5e87-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="f5e87-115">Изберете **Приемам**, за да потвърдите **Поверителност на данните и съответствие**.</span><span class="sxs-lookup"><span data-stu-id="f5e87-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="f5e87-116">Въведете своя **[ИД на аудиторията на Mailchimp](https://mailchimp.com/help/find-audience-id/)** и изберете **Свързване** за инициализиране на връзката с Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="f5e87-116">Enter your **[Mailchimp audience ID](https://mailchimp.com/help/find-audience-id/)** and select **Connect** to initialize the connection to Mailchimp.</span></span>

1. <span data-ttu-id="f5e87-117">Изберете **Удостоверете с Mailchimp** и предоставете вашите идентификационни данни на Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="f5e87-117">Select **Authenticate with Mailchimp** and provide your Mailchimp credentials.</span></span>

1. <span data-ttu-id="f5e87-118">Изберете **Добавете себе си като потребител за експортиране** и предоставете вашите идентификационни данни на Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="f5e87-118">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-connect-mailchimp.png" alt-text="Експортиране на екранна снимка за връзка с Mailchimp":::

1. <span data-ttu-id="f5e87-120">Изберете **Напред**, за да конфигурирате експортирането.</span><span class="sxs-lookup"><span data-stu-id="f5e87-120">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="f5e87-121">Конфигуриране на конектор</span><span class="sxs-lookup"><span data-stu-id="f5e87-121">Configure the connector</span></span>

1. <span data-ttu-id="f5e87-122">В секцията **Съвпадение на данни** в полето **Имейл** изберете полето във вашия унифициран потребителски профил, което представлява имейл адреса на клиента.</span><span class="sxs-lookup"><span data-stu-id="f5e87-122">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="f5e87-123">По желание можете да експортирате **Собствено име** и **Фамилно име** като допълнителни полета за създаване на по-персонализирани имейли.</span><span class="sxs-lookup"><span data-stu-id="f5e87-123">Optionally, you can export **First name** and **Last name** as additional fields to create more personalized emails.</span></span> <span data-ttu-id="f5e87-124">Изберете **Добавяне на атрибут** за нанасяне на тези полета.</span><span class="sxs-lookup"><span data-stu-id="f5e87-124">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="f5e87-125">Изберете сегментите, които искате да експортирате.</span><span class="sxs-lookup"><span data-stu-id="f5e87-125">Select the segments you want to export.</span></span> <span data-ttu-id="f5e87-126">Можете да експортирате до 1 милион потребителски профила общо в Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="f5e87-126">You can export up to 1 million customer profiles in total to Mailchimp.</span></span>

   :::image type="content" source="media/export-segments-mailchimp.png" alt-text="Изберете полета и сегменти, които да експортирате в Mailchimp":::

1. <span data-ttu-id="f5e87-128">Изберете **Записване**.</span><span class="sxs-lookup"><span data-stu-id="f5e87-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="f5e87-129">Експортиране на данните</span><span class="sxs-lookup"><span data-stu-id="f5e87-129">Export the data</span></span>

<span data-ttu-id="f5e87-130">Можете да [експортирате данни при поискване](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="f5e87-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="f5e87-131">Експортирането също ще се изпълнява с всяко [планирано обновяване](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="f5e87-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="f5e87-132">В Mailchimp вече можете да намерите своите сегменти под [Аудитории на Mailchimp](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="f5e87-132">In Mailchimp, you can now find your segments under [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="f5e87-133">Известни ограничения</span><span class="sxs-lookup"><span data-stu-id="f5e87-133">Known limitations</span></span>

- <span data-ttu-id="f5e87-134">До 1 милион профила на износ към Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="f5e87-134">Up to 1 million profiles per export to Mailchimp.</span></span>
- <span data-ttu-id="f5e87-135">Експортирането в Mailchimp е ограничено до сегменти.</span><span class="sxs-lookup"><span data-stu-id="f5e87-135">Exporting to Mailchimp is limited to segments.</span></span>
- <span data-ttu-id="f5e87-136">Експортирането на сегменти с общо 1 милион профила може да отнеме до три часа поради ограничения от страна на доставчика.</span><span class="sxs-lookup"><span data-stu-id="f5e87-136">Exporting segments with a total of 1 million profiles can take up to three hours due to limitations on the provider side.</span></span> 
- <span data-ttu-id="f5e87-137">Броят на профилите, които можете да експортирате в Mailchimp, зависи и е ограничен от вашия договор с Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="f5e87-137">The number of profiles that you can export to Mailchimp is dependent and limited on your contract with Mailchimp.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="f5e87-138">Поверителност и съответствие на данните</span><span class="sxs-lookup"><span data-stu-id="f5e87-138">Data privacy and compliance</span></span>

<span data-ttu-id="f5e87-139">Когато активирате Dynamics 365 Customer Insights, за да предавате данни на Mailchimp, разрешавате прехвърляне на данни извън границата за съответствие за Dynamics 365 Customer Insights, включително потенциално чувствителни данни като Лични данни.</span><span class="sxs-lookup"><span data-stu-id="f5e87-139">When you enable Dynamics 365 Customer Insights to transmit data to Mailchimp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="f5e87-140">Microsoft ще прехвърли такива данни по ваше указание, но вие носите отговорност да гарантирате, че Mailchimp отговаря на всички задължения за поверителност или сигурност, които може да имате.</span><span class="sxs-lookup"><span data-stu-id="f5e87-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Mailchimp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="f5e87-141">За информация посетете [Декларация за поверителност Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="f5e87-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="f5e87-142">Вашият администратор на Dynamics 365 Customer Insights да премахнете това местоназначение за експортиране по всяко време, за да прекратите използването на тази функционалност.</span><span class="sxs-lookup"><span data-stu-id="f5e87-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]