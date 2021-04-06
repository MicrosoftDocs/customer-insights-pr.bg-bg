---
title: Експортирайте данните от Customer Insights в AdRoll
description: Научете как да конфигурирате връзката с AdRoll.
ms.date: 02/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6fedd549c2e7de362f36e3fb23d363200bb92a04
ms.sourcegitcommit: d24e52150fe5a4fab45128e12d6a03637771d9b9
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 03/19/2021
ms.locfileid: "5697061"
---
# <a name="connector-for-adroll-preview"></a><span data-ttu-id="8d249-103">Конектор за AdRoll (преглед)</span><span class="sxs-lookup"><span data-stu-id="8d249-103">Connector for AdRoll (preview)</span></span>

<span data-ttu-id="8d249-104">Експортирайте сегменти от унифицирани клиентски профили в AdRoll и ги използвайте за реклама.</span><span class="sxs-lookup"><span data-stu-id="8d249-104">Export segments of unified customer profiles to AdRoll and use them for advertising.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="8d249-105">Предварителни изисквания</span><span class="sxs-lookup"><span data-stu-id="8d249-105">Prerequisites</span></span>

-   <span data-ttu-id="8d249-106">Имате [Акаунт в AdRoll](https://www.adroll.com/) и съответните идентификационни данни на администратора.</span><span class="sxs-lookup"><span data-stu-id="8d249-106">You have an [AdRoll account](https://www.adroll.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="8d249-107">Имате [конфигурирани сегменти](segments.md) в аналитични данни за аудитория.</span><span class="sxs-lookup"><span data-stu-id="8d249-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="8d249-108">Единните клиентски профили в експортираните сегменти съдържат поле, представляващо имейл адрес.</span><span class="sxs-lookup"><span data-stu-id="8d249-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-adroll"></a><span data-ttu-id="8d249-109">Свързване с AdRoll</span><span class="sxs-lookup"><span data-stu-id="8d249-109">Connect to AdRoll</span></span>

1. <span data-ttu-id="8d249-110">Отидете на **Администратор** > **Експортиране на дестинации**.</span><span class="sxs-lookup"><span data-stu-id="8d249-110">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="8d249-111">Под **AdRoll** изберете **Настройка**.</span><span class="sxs-lookup"><span data-stu-id="8d249-111">Under **AdRoll**, select **Set up**.</span></span>

1. <span data-ttu-id="8d249-112">Въведете разпознаваемо име за местоназначението за експортиране в полето **Показвано име**.</span><span class="sxs-lookup"><span data-stu-id="8d249-112">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/AdRoll_config.PNG" alt-text="Конфигурационен прозорец за връзка с AdRoll.":::

1. <span data-ttu-id="8d249-114">Изберете **Приемам**, за да потвърдите **Поверителност на данните и съответствие**.</span><span class="sxs-lookup"><span data-stu-id="8d249-114">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="8d249-115">Изберете **Свържете** за инициализиране на връзката с AdRoll.</span><span class="sxs-lookup"><span data-stu-id="8d249-115">Select **Connect** to initialize the connection to AdRoll.</span></span>

1. <span data-ttu-id="8d249-116">Изберете **Удостоверете с AdRoll** и предоставете вашите идентификационни данни на администратор за AdRoll.</span><span class="sxs-lookup"><span data-stu-id="8d249-116">Select **Authenticate with AdRoll** and provide your admin credentials for AdRoll.</span></span> 

1. <span data-ttu-id="8d249-117">Изберете **Добавете себе си като потребител за експортиране** и предоставете вашите идентификационни данни на Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="8d249-117">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="8d249-118">Въведете своя **ИД на рекламодател на AdRoll** [AdRoll Advertisable](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="8d249-118">Enter your **AdRoll Advertiser ID** [AdRoll Advertisable](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).</span></span>

1. <span data-ttu-id="8d249-119">Изберете **Напред**, за да конфигурирате експортирането.</span><span class="sxs-lookup"><span data-stu-id="8d249-119">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="8d249-120">Конфигуриране на конектор</span><span class="sxs-lookup"><span data-stu-id="8d249-120">Configure the connector</span></span>

1. <span data-ttu-id="8d249-121">В секцията **Съвпадение на данни** в полето **Имейл** изберете полето във вашия унифициран потребителски профил, което представлява имейл адреса на клиента.</span><span class="sxs-lookup"><span data-stu-id="8d249-121">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="8d249-122">Необходимо е да експортирате сегменти в AdRoll.</span><span class="sxs-lookup"><span data-stu-id="8d249-122">It's required to export segments to AdRoll.</span></span>

1. <span data-ttu-id="8d249-123">Изберете сегментите, които искате да експортирате.</span><span class="sxs-lookup"><span data-stu-id="8d249-123">Select the segments you want to export.</span></span> <span data-ttu-id="8d249-124">Изберете сегмент с поне 100 членове.</span><span class="sxs-lookup"><span data-stu-id="8d249-124">Select a segment with a least 100 members.</span></span> <span data-ttu-id="8d249-125">Не можете да експортирате по-малки сегменти.</span><span class="sxs-lookup"><span data-stu-id="8d249-125">You can't export smaller segments.</span></span> <span data-ttu-id="8d249-126">Освен това максималният размер на сегмент за експортиране е 250 000 членове на експортиране.</span><span class="sxs-lookup"><span data-stu-id="8d249-126">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="8d249-127">Изберете **Записване**.</span><span class="sxs-lookup"><span data-stu-id="8d249-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="8d249-128">Експортиране на данните</span><span class="sxs-lookup"><span data-stu-id="8d249-128">Export the data</span></span>

<span data-ttu-id="8d249-129">Можете да [експортирате данни при поискване](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="8d249-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="8d249-130">Експортирането също ще се изпълнява с всяко [планирано обновяване](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="8d249-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="8d249-131">Известни ограничения</span><span class="sxs-lookup"><span data-stu-id="8d249-131">Known limitations</span></span>

- <span data-ttu-id="8d249-132">Можете да експортирате до 250 000 профила на експортиране в AdRoll.</span><span class="sxs-lookup"><span data-stu-id="8d249-132">You can export up to 250'000 profiles in per export to AdRoll.</span></span>
- <span data-ttu-id="8d249-133">Не можете да експортирате сегменти с по-малко от 100 профила в AdRoll.</span><span class="sxs-lookup"><span data-stu-id="8d249-133">You can't export segments with fewer than 100 profiles to AdRoll.</span></span> 
- <span data-ttu-id="8d249-134">Експортирането в AdRoll е ограничено до сегменти.</span><span class="sxs-lookup"><span data-stu-id="8d249-134">Exporting to AdRoll is limited to segments.</span></span>
- <span data-ttu-id="8d249-135">Експортирането на до 250 000 профила в AdRoll може да отнеме до 10 минути.</span><span class="sxs-lookup"><span data-stu-id="8d249-135">Exporting up to 250'000 profiles to AdRoll can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="8d249-136">Броят на профилите, които можете да експортирате в AdRoll, зависи и е ограничен от вашия договор с AdRoll.</span><span class="sxs-lookup"><span data-stu-id="8d249-136">The number of profiles that you can export to AdRoll is dependent and limited on your contract with AdRoll.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="8d249-137">Поверителност и съответствие на данните</span><span class="sxs-lookup"><span data-stu-id="8d249-137">Data privacy and compliance</span></span>

<span data-ttu-id="8d249-138">Когато активирате Dynamics 365 Customer Insights, за да предавате данни на AdRoll, разрешавате прехвърляне на данни извън границата за съответствие за Dynamics 365 Customer Insights, включително потенциално чувствителни данни като Лични данни.</span><span class="sxs-lookup"><span data-stu-id="8d249-138">When you enable Dynamics 365 Customer Insights to transmit data to AdRoll, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="8d249-139">Microsoft ще прехвърли такива данни по ваше указание, но вие носите отговорност да гарантирате, че AdRoll отговаря на всички задължения за поверителност или сигурност, които може да имате.</span><span class="sxs-lookup"><span data-stu-id="8d249-139">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that AdRoll meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="8d249-140">За информация посетете [Декларация за поверителност Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="8d249-140">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="8d249-141">Вашият администратор на Dynamics 365 Customer Insights да премахнете това местоназначение за експортиране по всяко време, за да прекратите използването на тази функционалност.</span><span class="sxs-lookup"><span data-stu-id="8d249-141">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
