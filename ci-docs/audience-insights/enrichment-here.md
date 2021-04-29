---
title: Обогатяване с помощта на HERE Technologies за обогатяване от трети страни
description: Обща информация за обогатяването чрез HERE Technologies на трети страни.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 5d1f037377010153045c9255d2d01f98ebf1fdfd
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896038"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="c758b-103">Обогатяване на потребителски профили с HERE Technologies (преглед)</span><span class="sxs-lookup"><span data-stu-id="c758b-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="c758b-104">HERE Technologies е компания за платформи за местоположение, която предоставя данни и услуги, ориентирани към местоположението.</span><span class="sxs-lookup"><span data-stu-id="c758b-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="c758b-105">С услугите за обогатяване на данни от HERE Technologies можете да изградите по-точно разбиране на местоположението на вашите клиенти с нормализиране на адреса, извличане на географска ширина и дължина и др.</span><span class="sxs-lookup"><span data-stu-id="c758b-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c758b-106">Предварителни изисквания</span><span class="sxs-lookup"><span data-stu-id="c758b-106">Prerequisites</span></span>

<span data-ttu-id="c758b-107">За да конфигурирате обогатявания на HERE Technologies, трябва да са изпълнени следните предпоставки:</span><span class="sxs-lookup"><span data-stu-id="c758b-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="c758b-108">Трябва да имате активен абонамент за HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="c758b-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="c758b-109">За да получите абонамент, можете да се [регистрирайте се тук](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) или [да се свържете с HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) директно.</span><span class="sxs-lookup"><span data-stu-id="c758b-109">To get a subscription, you can [sign-up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="c758b-110">Научете повече за обогатяване на местоположението на HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="c758b-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="c758b-111">Има налична [връзка](connections.md) на HERE *или* имате разрешения на [администратор](permissions.md#administrator) и API ключа на HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="c758b-111">There is a HERE [connection](connections.md) available *or* you have [administrator](permissions.md#administrator) permissions and the HERE Technologies API key.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="c758b-112">Конфигуриране на допълването</span><span class="sxs-lookup"><span data-stu-id="c758b-112">Configure the enrichment</span></span>

1. <span data-ttu-id="c758b-113">Отидете в **Данни** > **Допълване**.</span><span class="sxs-lookup"><span data-stu-id="c758b-113">Go to **Data** > **Enrichment**.</span></span> 

1. <span data-ttu-id="c758b-114">Изберете **Допълване на моите данни** на плочката на HERE Technologies и изберете **Начало**.</span><span class="sxs-lookup"><span data-stu-id="c758b-114">Select **Enrich my data** on the HERE Technologies tile and select **Get started**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c758b-115">![Плочка на HERE Technologies](media/HERE-tile.png "Плочка на HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="c758b-115">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="c758b-116">Изберете [връзка](connections.md) от падащия списък.</span><span class="sxs-lookup"><span data-stu-id="c758b-116">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="c758b-117">Свържете се с администратор, ако няма налична връзка.</span><span class="sxs-lookup"><span data-stu-id="c758b-117">Contact  an administrator if no connection is available.</span></span> <span data-ttu-id="c758b-118">Ако сте администратор, можете да създадете връзка, като изберете **Добавяне на връзка**.</span><span class="sxs-lookup"><span data-stu-id="c758b-118">If you are an administrator, you can create a connection by selecting **Add connection**.</span></span> <span data-ttu-id="c758b-119">Изберете **HERE Technologies** от падащия списък.</span><span class="sxs-lookup"><span data-stu-id="c758b-119">Choose **HERE Technologies** from the drop-down.</span></span> 

1. <span data-ttu-id="c758b-120">Изберете **Свързване с HERE Technologies**, за да потвърдите избора.</span><span class="sxs-lookup"><span data-stu-id="c758b-120">Select **Connect to HERE Technologies** to confirm the selection.</span></span>

1.  <span data-ttu-id="c758b-121">Изберете **Напред** и изберете **набора от данни на клиента**, който искате да допълните с данни за местоположение от HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="c758b-121">Select **Next** and choose the **Customer data set** you want to enrich with location data from HERE Technologies.</span></span> <span data-ttu-id="c758b-122">Можете да изберете **Клиент** обект, за да обогатите всичките си клиентски профили или да изберете сегментен обект, за да обогатите само клиентски профили, съдържащи се в този сегмент.</span><span class="sxs-lookup"><span data-stu-id="c758b-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Снимка на екрана при избора на набор от данни за клиенти.":::

1. <span data-ttu-id="c758b-124">Изберете дали искате да присвоите полета на основния и/или вторичния адрес.</span><span class="sxs-lookup"><span data-stu-id="c758b-124">Choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="c758b-125">Можете да посочите съпоставяне на поле за двата адреса и да допълните профилите за двата адреса поотделно.</span><span class="sxs-lookup"><span data-stu-id="c758b-125">You can specify a field mapping for both addresses and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="c758b-126">Например, ако има домашен и бизнес адрес.</span><span class="sxs-lookup"><span data-stu-id="c758b-126">For example, if there's a home and a business address.</span></span> <span data-ttu-id="c758b-127">Изберете **Напред**.</span><span class="sxs-lookup"><span data-stu-id="c758b-127">Select **Next**.</span></span>

1. <span data-ttu-id="c758b-128">Определете кои полета от унифицираните ви профили трябва да се използват за търсене на съвпадащи данни за местоположението от HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="c758b-128">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="c758b-129">Полетата **Улица 1** и **Пощенски код** са задължителни за избрания основен и/или вторичен адрес.</span><span class="sxs-lookup"><span data-stu-id="c758b-129">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="c758b-130">За по-висока точност на съвпадението могат да се добавят повече полета.</span><span class="sxs-lookup"><span data-stu-id="c758b-130">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c758b-131">![Страница за конфигуриране на обогатяване на HERE Technologies](media/enrichment-HERE-configuration.png "Страница за конфигуриране на обогатяване на HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="c758b-131">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="c758b-132">Изберете **Напред**, за да завършите съпоставянето на полета.</span><span class="sxs-lookup"><span data-stu-id="c758b-132">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="c758b-133">Въведете име за допълването.</span><span class="sxs-lookup"><span data-stu-id="c758b-133">Provide a name for the enrichment.</span></span> 

<span data-ttu-id="c758b-134">1. Изберете **Записване на допълването**, след като прегледате избора си.</span><span class="sxs-lookup"><span data-stu-id="c758b-134">1.Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-here-technologies"></a><span data-ttu-id="c758b-135">Конфигуриране на връзката за HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="c758b-135">Configure the connection for HERE technologies</span></span> 

<span data-ttu-id="c758b-136">Трябва да сте администратор, за да конфигурирате връзки.</span><span class="sxs-lookup"><span data-stu-id="c758b-136">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="c758b-137">Изберете **Добавяне на връзка**, когато конфигурирате допълването, *или* отидете на **Администратор** > **Връзки** и изберете **Настройка** в плочката на HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="c758b-137">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the HERE Technologies tile.</span></span>

1. <span data-ttu-id="c758b-138">Въведете име за връзката в полето **Показвано име**.</span><span class="sxs-lookup"><span data-stu-id="c758b-138">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="c758b-139">Въведете валиден ключ за API на HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="c758b-139">Provide a valid HERE Technologies API key.</span></span>

1. <span data-ttu-id="c758b-140">Прегледайте и дайте своето съгласие за **Поверителност и съответствие на данните**, като изберете отметката **Приемам**</span><span class="sxs-lookup"><span data-stu-id="c758b-140">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox</span></span>

1. <span data-ttu-id="c758b-141">Изберете **Проверка**, за да проверите конфигурацията.</span><span class="sxs-lookup"><span data-stu-id="c758b-141">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="c758b-142">След като завършите проверката, изберете **Записване**.</span><span class="sxs-lookup"><span data-stu-id="c758b-142">After completing the verification, select **Save**.</span></span>

> [!div class="mx-imgBorder"]
   > <span data-ttu-id="c758b-143">![Страница за конфигуриране на връзка на HERE Technologies](media/enrichment-HERE-connection.png "Страница за конфигуриране на връзка на HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="c758b-143">![HERE Technologies connection configuration page](media/enrichment-HERE-connection.png "HERE Technologies connection configuration page")</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="c758b-144">Резултати от допълването</span><span class="sxs-lookup"><span data-stu-id="c758b-144">Enrichment results</span></span>

<span data-ttu-id="c758b-145">За да започнете процеса на допълване, изберете **Стартиране** от командната лента.</span><span class="sxs-lookup"><span data-stu-id="c758b-145">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="c758b-146">Можете също така да оставите системата да стартира допълването автоматично като част от [планирано обновяване](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="c758b-146">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="c758b-147">Времето за обработка ще зависи от размера на вашите клиентски данни и времето за реакция на API от HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="c758b-147">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="c758b-148">След като процесът на допълване завърши, можете да прегледате току-що допълнените данни за потребителски профили в **Моите допълвания**.</span><span class="sxs-lookup"><span data-stu-id="c758b-148">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="c758b-149">Освен това ще намерите часа на последната актуализация и броя на допълнените профили.</span><span class="sxs-lookup"><span data-stu-id="c758b-149">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="c758b-150">Можете да получите достъп до подробен изглед на всеки допълнен профил, като изберете **Преглед на допълнените данни**.</span><span class="sxs-lookup"><span data-stu-id="c758b-150">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="c758b-151">Следващи стъпки</span><span class="sxs-lookup"><span data-stu-id="c758b-151">Next steps</span></span>

<span data-ttu-id="c758b-152">Надградете допълнените клиентски данни.</span><span class="sxs-lookup"><span data-stu-id="c758b-152">Build on top of your enriched customer data.</span></span> <span data-ttu-id="c758b-153">Създайте [сегменти](segments.md), [мерки](measures.md) и дори [експортирайте данните](export-destinations.md), за да доставите персонализирано изживяване на клиентите си.</span><span class="sxs-lookup"><span data-stu-id="c758b-153">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="c758b-154">Поверителност и съответствие на данните</span><span class="sxs-lookup"><span data-stu-id="c758b-154">Data privacy and compliance</span></span>

<span data-ttu-id="c758b-155">Когато активирате Dynamics 365 Customer Insights, за да предавате данни на HERE Technologies, разрешавате прехвърляне на данни извън границата за съответствие за Dynamics 365 Customer Insights, включително потенциално чувствителни данни като Лични данни.</span><span class="sxs-lookup"><span data-stu-id="c758b-155">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="c758b-156">Microsoft ще прехвърли такива данни по ваше указание, но вие носите отговорност да гарантирате, че HERE Technologies отговаря на всички задължения за поверителност или сигурност, които може да имате.</span><span class="sxs-lookup"><span data-stu-id="c758b-156">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="c758b-157">За информация посетете [Декларация за поверителност Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="c758b-157">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="c758b-158">Вашият администратор на Dynamics 365 Customer Insights да премахнете това обогатяване по всяко време, за да прекратите използването на тази функционалност.</span><span class="sxs-lookup"><span data-stu-id="c758b-158">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
