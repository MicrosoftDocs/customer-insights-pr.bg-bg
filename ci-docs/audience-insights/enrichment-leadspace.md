---
title: Обогатяване на фирмени профили с Leadspace за обогатяване от трети страни
description: Обща информация за обогатяването чрез Leadspace на трети страни.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 0496d10c994cd077a778a6e745e3774e316765ae
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305189"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="d8aed-103">Допълване на фирмени профили с Leadspace (преглед)</span><span class="sxs-lookup"><span data-stu-id="d8aed-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="d8aed-104">Leadspace е фирма за анализ и обработка на данни, която предоставя B2B платформа за данни на клиенти.</span><span class="sxs-lookup"><span data-stu-id="d8aed-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="d8aed-105">Тя дава възможност на фирмите да допълнят своите данни за клиенти с унифицирани потребителски профили.</span><span class="sxs-lookup"><span data-stu-id="d8aed-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="d8aed-106">Допълването включва повече атрибути, като размер на фирмата, местоположение, индустрия и др.</span><span class="sxs-lookup"><span data-stu-id="d8aed-106">Enrichments include more attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d8aed-107">Предварителни изисквания</span><span class="sxs-lookup"><span data-stu-id="d8aed-107">Prerequisites</span></span>

<span data-ttu-id="d8aed-108">За да конфигурирате Leadspace, трябва да бъдат изпълнени следните предварителни изисквания:</span><span class="sxs-lookup"><span data-stu-id="d8aed-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="d8aed-109">Имате активен лиценз за Leadspace.</span><span class="sxs-lookup"><span data-stu-id="d8aed-109">You have an active Leadspace license.</span></span>
- <span data-ttu-id="d8aed-110">Да имате [унифицирани потребителски профили](customer-profiles.md) за фирми.</span><span class="sxs-lookup"><span data-stu-id="d8aed-110">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>
- <span data-ttu-id="d8aed-111">Връзка на Leadspace вече е конфигурирана от администратор или вие имате разрешения на [администратор](permissions.md#administrator) и „постоянния ключ” (наричан **маркер на Leadspace**).</span><span class="sxs-lookup"><span data-stu-id="d8aed-111">A Leadspace connection has already been configured by an administrator or you have [administrator](permissions.md#administrator) permissions and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="d8aed-112">Свържете се директно с [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) за подробности за продукта.</span><span class="sxs-lookup"><span data-stu-id="d8aed-112">Contact [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) directly for details about their product.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="d8aed-113">Конфигуриране на допълването</span><span class="sxs-lookup"><span data-stu-id="d8aed-113">Configure the enrichment</span></span>

1. <span data-ttu-id="d8aed-114">В статията за аудиторията отидете на **Данни** > **Обогатяване**.</span><span class="sxs-lookup"><span data-stu-id="d8aed-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="d8aed-115">Изберете **Допълване на моите данни** на плочката на Leadspace и изберете **Начало**.</span><span class="sxs-lookup"><span data-stu-id="d8aed-115">Select **Enrich my data** on the Leadspace tile and select **Get started**.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="Екранна снимка на плочката Leadspace.":::

1. <span data-ttu-id="d8aed-117">Изберете [връзка](connections.md) от падащия списък.</span><span class="sxs-lookup"><span data-stu-id="d8aed-117">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="d8aed-118">Свържете се с администратор, ако няма налична връзка.</span><span class="sxs-lookup"><span data-stu-id="d8aed-118">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="d8aed-119">Ако сте администратор, можете да създадете връзка, като изберете **Добавяне на връзка**, след което **Leadspace**.</span><span class="sxs-lookup"><span data-stu-id="d8aed-119">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **Leadspace**.</span></span> 

1. <span data-ttu-id="d8aed-120">Изберете **Свързване с Leadspace**, за да потвърдите избора на връзката.</span><span class="sxs-lookup"><span data-stu-id="d8aed-120">Select **Connect to Leadspace** to confirm the connection.</span></span>

1. <span data-ttu-id="d8aed-121">Изберете **Напред** и изберете **набора от данни на клиента**, който искате да допълните фирмените си данни от Leadspace.</span><span class="sxs-lookup"><span data-stu-id="d8aed-121">Select **Next** and choose the **Customer data set** you want to enrich with company data from Leadspace.</span></span> <span data-ttu-id="d8aed-122">Можете да изберете **Клиент** обект, за да обогатите всичките си клиентски профили или да изберете сегментен обект, за да обогатите само клиентски профили, съдържащи се в този сегмент.</span><span class="sxs-lookup"><span data-stu-id="d8aed-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Снимка на екрана при избора на набор от данни за клиенти.":::

1. <span data-ttu-id="d8aed-124">Изберете **Напред** и дефинирайте кой тип полета от унифицираните профили се използват за търсене на съответстващи фирмени данни от Leadspace.</span><span class="sxs-lookup"><span data-stu-id="d8aed-124">Select **Next** and define which fields from your unified profiles are used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="d8aed-125">Полето **Име на компания** е задължително.</span><span class="sxs-lookup"><span data-stu-id="d8aed-125">The **Name of company** field is required.</span></span> <span data-ttu-id="d8aed-126">За по-висока точност на съвпадение, до две други полета, **Уебсайт на компанията** и **Местоположение на фирмата**, може да се добави.</span><span class="sxs-lookup"><span data-stu-id="d8aed-126">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Панел за нанасяне на полето Leadspace.":::

1. <span data-ttu-id="d8aed-128">Изберете **Напред**, за да завършите съпоставянето на полета.</span><span class="sxs-lookup"><span data-stu-id="d8aed-128">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="d8aed-129">Посочете име за допълването и изберете **Записване на допълване**, след като прегледате избора си.</span><span class="sxs-lookup"><span data-stu-id="d8aed-129">Provide a name for the enrichment and select **Save enrichment** after reviewing your choices.</span></span>


## <a name="configure-the-connection-for-leadspace"></a><span data-ttu-id="d8aed-130">Конфигуриране на връзката за Leadspace</span><span class="sxs-lookup"><span data-stu-id="d8aed-130">Configure the connection for Leadspace</span></span> 

<span data-ttu-id="d8aed-131">Трябва да сте администратор, за да конфигурирате връзки.</span><span class="sxs-lookup"><span data-stu-id="d8aed-131">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="d8aed-132">Изберете **Добавяне на връзка**, когато конфигурирате допълването, *или* отидете на **Администратор** > **Връзки** и изберете **Настройка** в плочката на Leadspace.</span><span class="sxs-lookup"><span data-stu-id="d8aed-132">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Leadspace tile.</span></span>

1. <span data-ttu-id="d8aed-133">Изберете **Първи стъпки**.</span><span class="sxs-lookup"><span data-stu-id="d8aed-133">Select **Get Started**.</span></span> 

1. <span data-ttu-id="d8aed-134">Въведете име за връзката в полето **Показвано име**.</span><span class="sxs-lookup"><span data-stu-id="d8aed-134">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="d8aed-135">Въведете валиден маркер за Leadspace.</span><span class="sxs-lookup"><span data-stu-id="d8aed-135">Provide a valid Leadspace token.</span></span>

1. <span data-ttu-id="d8aed-136">Прегледайте и дайте съгласието си за **Поверителност и съответствие на данните** като изберете **съгласен съм**.</span><span class="sxs-lookup"><span data-stu-id="d8aed-136">Review and provide your consent for **Data privacy and compliance** by selecting **I agree**.</span></span>

1. <span data-ttu-id="d8aed-137">Изберете **Проверка**, за да проверите конфигурацията.</span><span class="sxs-lookup"><span data-stu-id="d8aed-137">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="d8aed-138">След като завършите проверката, изберете **Записване**.</span><span class="sxs-lookup"><span data-stu-id="d8aed-138">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Страница за конфигуриране на връзка на Leadspace.":::

## <a name="enrichment-results"></a><span data-ttu-id="d8aed-140">Резултати от допълването</span><span class="sxs-lookup"><span data-stu-id="d8aed-140">Enrichment results</span></span>

<span data-ttu-id="d8aed-141">След като опресните обогатяването, можете да прегледате ново обогатените данни на компанията под [Моите обогатявания](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="d8aed-141">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="d8aed-142">Можете да намерите времето на последната актуализация и броя на допълнените профили.</span><span class="sxs-lookup"><span data-stu-id="d8aed-142">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="d8aed-143">Можете да получите достъп до подробен изглед на всеки допълнен профил, като изберете **Преглед на допълнените данни**.</span><span class="sxs-lookup"><span data-stu-id="d8aed-143">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="d8aed-144">За повече информация вижте [API на Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span><span class="sxs-lookup"><span data-stu-id="d8aed-144">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="d8aed-145">Следващи стъпки</span><span class="sxs-lookup"><span data-stu-id="d8aed-145">Next steps</span></span>

<span data-ttu-id="d8aed-146">Надградете допълнените клиентски данни.</span><span class="sxs-lookup"><span data-stu-id="d8aed-146">Build on top of your enriched customer data.</span></span> <span data-ttu-id="d8aed-147">Създайте [сегменти](segments.md) и [мерки](measures.md) и дори [експортирайте данните](export-destinations.md) за да доставите персонализирано изживяване на клиентите си.</span><span class="sxs-lookup"><span data-stu-id="d8aed-147">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="d8aed-148">Поверителност и съответствие на данните</span><span class="sxs-lookup"><span data-stu-id="d8aed-148">Data privacy and compliance</span></span>

<span data-ttu-id="d8aed-149">Когато активирате Dynamics 365 Customer Insights, за да предавате данни на Leadspace, разрешавате прехвърляне на данни извън границата за съответствие за Dynamics 365 Customer Insights, включително потенциално чувствителни данни като Лични данни.</span><span class="sxs-lookup"><span data-stu-id="d8aed-149">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="d8aed-150">Microsoft ще прехвърли такива данни по ваше указание, но вие носите отговорност да гарантирате, че Leadspace отговаря на всички задължения за поверителност или сигурност, които може да имате.</span><span class="sxs-lookup"><span data-stu-id="d8aed-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="d8aed-151">За информация посетете [Декларация за поверителност Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="d8aed-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="d8aed-152">Вашият администратор на Dynamics 365 Customer Insights да премахнете това обогатяване по всяко време, за да прекратите използването на тази функционалност.</span><span class="sxs-lookup"><span data-stu-id="d8aed-152">Your Dynamics 365 Customer Insights administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
