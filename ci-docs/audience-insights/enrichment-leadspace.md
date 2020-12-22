---
title: Обогатяване на фирмени профили с Leadspace за обогатяване от трети страни
description: Обща информация за обогатяването чрез Leadspace на трети страни.
ms.date: 11/24/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 1b5c6e46e8e424df83e855d81fc4dd7ecb394e3c
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668710"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="60874-103">Допълване на фирмени профили с Leadspace (преглед)</span><span class="sxs-lookup"><span data-stu-id="60874-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="60874-104">Leadspace е фирма за анализ и обработка на данни, която предоставя B2B платформа за данни на клиенти.</span><span class="sxs-lookup"><span data-stu-id="60874-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="60874-105">Тя дава възможност на фирмите да допълнят своите данни за клиенти с унифицирани потребителски профили.</span><span class="sxs-lookup"><span data-stu-id="60874-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="60874-106">Обогатяванията включват допълнителни атрибути, като размер на фирмата, местоположение, индустрия и др.</span><span class="sxs-lookup"><span data-stu-id="60874-106">Enrichments include additional attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="60874-107">Предварителни изисквания</span><span class="sxs-lookup"><span data-stu-id="60874-107">Prerequisites</span></span>

<span data-ttu-id="60874-108">За да конфигурирате Leadspace, трябва да бъдат изпълнени следните предварителни изисквания:</span><span class="sxs-lookup"><span data-stu-id="60874-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="60874-109">Имате активен лиценз за Leadspace и „вечен ключ” (наричан **Leadspace маркер**).</span><span class="sxs-lookup"><span data-stu-id="60874-109">You have an active Leadspace license and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="60874-110">Свържете се директно с [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) за подробности относно техния продукт.</span><span class="sxs-lookup"><span data-stu-id="60874-110">Contact directly [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) for details about their product.</span></span>
- <span data-ttu-id="60874-111">Имате разрешения за [Администратор](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="60874-111">You have [Administrator](permissions.md#administrator) permissions.</span></span>
- <span data-ttu-id="60874-112">Да имате [унифицирани потребителски профили](customer-profiles.md) за фирми.</span><span class="sxs-lookup"><span data-stu-id="60874-112">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>

## <a name="configuration"></a><span data-ttu-id="60874-113">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="60874-113">Configuration</span></span>

1. <span data-ttu-id="60874-114">В статията за аудиторията отидете на **Данни** > **Обогатяване**.</span><span class="sxs-lookup"><span data-stu-id="60874-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="60874-115">Изберете **Допълване на моите данни** в плочката на Leadspace.</span><span class="sxs-lookup"><span data-stu-id="60874-115">Select **Enrich my data** on the Leadspace tile.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="Екранна снимка на плочката Leadspace.":::

1. <span data-ttu-id="60874-117">Изберете **Първи стъпки** и след това въведете активен **Leadspace маркер** (вечен ключ).</span><span class="sxs-lookup"><span data-stu-id="60874-117">Select **Get Started** and then enter an active **Leadspace token** (perpetual key).</span></span> <span data-ttu-id="60874-118">Прегледайте и дайте своето съгласие за **Поверителност и съответствие на данните**, като изберете отметката **Приемам**.</span><span class="sxs-lookup"><span data-stu-id="60874-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="60874-119">Потвърдете и двата входа, като изберете **Свързване с Leadspace**.</span><span class="sxs-lookup"><span data-stu-id="60874-119">Confirm both inputs by selecting **Connect to Leadspace**.</span></span>

1. <span data-ttu-id="60874-120">Изберете **Данни от картата** и дефинирайте кои полета от унифицираните ви профили трябва да се използват за търсене на съответстващи фирмени данни от Leadspace.</span><span class="sxs-lookup"><span data-stu-id="60874-120">Select **Map data** and define which fields from your unified profiles should be used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="60874-121">Полето **Име на компания** е задължително.</span><span class="sxs-lookup"><span data-stu-id="60874-121">The **Name of company** field is required.</span></span> <span data-ttu-id="60874-122">За по-висока точност на съвпадение, до две други полета, **Уебсайт на компанията** и **Местоположение на фирмата**, може да се добави.</span><span class="sxs-lookup"><span data-stu-id="60874-122">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Панел за нанасяне на полето Leadspace.":::
   
1. <span data-ttu-id="60874-124">Изберете **Приложи**, за да завършите нанасянето на полето.</span><span class="sxs-lookup"><span data-stu-id="60874-124">Select **Apply** to complete the field mapping.</span></span>

1. <span data-ttu-id="60874-125">Изберете **Стартиране**, за да допълните фирмените профили.</span><span class="sxs-lookup"><span data-stu-id="60874-125">Select **Run** to enrich the company profiles.</span></span> <span data-ttu-id="60874-126">Колко време отнема обогатяването зависи от броя на унифицираните потребителски профили.</span><span class="sxs-lookup"><span data-stu-id="60874-126">How long an enrichment takes depends on the number of unified customer profiles.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="60874-127">Резултати от допълването</span><span class="sxs-lookup"><span data-stu-id="60874-127">Enrichment results</span></span>

<span data-ttu-id="60874-128">След като опресните обогатяването, можете да прегледате ново обогатените данни на компанията под [Моите обогатявания](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="60874-128">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="60874-129">Можете да намерите времето на последната актуализация и броя на допълнените профили.</span><span class="sxs-lookup"><span data-stu-id="60874-129">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="60874-130">Можете да получите достъп до подробен изглед на всеки допълнен профил, като изберете **Преглед на допълнените данни**.</span><span class="sxs-lookup"><span data-stu-id="60874-130">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="60874-131">За повече информация вижте [API на Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span><span class="sxs-lookup"><span data-stu-id="60874-131">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="60874-132">Следващи стъпки</span><span class="sxs-lookup"><span data-stu-id="60874-132">Next steps</span></span>

<span data-ttu-id="60874-133">Надградете допълнените клиентски данни.</span><span class="sxs-lookup"><span data-stu-id="60874-133">Build on top of your enriched customer data.</span></span> <span data-ttu-id="60874-134">Създайте [сегменти](segments.md), [мерки](measures.md) и дори [експортирайте данните](export-destinations.md), за да доставите персонализирано изживяване на клиентите си.</span><span class="sxs-lookup"><span data-stu-id="60874-134">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="60874-135">Поверителност и съответствие на данните</span><span class="sxs-lookup"><span data-stu-id="60874-135">Data privacy and compliance</span></span>

<span data-ttu-id="60874-136">Когато активирате Dynamics 365 Customer Insights, за да предавате данни на Leadspace, разрешавате прехвърляне на данни извън границата за съответствие за Dynamics 365 Customer Insights, включително потенциално чувствителни данни като Лични данни.</span><span class="sxs-lookup"><span data-stu-id="60874-136">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="60874-137">Microsoft ще прехвърли такива данни по ваше указание, но вие носите отговорност да гарантирате, че Leadspace отговаря на всички задължения за поверителност или сигурност, които може да имате.</span><span class="sxs-lookup"><span data-stu-id="60874-137">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="60874-138">За информация посетете [Декларация за поверителност Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="60874-138">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="60874-139">Вашият администратор на Dynamics 365 Customer Insights да премахнете това обогатяване по всяко време, за да прекратите използването на тази функционалност.</span><span class="sxs-lookup"><span data-stu-id="60874-139">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>