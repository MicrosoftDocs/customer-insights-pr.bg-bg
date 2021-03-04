---
title: Експортирайте данните от Customer Insights в SendGrid
description: Научете как да конфигурирате връзката с SendGrid.
ms.date: 12/08/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f16d69deb2a0b48270ed04f9b72f03056f20b619
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268719"
---
# <a name="connector-for-sendgrid-preview"></a><span data-ttu-id="f7d4c-103">Конектор за SendGrid (преглед)</span><span class="sxs-lookup"><span data-stu-id="f7d4c-103">Connector for SendGrid (preview)</span></span>

<span data-ttu-id="f7d4c-104">Експортирайте сегменти от унифицирани клиентски профили в списъци с контакти на SendGrid и ги използвайте за кампании и маркетинг по имейл в SendGrid.</span><span class="sxs-lookup"><span data-stu-id="f7d4c-104">Export segments of unified customer profiles to SendGrid contact lists and use them for campaigns and email marketing in SendGrid.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="f7d4c-105">Предварителни изисквания</span><span class="sxs-lookup"><span data-stu-id="f7d4c-105">Prerequisites</span></span>

-   <span data-ttu-id="f7d4c-106">Имате [Акаунт в SendGrid](https://sendgrid.com/) и съответните идентификационни данни на администратора.</span><span class="sxs-lookup"><span data-stu-id="f7d4c-106">You have a [SendGrid account](https://sendgrid.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="f7d4c-107">В SendGrid има съществуващи списъци с контакти и съответните идентификатори.</span><span class="sxs-lookup"><span data-stu-id="f7d4c-107">There are existing contact lists in SendGrid and the corresponding IDs.</span></span> <span data-ttu-id="f7d4c-108">За повече информация вижте [SendGrid – управление на контакти](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span><span class="sxs-lookup"><span data-stu-id="f7d4c-108">For more information, see [SendGrid - Manage contacts](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span></span>
-   <span data-ttu-id="f7d4c-109">Имате [конфигурирани сегменти](segments.md) в аналитични данни за аудитория.</span><span class="sxs-lookup"><span data-stu-id="f7d4c-109">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="f7d4c-110">Единните клиентски профили в експортираните сегменти съдържат поле, представляващо имейл адрес.</span><span class="sxs-lookup"><span data-stu-id="f7d4c-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-sendgrid"></a><span data-ttu-id="f7d4c-111">Свързване със SendGrid</span><span class="sxs-lookup"><span data-stu-id="f7d4c-111">Connect to SendGrid</span></span>

1. <span data-ttu-id="f7d4c-112">Отидете на **Администратор** > **Експортиране на дестинации**.</span><span class="sxs-lookup"><span data-stu-id="f7d4c-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="f7d4c-113">Под **SendGrid** изберете **Настройка**.</span><span class="sxs-lookup"><span data-stu-id="f7d4c-113">Under **SendGrid**, select **Set up**.</span></span>

1. <span data-ttu-id="f7d4c-114">Въведете разпознаваемо име за местоназначението за експортиране в полето **Показвано име**.</span><span class="sxs-lookup"><span data-stu-id="f7d4c-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/export-sendgrid.PNG" alt-text="Конфигурационен прозорец за експортиране на SendGrid.":::

1. <span data-ttu-id="f7d4c-116">Въведете своя **API ключ на SendGrid** [API ключ на SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span><span class="sxs-lookup"><span data-stu-id="f7d4c-116">Enter your **SendGrid API key** [SendGrid API key](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span></span>

1. <span data-ttu-id="f7d4c-117">Въведете своя **[ИД на списъка на SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span><span class="sxs-lookup"><span data-stu-id="f7d4c-117">Enter your **[SendGrid list ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span></span>

1. <span data-ttu-id="f7d4c-118">Изберете **Приемам**, за да потвърдите **Поверителност на данните и съответствие**.</span><span class="sxs-lookup"><span data-stu-id="f7d4c-118">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="f7d4c-119">Изберете **Свържете** за инициализиране на връзката с SendGrid.</span><span class="sxs-lookup"><span data-stu-id="f7d4c-119">Select **Connect** to initialize the connection to SendGrid.</span></span>

1. <span data-ttu-id="f7d4c-120">Изберете **Добавете себе си като потребител за експортиране** и предоставете вашите идентификационни данни на Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="f7d4c-120">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="f7d4c-121">Изберете **Напред**, за да конфигурирате експортирането.</span><span class="sxs-lookup"><span data-stu-id="f7d4c-121">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="f7d4c-122">Конфигуриране на конектор</span><span class="sxs-lookup"><span data-stu-id="f7d4c-122">Configure the connector</span></span>

1. <span data-ttu-id="f7d4c-123">В секцията **Съвпадение на данни** в полето **Имейл** изберете полето във вашия унифициран потребителски профил, което представлява имейл адреса на клиента.</span><span class="sxs-lookup"><span data-stu-id="f7d4c-123">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="f7d4c-124">Повторете същите стъпки за други незадължителни полета, като например **собствено име**, **фамилно име**, **Държава/регион**, **Щат**, **Град** и **Пощенски код**.</span><span class="sxs-lookup"><span data-stu-id="f7d4c-124">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Country/Region**, **State**, **City**, and **Post code**.</span></span>

1. <span data-ttu-id="f7d4c-125">Изберете сегментите, които искате да експортирате.</span><span class="sxs-lookup"><span data-stu-id="f7d4c-125">Select the segments you want to export.</span></span> <span data-ttu-id="f7d4c-126">Ние силно **препоръчваме да не експортирате повече от 100 000 потребителски профила общо** към SendGrid.</span><span class="sxs-lookup"><span data-stu-id="f7d4c-126">We strongly **recommend to not export more than 100'000 customer profiles in total** to SendGrid.</span></span> 

1. <span data-ttu-id="f7d4c-127">Изберете **Записване**.</span><span class="sxs-lookup"><span data-stu-id="f7d4c-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="f7d4c-128">Експортиране на данните</span><span class="sxs-lookup"><span data-stu-id="f7d4c-128">Export the data</span></span>

<span data-ttu-id="f7d4c-129">Можете да [експортирате данни при поискване](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="f7d4c-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="f7d4c-130">Експортирането също ще се изпълнява с всяко [планирано обновяване](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="f7d4c-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="f7d4c-131">Известни ограничения</span><span class="sxs-lookup"><span data-stu-id="f7d4c-131">Known limitations</span></span>

- <span data-ttu-id="f7d4c-132">Общо до 100'000 профила в SendGrid.</span><span class="sxs-lookup"><span data-stu-id="f7d4c-132">Up to 100'000 profiles in total to SendGrid.</span></span>
- <span data-ttu-id="f7d4c-133">Експортирането в SendGrid е ограничено до сегменти.</span><span class="sxs-lookup"><span data-stu-id="f7d4c-133">Exporting to SendGrid is limited to segments.</span></span>
- <span data-ttu-id="f7d4c-134">Експортирането на до 100 000 профила в SendGrid може да отнеме до няколко часа.</span><span class="sxs-lookup"><span data-stu-id="f7d4c-134">Exporting up to 100'000 profiles to SendGrid can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="f7d4c-135">Броят на профилите, които можете да експортирате в SendGrid, зависи и е ограничен от вашия договор с SendGrid.</span><span class="sxs-lookup"><span data-stu-id="f7d4c-135">The number of profiles that you can export to SendGrid is dependent and limited on your contract with SendGrid.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="f7d4c-136">Поверителност и съответствие на данните</span><span class="sxs-lookup"><span data-stu-id="f7d4c-136">Data privacy and compliance</span></span>

<span data-ttu-id="f7d4c-137">Когато активирате Dynamics 365 Customer Insights, за да предавате данни на SendGrid, разрешавате прехвърляне на данни извън границата за съответствие за Dynamics 365 Customer Insights, включително потенциално чувствителни данни като Лични данни.</span><span class="sxs-lookup"><span data-stu-id="f7d4c-137">When you enable Dynamics 365 Customer Insights to transmit data to SendGrid, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="f7d4c-138">Microsoft ще прехвърли такива данни по ваше указание, но вие носите отговорност да гарантирате, че SendGrid отговаря на всички задължения за поверителност или сигурност, които може да имате.</span><span class="sxs-lookup"><span data-stu-id="f7d4c-138">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that SendGrid meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="f7d4c-139">За информация посетете [Декларация за поверителност Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="f7d4c-139">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="f7d4c-140">Вашият администратор на Dynamics 365 Customer Insights да премахнете това местоназначение за експортиране по всяко време, за да прекратите използването на тази функционалност.</span><span class="sxs-lookup"><span data-stu-id="f7d4c-140">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]