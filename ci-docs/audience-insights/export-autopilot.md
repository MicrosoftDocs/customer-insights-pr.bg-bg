---
title: Експортирайте данните от Customer Insights в Autopilot
description: Научете как да конфигурирате връзката с Autopilot.
ms.date: 12/08/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d039c4afd84eaad942d214d4e6fb8ef7b1ec72a
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596113"
---
# <a name="connector-for-autopilot-preview"></a><span data-ttu-id="259da-103">Конектор за Autopilot (преглед)</span><span class="sxs-lookup"><span data-stu-id="259da-103">Connector for Autopilot (preview)</span></span>

<span data-ttu-id="259da-104">Експортирайте сегменти от унифицирани клиентски профили в Autopilot и ги използвайте за маркетинг по имейл в Autopilot.</span><span class="sxs-lookup"><span data-stu-id="259da-104">Export segments of unified customer profiles to Autopilot and use them for email marketing in Autopilot.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="259da-105">Предварителни изисквания</span><span class="sxs-lookup"><span data-stu-id="259da-105">Prerequisites</span></span>

-   <span data-ttu-id="259da-106">Имате [Акаунт в Autopilot](https://www.autopilothq.com/) и съответните идентификационни данни на администратора.</span><span class="sxs-lookup"><span data-stu-id="259da-106">You have an [Autopilot account](https://www.autopilothq.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="259da-107">Имате [конфигурирани сегменти](segments.md) в аналитични данни за аудитория.</span><span class="sxs-lookup"><span data-stu-id="259da-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="259da-108">Единните клиентски профили в експортираните сегменти съдържат поле, представляващо имейл адрес.</span><span class="sxs-lookup"><span data-stu-id="259da-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-autopilot"></a><span data-ttu-id="259da-109">Свързване с Autopilot</span><span class="sxs-lookup"><span data-stu-id="259da-109">Connect to Autopilot</span></span>

1. <span data-ttu-id="259da-110">Отидете на **Администратор** > **Експортиране на дестинации**.</span><span class="sxs-lookup"><span data-stu-id="259da-110">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="259da-111">Под **Autopilot** изберете **Настройка**.</span><span class="sxs-lookup"><span data-stu-id="259da-111">Under **Autopilot**, select **Set up**.</span></span>

1. <span data-ttu-id="259da-112">Въведете разпознаваемо име за местоназначението за експортиране в полето **Показвано име**.</span><span class="sxs-lookup"><span data-stu-id="259da-112">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/export-autopilot.PNG" alt-text="Конфигурационен прозорец за връзка с Autopilot.":::

1. <span data-ttu-id="259da-114">Въведете своя **API ключ за Autopilot** [API ключ за Autopilot](https://autopilot.docs.apiary.io/#).</span><span class="sxs-lookup"><span data-stu-id="259da-114">Enter your **Autopilot API key** [Autopilot API key](https://autopilot.docs.apiary.io/#).</span></span>

1. <span data-ttu-id="259da-115">Изберете **Приемам**, за да потвърдите **Поверителност на данните и съответствие**.</span><span class="sxs-lookup"><span data-stu-id="259da-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="259da-116">Изберете **Свържете** за инициализиране на връзката с Autopilot.</span><span class="sxs-lookup"><span data-stu-id="259da-116">Select **Connect** to initialize the connection to Autopilot.</span></span>

1. <span data-ttu-id="259da-117">Изберете **Добавете себе си като потребител за експортиране** и предоставете вашите идентификационни данни на Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="259da-117">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="259da-118">Изберете **Напред**, за да конфигурирате експортирането.</span><span class="sxs-lookup"><span data-stu-id="259da-118">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="259da-119">Конфигуриране на конектор</span><span class="sxs-lookup"><span data-stu-id="259da-119">Configure the connector</span></span>

1. <span data-ttu-id="259da-120">В секцията **Съвпадение на данни** в полето **Имейл** изберете полето във вашия унифициран потребителски профил, което представлява имейл адреса на клиента.</span><span class="sxs-lookup"><span data-stu-id="259da-120">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="259da-121">Повторете същите стъпки за други незадължителни полета, като например **собствено име**, **фамилно име**.</span><span class="sxs-lookup"><span data-stu-id="259da-121">Repeat the same steps for other optional fields such as **First name**, **Last name**.</span></span>

1. <span data-ttu-id="259da-122">Изберете сегментите, които искате да експортирате.</span><span class="sxs-lookup"><span data-stu-id="259da-122">Select the segments you want to export.</span></span> <span data-ttu-id="259da-123">Ние силно **препоръчваме да не експортирате повече от 100 000 потребителски профила общо** към Autopilot.</span><span class="sxs-lookup"><span data-stu-id="259da-123">We strongly **recommend to not export more than 100'000 customer profiles in total** to Autopilot.</span></span> 

1. <span data-ttu-id="259da-124">Изберете **Записване**.</span><span class="sxs-lookup"><span data-stu-id="259da-124">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="259da-125">Експортиране на данните</span><span class="sxs-lookup"><span data-stu-id="259da-125">Export the data</span></span>

<span data-ttu-id="259da-126">Можете да [експортирате данни при поискване](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="259da-126">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="259da-127">Експортирането също ще се изпълнява с всяко [планирано обновяване](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="259da-127">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="259da-128">Известни ограничения</span><span class="sxs-lookup"><span data-stu-id="259da-128">Known limitations</span></span>

- <span data-ttu-id="259da-129">Можете да експортирате до 100 000 профила общо в Autopilot.</span><span class="sxs-lookup"><span data-stu-id="259da-129">You can export up to 100'000 profiles in total to Autopilot.</span></span>
- <span data-ttu-id="259da-130">Експортирането в Autopilot е ограничено до сегменти.</span><span class="sxs-lookup"><span data-stu-id="259da-130">Exporting to Autopilot is limited to segments.</span></span>
- <span data-ttu-id="259da-131">Експортирането на до 100 000 профила в Autopilot може да отнеме до няколко часа.</span><span class="sxs-lookup"><span data-stu-id="259da-131">Exporting up to 100'000 profiles to Autopilot can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="259da-132">Броят на профилите, които можете да експортирате в Autopilot, зависи и е ограничен от вашия договор с Autopilot.</span><span class="sxs-lookup"><span data-stu-id="259da-132">The number of profiles that you can export to Autopilot is dependent and limited on your contract with Autopilot.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="259da-133">Поверителност и съответствие на данните</span><span class="sxs-lookup"><span data-stu-id="259da-133">Data privacy and compliance</span></span>

<span data-ttu-id="259da-134">Когато активирате Dynamics 365 Customer Insights, за да предавате данни на Autopilot, разрешавате прехвърляне на данни извън границата за съответствие за Dynamics 365 Customer Insights, включително потенциално чувствителни данни като Лични данни.</span><span class="sxs-lookup"><span data-stu-id="259da-134">When you enable Dynamics 365 Customer Insights to transmit data to Autopilot, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="259da-135">Microsoft ще прехвърли такива данни по ваше указание, но вие носите отговорност да гарантирате, че Autopilot отговаря на всички задължения за поверителност или сигурност, които може да имате.</span><span class="sxs-lookup"><span data-stu-id="259da-135">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Autopilot meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="259da-136">За информация посетете [Декларация за поверителност Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="259da-136">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="259da-137">Вашият администратор на Dynamics 365 Customer Insights да премахнете това местоназначение за експортиране по всяко време, за да прекратите използването на тази функционалност.</span><span class="sxs-lookup"><span data-stu-id="259da-137">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]