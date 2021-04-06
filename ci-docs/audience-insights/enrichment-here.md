---
title: Обогатяване с помощта на HERE Technologies за обогатяване от трети страни
description: Обща информация за обогатяването чрез HERE Technologies на трети страни.
ms.date: 12/10/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 8e8d6bfea4e0df54682501f60759c24c893444af
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597728"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="e34f0-103">Обогатяване на потребителски профили с HERE Technologies (преглед)</span><span class="sxs-lookup"><span data-stu-id="e34f0-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="e34f0-104">HERE Technologies е компания за платформи за местоположение, която предоставя данни и услуги, ориентирани към местоположението.</span><span class="sxs-lookup"><span data-stu-id="e34f0-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="e34f0-105">С услугите за обогатяване на данни от HERE Technologies можете да изградите по-точно разбиране на местоположението на вашите клиенти с нормализиране на адреса, извличане на географска ширина и дължина и др.</span><span class="sxs-lookup"><span data-stu-id="e34f0-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e34f0-106">Предварителни изисквания</span><span class="sxs-lookup"><span data-stu-id="e34f0-106">Prerequisites</span></span>

<span data-ttu-id="e34f0-107">За да конфигурирате обогатявания на HERE Technologies, трябва да са изпълнени следните предпоставки:</span><span class="sxs-lookup"><span data-stu-id="e34f0-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="e34f0-108">Трябва да имате активен абонамент за HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="e34f0-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="e34f0-109">За да получите абонамент, можете да се [регистрирайте се тук](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) или [да се свържете с HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) директно.</span><span class="sxs-lookup"><span data-stu-id="e34f0-109">To get a subscription, you can [sign-up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="e34f0-110">Научете повече за обогатяване на местоположението на HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="e34f0-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="e34f0-111">Имате ключа за API на HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="e34f0-111">You have the HERE Technologies API key.</span></span>

- <span data-ttu-id="e34f0-112">Имате разрешения за [Администратор](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="e34f0-112">You have [Administrator](permissions.md#administrator) permissions.</span></span>

## <a name="configuration"></a><span data-ttu-id="e34f0-113">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="e34f0-113">Configuration</span></span>

1. <span data-ttu-id="e34f0-114">Отидете в **Данни** > **Допълване**.</span><span class="sxs-lookup"><span data-stu-id="e34f0-114">Go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="e34f0-115">Изберете **Обогати данните ми** в плочката на HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="e34f0-115">Select **Enrich my data** on the HERE Technologies tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e34f0-116">![Плочка на HERE Technologies](media/HERE-tile.png "Плочка на HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="e34f0-116">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="e34f0-117">Въведете активен **API ключ на HERE Technologies**.</span><span class="sxs-lookup"><span data-stu-id="e34f0-117">Enter an active **HERE Technologies API key**.</span></span> <span data-ttu-id="e34f0-118">Прегледайте и дайте своето съгласие за **Поверителност и съответствие на данните**, като изберете отметката **Приемам**.</span><span class="sxs-lookup"><span data-stu-id="e34f0-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> 

1. <span data-ttu-id="e34f0-119">Потвърдете и двата входа, като изберете **Свързване с HERE**.</span><span class="sxs-lookup"><span data-stu-id="e34f0-119">Confirm both inputs by selecting **Connect to HERE**.</span></span>

1.  <span data-ttu-id="e34f0-120">Изберете **Добавяне на данни** и изберете **набора от данни на клиент**, който искате да обогатите с данни за местоположение от HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="e34f0-120">Select **Add data** and choose the **Customer data set** you want to enrich with location data from HERE Technologies.</span></span> <span data-ttu-id="e34f0-121">Можете да изберете **Клиент** обект, за да обогатите всичките си клиентски профили или да изберете сегментен обект, за да обогатите само клиентски профили, съдържащи се в този сегмент.</span><span class="sxs-lookup"><span data-stu-id="e34f0-121">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Снимка на екрана при избора на набор от данни за клиенти.":::

1. <span data-ttu-id="e34f0-123">Изберете дали искате да присвоите полета на основния и/или вторичния адрес.</span><span class="sxs-lookup"><span data-stu-id="e34f0-123">Choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="e34f0-124">Можете да посочите картографиране на полета и за двата адреса (например домашен и бизнес адрес) и да обогатите профилите и за двата адреса поотделно.</span><span class="sxs-lookup"><span data-stu-id="e34f0-124">You can specify a field mapping for both addresses (for example, a home and a business address) and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="e34f0-125">Изберете **Напред**.</span><span class="sxs-lookup"><span data-stu-id="e34f0-125">Select **Next**.</span></span>

1. <span data-ttu-id="e34f0-126">Определете кои полета от унифицираните ви профили трябва да се използват за търсене на съвпадащи данни за местоположението от HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="e34f0-126">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="e34f0-127">Полетата **Улица 1** и **Пощенски код** са задължителни за избрания основен и/или вторичен адрес.</span><span class="sxs-lookup"><span data-stu-id="e34f0-127">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="e34f0-128">За по-висока точност на съвпадението могат да се добавят повече полета.</span><span class="sxs-lookup"><span data-stu-id="e34f0-128">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e34f0-129">![Страница за конфигуриране на обогатяване на HERE Technologies](media/enrichment-HERE-configuration.png "Страница за конфигуриране на обогатяване на HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="e34f0-129">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="e34f0-130">Изберете **Приложи**, за да завършите нанасянето на полето.</span><span class="sxs-lookup"><span data-stu-id="e34f0-130">Select **Apply** to complete the field mapping.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="e34f0-131">Резултати от допълването</span><span class="sxs-lookup"><span data-stu-id="e34f0-131">Enrichment results</span></span>

<span data-ttu-id="e34f0-132">За да започнете процеса на допълване, изберете **Стартиране** от командната лента.</span><span class="sxs-lookup"><span data-stu-id="e34f0-132">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="e34f0-133">Можете също така да оставите системата да стартира допълването автоматично като част от [планирано обновяване](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="e34f0-133">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="e34f0-134">Времето за обработка ще зависи от размера на вашите клиентски данни и времето за реакция на API от HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="e34f0-134">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="e34f0-135">След като процесът на допълване завърши, можете да прегледате току-що допълнените данни за потребителски профили в **Моите допълвания**.</span><span class="sxs-lookup"><span data-stu-id="e34f0-135">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="e34f0-136">Освен това ще намерите часа на последната актуализация и броя на допълнените профили.</span><span class="sxs-lookup"><span data-stu-id="e34f0-136">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="e34f0-137">Можете да получите достъп до подробен изглед на всеки допълнен профил, като изберете **Преглед на допълнените данни**.</span><span class="sxs-lookup"><span data-stu-id="e34f0-137">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e34f0-138">Следващи стъпки</span><span class="sxs-lookup"><span data-stu-id="e34f0-138">Next steps</span></span>

<span data-ttu-id="e34f0-139">Надградете допълнените клиентски данни.</span><span class="sxs-lookup"><span data-stu-id="e34f0-139">Build on top of your enriched customer data.</span></span> <span data-ttu-id="e34f0-140">Създайте [сегменти](segments.md), [мерки](measures.md) и дори [експортирайте данните](export-destinations.md), за да доставите персонализирано изживяване на клиентите си.</span><span class="sxs-lookup"><span data-stu-id="e34f0-140">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="e34f0-141">Поверителност и съответствие на данните</span><span class="sxs-lookup"><span data-stu-id="e34f0-141">Data privacy and compliance</span></span>

<span data-ttu-id="e34f0-142">Когато активирате Dynamics 365 Customer Insights, за да предавате данни на HERE Technologies, разрешавате прехвърляне на данни извън границата за съответствие за Dynamics 365 Customer Insights, включително потенциално чувствителни данни като Лични данни.</span><span class="sxs-lookup"><span data-stu-id="e34f0-142">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="e34f0-143">Microsoft ще прехвърли такива данни по ваше указание, но вие носите отговорност да гарантирате, че HERE Technologies отговаря на всички задължения за поверителност или сигурност, които може да имате.</span><span class="sxs-lookup"><span data-stu-id="e34f0-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="e34f0-144">За информация посетете [Декларация за поверителност Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="e34f0-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="e34f0-145">Вашият администратор на Dynamics 365 Customer Insights да премахнете това обогатяване по всяко време, за да прекратите използването на тази функционалност.</span><span class="sxs-lookup"><span data-stu-id="e34f0-145">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]