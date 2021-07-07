---
title: Обогатяване с Experian на обогатяване от трета страна
description: Обща информация за Experian обогатяване от трета страна.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 7c82fe92b3351a782a4fa6510300d870b742d042
ms.sourcegitcommit: 42b3bce1e20e7cc707d232844dacfeed3d6fc096
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 06/28/2021
ms.locfileid: "6309807"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="2e559-103">Обогатете потребителските профили с демографски данни от Experian (преглед)</span><span class="sxs-lookup"><span data-stu-id="2e559-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="2e559-104">Experian е световен лидер в отчитането на потребителски и бизнес кредити и маркетингови услуги.</span><span class="sxs-lookup"><span data-stu-id="2e559-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="2e559-105">С Experian услугите за обогатяване на данни, можете да изградите по-задълбочено разбиране на вашите клиенти, като обогатите своите клиентски профили с демографски данни като размер на домакинството, доходи и др.</span><span class="sxs-lookup"><span data-stu-id="2e559-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2e559-106">Предварителни изисквания</span><span class="sxs-lookup"><span data-stu-id="2e559-106">Prerequisites</span></span>

<span data-ttu-id="2e559-107">За конфигуриране ма Experian трябва да бъдат изпълнени следните предпоставки:</span><span class="sxs-lookup"><span data-stu-id="2e559-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="2e559-108">Трябва да имате активен абонамент за Experian.</span><span class="sxs-lookup"><span data-stu-id="2e559-108">You have an active Experian subscription.</span></span> <span data-ttu-id="2e559-109">За да получите абонамент, [свържете се с Experian](https://www.experian.com/marketing-services/contact) директно.</span><span class="sxs-lookup"><span data-stu-id="2e559-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="2e559-110">[Научете повече за допълване на данни на Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="2e559-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>

- <span data-ttu-id="2e559-111">Experian връзката вече е конфигурирана от администратор *или* вие имате разрешения на [администратор](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="2e559-111">An Experian connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="2e559-112">Също така се нуждаете от User ID, Party ID и Номер на модела за вашия акаунт за защитен транспорт (ST) с активиран SSH Experian създаден за вас.</span><span class="sxs-lookup"><span data-stu-id="2e559-112">You also need the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="2e559-113">Поддържани държави / региони</span><span class="sxs-lookup"><span data-stu-id="2e559-113">Supported countries/regions</span></span>

<span data-ttu-id="2e559-114">Понастоящем поддържаме обогатяване на потребителски профили само в САЩ.</span><span class="sxs-lookup"><span data-stu-id="2e559-114">We currently support enriching customer profiles in the United States only.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="2e559-115">Конфигуриране на допълването</span><span class="sxs-lookup"><span data-stu-id="2e559-115">Configure the enrichment</span></span>

1. <span data-ttu-id="2e559-116">Отидете в раздела **Данни** > **Допълване** и изберете раздела **Откриване**.</span><span class="sxs-lookup"><span data-stu-id="2e559-116">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="2e559-117">Изберете **Обогатете данните ми** на плочката Experian.</span><span class="sxs-lookup"><span data-stu-id="2e559-117">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="2e559-118">![Experian плочк](media/experian-tile.png "Experian tile")</span><span class="sxs-lookup"><span data-stu-id="2e559-118">![Experian tile](media/experian-tile.png "Experian tile")</span></span>
   > 

1. <span data-ttu-id="2e559-119">Изберете [връзка](connections.md) от падащия списък.</span><span class="sxs-lookup"><span data-stu-id="2e559-119">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="2e559-120">Свържете се с администратор, ако няма налична връзка.</span><span class="sxs-lookup"><span data-stu-id="2e559-120">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="2e559-121">Ако сте администратор, можете да създадете връзка, като изберете **Добавете връзка** и изберете Experian от падащия списък.</span><span class="sxs-lookup"><span data-stu-id="2e559-121">If you are an administrator, you can create a connection by selecting **Add connection** and choosing Experian from the dropdown list.</span></span> 

1. <span data-ttu-id="2e559-122">Изберете **Свържете се с Experian** за да потвърдите избора на връзка.</span><span class="sxs-lookup"><span data-stu-id="2e559-122">Select **Connect to Experian** to confirm the connection selection.</span></span>

1.  <span data-ttu-id="2e559-123">Изберете **Напред** и изберете **Набор от данни на клиента** искате да обогатите с демографски данни от Experian.</span><span class="sxs-lookup"><span data-stu-id="2e559-123">Select **Next** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="2e559-124">Можете да изберете **Клиент** обект, за да обогатите всичките си клиентски профили или да изберете сегментен обект, за да обогатите само клиентски профили, съдържащи се в този сегмент.</span><span class="sxs-lookup"><span data-stu-id="2e559-124">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Снимка на екрана при избора на набор от данни за клиенти.":::

1. <span data-ttu-id="2e559-126">Изберете **Напред** и дефинирайте кой тип полета от обединените ви профили трябва да се използват за търсене на съвпадащи демографски данни от Experian.</span><span class="sxs-lookup"><span data-stu-id="2e559-126">Select **Next** and define which type of fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="2e559-127">Изисква се поне едно от полетата **Име и адрес**, **Телефон** или **Имейл**.</span><span class="sxs-lookup"><span data-stu-id="2e559-127">At least one of the fields **Name and address**, **Phone**, or **Email** is required.</span></span> <span data-ttu-id="2e559-128">За по-висока точност на съвпадението могат да се добавят до две други полета.</span><span class="sxs-lookup"><span data-stu-id="2e559-128">For a higher match accuracy, up to two other fields can be added.</span></span> <span data-ttu-id="2e559-129">Този избор ще повлияе на полетата за съпоставяне, до които имате достъп в следващата стъпка.</span><span class="sxs-lookup"><span data-stu-id="2e559-129">This selection will affect the mapping fields you have access to in the next step.</span></span>

    > [!TIP]
    > <span data-ttu-id="2e559-130">Повече атрибути на идентификатора на ключ, изпратени на Experian, вероятно ще доведат до по-висок процент на съвпадение.</span><span class="sxs-lookup"><span data-stu-id="2e559-130">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="2e559-131">Изберете **Напред**, за да започнете съпоставянето на полета.</span><span class="sxs-lookup"><span data-stu-id="2e559-131">Select **Next** to start the field mapping.</span></span>

1. <span data-ttu-id="2e559-132">Дефинирайте кой тип полета от обединените ви профили трябва да се използват за търсене на съвпадащи демографски данни от Experian.</span><span class="sxs-lookup"><span data-stu-id="2e559-132">Define which fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="2e559-133">Задължителните полета са маркирани.</span><span class="sxs-lookup"><span data-stu-id="2e559-133">Required fields are marked.</span></span>

1. <span data-ttu-id="2e559-134">Въведете име за допълването и име за изходния обект.</span><span class="sxs-lookup"><span data-stu-id="2e559-134">Provide a name for the enrichment and a name for the output entity.</span></span>

1. <span data-ttu-id="2e559-135">Изберете **Записване на допълването**, след като прегледате избора си.</span><span class="sxs-lookup"><span data-stu-id="2e559-135">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-experian"></a><span data-ttu-id="2e559-136">Конфигуриране на роли на връзка за Experian</span><span class="sxs-lookup"><span data-stu-id="2e559-136">Configure the connection for Experian</span></span> 

<span data-ttu-id="2e559-137">Трябва да сте администратор, за да конфигурирате връзки.</span><span class="sxs-lookup"><span data-stu-id="2e559-137">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="2e559-138">Изберете **Добавете връзка** при конфигуриране на обогатяване *или* отидете на **Администратор** > **Връзки** и изберете **Настройка** на плочка Experian.</span><span class="sxs-lookup"><span data-stu-id="2e559-138">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Experian tile.</span></span>

1. <span data-ttu-id="2e559-139">Изберете **Първи стъпки**.</span><span class="sxs-lookup"><span data-stu-id="2e559-139">Select **Get Started**.</span></span>

1. <span data-ttu-id="2e559-140">Въведете име за връзката в полето **Показвано име**.</span><span class="sxs-lookup"><span data-stu-id="2e559-140">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="2e559-141">Въведете валиден User ID, Party ID и номер на модел за вашата Защитена транспортна сметка на Experian.</span><span class="sxs-lookup"><span data-stu-id="2e559-141">Enter valid User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span>

1. <span data-ttu-id="2e559-142">Прегледайте и дайте съгласието си за **Поверителност и съответствие на данните** като изберете **съгласен съм**.</span><span class="sxs-lookup"><span data-stu-id="2e559-142">Review and provide your consent for **Data privacy and compliance** by selecting **I agree**.</span></span>

1. <span data-ttu-id="2e559-143">Изберете **Проверка**, за да проверите конфигурацията.</span><span class="sxs-lookup"><span data-stu-id="2e559-143">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="2e559-144">След като завършите проверката, изберете **Записване**.</span><span class="sxs-lookup"><span data-stu-id="2e559-144">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Екран за конфигурация на връзка на Experian":::

## <a name="enrichment-results"></a><span data-ttu-id="2e559-146">Резултати от допълването</span><span class="sxs-lookup"><span data-stu-id="2e559-146">Enrichment results</span></span>

<span data-ttu-id="2e559-147">За да започнете процеса на допълване, изберете **Стартиране** от командната лента.</span><span class="sxs-lookup"><span data-stu-id="2e559-147">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="2e559-148">Можете също така да оставите системата да стартира допълването автоматично като част от [планирано обновяване](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="2e559-148">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="2e559-149">Времето за обработка ще зависи от размера на вашите клиентски данни и процесите на обогатяване, настроени за вашия акаунт от Experian.</span><span class="sxs-lookup"><span data-stu-id="2e559-149">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="2e559-150">След като процесът на допълване завърши, можете да прегледате току-що допълнените данни за потребителски профили в **Моите допълвания**.</span><span class="sxs-lookup"><span data-stu-id="2e559-150">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="2e559-151">Освен това ще намерите часа на последната актуализация и броя на допълнените профили.</span><span class="sxs-lookup"><span data-stu-id="2e559-151">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="2e559-152">Можете да получите достъп до подробен изглед на всеки допълнен профил, като изберете **Преглед на допълнените данни**.</span><span class="sxs-lookup"><span data-stu-id="2e559-152">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="2e559-153">Следващи стъпки</span><span class="sxs-lookup"><span data-stu-id="2e559-153">Next steps</span></span>

<span data-ttu-id="2e559-154">Надградете допълнените клиентски данни.</span><span class="sxs-lookup"><span data-stu-id="2e559-154">Build on top of your enriched customer data.</span></span> <span data-ttu-id="2e559-155">Създайте [сегменти](segments.md) и [мерки](measures.md) и дори [експортирайте данните](export-destinations.md) за да доставите персонализирано изживяване на клиентите си.</span><span class="sxs-lookup"><span data-stu-id="2e559-155">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="2e559-156">Поверителност и съответствие на данните</span><span class="sxs-lookup"><span data-stu-id="2e559-156">Data privacy and compliance</span></span>

<span data-ttu-id="2e559-157">Когато активирате Dynamics 365 Customer Insights за предаване на данни на Experian, разрешавате прехвърляне на данни извън границата за съответствие за Dynamics 365 Customer Insights, включително потенциално чувствителни данни като Лични данни.</span><span class="sxs-lookup"><span data-stu-id="2e559-157">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="2e559-158">Microsoft ще прехвърли такива данни по ваше указание, но вие сте отговорни за това Experian отговаря на всички задължения за поверителност или сигурност, които може да имате.</span><span class="sxs-lookup"><span data-stu-id="2e559-158">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="2e559-159">За информация посетете [Декларация за поверителност Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="2e559-159">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="2e559-160">Вашият администратор на Dynamics 365 Customer Insights да премахнете това обогатяване по всяко време, за да прекратите използването на тази функционалност.</span><span class="sxs-lookup"><span data-stu-id="2e559-160">Your Dynamics 365 Customer Insights administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
