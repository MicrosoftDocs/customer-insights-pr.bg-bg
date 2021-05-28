---
title: Адресно обогатяване
description: Обогатете и нормализирайте адресната информация на потребителските профили с моделите на Microsoft.
ms.date: 04/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 07271d491460764f2c738e760e41c3492f2b6de9
ms.sourcegitcommit: 27f9dd837304ef9fc00f055a6e900fbf6fce1429
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 04/30/2021
ms.locfileid: "5965565"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a><span data-ttu-id="9ec26-103">Обогатяване на потребителски профили с подобрени адреси</span><span class="sxs-lookup"><span data-stu-id="9ec26-103">Enrichment of customer profiles with enhanced addresses</span></span>

<span data-ttu-id="9ec26-104">Адресите във вашите данни могат да бъдат неструктурирани, непълни или неправилни.</span><span class="sxs-lookup"><span data-stu-id="9ec26-104">Addresses in your data can be unstructured, incomplete, or incorrect.</span></span> <span data-ttu-id="9ec26-105">Използвайте моделите на Microsoft, за да нормализирате и обогатите адресите си във [формата на Common Data Model](/common-data-model/schema/core/applicationcommon/address) за по-добра точност и прозрения.</span><span class="sxs-lookup"><span data-stu-id="9ec26-105">Use Microsoft's models to normalize and enrich your addresses into the [Common Data Model format](/common-data-model/schema/core/applicationcommon/address) for better accuracy and insights.</span></span>

## <a name="how-we-enhance-addresses"></a><span data-ttu-id="9ec26-106">Как подобряваме адресите</span><span class="sxs-lookup"><span data-stu-id="9ec26-106">How we enhance addresses</span></span>

<span data-ttu-id="9ec26-107">Нашият модел преминава през процес от две стъпки за подобряване на адрес.</span><span class="sxs-lookup"><span data-stu-id="9ec26-107">Our model goes through a two-step process to enhance an address.</span></span> <span data-ttu-id="9ec26-108">Първо, той анализира адреса, за да идентифицира компонентите му и ги поставя в структуриран формат.</span><span class="sxs-lookup"><span data-stu-id="9ec26-108">First, it parses the address to identify its components and puts them into a structured format.</span></span> <span data-ttu-id="9ec26-109">След това използваме изкуствен интелект, за да коригираме, допълним и стандартизираме стойностите в адреса.</span><span class="sxs-lookup"><span data-stu-id="9ec26-109">Then, we use artificial intelligence to correct, complete, and standardize the values in the address.</span></span>

### <a name="example"></a><span data-ttu-id="9ec26-110">Пример</span><span class="sxs-lookup"><span data-stu-id="9ec26-110">Example</span></span>

<span data-ttu-id="9ec26-111">Информацията за адреса може да е в нестандартен формат и да съдържа правописни грешки.</span><span class="sxs-lookup"><span data-stu-id="9ec26-111">Address information might be in a non-standard format and contain spelling errors.</span></span> <span data-ttu-id="9ec26-112">Моделът може да поправи тези проблеми и да създаде последователни адреси в единни клиентски профили.</span><span class="sxs-lookup"><span data-stu-id="9ec26-112">The model can fix these issues and create consistent addresses in unified customer profiles.</span></span>

```Input
4567 w main stret californa missouri 54321 us
```

```Output
- Street1: 4567 W Main St
- City: California
- StateOrProvince: MO
- ZipOrPostalCode: 54321
- CountryOrRegion: United States of America

- Address: 4567 W Main St, California, MO, 54321, United States of America
```

### <a name="limitations"></a><span data-ttu-id="9ec26-113">Ограничения</span><span class="sxs-lookup"><span data-stu-id="9ec26-113">Limitations</span></span>

<span data-ttu-id="9ec26-114">Подобрените адреси работят само със стойностите, които вече съществуват в погълнатите ви адресни данни.</span><span class="sxs-lookup"><span data-stu-id="9ec26-114">Enhanced addresses only works with the values that already exist in your ingested address data.</span></span> <span data-ttu-id="9ec26-115">Моделът не:</span><span class="sxs-lookup"><span data-stu-id="9ec26-115">The model doesn't:</span></span> 

1. <span data-ttu-id="9ec26-116">Проверява дали адресът е валиден адрес.</span><span class="sxs-lookup"><span data-stu-id="9ec26-116">Verify if the address is a valid address.</span></span>
2. <span data-ttu-id="9ec26-117">Проверява дали някоя от стойностите, като пощенски кодове или имена на улици, е валидна.</span><span class="sxs-lookup"><span data-stu-id="9ec26-117">Verify if any of the values, such as ZIP codes or street names, are valid.</span></span>
3. <span data-ttu-id="9ec26-118">Променя стойностите, които не разпознава.</span><span class="sxs-lookup"><span data-stu-id="9ec26-118">Change values it doesn't recognize.</span></span>

<span data-ttu-id="9ec26-119">Моделът използва техники, базирани на машинно обучение, за подобряване на адресите.</span><span class="sxs-lookup"><span data-stu-id="9ec26-119">The model uses machine learning-based techniques to enhance addresses.</span></span> <span data-ttu-id="9ec26-120">Въпреки че прилагаме висок праг на доверие, когато моделът променя входната стойност, както при всеки модел, базиран на ML, не е гарантирана 100% точност.</span><span class="sxs-lookup"><span data-stu-id="9ec26-120">While we apply a high confidence threshold for when the model changes an input value, as with any ML-based model, 100% accuracy is not guaranteed.</span></span>

## <a name="supported-countries-or-regions"></a><span data-ttu-id="9ec26-121">Поддържани държави или региони</span><span class="sxs-lookup"><span data-stu-id="9ec26-121">Supported countries or regions</span></span>

<span data-ttu-id="9ec26-122">Понастоящем поддържаме обогатяващи адреси в тези страни или региони:</span><span class="sxs-lookup"><span data-stu-id="9ec26-122">We currently support enriching addresses in these countries or regions:</span></span> 

- <span data-ttu-id="9ec26-123">Австралия</span><span class="sxs-lookup"><span data-stu-id="9ec26-123">Australia</span></span>
- <span data-ttu-id="9ec26-124">Канада</span><span class="sxs-lookup"><span data-stu-id="9ec26-124">Canada</span></span>
- <span data-ttu-id="9ec26-125">Обединено кралство</span><span class="sxs-lookup"><span data-stu-id="9ec26-125">United Kingdom</span></span>
- <span data-ttu-id="9ec26-126">САЩ</span><span class="sxs-lookup"><span data-stu-id="9ec26-126">United States</span></span>

<span data-ttu-id="9ec26-127">Адресите трябва да съдържат стойност за държава/регион.</span><span class="sxs-lookup"><span data-stu-id="9ec26-127">Addresses must contain a country/region value.</span></span> <span data-ttu-id="9ec26-128">Ние не обработваме адреси за държави или региони, които не се поддържат и адреси, които не са предоставили държава или регион.</span><span class="sxs-lookup"><span data-stu-id="9ec26-128">We don't process addresses for countries or regions that aren't supported and addresses that have no country or region provided.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="9ec26-129">Конфигуриране на допълването</span><span class="sxs-lookup"><span data-stu-id="9ec26-129">Configure the enrichment</span></span>

1. <span data-ttu-id="9ec26-130">Отидете в **Данни** > **Допълване**.</span><span class="sxs-lookup"><span data-stu-id="9ec26-130">Go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="9ec26-131">Изберете **Обогатете данните ми** на **Подобрени адреси** плочка.</span><span class="sxs-lookup"><span data-stu-id="9ec26-131">Select **Enrich my data** on the **Enhanced addresses** tile.</span></span>

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="Екранна снимка на плочката Разширени адреси.":::

1. <span data-ttu-id="9ec26-133">Изберете **Набор от данни на клиента** и изберете обекта, съдържащ адресите, които искате да обогатите.</span><span class="sxs-lookup"><span data-stu-id="9ec26-133">Select the **Customer data set** and choose the entity containing the addresses you want to enrich.</span></span> <span data-ttu-id="9ec26-134">Можете да изберете *Клиент* обект за обогатяване на адреси във всички ваши клиентски профили или изберете сегмент за обогатяване на адреси само в клиентски профили, съдържащи се в този сегмент.</span><span class="sxs-lookup"><span data-stu-id="9ec26-134">You can select the *Customer* entity to enrich addresses in all your customer profiles or select a segment entity to enrich addresses only in customer profiles contained in that segment.</span></span>

1. <span data-ttu-id="9ec26-135">Изберете формата на адресите в набора ви от данни.</span><span class="sxs-lookup"><span data-stu-id="9ec26-135">Select how addresses are formatted in your data set.</span></span> <span data-ttu-id="9ec26-136">Изберете **Адрес с един атрибут**, ако адресите във вашите данни използват едно поле.</span><span class="sxs-lookup"><span data-stu-id="9ec26-136">Choose **Single-attribute address** if addresses in your data use a single field.</span></span> <span data-ttu-id="9ec26-137">Изберете **Адрес с много атрибути**, ако адресите във вашите данни използват повече от едно поле за данни.</span><span class="sxs-lookup"><span data-stu-id="9ec26-137">Choose **Multiple-attribute address** if addresses in your data use more than one data field.</span></span>

   > [!NOTE]
   > <span data-ttu-id="9ec26-138">Държава / регион е задължителен както в едноатрибутен, така и в многоатрибутен адрес.</span><span class="sxs-lookup"><span data-stu-id="9ec26-138">Country/Region is mandatory in both single-attribute and multiple-attribute address.</span></span> <span data-ttu-id="9ec26-139">Адресите, които не съдържат валидни или поддържани стойности за държава / регион, няма да бъдат обогатени</span><span class="sxs-lookup"><span data-stu-id="9ec26-139">Addresses that don't contain valid or supported country/region values won't be enriched</span></span>

1.  <span data-ttu-id="9ec26-140">Съставете адресните полета от вашия обединен клиентски обект.</span><span class="sxs-lookup"><span data-stu-id="9ec26-140">Map the address fields from your unified customer entity.</span></span>

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Подобрена страница за картографиране на адресно поле.":::

1. <span data-ttu-id="9ec26-142">Изберете **Напред**, за да завършите съпоставянето на полета.</span><span class="sxs-lookup"><span data-stu-id="9ec26-142">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="9ec26-143">Въведете име за допълването и изходния обект.</span><span class="sxs-lookup"><span data-stu-id="9ec26-143">Provide a name for the enrichment and the output entity.</span></span>

1. <span data-ttu-id="9ec26-144">Изберете **Записване на допълването**, след като прегледате избора си.</span><span class="sxs-lookup"><span data-stu-id="9ec26-144">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="9ec26-145">Резултати от допълването</span><span class="sxs-lookup"><span data-stu-id="9ec26-145">Enrichment results</span></span>

<span data-ttu-id="9ec26-146">За да започнете процеса на допълване, изберете **Стартиране** от командната лента.</span><span class="sxs-lookup"><span data-stu-id="9ec26-146">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="9ec26-147">Можете също така да оставите системата да стартира допълването автоматично като част от [планирано обновяване](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="9ec26-147">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="9ec26-148">Времето за обработка зависи от размера на вашите клиентски данни.</span><span class="sxs-lookup"><span data-stu-id="9ec26-148">The processing time depends on the size of your customer data.</span></span>

<span data-ttu-id="9ec26-149">След като процесът на допълване завърши, можете да прегледате току-що допълнените данни за потребителски профили в **Моите допълвания**.</span><span class="sxs-lookup"><span data-stu-id="9ec26-149">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="9ec26-150">Освен това ще намерите часа на последната актуализация и броя на допълнените профили.</span><span class="sxs-lookup"><span data-stu-id="9ec26-150">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="9ec26-151">Можете да получите достъп до подробен изглед на всеки допълнен профил, като изберете **Преглед на допълнените данни**.</span><span class="sxs-lookup"><span data-stu-id="9ec26-151">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="9ec26-152">Следващи стъпки</span><span class="sxs-lookup"><span data-stu-id="9ec26-152">Next steps</span></span>

<span data-ttu-id="9ec26-153">Надградете допълнените клиентски данни.</span><span class="sxs-lookup"><span data-stu-id="9ec26-153">Build on top of your enriched customer data.</span></span> <span data-ttu-id="9ec26-154">Създайте [сегменти](segments.md), [мерки](measures.md) и дори [експортирайте данните](export-destinations.md), за да доставите персонализирано изживяване на клиентите си.</span><span class="sxs-lookup"><span data-stu-id="9ec26-154">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
