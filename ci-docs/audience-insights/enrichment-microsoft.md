---
title: Допълване на клиентски профили с данни от Microsoft
description: Използвайте собствени данни от Microsoft, за да допълните данните на клиентите с афинитет към марки и интереси.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: be042dd139607849b795c903fa58da2edb9ff589
ms.sourcegitcommit: 72603fb39c4d5dbca71128815a2e1692542ea4dc
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 05/19/2021
ms.locfileid: "6064878"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a><span data-ttu-id="89143-103">Допълване на клиентски профили с афинитети към марки и интереси (преглед)</span><span class="sxs-lookup"><span data-stu-id="89143-103">Enrich customer profiles with brand and interest affinities (preview)</span></span>

<span data-ttu-id="89143-104">Използвайте собствени данни на Microsoft, за да допълните данните на клиентите с афинитет към марки и интереси.</span><span class="sxs-lookup"><span data-stu-id="89143-104">Use Microsoft's proprietary data to enrich your customer data with brand and interest affinities.</span></span> <span data-ttu-id="89143-105">Тези афинитети се определят въз основа на данни от хора с демография, сходна с тази на вашите клиенти.</span><span class="sxs-lookup"><span data-stu-id="89143-105">These affinities are determined based on data from people with similar demographics to your customers.</span></span> <span data-ttu-id="89143-106">Тази информация ви помага да разберете по-добре и сегментирате клиентите си въз основа на афинитета им към конкретни марки и интереси.</span><span class="sxs-lookup"><span data-stu-id="89143-106">This information helps you to better understand and segment your customers based on their affinities to specific brands and interests.</span></span>

<span data-ttu-id="89143-107">В аналитични данни за аудитория, отидете на **Данни** > **Обогатяване**, за да [конфигурирате и прегледате обогатявания](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="89143-107">In audience insights, go to **Data** > **Enrichment** to [configure and view enrichments](enrichment-hub.md).</span></span>

<span data-ttu-id="89143-108">За да конфигурирате допълването на афинитети към марки, отидете в раздела **Откриване** и изберете **Допълване на моите данни** в плочката **Марки**.</span><span class="sxs-lookup"><span data-stu-id="89143-108">To configure brand affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Brands** tile.</span></span>

<span data-ttu-id="89143-109">За да конфигурирате допълването на афинитети към интереси, отидете в раздела **Откриване** и изберете **Допълване на моите данни** в плочката **Интереси**.</span><span class="sxs-lookup"><span data-stu-id="89143-109">To configure interest affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Interests** tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="89143-110">![Плочки с марки и интереси](media/BrandsInterest-tile-Hub.png "Плочки с марки и интереси")</span><span class="sxs-lookup"><span data-stu-id="89143-110">![Brands & Interests tiles](media/BrandsInterest-tile-Hub.png "Brands & Interest tiles")</span></span>

## <a name="how-we-determine-affinities"></a><span data-ttu-id="89143-111">Как определяме афинитета</span><span class="sxs-lookup"><span data-stu-id="89143-111">How we determine affinities</span></span>

<span data-ttu-id="89143-112">Използваме данните за онлайн търсене на Microsoft, за да намерим афинитети към марки и интереси в различни демографски сегменти (дефинирани по възраст, пол или местоположение).</span><span class="sxs-lookup"><span data-stu-id="89143-112">We use Microsoft’s online search data to find affinities for brands and interests across various demographic segments (defined by age, gender, or location).</span></span> <span data-ttu-id="89143-113">Размерът на онлайн търсенето на марка или интерес определя размера на афинитета на даден демографски сегмент в сравнение с други сегменти към тази марка или интерес.</span><span class="sxs-lookup"><span data-stu-id="89143-113">The online search volume for a brand or interest determines how much affinity a demographic segment, compared to other segments, has to that brand or interest.</span></span>

## <a name="affinity-level-and-score"></a><span data-ttu-id="89143-114">Ниво на афинитет и резултат</span><span class="sxs-lookup"><span data-stu-id="89143-114">Affinity level and score</span></span>

<span data-ttu-id="89143-115">За всеки обогатен потребителски профил ние предоставяме две свързани стойности - ниво на афинитет и оценка на афинитета.</span><span class="sxs-lookup"><span data-stu-id="89143-115">On every enriched customer profile, we provide two related values – affinity level and affinity score.</span></span> <span data-ttu-id="89143-116">Тези стойности ви помагат да определите колко силен е афинитетът към демографския сегмент на този профил, към марка или интерес, в сравнение с други демографски сегменти.</span><span class="sxs-lookup"><span data-stu-id="89143-116">These values help you determine how strong the affinity is for that profile’s demographic segment, for a brand or interest, as compared to other demographic segments.</span></span>

<span data-ttu-id="89143-117">*Ниво на афинитет* се състои от четири нива, а *оценка на афинитет* се изчислява по 100-точкова скала, която съответства на нивата на афинитет.</span><span class="sxs-lookup"><span data-stu-id="89143-117">*Affinity level* consists of four levels and *affinity score* is calculated on a 100-point scale that maps to the affinity levels.</span></span>


|<span data-ttu-id="89143-118">Ниво на афинитет</span><span class="sxs-lookup"><span data-stu-id="89143-118">Affinity level</span></span> |<span data-ttu-id="89143-119">Резултат за афинитет</span><span class="sxs-lookup"><span data-stu-id="89143-119">Affinity score</span></span>  |
|---------|---------|
|<span data-ttu-id="89143-120">Много висок</span><span class="sxs-lookup"><span data-stu-id="89143-120">Very high</span></span>     | <span data-ttu-id="89143-121">85-100</span><span class="sxs-lookup"><span data-stu-id="89143-121">85-100</span></span>       |
|<span data-ttu-id="89143-122">Висока</span><span class="sxs-lookup"><span data-stu-id="89143-122">High</span></span>     | <span data-ttu-id="89143-123">70-84</span><span class="sxs-lookup"><span data-stu-id="89143-123">70-84</span></span>        |
|<span data-ttu-id="89143-124">Среден</span><span class="sxs-lookup"><span data-stu-id="89143-124">Medium</span></span>     | <span data-ttu-id="89143-125">35-69</span><span class="sxs-lookup"><span data-stu-id="89143-125">35-69</span></span>        |
|<span data-ttu-id="89143-126">Ниска</span><span class="sxs-lookup"><span data-stu-id="89143-126">Low</span></span>     | <span data-ttu-id="89143-127">1-34</span><span class="sxs-lookup"><span data-stu-id="89143-127">1-34</span></span>        |

<span data-ttu-id="89143-128">В зависимост от детайлността, която искате за измерване на афинитета, можете да използвате или ниво на афинитет, или оценка.</span><span class="sxs-lookup"><span data-stu-id="89143-128">Depending on the granularity you would like for measuring the affinity, you can use either affinity level or score.</span></span> <span data-ttu-id="89143-129">Резултатът за афинитет ви дава по-прецизен контрол.</span><span class="sxs-lookup"><span data-stu-id="89143-129">Affinity score gives you more precise control.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="89143-130">Поддържани държави / региони</span><span class="sxs-lookup"><span data-stu-id="89143-130">Supported countries/regions</span></span>

<span data-ttu-id="89143-131">В момента поддържаме следните опции за държава / регион: Австралия, Канада (английски), Франция, Германия, Обединеното кралство или Съединените щати (английски).</span><span class="sxs-lookup"><span data-stu-id="89143-131">We currently support the following country/region options: Australia, Canada (English), France, Germany, United Kingdom, or United States (English).</span></span>

<span data-ttu-id="89143-132">За да изберете държава, отворете **Обогатяване на марки** или **Обогатяване на интереси** и изберете **промяна** до **Държава/регион**.</span><span class="sxs-lookup"><span data-stu-id="89143-132">To select a country, open the **Brands enrichment** or **Interest enrichment** and select **Change** next to **Country/Region**.</span></span> <span data-ttu-id="89143-133">В екрана **Настройки за държава/регион** панел, изберете опция и изберете **Приложи**.</span><span class="sxs-lookup"><span data-stu-id="89143-133">In the **Country/Region settings** pane, choose an option and select **Apply**.</span></span>

### <a name="implications-related-to-country-selection"></a><span data-ttu-id="89143-134">Последици, свързани с избора на държава</span><span class="sxs-lookup"><span data-stu-id="89143-134">Implications related to country selection</span></span>

- <span data-ttu-id="89143-135">Когато [избирате собствени марки](#define-your-brands-or-interests), системата предоставя предложения въз основа на избраната държава или регион.</span><span class="sxs-lookup"><span data-stu-id="89143-135">When [choosing your own brands](#define-your-brands-or-interests), the system provides suggestions based on the selected country or region.</span></span>

- <span data-ttu-id="89143-136">Когато [избирате отрасъл](#define-your-brands-or-interests), ще получите най-подходящите марки или интереси въз основа на избраната държава или регион.</span><span class="sxs-lookup"><span data-stu-id="89143-136">When [choosing an industry](#define-your-brands-or-interests), you'll get the most relevant brands or interests based on the selected country or region.</span></span>

- <span data-ttu-id="89143-137">Когато [обогатявате профили](#refresh-enrichment), ние ще обогатим всички клиентски профили, за които получаваме данни за избраните марки и интереси.</span><span class="sxs-lookup"><span data-stu-id="89143-137">When [enriching profiles](#refresh-enrichment), we'll enrich all customer profiles for which we get data for the selected brands and interests.</span></span> <span data-ttu-id="89143-138">Включително профили, които не са в избраната държава или регион.</span><span class="sxs-lookup"><span data-stu-id="89143-138">Including profiles that are not in the selected country or region.</span></span> <span data-ttu-id="89143-139">Например, ако сте избрали Германия, ние ще допълним профилите, намиращи се в САЩ, ако имаме налични данни за избраните марки и интереси в САЩ.</span><span class="sxs-lookup"><span data-stu-id="89143-139">For example, if you selected Germany, we'll enrich profiles located in the United States if we have data available for the selected brands and interests in the US.</span></span>

## <a name="configure-enrichment"></a><span data-ttu-id="89143-140">Конфигуриране на допълване</span><span class="sxs-lookup"><span data-stu-id="89143-140">Configure Enrichment</span></span>

<span data-ttu-id="89143-141">Насоките ви помагат при конфигурирането на допълвания.</span><span class="sxs-lookup"><span data-stu-id="89143-141">A guided experience helps you through the configuration of the enrichments.</span></span> 

### <a name="define-your-brands-or-interests"></a><span data-ttu-id="89143-142">Определяне на марките или интересите</span><span class="sxs-lookup"><span data-stu-id="89143-142">Define your brands or interests</span></span>

<span data-ttu-id="89143-143">Изберете една от следните опции:</span><span class="sxs-lookup"><span data-stu-id="89143-143">Select one of the following options:</span></span>

- <span data-ttu-id="89143-144">**Отрасъл**: Системата идентифицира водещите марки или интереси, свързани с отрасъла, и допълва клиентските данни с тях.</span><span class="sxs-lookup"><span data-stu-id="89143-144">**Industry**: The system identifies the top brands or interests relevant to your industry and enriches your customer data with them.</span></span>
- <span data-ttu-id="89143-145">**Избор на собствени**: Изберете до пет елемента от списъка с марки или интереси, които са най-подходящи за вашата организация.</span><span class="sxs-lookup"><span data-stu-id="89143-145">**Choose your own**: Select up to five items from the list of brands or interests that are most relevant to your organization.</span></span>

<span data-ttu-id="89143-146">За да добавите марка или интерес, въведете я в областта за въвеждане, за да получите предложения, базирани на съвпадащи условия.</span><span class="sxs-lookup"><span data-stu-id="89143-146">To add a brand or interest, enter it in the input area to get suggestions based on matching terms.</span></span> <span data-ttu-id="89143-147">Ако в списъка не е включена марка или интерес, които търсите, изпратете ни обратна връзка, като използвате връзката **Предложение**.</span><span class="sxs-lookup"><span data-stu-id="89143-147">If we don't list a brand or interest you're looking for, send us feedback using the **Suggest** link.</span></span>

### <a name="review-enrichment-preferences"></a><span data-ttu-id="89143-148">Предпочитания за обогатяване на преглед</span><span class="sxs-lookup"><span data-stu-id="89143-148">Review enrichment preferences</span></span>

<span data-ttu-id="89143-149">Прегледайте предпочитанията си за обогатяване по подразбиране и ги актуализирайте при необходимост.</span><span class="sxs-lookup"><span data-stu-id="89143-149">Review your default enrichment preferences and update them as needed.</span></span>

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Екранна снимка на прозореца за предпочитания за обогатяване.":::

### <a name="select-entity-to-enrich"></a><span data-ttu-id="89143-151">Избор на обект за обогатяване</span><span class="sxs-lookup"><span data-stu-id="89143-151">Select entity to enrich</span></span>

<span data-ttu-id="89143-152">Изберете **Допълнен обект** и изберете набора от данни, който искате да допълните фирмените данни от Microsoft.</span><span class="sxs-lookup"><span data-stu-id="89143-152">Select **Enriched entity** and choose the data set you want to enrich with company data from the Microsoft.</span></span> <span data-ttu-id="89143-153">Можете да изберете Клиент обект, за да обогатите всичките си клиентски профили или да изберете сегментен обект, за да обогатите само клиентски профили, съдържащи се в този сегмент.</span><span class="sxs-lookup"><span data-stu-id="89143-153">You can select the Customer entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

### <a name="map-your-fields"></a><span data-ttu-id="89143-154">Нанесете полетата</span><span class="sxs-lookup"><span data-stu-id="89143-154">Map your fields</span></span>

<span data-ttu-id="89143-155">Съставете полета от вашата обединена клиентска единица, за да определите демографския сегмент, който искате системата да използва за обогатяване на вашите клиентски данни.</span><span class="sxs-lookup"><span data-stu-id="89143-155">Map fields from your unified customer entity to define the demographic segment you want the system to use for enriching your customer data.</span></span> <span data-ttu-id="89143-156">Карта на държава / регион и поне атрибути на дата на раждане или пол.</span><span class="sxs-lookup"><span data-stu-id="89143-156">Map Country/Region and at least Date of Birth or Gender attributes.</span></span> <span data-ttu-id="89143-157">Освен това трябва да съпоставите поне едно от „Град“ (и „Щат/провинция“) или „Пощенски код“.</span><span class="sxs-lookup"><span data-stu-id="89143-157">Additionally, you must map at least one of City (and State/Province) or Postal code.</span></span> <span data-ttu-id="89143-158">Изберете **Редактиране**, за да определите нанасянето на полетата, и изберете **Прилагане**, когато сте готови.</span><span class="sxs-lookup"><span data-stu-id="89143-158">Select **Edit** to define the mapping of the fields and select **Apply** when you're done.</span></span> <span data-ttu-id="89143-159">Изберете **Записване**, за да завършите съпоставянето на полета.</span><span class="sxs-lookup"><span data-stu-id="89143-159">Select **Save** to complete the field mapping.</span></span>

<span data-ttu-id="89143-160">Поддържат се следните формати и стойности, като стойностите не са чувствителни към регистъра:</span><span class="sxs-lookup"><span data-stu-id="89143-160">The following formats and values are supported, values are not case-sensitive:</span></span>

- <span data-ttu-id="89143-161">**Дата на раждане**: Препоръчваме датата на раждане да се преобразува в тип DateTime по време на приемане на данни.</span><span class="sxs-lookup"><span data-stu-id="89143-161">**Date of Birth**: We recommend that date of birth is converted to DateTime type during data ingestion.</span></span> <span data-ttu-id="89143-162">Алтернативно, тя може да бъде низ в [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) формат "yyyy-MM-dd" или "yyyy-MM-ddTHH:mm:ssZ".</span><span class="sxs-lookup"><span data-stu-id="89143-162">Alternatively, it can be a string in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format "yyyy-MM-dd" or "yyyy-MM-ddTHH:mm:ssZ".</span></span>
- <span data-ttu-id="89143-163">**Пол**: мъж, жена, неизвестен</span><span class="sxs-lookup"><span data-stu-id="89143-163">**Gender**: Male, Female, Unknown</span></span>
- <span data-ttu-id="89143-164">**Пощенски код**: Петцифрени пощенски кодове за САЩ, стандартен пощенски код навсякъде другаде</span><span class="sxs-lookup"><span data-stu-id="89143-164">**Postal code**: Five-digit ZIP Codes for US, standard postal code everywhere else</span></span>
- <span data-ttu-id="89143-165">**Град**: Име на град на английски</span><span class="sxs-lookup"><span data-stu-id="89143-165">**City**: City name in English</span></span>
- <span data-ttu-id="89143-166">**Щат/Провинция**: Съкращение с две букви за САЩ и Канада.</span><span class="sxs-lookup"><span data-stu-id="89143-166">**State/Province**: Two-letter abbreviation for the US and Canada.</span></span> <span data-ttu-id="89143-167">Съкращение с две или три букви за Австралия.</span><span class="sxs-lookup"><span data-stu-id="89143-167">Two or three letter abbreviation for Australia.</span></span> <span data-ttu-id="89143-168">Не е приложимо за Франция, Германия или Великобритания.</span><span class="sxs-lookup"><span data-stu-id="89143-168">Not applicable for France, Germany, or the UK.</span></span>
- <span data-ttu-id="89143-169">**Страна/регион**:</span><span class="sxs-lookup"><span data-stu-id="89143-169">**Country/Region**:</span></span>

  - <span data-ttu-id="89143-170">САЩ: Съединени американски щати, Съединени щати, САЩ, Америка</span><span class="sxs-lookup"><span data-stu-id="89143-170">US: United States of America, United States, USA, US, America</span></span>
  - <span data-ttu-id="89143-171">CA: Канада, Калифорния</span><span class="sxs-lookup"><span data-stu-id="89143-171">CA: Canada, CA</span></span>
  - <span data-ttu-id="89143-172">GB: Обединено кралство, Великобритания, Обединено кралство Великобритания и Северна Ирландия, Обединено кралство Великобритания</span><span class="sxs-lookup"><span data-stu-id="89143-172">GB: United Kingdom, UK, Great Britain, GB, United Kingdom of Great Britain and Northern Ireland, United Kingdom of Great Britain</span></span>
  - <span data-ttu-id="89143-173">AU: Австралия, Общо богатство на Австралия</span><span class="sxs-lookup"><span data-stu-id="89143-173">AU: Australia, AU, Common Wealth of Australia</span></span>
  - <span data-ttu-id="89143-174">FR: Франция. Френска република</span><span class="sxs-lookup"><span data-stu-id="89143-174">FR: France, FR, French Republic</span></span>
  - <span data-ttu-id="89143-175">DE: Германия, Федерална република Германия, Република Германия</span><span class="sxs-lookup"><span data-stu-id="89143-175">DE: Germany, German, Deutschland, Allemagne, DE, Federal Republic of Germany, Republic of Germany</span></span>

## <a name="review-and-name-the-enrichment"></a><span data-ttu-id="89143-176">Преглед и задаване на име на допълването</span><span class="sxs-lookup"><span data-stu-id="89143-176">Review and name the enrichment</span></span>

<span data-ttu-id="89143-177">И накрая, може да прегледате информацията и да предоставите име за допълването.</span><span class="sxs-lookup"><span data-stu-id="89143-177">Finally, you get to review the information and provide a name for the enrichment.</span></span>

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="Страница за преглед на интереси и задаване на име.":::

## <a name="refresh-enrichment"></a><span data-ttu-id="89143-179">Освежете обогатяването</span><span class="sxs-lookup"><span data-stu-id="89143-179">Refresh enrichment</span></span>

<span data-ttu-id="89143-180">Изпълнете допълването след конфигуриране на марки, интереси и нанасяне на полета за демографски данни.</span><span class="sxs-lookup"><span data-stu-id="89143-180">Run the enrichment after configuring brands, interests, and the field mapping for demographics.</span></span> <span data-ttu-id="89143-181">За да стартирате процеса, изберете **Стартиране** на страницата за конфигуриране на марки или интереси.</span><span class="sxs-lookup"><span data-stu-id="89143-181">To start the process, select **Run** on the brand or interest configuration page.</span></span> <span data-ttu-id="89143-182">Освен това можете да оставите системата да изпълни допълването автоматично като част от планирано обновяване.</span><span class="sxs-lookup"><span data-stu-id="89143-182">Additionally, you can let the system run the enrichment automatically as part of a scheduled refresh.</span></span>
<span data-ttu-id="89143-183">В зависимост от размера на клиентските данни, завършването на допълването може да отнеме няколко минути.</span><span class="sxs-lookup"><span data-stu-id="89143-183">Depending on the size of your customer data, it may take several minutes for an enrichment run to complete.</span></span>

> [!TIP]
> <span data-ttu-id="89143-184">Съществуват [шест вида статус](system.md#status-types) на задачите/процесите.</span><span class="sxs-lookup"><span data-stu-id="89143-184">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="89143-185">Освен това повечето процеси [зависят от други процеси надолу по веригата](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="89143-185">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="89143-186">Можете да изберете състоянието на процес, за да видите подробности за напредъка на цялата задача.</span><span class="sxs-lookup"><span data-stu-id="89143-186">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="89143-187">След като изберете **Вижте подробности** за една от задачите на заданието, ще намерите допълнителна информация: време за обработка, дата на последната обработка и всички грешки и предупреждения, свързани със задачата.</span><span class="sxs-lookup"><span data-stu-id="89143-187">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="89143-188">Резултати от допълването</span><span class="sxs-lookup"><span data-stu-id="89143-188">Enrichment results</span></span>

<span data-ttu-id="89143-189">След като стартирате процеса за допълване, отидете в **Моите допълвания**, за да прегледате общия брой допълнени клиенти и разбивка на марки или интереси в допълнените клиентски профили.</span><span class="sxs-lookup"><span data-stu-id="89143-189">After running the enrichment process, go to **My enrichments** to review the total number of enriched customers and a breakdown of brands or interests in the enriched customer profiles.</span></span>

:::image type="content" source="media/my-enrichments.png" alt-text="Преглед на резултатите след изпълнение на процеса на допълване":::

<span data-ttu-id="89143-191">Прегледайте допълнените данни, като изберете **Преглед на допълнени данни** в диаграмата.</span><span class="sxs-lookup"><span data-stu-id="89143-191">Review the enriched data by selecting **View enriched data** in the chart.</span></span> <span data-ttu-id="89143-192">Допълнените данни за марки отиват в обекта **BrandAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="89143-192">Enriched data for brands goes to the **BrandAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="89143-193">Данните за интереси са в обекта **InterestAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="89143-193">Data for interests is in the **InterestAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="89143-194">Ще намерите тези обекти, посочени и в групата **Допълване** в **Данни** > **Обекти**.</span><span class="sxs-lookup"><span data-stu-id="89143-194">You'll also find these entities listed in the **Enrichment** group in **Data** > **Entities**.</span></span>

## <a name="see-enrichment-data-on-the-customer-card"></a><span data-ttu-id="89143-195">Преглед на данните за допълване в картата на клиента</span><span class="sxs-lookup"><span data-stu-id="89143-195">See enrichment data on the customer card</span></span>

<span data-ttu-id="89143-196">Афинитетите към марки и интереси могат да се прегледат и в отделни карти на клиент.</span><span class="sxs-lookup"><span data-stu-id="89143-196">Brand and interest affinities can also be viewed on individual customer cards.</span></span> <span data-ttu-id="89143-197">Отидете на **Клиенти** и изберете клиентски профил.</span><span class="sxs-lookup"><span data-stu-id="89143-197">Go to **Customers** and select a customer profile.</span></span> <span data-ttu-id="89143-198">В клиентската карта ще намерите диаграми за марките или интересите, към които хората в демографския профил на този клиент имат афинитет.</span><span class="sxs-lookup"><span data-stu-id="89143-198">In the customer card, you'll find charts for the brands or interests that people in that customer's demographic profile have affinity for.</span></span>

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Карта на клиент с допълнени данни":::

## <a name="next-steps"></a><span data-ttu-id="89143-200">Следващи стъпки</span><span class="sxs-lookup"><span data-stu-id="89143-200">Next steps</span></span>

<span data-ttu-id="89143-201">Надградете допълнените клиентски данни.</span><span class="sxs-lookup"><span data-stu-id="89143-201">Build on top of your enriched customer data.</span></span> <span data-ttu-id="89143-202">Създайте [сегменти](segments.md), [мерки](measures.md) и дори [експортирайте данните](export-destinations.md), за да доставите персонализирани преживявания на клиентите си.</span><span class="sxs-lookup"><span data-stu-id="89143-202">Create [Segments](segments.md), [Measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
