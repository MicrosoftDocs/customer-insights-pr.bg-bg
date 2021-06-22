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
ms.openlocfilehash: e92360bb886739cfe477ce1d2eb62219228a0292
ms.sourcegitcommit: d4b4053f6ee8f60f1a214982c4726c9de84615ef
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 06/14/2021
ms.locfileid: "6245694"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a><span data-ttu-id="a58bd-103">Допълване на клиентски профили с афинитети към марки и интереси (преглед)</span><span class="sxs-lookup"><span data-stu-id="a58bd-103">Enrich customer profiles with brand and interest affinities (preview)</span></span>

<span data-ttu-id="a58bd-104">Използвайте собствени данни на Microsoft, за да допълните данните на клиентите с афинитет към марки и интереси.</span><span class="sxs-lookup"><span data-stu-id="a58bd-104">Use Microsoft's proprietary data to enrich your customer data with brand and interest affinities.</span></span> <span data-ttu-id="a58bd-105">Тези афинитети се определят въз основа на данни от хора с демография, сходна с тази на вашите клиенти.</span><span class="sxs-lookup"><span data-stu-id="a58bd-105">These affinities are determined based on data from people with similar demographics to your customers.</span></span> <span data-ttu-id="a58bd-106">Тази информация ви помага да разберете по-добре и сегментирате клиентите си въз основа на афинитета им към конкретни марки и интереси.</span><span class="sxs-lookup"><span data-stu-id="a58bd-106">This information helps you to better understand and segment your customers based on their affinities to specific brands and interests.</span></span>

<span data-ttu-id="a58bd-107">В аналитични данни за аудитория, отидете на **Данни** > **Обогатяване**, за да [конфигурирате и прегледате обогатявания](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="a58bd-107">In audience insights, go to **Data** > **Enrichment** to [configure and view enrichments](enrichment-hub.md).</span></span>

<span data-ttu-id="a58bd-108">За да конфигурирате допълването на афинитети към марки, отидете в раздела **Откриване** и изберете **Допълване на моите данни** в плочката **Марки**.</span><span class="sxs-lookup"><span data-stu-id="a58bd-108">To configure brand affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Brands** tile.</span></span>

<span data-ttu-id="a58bd-109">За да конфигурирате допълването на афинитети към интереси, отидете в раздела **Откриване** и изберете **Допълване на моите данни** в плочката **Интереси**.</span><span class="sxs-lookup"><span data-stu-id="a58bd-109">To configure interest affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Interests** tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a58bd-110">![Плочки с марки и интереси](media/BrandsInterest-tile-Hub.png "Плочки с марки и интереси")</span><span class="sxs-lookup"><span data-stu-id="a58bd-110">![Brands & Interests tiles](media/BrandsInterest-tile-Hub.png "Brands & Interest tiles")</span></span>

## <a name="how-we-determine-affinities"></a><span data-ttu-id="a58bd-111">Как определяме афинитета</span><span class="sxs-lookup"><span data-stu-id="a58bd-111">How we determine affinities</span></span>

<span data-ttu-id="a58bd-112">Използваме данните за онлайн търсене на Microsoft, за да намерим афинитети към марки и интереси в различни демографски сегменти (дефинирани по възраст, пол или местоположение).</span><span class="sxs-lookup"><span data-stu-id="a58bd-112">We use Microsoft’s online search data to find affinities for brands and interests across various demographic segments (defined by age, gender, or location).</span></span> <span data-ttu-id="a58bd-113">Размерът на онлайн търсенето на марка или интерес определя размера на афинитета на даден демографски сегмент в сравнение с други сегменти към тази марка или интерес.</span><span class="sxs-lookup"><span data-stu-id="a58bd-113">The online search volume for a brand or interest determines how much affinity a demographic segment, compared to other segments, has to that brand or interest.</span></span>

## <a name="affinity-level-and-score"></a><span data-ttu-id="a58bd-114">Ниво на афинитет и резултат</span><span class="sxs-lookup"><span data-stu-id="a58bd-114">Affinity level and score</span></span>

<span data-ttu-id="a58bd-115">За всеки обогатен потребителски профил ние предоставяме две свързани стойности - ниво на афинитет и оценка на афинитета.</span><span class="sxs-lookup"><span data-stu-id="a58bd-115">On every enriched customer profile, we provide two related values – affinity level and affinity score.</span></span> <span data-ttu-id="a58bd-116">Тези стойности ви помагат да определите колко силен е афинитетът към демографския сегмент на този профил, към марка или интерес, в сравнение с други демографски сегменти.</span><span class="sxs-lookup"><span data-stu-id="a58bd-116">These values help you determine how strong the affinity is for that profile’s demographic segment, for a brand or interest, as compared to other demographic segments.</span></span>

<span data-ttu-id="a58bd-117">*Ниво на афинитет* се състои от четири нива, а *оценка на афинитет* се изчислява по 100-точкова скала, която съответства на нивата на афинитет.</span><span class="sxs-lookup"><span data-stu-id="a58bd-117">*Affinity level* consists of four levels and *affinity score* is calculated on a 100-point scale that maps to the affinity levels.</span></span>


|<span data-ttu-id="a58bd-118">Ниво на афинитет</span><span class="sxs-lookup"><span data-stu-id="a58bd-118">Affinity level</span></span> |<span data-ttu-id="a58bd-119">Резултат за афинитет</span><span class="sxs-lookup"><span data-stu-id="a58bd-119">Affinity score</span></span>  |
|---------|---------|
|<span data-ttu-id="a58bd-120">Много висок</span><span class="sxs-lookup"><span data-stu-id="a58bd-120">Very high</span></span>     | <span data-ttu-id="a58bd-121">85-100</span><span class="sxs-lookup"><span data-stu-id="a58bd-121">85-100</span></span>       |
|<span data-ttu-id="a58bd-122">Висока</span><span class="sxs-lookup"><span data-stu-id="a58bd-122">High</span></span>     | <span data-ttu-id="a58bd-123">70-84</span><span class="sxs-lookup"><span data-stu-id="a58bd-123">70-84</span></span>        |
|<span data-ttu-id="a58bd-124">Среден</span><span class="sxs-lookup"><span data-stu-id="a58bd-124">Medium</span></span>     | <span data-ttu-id="a58bd-125">35-69</span><span class="sxs-lookup"><span data-stu-id="a58bd-125">35-69</span></span>        |
|<span data-ttu-id="a58bd-126">Ниска</span><span class="sxs-lookup"><span data-stu-id="a58bd-126">Low</span></span>     | <span data-ttu-id="a58bd-127">1-34</span><span class="sxs-lookup"><span data-stu-id="a58bd-127">1-34</span></span>        |

<span data-ttu-id="a58bd-128">В зависимост от детайлността, която искате за измерване на афинитета, можете да използвате или ниво на афинитет, или оценка.</span><span class="sxs-lookup"><span data-stu-id="a58bd-128">Depending on the granularity you would like for measuring the affinity, you can use either affinity level or score.</span></span> <span data-ttu-id="a58bd-129">Резултатът за афинитет ви дава по-прецизен контрол.</span><span class="sxs-lookup"><span data-stu-id="a58bd-129">Affinity score gives you more precise control.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="a58bd-130">Поддържани държави / региони</span><span class="sxs-lookup"><span data-stu-id="a58bd-130">Supported countries/regions</span></span>

<span data-ttu-id="a58bd-131">В момента поддържаме следните опции за държава / регион: Австралия, Канада (английски), Франция, Германия, Обединеното кралство или Съединените щати (английски).</span><span class="sxs-lookup"><span data-stu-id="a58bd-131">We currently support the following country/region options: Australia, Canada (English), France, Germany, United Kingdom, or United States (English).</span></span>

<span data-ttu-id="a58bd-132">За да изберете държава, отворете **Обогатяване на марки** или **Обогатяване на интереси** и изберете **промяна** до **Държава/регион**.</span><span class="sxs-lookup"><span data-stu-id="a58bd-132">To select a country, open the **Brands enrichment** or **Interest enrichment** and select **Change** next to **Country/Region**.</span></span> <span data-ttu-id="a58bd-133">В екрана **Настройки за държава/регион** панел, изберете опция и изберете **Приложи**.</span><span class="sxs-lookup"><span data-stu-id="a58bd-133">In the **Country/Region settings** pane, choose an option and select **Apply**.</span></span>

### <a name="implications-related-to-country-selection"></a><span data-ttu-id="a58bd-134">Последици, свързани с избора на държава</span><span class="sxs-lookup"><span data-stu-id="a58bd-134">Implications related to country selection</span></span>

- <span data-ttu-id="a58bd-135">Когато [избирате собствени марки](#define-your-brands-or-interests), системата предоставя предложения въз основа на избраната държава или регион.</span><span class="sxs-lookup"><span data-stu-id="a58bd-135">When [choosing your own brands](#define-your-brands-or-interests), the system provides suggestions based on the selected country or region.</span></span>

- <span data-ttu-id="a58bd-136">Когато [избирате отрасъл](#define-your-brands-or-interests), ще получите най-подходящите марки или интереси въз основа на избраната държава или регион.</span><span class="sxs-lookup"><span data-stu-id="a58bd-136">When [choosing an industry](#define-your-brands-or-interests), you'll get the most relevant brands or interests based on the selected country or region.</span></span>

- <span data-ttu-id="a58bd-137">Когато [обогатявате профили](#refresh-enrichment), ние ще обогатим всички клиентски профили, за които получаваме данни за избраните марки и интереси.</span><span class="sxs-lookup"><span data-stu-id="a58bd-137">When [enriching profiles](#refresh-enrichment), we'll enrich all customer profiles for which we get data for the selected brands and interests.</span></span> <span data-ttu-id="a58bd-138">Включително профили, които не са в избраната държава или регион.</span><span class="sxs-lookup"><span data-stu-id="a58bd-138">Including profiles that are not in the selected country or region.</span></span> <span data-ttu-id="a58bd-139">Например, ако сте избрали Германия, ние ще допълним профилите, намиращи се в САЩ, ако имаме налични данни за избраните марки и интереси в САЩ.</span><span class="sxs-lookup"><span data-stu-id="a58bd-139">For example, if you selected Germany, we'll enrich profiles located in the United States if we have data available for the selected brands and interests in the US.</span></span>

## <a name="configure-enrichment"></a><span data-ttu-id="a58bd-140">Конфигуриране на допълване</span><span class="sxs-lookup"><span data-stu-id="a58bd-140">Configure Enrichment</span></span>

<span data-ttu-id="a58bd-141">Насоките ви помагат при конфигурирането на допълвания.</span><span class="sxs-lookup"><span data-stu-id="a58bd-141">A guided experience helps you through the configuration of the enrichments.</span></span> 

### <a name="define-your-brands-or-interests"></a><span data-ttu-id="a58bd-142">Определяне на марките или интересите</span><span class="sxs-lookup"><span data-stu-id="a58bd-142">Define your brands or interests</span></span>

<span data-ttu-id="a58bd-143">Изберете до пет марки или интереси, като използвате една или и двете от тези опции:</span><span class="sxs-lookup"><span data-stu-id="a58bd-143">Choose up to five brands or interests using one or both of these options:</span></span>

- <span data-ttu-id="a58bd-144">**Промишленост**: Изберете вашата индустрия от падащия списък и след това изберете от най-добрите марки или интереси за тази индустрия.</span><span class="sxs-lookup"><span data-stu-id="a58bd-144">**Industry**: Select your industry from the drop-down list and then choose from the top brands or interests for that industry.</span></span>
- <span data-ttu-id="a58bd-145">**Изберете своя**: Въведете марка или интерес, който е от значение за вашата организация и след това изберете от предложенията за съвпадение.</span><span class="sxs-lookup"><span data-stu-id="a58bd-145">**Choose your own**: Enter a brand or interest that is relevant to your organization and then choose from the matching suggestions.</span></span> <span data-ttu-id="a58bd-146">Ако в списъка не е включена марка или интерес, които търсите, изпратете ни обратна връзка, като използвате връзката **Предложение**.</span><span class="sxs-lookup"><span data-stu-id="a58bd-146">If we don't list a brand or interest you're looking for, send us feedback using the **Suggest** link.</span></span>

### <a name="review-enrichment-preferences"></a><span data-ttu-id="a58bd-147">Предпочитания за обогатяване на преглед</span><span class="sxs-lookup"><span data-stu-id="a58bd-147">Review enrichment preferences</span></span>

<span data-ttu-id="a58bd-148">Прегледайте предпочитанията си за обогатяване по подразбиране и ги актуализирайте при необходимост.</span><span class="sxs-lookup"><span data-stu-id="a58bd-148">Review your default enrichment preferences and update them as needed.</span></span>

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Екранна снимка на прозореца за предпочитания за обогатяване.":::

### <a name="select-entity-to-enrich"></a><span data-ttu-id="a58bd-150">Избор на обект за обогатяване</span><span class="sxs-lookup"><span data-stu-id="a58bd-150">Select entity to enrich</span></span>

<span data-ttu-id="a58bd-151">Изберете **Допълнен обект** и изберете набора от данни, който искате да допълните фирмените данни от Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a58bd-151">Select **Enriched entity** and choose the data set you want to enrich with company data from the Microsoft.</span></span> <span data-ttu-id="a58bd-152">Можете да изберете Клиент обект, за да обогатите всичките си клиентски профили или да изберете сегментен обект, за да обогатите само клиентски профили, съдържащи се в този сегмент.</span><span class="sxs-lookup"><span data-stu-id="a58bd-152">You can select the Customer entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

### <a name="map-your-fields"></a><span data-ttu-id="a58bd-153">Нанесете полетата</span><span class="sxs-lookup"><span data-stu-id="a58bd-153">Map your fields</span></span>

<span data-ttu-id="a58bd-154">Съставете полета от вашата обединена клиентска единица, за да определите демографския сегмент, който искате системата да използва за обогатяване на вашите клиентски данни.</span><span class="sxs-lookup"><span data-stu-id="a58bd-154">Map fields from your unified customer entity to define the demographic segment you want the system to use for enriching your customer data.</span></span> <span data-ttu-id="a58bd-155">Карта на държава / регион и поне атрибути на дата на раждане или пол.</span><span class="sxs-lookup"><span data-stu-id="a58bd-155">Map Country/Region and at least Date of Birth or Gender attributes.</span></span> <span data-ttu-id="a58bd-156">Освен това трябва да съпоставите поне едно от „Град“ (и „Щат/провинция“) или „Пощенски код“.</span><span class="sxs-lookup"><span data-stu-id="a58bd-156">Additionally, you must map at least one of City (and State/Province) or Postal code.</span></span> <span data-ttu-id="a58bd-157">Изберете **Редактиране**, за да определите нанасянето на полетата, и изберете **Прилагане**, когато сте готови.</span><span class="sxs-lookup"><span data-stu-id="a58bd-157">Select **Edit** to define the mapping of the fields and select **Apply** when you're done.</span></span> <span data-ttu-id="a58bd-158">Изберете **Записване**, за да завършите съпоставянето на полета.</span><span class="sxs-lookup"><span data-stu-id="a58bd-158">Select **Save** to complete the field mapping.</span></span>

<span data-ttu-id="a58bd-159">Поддържат се следните формати и стойности, като стойностите не са чувствителни към регистъра:</span><span class="sxs-lookup"><span data-stu-id="a58bd-159">The following formats and values are supported, values are not case-sensitive:</span></span>

- <span data-ttu-id="a58bd-160">**Дата на раждане**: Препоръчваме датата на раждане да се преобразува в тип DateTime по време на приемане на данни.</span><span class="sxs-lookup"><span data-stu-id="a58bd-160">**Date of Birth**: We recommend that date of birth is converted to DateTime type during data ingestion.</span></span> <span data-ttu-id="a58bd-161">Алтернативно, тя може да бъде низ в [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) формат "yyyy-MM-dd" или "yyyy-MM-ddTHH:mm:ssZ".</span><span class="sxs-lookup"><span data-stu-id="a58bd-161">Alternatively, it can be a string in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format "yyyy-MM-dd" or "yyyy-MM-ddTHH:mm:ssZ".</span></span>
- <span data-ttu-id="a58bd-162">**Пол**: мъж, жена, неизвестен</span><span class="sxs-lookup"><span data-stu-id="a58bd-162">**Gender**: Male, Female, Unknown</span></span>
- <span data-ttu-id="a58bd-163">**Пощенски код**: Петцифрени пощенски кодове за САЩ, стандартен пощенски код навсякъде другаде</span><span class="sxs-lookup"><span data-stu-id="a58bd-163">**Postal code**: Five-digit ZIP Codes for US, standard postal code everywhere else</span></span>
- <span data-ttu-id="a58bd-164">**Град**: Име на град на английски</span><span class="sxs-lookup"><span data-stu-id="a58bd-164">**City**: City name in English</span></span>
- <span data-ttu-id="a58bd-165">**Щат/Провинция**: Съкращение с две букви за САЩ и Канада.</span><span class="sxs-lookup"><span data-stu-id="a58bd-165">**State/Province**: Two-letter abbreviation for the US and Canada.</span></span> <span data-ttu-id="a58bd-166">Съкращение с две или три букви за Австралия.</span><span class="sxs-lookup"><span data-stu-id="a58bd-166">Two or three letter abbreviation for Australia.</span></span> <span data-ttu-id="a58bd-167">Не е приложимо за Франция, Германия или Великобритания.</span><span class="sxs-lookup"><span data-stu-id="a58bd-167">Not applicable for France, Germany, or the UK.</span></span>
- <span data-ttu-id="a58bd-168">**Страна/регион**:</span><span class="sxs-lookup"><span data-stu-id="a58bd-168">**Country/Region**:</span></span>

  - <span data-ttu-id="a58bd-169">САЩ: Съединени американски щати, Съединени щати, САЩ, Америка</span><span class="sxs-lookup"><span data-stu-id="a58bd-169">US: United States of America, United States, USA, US, America</span></span>
  - <span data-ttu-id="a58bd-170">CA: Канада, Калифорния</span><span class="sxs-lookup"><span data-stu-id="a58bd-170">CA: Canada, CA</span></span>
  - <span data-ttu-id="a58bd-171">GB: Обединено кралство, Великобритания, Обединено кралство Великобритания и Северна Ирландия, Обединено кралство Великобритания</span><span class="sxs-lookup"><span data-stu-id="a58bd-171">GB: United Kingdom, UK, Great Britain, GB, United Kingdom of Great Britain and Northern Ireland, United Kingdom of Great Britain</span></span>
  - <span data-ttu-id="a58bd-172">AU: Австралия, Общо богатство на Австралия</span><span class="sxs-lookup"><span data-stu-id="a58bd-172">AU: Australia, AU, Common Wealth of Australia</span></span>
  - <span data-ttu-id="a58bd-173">FR: Франция. Френска република</span><span class="sxs-lookup"><span data-stu-id="a58bd-173">FR: France, FR, French Republic</span></span>
  - <span data-ttu-id="a58bd-174">DE: Германия, Федерална република Германия, Република Германия</span><span class="sxs-lookup"><span data-stu-id="a58bd-174">DE: Germany, German, Deutschland, Allemagne, DE, Federal Republic of Germany, Republic of Germany</span></span>

## <a name="review-and-name-the-enrichment"></a><span data-ttu-id="a58bd-175">Преглед и задаване на име на допълването</span><span class="sxs-lookup"><span data-stu-id="a58bd-175">Review and name the enrichment</span></span>

<span data-ttu-id="a58bd-176">И накрая, може да прегледате информацията и да предоставите име за допълването.</span><span class="sxs-lookup"><span data-stu-id="a58bd-176">Finally, you get to review the information and provide a name for the enrichment.</span></span>

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="Страница за преглед на интереси и задаване на име.":::

## <a name="refresh-enrichment"></a><span data-ttu-id="a58bd-178">Освежете обогатяването</span><span class="sxs-lookup"><span data-stu-id="a58bd-178">Refresh enrichment</span></span>

<span data-ttu-id="a58bd-179">Изпълнете допълването след конфигуриране на марки, интереси и нанасяне на полета за демографски данни.</span><span class="sxs-lookup"><span data-stu-id="a58bd-179">Run the enrichment after configuring brands, interests, and the field mapping for demographics.</span></span> <span data-ttu-id="a58bd-180">За да стартирате процеса, изберете **Стартиране** на страницата за конфигуриране на марки или интереси.</span><span class="sxs-lookup"><span data-stu-id="a58bd-180">To start the process, select **Run** on the brand or interest configuration page.</span></span> <span data-ttu-id="a58bd-181">Освен това можете да оставите системата да изпълни допълването автоматично като част от планирано обновяване.</span><span class="sxs-lookup"><span data-stu-id="a58bd-181">Additionally, you can let the system run the enrichment automatically as part of a scheduled refresh.</span></span>
<span data-ttu-id="a58bd-182">В зависимост от размера на клиентските данни, завършването на допълването може да отнеме няколко минути.</span><span class="sxs-lookup"><span data-stu-id="a58bd-182">Depending on the size of your customer data, it may take several minutes for an enrichment run to complete.</span></span>

> [!TIP]
> <span data-ttu-id="a58bd-183">Съществуват [шест вида статус](system.md#status-types) на задачите/процесите.</span><span class="sxs-lookup"><span data-stu-id="a58bd-183">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="a58bd-184">Освен това повечето процеси [зависят от други процеси надолу по веригата](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="a58bd-184">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="a58bd-185">Можете да изберете състоянието на процес, за да видите подробности за напредъка на цялата задача.</span><span class="sxs-lookup"><span data-stu-id="a58bd-185">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="a58bd-186">След като изберете **Вижте подробности** за една от задачите на заданието, ще намерите допълнителна информация: време за обработка, дата на последната обработка и всички грешки и предупреждения, свързани със задачата.</span><span class="sxs-lookup"><span data-stu-id="a58bd-186">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="a58bd-187">Резултати от допълването</span><span class="sxs-lookup"><span data-stu-id="a58bd-187">Enrichment results</span></span>

<span data-ttu-id="a58bd-188">След като стартирате процеса за допълване, отидете в **Моите допълвания**, за да прегледате общия брой допълнени клиенти и разбивка на марки или интереси в допълнените клиентски профили.</span><span class="sxs-lookup"><span data-stu-id="a58bd-188">After running the enrichment process, go to **My enrichments** to review the total number of enriched customers and a breakdown of brands or interests in the enriched customer profiles.</span></span>

:::image type="content" source="media/my-enrichments.png" alt-text="Преглед на резултатите след изпълнение на процеса на допълване":::

<span data-ttu-id="a58bd-190">Прегледайте допълнените данни, като изберете **Преглед на допълнени данни** в диаграмата.</span><span class="sxs-lookup"><span data-stu-id="a58bd-190">Review the enriched data by selecting **View enriched data** in the chart.</span></span> <span data-ttu-id="a58bd-191">Допълнените данни за марки отиват в обекта **BrandAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="a58bd-191">Enriched data for brands goes to the **BrandAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="a58bd-192">Данните за интереси са в обекта **InterestAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="a58bd-192">Data for interests is in the **InterestAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="a58bd-193">Ще намерите тези обекти, посочени и в групата **Допълване** в **Данни** > **Обекти**.</span><span class="sxs-lookup"><span data-stu-id="a58bd-193">You'll also find these entities listed in the **Enrichment** group in **Data** > **Entities**.</span></span>

## <a name="see-enrichment-data-on-the-customer-card"></a><span data-ttu-id="a58bd-194">Преглед на данните за допълване в картата на клиента</span><span class="sxs-lookup"><span data-stu-id="a58bd-194">See enrichment data on the customer card</span></span>

<span data-ttu-id="a58bd-195">Афинитетите към марки и интереси могат да се прегледат и в отделни карти на клиент.</span><span class="sxs-lookup"><span data-stu-id="a58bd-195">Brand and interest affinities can also be viewed on individual customer cards.</span></span> <span data-ttu-id="a58bd-196">Отидете на **Клиенти** и изберете клиентски профил.</span><span class="sxs-lookup"><span data-stu-id="a58bd-196">Go to **Customers** and select a customer profile.</span></span> <span data-ttu-id="a58bd-197">В клиентската карта ще намерите диаграми за марките или интересите, към които хората в демографския профил на този клиент имат афинитет.</span><span class="sxs-lookup"><span data-stu-id="a58bd-197">In the customer card, you'll find charts for the brands or interests that people in that customer's demographic profile have affinity for.</span></span>

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Карта на клиент с допълнени данни":::

## <a name="next-steps"></a><span data-ttu-id="a58bd-199">Следващи стъпки</span><span class="sxs-lookup"><span data-stu-id="a58bd-199">Next steps</span></span>

<span data-ttu-id="a58bd-200">Надградете допълнените клиентски данни.</span><span class="sxs-lookup"><span data-stu-id="a58bd-200">Build on top of your enriched customer data.</span></span> <span data-ttu-id="a58bd-201">Създайте [сегменти](segments.md), [мерки](measures.md) и дори [експортирайте данните](export-destinations.md), за да доставите персонализирани преживявания на клиентите си.</span><span class="sxs-lookup"><span data-stu-id="a58bd-201">Create [Segments](segments.md), [Measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
