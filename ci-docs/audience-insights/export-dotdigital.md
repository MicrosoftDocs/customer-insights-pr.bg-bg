---
title: Експортирайте данните от Customer Insights в DotDigital
description: Научете как да конфигурирате връзката с DotDigital.
ms.date: 11/14/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 51a28bdf0de34f0555d8ad7e3d13b2ef8911d417
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598003"
---
# <a name="connector-for-dotdigital-preview"></a><span data-ttu-id="6c8bd-103">Конектор за DotDigital (преглед)</span><span class="sxs-lookup"><span data-stu-id="6c8bd-103">Connector for DotDigital (preview)</span></span>

<span data-ttu-id="6c8bd-104">Експортирайте сегменти от унифицирани клиентски профили в адресните книги на DotDigital и ги използвайте за кампании, маркетинг по имейл и за изграждане на клиентски сегменти с DotDigital.</span><span class="sxs-lookup"><span data-stu-id="6c8bd-104">Export segments of unified customer profiles to DotDigital address books and use them for campaigns, email marketing, and to build customer segments with DotDigital.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="6c8bd-105">Предварителни изисквания</span><span class="sxs-lookup"><span data-stu-id="6c8bd-105">Prerequisites</span></span>

-   <span data-ttu-id="6c8bd-106">Имате [Акаунт в DotDigital](https://dotdigital.com/) и съответните идентификационни данни на администратора.</span><span class="sxs-lookup"><span data-stu-id="6c8bd-106">You have a [DotDigital account](https://dotdigital.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="6c8bd-107">В Google Ads има съществуващи адресни книги в DotDigital и съответните идентификатори.</span><span class="sxs-lookup"><span data-stu-id="6c8bd-107">There are existing address books in DotDigital and the corresponding IDs.</span></span> <span data-ttu-id="6c8bd-108">Идентификаторът може да бъде намерен в URL адреса, когато изберете и отворите адресна книга.</span><span class="sxs-lookup"><span data-stu-id="6c8bd-108">The ID can be found in the URL when you select and open an address book.</span></span> <span data-ttu-id="6c8bd-109">За повече информация вижте [Адресни книги на DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="6c8bd-109">For more information, see [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>
-   <span data-ttu-id="6c8bd-110">Имате [конфигурирани сегменти](segments.md) в аналитични данни за аудитория.</span><span class="sxs-lookup"><span data-stu-id="6c8bd-110">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="6c8bd-111">Единните клиентски профили в експортираните сегменти съдържат поле, представляващо имейл адрес.</span><span class="sxs-lookup"><span data-stu-id="6c8bd-111">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-dotdigital"></a><span data-ttu-id="6c8bd-112">Свързване към DotDigital</span><span class="sxs-lookup"><span data-stu-id="6c8bd-112">Connect to DotDigital</span></span>

1. <span data-ttu-id="6c8bd-113">Отидете на **Администратор** > **Експортиране на дестинации**.</span><span class="sxs-lookup"><span data-stu-id="6c8bd-113">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="6c8bd-114">Под **DotDigital** изберете **Настройка**.</span><span class="sxs-lookup"><span data-stu-id="6c8bd-114">Under **DotDigital**, select **Set up**.</span></span>

1. <span data-ttu-id="6c8bd-115">Въведете разпознаваемо име за местоназначението за експортиране в полето **Показвано име**.</span><span class="sxs-lookup"><span data-stu-id="6c8bd-115">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/DotDigital_config.PNG" alt-text="Конфигурационен прозорец за експортиране на DotDigital.":::

1. <span data-ttu-id="6c8bd-117">Въведете **потребителско име и парола за DotDigital**.</span><span class="sxs-lookup"><span data-stu-id="6c8bd-117">Enter your **DotDigital username and password**.</span></span>

1. <span data-ttu-id="6c8bd-118">Въведете своя **[Идентификатор на адресната книга на DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span><span class="sxs-lookup"><span data-stu-id="6c8bd-118">Enter your **[DotDigital address book ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span></span>

1. <span data-ttu-id="6c8bd-119">Изберете **Приемам**, за да потвърдите **Поверителност на данните и съответствие**.</span><span class="sxs-lookup"><span data-stu-id="6c8bd-119">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="6c8bd-120">Изберете **Свържете** за инициализиране на връзката с DotDigital.</span><span class="sxs-lookup"><span data-stu-id="6c8bd-120">Select **Connect** to initialize the connection to DotDigital.</span></span>

1. <span data-ttu-id="6c8bd-121">Изберете **Добавете себе си като потребител за експортиране** и предоставете вашите идентификационни данни на Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="6c8bd-121">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="6c8bd-122">Изберете **Напред**, за да конфигурирате експортирането.</span><span class="sxs-lookup"><span data-stu-id="6c8bd-122">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="6c8bd-123">Конфигуриране на конектор</span><span class="sxs-lookup"><span data-stu-id="6c8bd-123">Configure the connector</span></span>

1. <span data-ttu-id="6c8bd-124">В секцията **Съвпадение на данни** в полето **Имейл** изберете полето във вашия унифициран потребителски профил, което представлява имейл адреса на клиента.</span><span class="sxs-lookup"><span data-stu-id="6c8bd-124">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="6c8bd-125">Повторете същите стъпки за други незадължителни полета, като например **собствено име**, **фамилно име**, **Пълно име**, **Пол** и **Пощенски код**.</span><span class="sxs-lookup"><span data-stu-id="6c8bd-125">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Full name**, **Gender**, and **Post code**.</span></span>

1. <span data-ttu-id="6c8bd-126">Изберете сегментите, които искате да експортирате.</span><span class="sxs-lookup"><span data-stu-id="6c8bd-126">Select the segments you want to export.</span></span> <span data-ttu-id="6c8bd-127">Можете да експортирате до 1 милион потребителски профила общо в DotDigital.</span><span class="sxs-lookup"><span data-stu-id="6c8bd-127">You can export up to 1 million customer profiles in total to DotDigital.</span></span>

1. <span data-ttu-id="6c8bd-128">Изберете **Записване**.</span><span class="sxs-lookup"><span data-stu-id="6c8bd-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="6c8bd-129">Експортиране на данните</span><span class="sxs-lookup"><span data-stu-id="6c8bd-129">Export the data</span></span>

<span data-ttu-id="6c8bd-130">Можете да [експортирате данни при поискване](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="6c8bd-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="6c8bd-131">Експортирането също ще се изпълнява с всяко [планирано обновяване](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="6c8bd-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="6c8bd-132">В DotDigital вече можете да намерите своите сегменти в [адресни книги в DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="6c8bd-132">In DotDigital, you can now find your segments in [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="6c8bd-133">Известни ограничения</span><span class="sxs-lookup"><span data-stu-id="6c8bd-133">Known limitations</span></span>

- <span data-ttu-id="6c8bd-134">До 1 милион профила на износ към DotDigital.</span><span class="sxs-lookup"><span data-stu-id="6c8bd-134">Up to 1 million profiles per export to DotDigital.</span></span>
- <span data-ttu-id="6c8bd-135">Експортирането в DotDigital е ограничено до сегменти.</span><span class="sxs-lookup"><span data-stu-id="6c8bd-135">Exporting to DotDigital is limited to segments.</span></span>
- <span data-ttu-id="6c8bd-136">Експортирането на сегменти с общо 1 милион профила може да отнеме до 3 часа поради ограничения от страна на доставчика.</span><span class="sxs-lookup"><span data-stu-id="6c8bd-136">Exporting segments with a total of 1 million profiles can take up to 3 hours because of limitations on the provider side.</span></span> 
- <span data-ttu-id="6c8bd-137">Броят на профилите, които можете да експортирате в DotDigital, зависи и е ограничен от вашия договор с DotDigital.</span><span class="sxs-lookup"><span data-stu-id="6c8bd-137">The number of profiles that you can export to DotDigital is dependent and limited on your contract with DotDigital.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="6c8bd-138">Поверителност и съответствие на данните</span><span class="sxs-lookup"><span data-stu-id="6c8bd-138">Data privacy and compliance</span></span>

<span data-ttu-id="6c8bd-139">Когато активирате Dynamics 365 Customer Insights, за да предавате данни на DotDigital, разрешавате прехвърляне на данни извън границата за съответствие за Dynamics 365 Customer Insights, включително потенциално чувствителни данни като Лични данни.</span><span class="sxs-lookup"><span data-stu-id="6c8bd-139">When you enable Dynamics 365 Customer Insights to transmit data to DotDigital, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="6c8bd-140">Microsoft ще прехвърли такива данни по ваше указание, но вие носите отговорност да гарантирате, че DotDigital отговаря на всички задължения за поверителност или сигурност, които може да имате.</span><span class="sxs-lookup"><span data-stu-id="6c8bd-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that DotDigital meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="6c8bd-141">За информация посетете [Декларация за поверителност Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="6c8bd-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="6c8bd-142">Вашият администратор на Dynamics 365 Customer Insights да премахнете това местоназначение за експортиране по всяко време, за да прекратите използването на тази функционалност.</span><span class="sxs-lookup"><span data-stu-id="6c8bd-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]