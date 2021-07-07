---
title: Допълване на клиентски профили с данни от Microsoft
description: Използвайте собствени данни от Microsoft, за да допълните данните на клиентите с афинитет към марки и интереси.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 1b11c325649b91ebb47cde924227eacedae64b7a
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305143"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a><span data-ttu-id="bdda3-103">Допълване на клиентски профили с афинитети към марки и интереси (преглед)</span><span class="sxs-lookup"><span data-stu-id="bdda3-103">Enrich customer profiles with brand and interest affinities (preview)</span></span>

<span data-ttu-id="bdda3-104">Използвайте собствени данни на Microsoft, за да допълните данните на клиентите с афинитет към марки и интереси.</span><span class="sxs-lookup"><span data-stu-id="bdda3-104">Use Microsoft's proprietary data to enrich your customer data with brand and interest affinities.</span></span> <span data-ttu-id="bdda3-105">Тези афинитети са базирани на данни от хора с демография, подобна на тази на клиентите ви.</span><span class="sxs-lookup"><span data-stu-id="bdda3-105">These affinities are based on data from people with demographics similar to your customers.</span></span> <span data-ttu-id="bdda3-106">Тази информация ви помага да разберете по-добре и сегментирате клиентите си въз основа на афинитета им към конкретни марки и интереси.</span><span class="sxs-lookup"><span data-stu-id="bdda3-106">This information helps you to better understand and segment your customers based on their affinities to specific brands and interests.</span></span>

<span data-ttu-id="bdda3-107">В аналитични данни за аудитория, отидете на **Данни** > **Обогатяване**, за да [конфигурирате и прегледате обогатявания](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="bdda3-107">In audience insights, go to **Data** > **Enrichment** to [configure and view enrichments](enrichment-hub.md).</span></span>

<span data-ttu-id="bdda3-108">За да конфигурирате допълването на афинитети към марки, отидете в раздела **Откриване** и изберете **Допълване на моите данни** в плочката **Марки**.</span><span class="sxs-lookup"><span data-stu-id="bdda3-108">To configure brand affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Brands** tile.</span></span>

<span data-ttu-id="bdda3-109">За да конфигурирате допълването на афинитети към интереси, отидете в раздела **Откриване** и изберете **Допълване на моите данни** в плочката **Интереси**.</span><span class="sxs-lookup"><span data-stu-id="bdda3-109">To configure interest affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Interests** tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="bdda3-110">![Плочки за марки и интереси](media/BrandsInterest-tile-Hub.png "Плочки за марки и интереси")</span><span class="sxs-lookup"><span data-stu-id="bdda3-110">![Brands and Interests tiles](media/BrandsInterest-tile-Hub.png "Brands and Interest tiles")</span></span>

## <a name="how-we-determine-affinities"></a><span data-ttu-id="bdda3-111">Как определяме афинитета</span><span class="sxs-lookup"><span data-stu-id="bdda3-111">How we determine affinities</span></span>

<span data-ttu-id="bdda3-112">Използваме данните за онлайн търсене на Microsoft, за да намерим афинитети към марки и интереси в различни демографски сегменти (дефинирани по възраст, пол или местоположение).</span><span class="sxs-lookup"><span data-stu-id="bdda3-112">We use Microsoft’s online search data to find affinities for brands and interests across various demographic segments (defined by age, gender, or location).</span></span> <span data-ttu-id="bdda3-113">Размерът на онлайн търсенето на марка или интерес определя размера на афинитета на даден демографски сегмент в сравнение с други сегменти към тази марка или интерес.</span><span class="sxs-lookup"><span data-stu-id="bdda3-113">The online search volume for a brand or interest determines how much affinity a demographic segment, compared to other segments, has to that brand or interest.</span></span>

## <a name="affinity-level-and-score"></a><span data-ttu-id="bdda3-114">Ниво на афинитет и резултат</span><span class="sxs-lookup"><span data-stu-id="bdda3-114">Affinity level and score</span></span>

<span data-ttu-id="bdda3-115">За всеки обогатен потребителски профил ние предоставяме две свързани стойности: ниво на афинитет и оценка на афинитета.</span><span class="sxs-lookup"><span data-stu-id="bdda3-115">On every enriched customer profile, we provide two related values: affinity level and affinity score.</span></span> <span data-ttu-id="bdda3-116">Тези стойности ви помагат да определите колко силен е афинитетът към демографския сегмент на този профил, към марка или интерес, в сравнение с други демографски сегменти.</span><span class="sxs-lookup"><span data-stu-id="bdda3-116">These values help you determine how strong the affinity is for that profile’s demographic segment, for a brand or interest, as compared to other demographic segments.</span></span>

<span data-ttu-id="bdda3-117">*Ниво на афинитет* се състои от четири нива, а *оценка на афинитет* се изчислява по 100-точкова скала, която съответства на нивата на афинитет.</span><span class="sxs-lookup"><span data-stu-id="bdda3-117">*Affinity level* consists of four levels and *affinity score* is calculated on a 100-point scale that maps to the affinity levels.</span></span>


|<span data-ttu-id="bdda3-118">Ниво на афинитет</span><span class="sxs-lookup"><span data-stu-id="bdda3-118">Affinity level</span></span> |<span data-ttu-id="bdda3-119">Резултат за афинитет</span><span class="sxs-lookup"><span data-stu-id="bdda3-119">Affinity score</span></span>  |
|---------|---------|
|<span data-ttu-id="bdda3-120">Много висок</span><span class="sxs-lookup"><span data-stu-id="bdda3-120">Very high</span></span>     | <span data-ttu-id="bdda3-121">85-100</span><span class="sxs-lookup"><span data-stu-id="bdda3-121">85-100</span></span>       |
|<span data-ttu-id="bdda3-122">Висока</span><span class="sxs-lookup"><span data-stu-id="bdda3-122">High</span></span>     | <span data-ttu-id="bdda3-123">70-84</span><span class="sxs-lookup"><span data-stu-id="bdda3-123">70-84</span></span>        |
|<span data-ttu-id="bdda3-124">Среден</span><span class="sxs-lookup"><span data-stu-id="bdda3-124">Medium</span></span>     | <span data-ttu-id="bdda3-125">35-69</span><span class="sxs-lookup"><span data-stu-id="bdda3-125">35-69</span></span>        |
|<span data-ttu-id="bdda3-126">Ниска</span><span class="sxs-lookup"><span data-stu-id="bdda3-126">Low</span></span>     | <span data-ttu-id="bdda3-127">1-34</span><span class="sxs-lookup"><span data-stu-id="bdda3-127">1-34</span></span>        |

<span data-ttu-id="bdda3-128">В зависимост от детайлността, която искате за измерване на афинитета, можете да използвате или ниво на афинитет, или оценка.</span><span class="sxs-lookup"><span data-stu-id="bdda3-128">Depending on the granularity you would like for measuring the affinity, you can use either affinity level or score.</span></span> <span data-ttu-id="bdda3-129">Резултатът за афинитет ви дава по-прецизен контрол.</span><span class="sxs-lookup"><span data-stu-id="bdda3-129">Affinity score gives you more precise control.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="bdda3-130">Поддържани държави / региони</span><span class="sxs-lookup"><span data-stu-id="bdda3-130">Supported countries/regions</span></span>

<span data-ttu-id="bdda3-131">В момента поддържаме следните опции за държава / регион: Австралия, Канада (английски), Франция, Германия, Обединеното кралство или Съединените щати (английски).</span><span class="sxs-lookup"><span data-stu-id="bdda3-131">We currently support the following country/region options: Australia, Canada (English), France, Germany, United Kingdom, or United States (English).</span></span>

<span data-ttu-id="bdda3-132">За да изберете държава или регион, отворете **Обогатяване на марки** или **Обогатяване на лихвите** и изберете **Промяна** до **Страна/регион**.</span><span class="sxs-lookup"><span data-stu-id="bdda3-132">To select a country or region, open **Brands enrichment** or **Interest enrichment** and select **Change** next to **Country/Region**.</span></span> <span data-ttu-id="bdda3-133">В екрана **Настройки за държава/регион** панел, изберете опция и изберете **Приложи**.</span><span class="sxs-lookup"><span data-stu-id="bdda3-133">In the **Country/Region settings** pane, choose an option and select **Apply**.</span></span>

### <a name="implications-related-to-country-selection"></a><span data-ttu-id="bdda3-134">Последици, свързани с избора на държава</span><span class="sxs-lookup"><span data-stu-id="bdda3-134">Implications related to country selection</span></span>

- <span data-ttu-id="bdda3-135">Когато [избирате собствени марки](#define-your-brands-or-interests), системата предоставя предложения въз основа на избраната държава или регион.</span><span class="sxs-lookup"><span data-stu-id="bdda3-135">When [choosing your own brands](#define-your-brands-or-interests), the system provides suggestions based on the selected country or region.</span></span>

- <span data-ttu-id="bdda3-136">Когато [избирате отрасъл](#define-your-brands-or-interests), ще получите най-подходящите марки или интереси въз основа на избраната държава или регион.</span><span class="sxs-lookup"><span data-stu-id="bdda3-136">When [choosing an industry](#define-your-brands-or-interests), you'll get the most relevant brands or interests based on the selected country or region.</span></span>

- <span data-ttu-id="bdda3-137">Кога [обогатяваме профили](#refresh-enrichment), ние ще обогатим всички потребителски профили, за които получаваме данни за избраните марки и интереси, включително профили, които не са в избраната държава или регион.</span><span class="sxs-lookup"><span data-stu-id="bdda3-137">When [enriching profiles](#refresh-enrichment), we'll enrich all customer profiles for which we get data for the selected brands and interests, including profiles that are not in the selected country or region.</span></span> <span data-ttu-id="bdda3-138">Например, ако сте избрали Германия, ние ще допълним профилите, намиращи се в САЩ, ако имаме налични данни за избраните марки и интереси в САЩ.</span><span class="sxs-lookup"><span data-stu-id="bdda3-138">For example, if you selected Germany, we'll enrich profiles located in the United States if we have data available for the selected brands and interests in the US.</span></span>

## <a name="configure-enrichment"></a><span data-ttu-id="bdda3-139">Конфигуриране на обогатяване</span><span class="sxs-lookup"><span data-stu-id="bdda3-139">Configure enrichment</span></span>

<span data-ttu-id="bdda3-140">Насоките ви помагат при конфигурирането на допълвания.</span><span class="sxs-lookup"><span data-stu-id="bdda3-140">A guided experience helps you through the configuration of the enrichments.</span></span> 

### <a name="define-your-brands-or-interests"></a><span data-ttu-id="bdda3-141">Определяне на марките или интересите</span><span class="sxs-lookup"><span data-stu-id="bdda3-141">Define your brands or interests</span></span>

<span data-ttu-id="bdda3-142">Изберете до пет марки или интереси, като използвате една или и двете от тези опции:</span><span class="sxs-lookup"><span data-stu-id="bdda3-142">Choose up to five brands or interests using one or both of these options:</span></span>

- <span data-ttu-id="bdda3-143">**Промишленост**: Изберете вашата индустрия от падащия списък и след това изберете от най-добрите марки или интереси за тази индустрия.</span><span class="sxs-lookup"><span data-stu-id="bdda3-143">**Industry**: Select your industry from the dropdown list and then choose from the top brands or interests for that industry.</span></span>
- <span data-ttu-id="bdda3-144">**Изберете своя**: Въведете марка или интерес, който е от значение за вашата организация и след това изберете от предложенията за съвпадение.</span><span class="sxs-lookup"><span data-stu-id="bdda3-144">**Choose your own**: Enter a brand or interest that is relevant to your organization and then choose from the matching suggestions.</span></span> <span data-ttu-id="bdda3-145">Ако в списъка не е включена марка или интерес, които търсите, изпратете ни обратна връзка, като използвате връзката **Предложение**.</span><span class="sxs-lookup"><span data-stu-id="bdda3-145">If we don't list a brand or interest you're looking for, send us feedback using the **Suggest** link.</span></span>

### <a name="review-enrichment-preferences"></a><span data-ttu-id="bdda3-146">Предпочитания за обогатяване на преглед</span><span class="sxs-lookup"><span data-stu-id="bdda3-146">Review enrichment preferences</span></span>

<span data-ttu-id="bdda3-147">Прегледайте предпочитанията си за обогатяване по подразбиране и ги актуализирайте при необходимост.</span><span class="sxs-lookup"><span data-stu-id="bdda3-147">Review your default enrichment preferences and update them as needed.</span></span>

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Екранна снимка на прозореца за предпочитания за обогатяване.":::

### <a name="select-entity-to-enrich"></a><span data-ttu-id="bdda3-149">Избор на обект за обогатяване</span><span class="sxs-lookup"><span data-stu-id="bdda3-149">Select entity to enrich</span></span>

<span data-ttu-id="bdda3-150">Изберете **Допълнен обект** и изберете набора от данни, който искате да допълните фирмените данни от Microsoft.</span><span class="sxs-lookup"><span data-stu-id="bdda3-150">Select **Enriched entity** and choose the data set you want to enrich with company data from the Microsoft.</span></span> <span data-ttu-id="bdda3-151">Можете да изберете Клиент обект, за да обогатите всичките си клиентски профили или да изберете сегментен обект, за да обогатите само клиентски профили, съдържащи се в този сегмент.</span><span class="sxs-lookup"><span data-stu-id="bdda3-151">You can select the Customer entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

### <a name="map-your-fields"></a><span data-ttu-id="bdda3-152">Нанесете полетата</span><span class="sxs-lookup"><span data-stu-id="bdda3-152">Map your fields</span></span>

<span data-ttu-id="bdda3-153">Съставете полета от вашата обединена клиентска единица, за да определите демографския сегмент, който искате системата да използва за обогатяване на вашите клиентски данни.</span><span class="sxs-lookup"><span data-stu-id="bdda3-153">Map fields from your unified customer entity to define the demographic segment you want the system to use for enriching your customer data.</span></span> <span data-ttu-id="bdda3-154">Карта на държава / регион и поне атрибути на дата на раждане или пол.</span><span class="sxs-lookup"><span data-stu-id="bdda3-154">Map Country/Region and at least Date of Birth or Gender attributes.</span></span> <span data-ttu-id="bdda3-155">Освен това трябва да съпоставите поне едно от „Град“ (и „Щат/провинция“) или „Пощенски код“.</span><span class="sxs-lookup"><span data-stu-id="bdda3-155">Additionally, you must map at least one of City (and State/Province) or Postal code.</span></span> <span data-ttu-id="bdda3-156">Изберете **Редактиране**, за да определите нанасянето на полетата, и изберете **Прилагане**, когато сте готови.</span><span class="sxs-lookup"><span data-stu-id="bdda3-156">Select **Edit** to define the mapping of the fields and select **Apply** when you're done.</span></span> <span data-ttu-id="bdda3-157">Изберете **Записване**, за да завършите съпоставянето на полета.</span><span class="sxs-lookup"><span data-stu-id="bdda3-157">Select **Save** to complete the field mapping.</span></span>

<span data-ttu-id="bdda3-158">Поддържат се следните формати и стойности (стойностите не са чувствителни към регистъра):</span><span class="sxs-lookup"><span data-stu-id="bdda3-158">The following formats and values are supported (values are not case-sensitive):</span></span>

- <span data-ttu-id="bdda3-159">**Дата на раждане**: Препоръчваме датата на раждане да се преобразува в тип DateTime по време на приемане на данни.</span><span class="sxs-lookup"><span data-stu-id="bdda3-159">**Date of Birth**: We recommend that date of birth is converted to DateTime type during data ingestion.</span></span> <span data-ttu-id="bdda3-160">Алтернативно, това може да бъде низ в [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) формат "yyyy-MM-dd" или "yyyy-MM-ddTHH:mm:ss".</span><span class="sxs-lookup"><span data-stu-id="bdda3-160">Alternatively, it can be a string in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format "yyyy-MM-dd" or "yyyy-MM-ddTHH:mm:ss".</span></span>
- <span data-ttu-id="bdda3-161">**Пол**: мъж, жена, неизвестен.</span><span class="sxs-lookup"><span data-stu-id="bdda3-161">**Gender**: Male, Female, Unknown.</span></span>
- <span data-ttu-id="bdda3-162">**Пощенски код**: Петцифрени пощенски кодове за САЩ, стандартен пощенски код навсякъде другаде.</span><span class="sxs-lookup"><span data-stu-id="bdda3-162">**Postal code**: Five-digit ZIP codes for United States, standard postal code everywhere else.</span></span>
- <span data-ttu-id="bdda3-163">**Град**: Име на град на английски.</span><span class="sxs-lookup"><span data-stu-id="bdda3-163">**City**: City name in English.</span></span>
- <span data-ttu-id="bdda3-164">**Щат/Провинция**: Съкращение с две букви за САЩ и Канада.</span><span class="sxs-lookup"><span data-stu-id="bdda3-164">**State/Province**: Two-letter abbreviation for the US and Canada.</span></span> <span data-ttu-id="bdda3-165">Съкращение с две или три букви за Австралия.</span><span class="sxs-lookup"><span data-stu-id="bdda3-165">Two- or three-letter abbreviation for Australia.</span></span> <span data-ttu-id="bdda3-166">Не е приложимо за Франция, Германия или Великобритания.</span><span class="sxs-lookup"><span data-stu-id="bdda3-166">Not applicable for France, Germany, or the UK.</span></span>
- <span data-ttu-id="bdda3-167">**Страна/регион**:</span><span class="sxs-lookup"><span data-stu-id="bdda3-167">**Country/Region**:</span></span>

  - <span data-ttu-id="bdda3-168">САЩ: Съединени американски щати, Съединени щати, САЩ, Америка</span><span class="sxs-lookup"><span data-stu-id="bdda3-168">US: United States of America, United States, USA, US, America</span></span>
  - <span data-ttu-id="bdda3-169">CA: Канада, Калифорния</span><span class="sxs-lookup"><span data-stu-id="bdda3-169">CA: Canada, CA</span></span>
  - <span data-ttu-id="bdda3-170">GB: Обединено кралство, Великобритания, Обединено кралство Великобритания и Северна Ирландия, Обединено кралство Великобритания</span><span class="sxs-lookup"><span data-stu-id="bdda3-170">GB: United Kingdom, UK, Great Britain, GB, United Kingdom of Great Britain and Northern Ireland, United Kingdom of Great Britain</span></span>
  - <span data-ttu-id="bdda3-171">AU: Австралия, AU, Австралийска общност</span><span class="sxs-lookup"><span data-stu-id="bdda3-171">AU: Australia, AU, Commonwealth of Australia</span></span>
  - <span data-ttu-id="bdda3-172">FR: Франция. Френска република</span><span class="sxs-lookup"><span data-stu-id="bdda3-172">FR: France, FR, French Republic</span></span>
  - <span data-ttu-id="bdda3-173">DE: Германия, Федерална република Германия, Република Германия</span><span class="sxs-lookup"><span data-stu-id="bdda3-173">DE: Germany, German, Deutschland, Allemagne, DE, Federal Republic of Germany, Republic of Germany</span></span>

## <a name="review-and-name-the-enrichment"></a><span data-ttu-id="bdda3-174">Преглед и задаване на име на допълването</span><span class="sxs-lookup"><span data-stu-id="bdda3-174">Review and name the enrichment</span></span>

<span data-ttu-id="bdda3-175">И накрая, може да прегледате информацията и да предоставите име за допълването.</span><span class="sxs-lookup"><span data-stu-id="bdda3-175">Finally, you get to review the information and provide a name for the enrichment.</span></span>

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="Страница за преглед на интереси и задаване на име.":::

## <a name="refresh-enrichment"></a><span data-ttu-id="bdda3-177">Освежете обогатяването</span><span class="sxs-lookup"><span data-stu-id="bdda3-177">Refresh enrichment</span></span>

<span data-ttu-id="bdda3-178">Изпълнете допълването след конфигуриране на марки, интереси и нанасяне на полета за демографски данни.</span><span class="sxs-lookup"><span data-stu-id="bdda3-178">Run the enrichment after configuring brands, interests, and the field mapping for demographics.</span></span> <span data-ttu-id="bdda3-179">За да стартирате процеса, изберете **Стартиране** на страницата за конфигуриране на марки или интереси.</span><span class="sxs-lookup"><span data-stu-id="bdda3-179">To start the process, select **Run** on the brand or interest configuration page.</span></span> <span data-ttu-id="bdda3-180">Освен това можете да оставите системата да изпълни допълването автоматично като част от планирано обновяване.</span><span class="sxs-lookup"><span data-stu-id="bdda3-180">Additionally, you can let the system run the enrichment automatically as part of a scheduled refresh.</span></span>

<span data-ttu-id="bdda3-181">В зависимост от размера на клиентските данни, завършването на допълването може да отнеме няколко минути.</span><span class="sxs-lookup"><span data-stu-id="bdda3-181">Depending on the size of your customer data, it may take several minutes for an enrichment run to complete.</span></span>

> [!TIP]
> <span data-ttu-id="bdda3-182">Съществуват [шест вида статус](system.md#status-types) на задачите/процесите.</span><span class="sxs-lookup"><span data-stu-id="bdda3-182">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="bdda3-183">Освен това повечето процеси [зависят от други процеси надолу по веригата](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="bdda3-183">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="bdda3-184">Можете да изберете състоянието на процес, за да видите подробности за напредъка на цялата задача.</span><span class="sxs-lookup"><span data-stu-id="bdda3-184">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="bdda3-185">След като изберете **Виж детайлите** за една от задачите на заданието ще намерите допълнителна информация: време за обработка, последната дата на обработка и всички грешки и предупреждения, свързани със задачата.</span><span class="sxs-lookup"><span data-stu-id="bdda3-185">After selecting **See details** for one of the job's tasks, you'll find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="bdda3-186">Резултати от допълването</span><span class="sxs-lookup"><span data-stu-id="bdda3-186">Enrichment results</span></span>

<span data-ttu-id="bdda3-187">След като стартирате процеса за допълване, отидете в **Моите допълвания**, за да прегледате общия брой допълнени клиенти и разбивка на марки или интереси в допълнените клиентски профили.</span><span class="sxs-lookup"><span data-stu-id="bdda3-187">After running the enrichment process, go to **My enrichments** to review the total number of enriched customers and a breakdown of brands or interests in the enriched customer profiles.</span></span>

:::image type="content" source="media/my-enrichments.png" alt-text="Преглед на резултатите след изпълнение на процеса на допълване":::

<span data-ttu-id="bdda3-189">Прегледайте допълнените данни, като изберете **Преглед на допълнени данни** в диаграмата.</span><span class="sxs-lookup"><span data-stu-id="bdda3-189">Review the enriched data by selecting **View enriched data** in the chart.</span></span> <span data-ttu-id="bdda3-190">Допълнените данни за марки отиват в обекта **BrandAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="bdda3-190">Enriched data for brands goes to the **BrandAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="bdda3-191">Данните за интереси са в обекта **InterestAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="bdda3-191">Data for interests is in the **InterestAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="bdda3-192">Ще намерите тези обекти, посочени и в групата **Допълване** в **Данни** > **Обекти**.</span><span class="sxs-lookup"><span data-stu-id="bdda3-192">You'll also find these entities listed in the **Enrichment** group in **Data** > **Entities**.</span></span>

## <a name="see-enrichment-data-on-the-customer-card"></a><span data-ttu-id="bdda3-193">Преглед на данните за допълване в картата на клиента</span><span class="sxs-lookup"><span data-stu-id="bdda3-193">See enrichment data on the customer card</span></span>

<span data-ttu-id="bdda3-194">Афинитетите към марки и интереси могат да се прегледат и в отделни карти на клиент.</span><span class="sxs-lookup"><span data-stu-id="bdda3-194">Brand and interest affinities can also be viewed on individual customer cards.</span></span> <span data-ttu-id="bdda3-195">Отидете на **Клиенти** и изберете клиентски профил.</span><span class="sxs-lookup"><span data-stu-id="bdda3-195">Go to **Customers** and select a customer profile.</span></span> <span data-ttu-id="bdda3-196">В клиентската карта ще намерите диаграми за марките или интересите, към които хората в демографския профил на този клиент имат афинитет.</span><span class="sxs-lookup"><span data-stu-id="bdda3-196">In the customer card, you'll find charts for the brands or interests that people in that customer's demographic profile have affinity for.</span></span>

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Карта на клиент с допълнени данни":::

## <a name="next-steps"></a><span data-ttu-id="bdda3-198">Следващи стъпки</span><span class="sxs-lookup"><span data-stu-id="bdda3-198">Next steps</span></span>

<span data-ttu-id="bdda3-199">Надградете допълнените клиентски данни.</span><span class="sxs-lookup"><span data-stu-id="bdda3-199">Build on top of your enriched customer data.</span></span> <span data-ttu-id="bdda3-200">Създайте [сегменти](segments.md) и [мерки](measures.md) и дори [експортирайте данните](export-destinations.md) за да доставите персонализирано изживяване на клиентите си.</span><span class="sxs-lookup"><span data-stu-id="bdda3-200">Create [Segments](segments.md) and [Measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
