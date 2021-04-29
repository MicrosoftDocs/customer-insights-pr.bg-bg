---
title: Експортирайте данните от Customer Insights в Google Ads
description: Научете как да конфигурирате връзката и да експортирате в Google Ads.
ms.date: 03/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: f4c094e486577d00d8c0c64e8527829820b335f6
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759680"
---
# <a name="export-segments-to-google-ads-preview"></a><span data-ttu-id="bd6b0-103">Експортиране на сегменти в Google Ads (преглед)</span><span class="sxs-lookup"><span data-stu-id="bd6b0-103">Export segments to Google Ads (preview)</span></span>

<span data-ttu-id="bd6b0-104">Експортирайте сегменти на унифицирани клиентски профили в списъци с аудитории на Google Ads и ги използвайте за рекламиране в Google Search, Gmail, YouTube и Google Display Network.</span><span class="sxs-lookup"><span data-stu-id="bd6b0-104">Export segments of unified customer profiles to Google Ads audience list and use them to advertise on Google Search, Gmail, YouTube, and Google Display Network.</span></span> 

## <a name="prerequisites-for-connection"></a><span data-ttu-id="bd6b0-105">Предварителни изисквания за връзка</span><span class="sxs-lookup"><span data-stu-id="bd6b0-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="bd6b0-106">Имате [Акаунт в Google Ads](https://ads.google.com/) и съответните идентификационни данни на администратора.</span><span class="sxs-lookup"><span data-stu-id="bd6b0-106">You have a [Google Ads account](https://ads.google.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="bd6b0-107">Имате [одобрен маркер за разработчик в Google Ads](https://developers.google.com/google-ads/api/docs/first-call/dev-token)</span><span class="sxs-lookup"><span data-stu-id="bd6b0-107">You have an [approved Google Ads Developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)</span></span> 
-   <span data-ttu-id="bd6b0-108">Изпълнявате изискванията на [правилата за съвпадение на клиенти](https://support.google.com/adspolicy/answer/6299717)</span><span class="sxs-lookup"><span data-stu-id="bd6b0-108">You fulfill the requirements of the [Customer Match Policy](https://support.google.com/adspolicy/answer/6299717)</span></span>
-   <span data-ttu-id="bd6b0-109">Изпълнявате изискванията на [размерите на списъка за повторен маркетинг](https://support.google.com/google-ads/answer/7558048)</span><span class="sxs-lookup"><span data-stu-id="bd6b0-109">You fulfill the requirements of the [remarketing list sizes](https://support.google.com/google-ads/answer/7558048)</span></span> 

-   <span data-ttu-id="bd6b0-110">В Google Ads има съществуващи аудитории и съответните идентификатори.</span><span class="sxs-lookup"><span data-stu-id="bd6b0-110">There are existing audiences in Google Ads and the corresponding IDs.</span></span> <span data-ttu-id="bd6b0-111">За повече информация вижте [аудитории на Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span><span class="sxs-lookup"><span data-stu-id="bd6b0-111">For more information, see [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span></span>
-   <span data-ttu-id="bd6b0-112">Имате [конфигурирани сегменти](segments.md)</span><span class="sxs-lookup"><span data-stu-id="bd6b0-112">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="bd6b0-113">Единните клиентски профили в експортираните сегменти съдържат полета, представляващи имейл адрес, собствено име и фамилно име</span><span class="sxs-lookup"><span data-stu-id="bd6b0-113">Unified customer profiles in the exported segments contain fields representing an email address, first name, and last name</span></span>

## <a name="known-limitations"></a><span data-ttu-id="bd6b0-114">Известни ограничения</span><span class="sxs-lookup"><span data-stu-id="bd6b0-114">Known limitations</span></span>

- <span data-ttu-id="bd6b0-115">До 1 милион профила на износ към Google Ads.</span><span class="sxs-lookup"><span data-stu-id="bd6b0-115">Up to 1 million profiles per export to Google Ads.</span></span>
- <span data-ttu-id="bd6b0-116">Експортирането в Google Ads е ограничено до сегменти.</span><span class="sxs-lookup"><span data-stu-id="bd6b0-116">Exporting to Google Ads is limited to segments.</span></span>
- <span data-ttu-id="bd6b0-117">Експортирането на сегменти с общо 1 милион профила може да отнеме до 5 минути поради ограничения от страна на доставчика.</span><span class="sxs-lookup"><span data-stu-id="bd6b0-117">Exporting segments with a total of 1 million profiles can take up to 5 minutes because of limitations on the provider side.</span></span> 
- <span data-ttu-id="bd6b0-118">Съответствието в Google Ads може да отнеме до 48 часа.</span><span class="sxs-lookup"><span data-stu-id="bd6b0-118">The matching in Google Ads can take up to 48 hours.</span></span>

## <a name="set-up-connection-to-google-ads"></a><span data-ttu-id="bd6b0-119">Настройване на връзка с Google Ads</span><span class="sxs-lookup"><span data-stu-id="bd6b0-119">Set up connection to Google Ads</span></span>

1. <span data-ttu-id="bd6b0-120">Отидете на **Администратор** > **Връзки**.</span><span class="sxs-lookup"><span data-stu-id="bd6b0-120">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="bd6b0-121">Изберете **Добавяне на връзка** и изберете **Google Ads** за конфигуриране на връзката.</span><span class="sxs-lookup"><span data-stu-id="bd6b0-121">Select **Add connection** and choose **Google Ads** to configure the connection.</span></span>

1. <span data-ttu-id="bd6b0-122">Въведете разпознаваемо име за връзката в полето **Показвано име**.</span><span class="sxs-lookup"><span data-stu-id="bd6b0-122">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="bd6b0-123">Показваното име и типът описват тази връзка.</span><span class="sxs-lookup"><span data-stu-id="bd6b0-123">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="bd6b0-124">Препоръчваме да изберете име, което обяснява целта на връзката.</span><span class="sxs-lookup"><span data-stu-id="bd6b0-124">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="bd6b0-125">Изберете кой може да използва тази връзка.</span><span class="sxs-lookup"><span data-stu-id="bd6b0-125">Choose who can use this connection.</span></span> <span data-ttu-id="bd6b0-126">Ако не предприемете нищо, по подразбиране ще е Администратори.</span><span class="sxs-lookup"><span data-stu-id="bd6b0-126">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="bd6b0-127">За повече информация вижте [Разрешаване на сътрудници да използват връзка за експортиране](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="bd6b0-127">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="bd6b0-128">Въведете своя **[ИД на клиента в Google Ads](https://support.google.com/google-ads/answer/1704344)**.</span><span class="sxs-lookup"><span data-stu-id="bd6b0-128">Enter your **[Google Ads customer ID](https://support.google.com/google-ads/answer/1704344)**.</span></span>

1. <span data-ttu-id="bd6b0-129">Въведете своя **[Одобрен от Google Ads маркер за програмисти](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span><span class="sxs-lookup"><span data-stu-id="bd6b0-129">Enter your **[Google Ads approved developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span></span>

1. <span data-ttu-id="bd6b0-130">Изберете **Приемам**, за да потвърдите **Поверителност на данните и съответствие**.</span><span class="sxs-lookup"><span data-stu-id="bd6b0-130">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="bd6b0-131">Изберете **Удостоверете с Google Ads** и предоставете вашите идентификационни данни на Google Ads.</span><span class="sxs-lookup"><span data-stu-id="bd6b0-131">Select **Authenticate with Google Ads** and provide your Google Ads credentials.</span></span>

1. <span data-ttu-id="bd6b0-132">Изберете **Добавете себе си като потребител за експортиране** и предоставете вашите идентификационни данни на Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="bd6b0-132">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="bd6b0-133">Изберете **Записване**, за да завършите връзката.</span><span class="sxs-lookup"><span data-stu-id="bd6b0-133">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="bd6b0-134">Конфигуриране на експортиране</span><span class="sxs-lookup"><span data-stu-id="bd6b0-134">Configure an export</span></span>

<span data-ttu-id="bd6b0-135">Можете да конфигурирате това експортиране, ако имате достъп до връзка от този тип.</span><span class="sxs-lookup"><span data-stu-id="bd6b0-135">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="bd6b0-136">За повече информация вижте [Разрешения, необходими за конфигуриране на експортиране](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="bd6b0-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="bd6b0-137">Отидете на **Данни** > **Експортиране**.</span><span class="sxs-lookup"><span data-stu-id="bd6b0-137">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="bd6b0-138">За да създадете ново експортиране, изберете **Добавяне на местоназначение**.</span><span class="sxs-lookup"><span data-stu-id="bd6b0-138">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="bd6b0-139">В полето **Връзка за експортиране** изберете връзка от секцията Google Ads.</span><span class="sxs-lookup"><span data-stu-id="bd6b0-139">In the **Connection for export** field, choose a connection from the Google Ads section.</span></span> <span data-ttu-id="bd6b0-140">Ако не виждате името на тази секция, няма достъпни за вас връзки от този тип.</span><span class="sxs-lookup"><span data-stu-id="bd6b0-140">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="bd6b0-141">Въведете своя **[ИД на аудиторията на Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** и изберете **Свързване** за инициализиране на връзката с Google Ads.</span><span class="sxs-lookup"><span data-stu-id="bd6b0-141">Enter your **[Google Ads audience ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** and select **Connect** to initialize the connection to Google Ads.</span></span>

1. <span data-ttu-id="bd6b0-142">В секцията **Съвпадение на данни** в полето **Имейл** изберете полето във вашия унифициран потребителски профил, което представлява имейл адреса на клиента.</span><span class="sxs-lookup"><span data-stu-id="bd6b0-142">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="bd6b0-143">Повторете същите стъпки за полетата **Собствено име** и **фамилно име**.</span><span class="sxs-lookup"><span data-stu-id="bd6b0-143">Repeat the same steps for \*\*First name" and **Last name** fields.</span></span>

1. <span data-ttu-id="bd6b0-144">Изберете сегментите, които искате да експортирате.</span><span class="sxs-lookup"><span data-stu-id="bd6b0-144">Select the segments you want to export.</span></span> <span data-ttu-id="bd6b0-145">Можете да експортирате до 1 милион потребителски профила общо в Google Ads.</span><span class="sxs-lookup"><span data-stu-id="bd6b0-145">You can export up to 1 million customer profiles in total to Google Ads.</span></span>

<span data-ttu-id="bd6b0-146">Запазването на експортиране не го изпълнява незабавно.</span><span class="sxs-lookup"><span data-stu-id="bd6b0-146">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="bd6b0-147">Експортирането се изпълнява с всяко [планирано обновяване](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="bd6b0-147">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="bd6b0-148">Може също [да експортирате данни при поискване](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="bd6b0-148">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="bd6b0-149">Поверителност и съответствие на данните</span><span class="sxs-lookup"><span data-stu-id="bd6b0-149">Data privacy and compliance</span></span>

<span data-ttu-id="bd6b0-150">Когато активирате Dynamics 365 Customer Insights, за да предавате данни на Google Ads, разрешавате прехвърляне на данни извън границата за съответствие за Dynamics 365 Customer Insights, включително потенциално чувствителни данни като Лични данни.</span><span class="sxs-lookup"><span data-stu-id="bd6b0-150">When you enable Dynamics 365 Customer Insights to transmit data to Google Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="bd6b0-151">Microsoft ще прехвърли такива данни по ваше указание, но вие носите отговорност да гарантирате, че Google Ads отговаря на всички задължения за поверителност или сигурност, които може да имате.</span><span class="sxs-lookup"><span data-stu-id="bd6b0-151">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Google Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="bd6b0-152">За информация посетете [Декларация за поверителност Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="bd6b0-152">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="bd6b0-153">Вашият администратор на Dynamics 365 Customer Insights да премахнете това местоназначение за експортиране по всяко време, за да прекратите използването на тази функционалност.</span><span class="sxs-lookup"><span data-stu-id="bd6b0-153">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
