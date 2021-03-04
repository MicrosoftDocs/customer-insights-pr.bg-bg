---
title: Експортирайте данните от Customer Insights в Google Ads
description: Научете как да конфигурирате връзката с Google Ads.
ms.date: 11/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ba7c82e643ea0dc1897e0954e78646932cafffa3
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268949"
---
# <a name="connector-for-google-ads-preview"></a><span data-ttu-id="2651c-103">Конектор за Google Ads (преглед)</span><span class="sxs-lookup"><span data-stu-id="2651c-103">Connector for Google Ads (preview)</span></span>

<span data-ttu-id="2651c-104">Експортирайте сегменти на унифицирани клиентски профили в списъци с аудитории на Google Ads и ги използвайте за рекламиране в Google Search, Gmail, YouTube и Google Display Network.</span><span class="sxs-lookup"><span data-stu-id="2651c-104">Export segments of unified customer profiles to Google Ads audience list and use them to advertise on Google Search, Gmail, YouTube, and Google Display Network.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="2651c-105">Предварителни изисквания</span><span class="sxs-lookup"><span data-stu-id="2651c-105">Prerequisites</span></span>

-   <span data-ttu-id="2651c-106">Имате [Акаунт в Google Ads](https://ads.google.com/) и съответните идентификационни данни на администратора.</span><span class="sxs-lookup"><span data-stu-id="2651c-106">You have a [Google Ads account](https://ads.google.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="2651c-107">В Google Ads има съществуващи аудитории и съответните идентификатори.</span><span class="sxs-lookup"><span data-stu-id="2651c-107">There are existing audiences in Google Ads and the corresponding IDs.</span></span> <span data-ttu-id="2651c-108">За повече информация вижте [аудитории на Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span><span class="sxs-lookup"><span data-stu-id="2651c-108">For more information, see [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span></span>
-   <span data-ttu-id="2651c-109">Имате [конфигурирани сегменти](segments.md)</span><span class="sxs-lookup"><span data-stu-id="2651c-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="2651c-110">Единните клиентски профили в експортираните сегменти съдържат полета, представляващи имейл адрес, собствено име и фамилно име</span><span class="sxs-lookup"><span data-stu-id="2651c-110">Unified customer profiles in the exported segments contain fields representing an email address, first name, and last name</span></span>

## <a name="connect-to-google-ads"></a><span data-ttu-id="2651c-111">Свързване с Google Ads</span><span class="sxs-lookup"><span data-stu-id="2651c-111">Connect to Google Ads</span></span>

1. <span data-ttu-id="2651c-112">Отидете на **Администратор** > **Експортиране на дестинации**.</span><span class="sxs-lookup"><span data-stu-id="2651c-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="2651c-113">Под **Google Ads** изберете **Настройка**.</span><span class="sxs-lookup"><span data-stu-id="2651c-113">Under **Google Ads**, select **Set up**.</span></span>

1. <span data-ttu-id="2651c-114">Въведете разпознаваемо име за местоназначението за експортиране в полето **Показвано име**.</span><span class="sxs-lookup"><span data-stu-id="2651c-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="2651c-115">Въведете своя **[ИД на клиента в Google Ads](https://support.google.com/google-ads/answer/1704344)**.</span><span class="sxs-lookup"><span data-stu-id="2651c-115">Enter your **[Google Ads customer ID](https://support.google.com/google-ads/answer/1704344)**.</span></span>

1. <span data-ttu-id="2651c-116">Въведете своя **[Одобрен от Google Ads маркер за програмисти](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span><span class="sxs-lookup"><span data-stu-id="2651c-116">Enter your **[Google Ads approved developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span></span>

1. <span data-ttu-id="2651c-117">Изберете **Приемам**, за да потвърдите **Поверителност на данните и съответствие**.</span><span class="sxs-lookup"><span data-stu-id="2651c-117">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="2651c-118">Въведете своя **[ИД на аудиторията на Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** и изберете **Свързване** за инициализиране на връзката с Google Ads.</span><span class="sxs-lookup"><span data-stu-id="2651c-118">Enter your **[Google Ads audience ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** and select **Connect** to initialize the connection to Google Ads.</span></span>

1. <span data-ttu-id="2651c-119">Изберете **Удостоверете с Google Ads** и предоставете вашите идентификационни данни на Google Ads.</span><span class="sxs-lookup"><span data-stu-id="2651c-119">Select **Authenticate with Google Ads** and provide your Google Ads credentials.</span></span>

1. <span data-ttu-id="2651c-120">Изберете **Добавете себе си като потребител за експортиране** и предоставете вашите идентификационни данни на Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="2651c-120">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-segments-googleads.PNG" alt-text="Експортиране на екранна снимка за връзка с Google Ads":::

1. <span data-ttu-id="2651c-122">Изберете **Напред**, за да конфигурирате експортирането.</span><span class="sxs-lookup"><span data-stu-id="2651c-122">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="2651c-123">Конфигуриране на конектор</span><span class="sxs-lookup"><span data-stu-id="2651c-123">Configure the connector</span></span>

1. <span data-ttu-id="2651c-124">В секцията **Съвпадение на данни** в полето **Имейл** изберете полето във вашия унифициран потребителски профил, което представлява имейл адреса на клиента.</span><span class="sxs-lookup"><span data-stu-id="2651c-124">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="2651c-125">Повторете същите стъпки за полетата **Собствено име** и **фамилно име**.</span><span class="sxs-lookup"><span data-stu-id="2651c-125">Repeat the same steps for \*\*First name" and **Last name** fields.</span></span>

1. <span data-ttu-id="2651c-126">Изберете сегментите, които искате да експортирате.</span><span class="sxs-lookup"><span data-stu-id="2651c-126">Select the segments you want to export.</span></span> <span data-ttu-id="2651c-127">Можете да експортирате до 1 милион потребителски профила общо в Google Ads.</span><span class="sxs-lookup"><span data-stu-id="2651c-127">You can export up to 1 million customer profiles in total to Google Ads.</span></span>

1. <span data-ttu-id="2651c-128">Изберете **Записване**.</span><span class="sxs-lookup"><span data-stu-id="2651c-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="2651c-129">Експортиране на данните</span><span class="sxs-lookup"><span data-stu-id="2651c-129">Export the data</span></span>

<span data-ttu-id="2651c-130">Можете да [експортирате данни при поискване](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="2651c-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="2651c-131">Експортирането също ще се изпълнява с всяко [планирано обновяване](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="2651c-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="2651c-132">В Google Ads вече можете да намерите своите сегменти под [Аудитории на Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en/).</span><span class="sxs-lookup"><span data-stu-id="2651c-132">In Google Ads, you can now find your segments under [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en/).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="2651c-133">Известни ограничения</span><span class="sxs-lookup"><span data-stu-id="2651c-133">Known limitations</span></span>

- <span data-ttu-id="2651c-134">До 1 милион профила на износ към Google Ads.</span><span class="sxs-lookup"><span data-stu-id="2651c-134">Up to 1 million profiles per export to Google Ads.</span></span>
- <span data-ttu-id="2651c-135">Експортирането в Google Ads е ограничено до сегменти.</span><span class="sxs-lookup"><span data-stu-id="2651c-135">Exporting to Google Ads is limited to segments.</span></span>
- <span data-ttu-id="2651c-136">Експортирането на сегменти с общо 1 милион профила може да отнеме до 5 минути поради ограничения от страна на доставчика.</span><span class="sxs-lookup"><span data-stu-id="2651c-136">Exporting segments with a total of 1 million profiles can take up to 5 minutes because of limitations on the provider side.</span></span> 
- <span data-ttu-id="2651c-137">Съответствието в Google Ads може да отнеме до 48 часа.</span><span class="sxs-lookup"><span data-stu-id="2651c-137">The matching in Google Ads can take up to 48 hours.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="2651c-138">Поверителност и съответствие на данните</span><span class="sxs-lookup"><span data-stu-id="2651c-138">Data privacy and compliance</span></span>

<span data-ttu-id="2651c-139">Когато активирате Dynamics 365 Customer Insights, за да предавате данни на Google Ads, разрешавате прехвърляне на данни извън границата за съответствие за Dynamics 365 Customer Insights, включително потенциално чувствителни данни като Лични данни.</span><span class="sxs-lookup"><span data-stu-id="2651c-139">When you enable Dynamics 365 Customer Insights to transmit data to Google Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="2651c-140">Microsoft ще прехвърли такива данни по ваше указание, но вие носите отговорност да гарантирате, че Google Ads отговаря на всички задължения за поверителност или сигурност, които може да имате.</span><span class="sxs-lookup"><span data-stu-id="2651c-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Google Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="2651c-141">За информация посетете [Декларация за поверителност Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="2651c-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="2651c-142">Вашият администратор на Dynamics 365 Customer Insights да премахнете това местоназначение за експортиране по всяко време, за да прекратите използването на тази функционалност.</span><span class="sxs-lookup"><span data-stu-id="2651c-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]