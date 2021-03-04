---
title: Експортирайте данните от Customer Insights в Marketo
description: Научете как да конфигурирате връзката с Marketo.
ms.date: 11/12/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: e0245f2d01aabc86f43532822c056965ff7ae67a
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267068"
---
# <a name="connector-for-marketo-preview"></a><span data-ttu-id="12b3b-103">Конектор за Marketo (преглед)</span><span class="sxs-lookup"><span data-stu-id="12b3b-103">Connector for Marketo (preview)</span></span>

<span data-ttu-id="12b3b-104">Експортирайте сегменти на унифицирани клиентски профили, за да генерирате кампании, да предоставяте маркетинг по имейл и да използвате конкретни групи клиенти с Marketo.</span><span class="sxs-lookup"><span data-stu-id="12b3b-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="12b3b-105">Предварителни изисквания</span><span class="sxs-lookup"><span data-stu-id="12b3b-105">Prerequisites</span></span>

-   <span data-ttu-id="12b3b-106">Имате [Акаунт в Marketo](https://login.marketo.com/) и съответните идентификационни данни на администратора.</span><span class="sxs-lookup"><span data-stu-id="12b3b-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="12b3b-107">В Marketo има съществуващи списъци и съответните идентификатори.</span><span class="sxs-lookup"><span data-stu-id="12b3b-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="12b3b-108">За повече информация вижте [Списъци на Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="12b3b-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="12b3b-109">Имате [конфигурирани сегменти](segments.md).</span><span class="sxs-lookup"><span data-stu-id="12b3b-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="12b3b-110">Единните клиентски профили в експортираните сегменти съдържат поле, представляващо имейл адрес.</span><span class="sxs-lookup"><span data-stu-id="12b3b-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-marketo"></a><span data-ttu-id="12b3b-111">Свързване с Marketo</span><span class="sxs-lookup"><span data-stu-id="12b3b-111">Connect to Marketo</span></span>

1. <span data-ttu-id="12b3b-112">Отидете на **Администратор** > **Експортиране на дестинации**.</span><span class="sxs-lookup"><span data-stu-id="12b3b-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="12b3b-113">Под **Marketo** изберете **Настройка**.</span><span class="sxs-lookup"><span data-stu-id="12b3b-113">Under **Marketo**, select **Set up**.</span></span>

1. <span data-ttu-id="12b3b-114">Въведете разпознаваемо име за местоназначението за експортиране в полето **Показвано име**.</span><span class="sxs-lookup"><span data-stu-id="12b3b-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="12b3b-115">Въведете своя **[Идентификатор на клиент Marketo, тайна на клиента и име на хост REST Endpoint](https://developers.marketo.com/rest-api/authentication/)**.</span><span class="sxs-lookup"><span data-stu-id="12b3b-115">Enter your **[Marketo client ID, Client secret and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span>

1. <span data-ttu-id="12b3b-116">Въведете своя **[ИД на списъка на Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span><span class="sxs-lookup"><span data-stu-id="12b3b-116">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span></span> 

1. <span data-ttu-id="12b3b-117">Изберете **Съгласен съм**, за да потвърдите **Поверителност и съответствие на данните** и изберете **Свържете** за инициализиране на връзката с Marketo.</span><span class="sxs-lookup"><span data-stu-id="12b3b-117">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="12b3b-118">Изберете **Добавете себе си като потребител за експортиране** и предоставете вашите идентификационни данни на Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="12b3b-118">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-connect-marketo.png" alt-text="Експортиране на екранна снимка за връзка с Marketo":::

1. <span data-ttu-id="12b3b-120">Изберете **Напред**, за да конфигурирате експортирането.</span><span class="sxs-lookup"><span data-stu-id="12b3b-120">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="12b3b-121">Конфигуриране на конектор</span><span class="sxs-lookup"><span data-stu-id="12b3b-121">Configure the connector</span></span>

1. <span data-ttu-id="12b3b-122">В секцията **Съвпадение на данни** в полето **Имейл** изберете полето във вашия унифициран потребителски профил, което представлява имейл адреса на клиента.</span><span class="sxs-lookup"><span data-stu-id="12b3b-122">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="12b3b-123">По желание можете да експортирате **Собствено име**, **Фамилно име**, **Град**, **Щат** и **Държава/регион** като допълнителни полета за създаване на по-персонализирани имейли.</span><span class="sxs-lookup"><span data-stu-id="12b3b-123">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  as additional fields to create more personalized emails.</span></span> <span data-ttu-id="12b3b-124">Изберете **Добавяне на атрибут** за нанасяне на тези полета.</span><span class="sxs-lookup"><span data-stu-id="12b3b-124">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="12b3b-125">Изберете сегментите, които искате да експортирате.</span><span class="sxs-lookup"><span data-stu-id="12b3b-125">Select the segments you want to export.</span></span> <span data-ttu-id="12b3b-126">Можете да експортирате до 1 милион потребителски профила общо в Marketo.</span><span class="sxs-lookup"><span data-stu-id="12b3b-126">You can export up to 1 million customer profiles in total to Marketo.</span></span>

   :::image type="content" source="media/export-segment-marketo.png" alt-text="Изберете полета и сегменти, които да експортирате в Marketo":::

1. <span data-ttu-id="12b3b-128">Изберете **Записване**.</span><span class="sxs-lookup"><span data-stu-id="12b3b-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="12b3b-129">Експортиране на данните</span><span class="sxs-lookup"><span data-stu-id="12b3b-129">Export the data</span></span>

<span data-ttu-id="12b3b-130">Можете да [експортирате данни при поискване](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="12b3b-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="12b3b-131">Експортирането също ще се изпълнява с всяко [планирано обновяване](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="12b3b-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="12b3b-132">В Marketo вече можете да намерите своите сегменти под [Списъци на Marketo](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="12b3b-132">In Marketo, you can now find your segments under [Marketo lists](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="12b3b-133">Известни ограничения</span><span class="sxs-lookup"><span data-stu-id="12b3b-133">Known limitations</span></span>

- <span data-ttu-id="12b3b-134">До 1 милион профила на износ към Marketo.</span><span class="sxs-lookup"><span data-stu-id="12b3b-134">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="12b3b-135">Експортирането в Marketo е ограничено до сегменти.</span><span class="sxs-lookup"><span data-stu-id="12b3b-135">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="12b3b-136">Експортирането на сегменти с общо 1 милион профила може да отнеме до 3 часа.</span><span class="sxs-lookup"><span data-stu-id="12b3b-136">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="12b3b-137">Броят на профилите, които можете да експортирате в Marketo, зависи и е ограничен от вашия договор с Marketo.</span><span class="sxs-lookup"><span data-stu-id="12b3b-137">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="12b3b-138">Поверителност и съответствие на данните</span><span class="sxs-lookup"><span data-stu-id="12b3b-138">Data privacy and compliance</span></span>

<span data-ttu-id="12b3b-139">Когато активирате Dynamics 365 Customer Insights, за да предавате данни на Marketo, разрешавате прехвърляне на данни извън границата за съответствие за Dynamics 365 Customer Insights, включително потенциално чувствителни данни като Лични данни.</span><span class="sxs-lookup"><span data-stu-id="12b3b-139">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="12b3b-140">Microsoft ще прехвърли такива данни по ваше указание, но вие носите отговорност да гарантирате, че Marketo отговаря на всички задължения за поверителност или сигурност, които може да имате.</span><span class="sxs-lookup"><span data-stu-id="12b3b-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="12b3b-141">За информация посетете [Декларация за поверителност Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="12b3b-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="12b3b-142">Вашият администратор на Dynamics 365 Customer Insights да премахнете това местоназначение за експортиране по всяко време, за да прекратите използването на тази функционалност.</span><span class="sxs-lookup"><span data-stu-id="12b3b-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]