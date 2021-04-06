---
title: Обогатяване на фирмени профили с Leadspace за обогатяване от трети страни
description: Обща информация за обогатяването чрез Leadspace на трети страни.
ms.date: 11/24/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 41c56aece043c2d7658fd2655713e1e98775edec
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597636"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="3c166-103">Допълване на фирмени профили с Leadspace (преглед)</span><span class="sxs-lookup"><span data-stu-id="3c166-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="3c166-104">Leadspace е фирма за анализ и обработка на данни, която предоставя B2B платформа за данни на клиенти.</span><span class="sxs-lookup"><span data-stu-id="3c166-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="3c166-105">Тя дава възможност на фирмите да допълнят своите данни за клиенти с унифицирани потребителски профили.</span><span class="sxs-lookup"><span data-stu-id="3c166-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="3c166-106">Обогатяванията включват допълнителни атрибути, като размер на фирмата, местоположение, индустрия и др.</span><span class="sxs-lookup"><span data-stu-id="3c166-106">Enrichments include additional attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3c166-107">Предварителни изисквания</span><span class="sxs-lookup"><span data-stu-id="3c166-107">Prerequisites</span></span>

<span data-ttu-id="3c166-108">За да конфигурирате Leadspace, трябва да бъдат изпълнени следните предварителни изисквания:</span><span class="sxs-lookup"><span data-stu-id="3c166-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="3c166-109">Имате активен лиценз за Leadspace и „вечен ключ” (наричан **Leadspace маркер**).</span><span class="sxs-lookup"><span data-stu-id="3c166-109">You have an active Leadspace license and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="3c166-110">Свържете се директно с [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) за подробности относно техния продукт.</span><span class="sxs-lookup"><span data-stu-id="3c166-110">Contact directly [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) for details about their product.</span></span>
- <span data-ttu-id="3c166-111">Имате разрешения за [Администратор](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="3c166-111">You have [Administrator](permissions.md#administrator) permissions.</span></span>
- <span data-ttu-id="3c166-112">Да имате [унифицирани потребителски профили](customer-profiles.md) за фирми.</span><span class="sxs-lookup"><span data-stu-id="3c166-112">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>

## <a name="configuration"></a><span data-ttu-id="3c166-113">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="3c166-113">Configuration</span></span>

1. <span data-ttu-id="3c166-114">В статията за аудиторията отидете на **Данни** > **Обогатяване**.</span><span class="sxs-lookup"><span data-stu-id="3c166-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="3c166-115">Изберете **Допълване на моите данни** в плочката на Leadspace.</span><span class="sxs-lookup"><span data-stu-id="3c166-115">Select **Enrich my data** on the Leadspace tile.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="Екранна снимка на плочката Leadspace.":::

1. <span data-ttu-id="3c166-117">Изберете **Първи стъпки** и след това въведете активен **Leadspace маркер** (вечен ключ).</span><span class="sxs-lookup"><span data-stu-id="3c166-117">Select **Get Started** and then enter an active **Leadspace token** (perpetual key).</span></span> <span data-ttu-id="3c166-118">Прегледайте и дайте своето съгласие за **Поверителност и съответствие на данните**, като изберете отметката **Приемам**.</span><span class="sxs-lookup"><span data-stu-id="3c166-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="3c166-119">Потвърдете и двата входа, като изберете **Свързване с Leadspace**.</span><span class="sxs-lookup"><span data-stu-id="3c166-119">Confirm both inputs by selecting **Connect to Leadspace**.</span></span>

1. <span data-ttu-id="3c166-120">Изберете **Нанасяне на данни** и изберете набора от данни, който искате да обогатите с фирмени данни от Leadspace.</span><span class="sxs-lookup"><span data-stu-id="3c166-120">Select **Map data** and choose the data set you want to enrich with company data from Leadspace.</span></span> <span data-ttu-id="3c166-121">Можете да изберете *Клиент* обект, за да обогатите всичките си клиентски профили или да изберете сегментен обект, за да обогатите само клиентски профили, съдържащи се в този сегмент.</span><span class="sxs-lookup"><span data-stu-id="3c166-121">You can select the *Customer* entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

   :::image type="content" source="media/enrichment-leadspace-select-segment.png" alt-text="Изберете между потребителски профил и обогатяване на сегменти.":::

1. <span data-ttu-id="3c166-123">Щракнете върху **Напред** и дефинирайте кои полета от унифицираните ви профили трябва да се използват за търсене на съответстващи фирмени данни от Leadspace.</span><span class="sxs-lookup"><span data-stu-id="3c166-123">Click **Next** and define which fields from your unified profiles should be used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="3c166-124">Полето **Име на компания** е задължително.</span><span class="sxs-lookup"><span data-stu-id="3c166-124">The **Name of company** field is required.</span></span> <span data-ttu-id="3c166-125">За по-висока точност на съвпадение, до две други полета, **Уебсайт на компанията** и **Местоположение на фирмата**, може да се добави.</span><span class="sxs-lookup"><span data-stu-id="3c166-125">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Панел за нанасяне на полето Leadspace.":::
   
1. <span data-ttu-id="3c166-127">Изберете **Приложи**, за да завършите нанасянето на полето.</span><span class="sxs-lookup"><span data-stu-id="3c166-127">Select **Apply** to complete the field mapping.</span></span>

1. <span data-ttu-id="3c166-128">Изберете **Стартиране**, за да допълните фирмените профили.</span><span class="sxs-lookup"><span data-stu-id="3c166-128">Select **Run** to enrich the company profiles.</span></span> <span data-ttu-id="3c166-129">Колко време отнема обогатяването зависи от броя на унифицираните потребителски профили.</span><span class="sxs-lookup"><span data-stu-id="3c166-129">How long an enrichment takes depends on the number of unified customer profiles.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="3c166-130">Резултати от допълването</span><span class="sxs-lookup"><span data-stu-id="3c166-130">Enrichment results</span></span>

<span data-ttu-id="3c166-131">След като опресните обогатяването, можете да прегледате ново обогатените данни на компанията под [Моите обогатявания](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="3c166-131">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="3c166-132">Можете да намерите времето на последната актуализация и броя на допълнените профили.</span><span class="sxs-lookup"><span data-stu-id="3c166-132">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="3c166-133">Можете да получите достъп до подробен изглед на всеки допълнен профил, като изберете **Преглед на допълнените данни**.</span><span class="sxs-lookup"><span data-stu-id="3c166-133">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="3c166-134">За повече информация вижте [API на Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span><span class="sxs-lookup"><span data-stu-id="3c166-134">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="3c166-135">Следващи стъпки</span><span class="sxs-lookup"><span data-stu-id="3c166-135">Next steps</span></span>

<span data-ttu-id="3c166-136">Надградете допълнените клиентски данни.</span><span class="sxs-lookup"><span data-stu-id="3c166-136">Build on top of your enriched customer data.</span></span> <span data-ttu-id="3c166-137">Създайте [сегменти](segments.md), [мерки](measures.md) и дори [експортирайте данните](export-destinations.md), за да доставите персонализирано изживяване на клиентите си.</span><span class="sxs-lookup"><span data-stu-id="3c166-137">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="3c166-138">Поверителност и съответствие на данните</span><span class="sxs-lookup"><span data-stu-id="3c166-138">Data privacy and compliance</span></span>

<span data-ttu-id="3c166-139">Когато активирате Dynamics 365 Customer Insights, за да предавате данни на Leadspace, разрешавате прехвърляне на данни извън границата за съответствие за Dynamics 365 Customer Insights, включително потенциално чувствителни данни като Лични данни.</span><span class="sxs-lookup"><span data-stu-id="3c166-139">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="3c166-140">Microsoft ще прехвърли такива данни по ваше указание, но вие носите отговорност да гарантирате, че Leadspace отговаря на всички задължения за поверителност или сигурност, които може да имате.</span><span class="sxs-lookup"><span data-stu-id="3c166-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="3c166-141">За информация посетете [Декларация за поверителност Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="3c166-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="3c166-142">Вашият администратор на Dynamics 365 Customer Insights да премахнете това обогатяване по всяко време, за да прекратите използването на тази функционалност.</span><span class="sxs-lookup"><span data-stu-id="3c166-142">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]