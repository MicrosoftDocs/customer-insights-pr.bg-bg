---
title: Обогатяване с помощта на Experian за обогатяване от трети страни
description: Обща информация за обогатяването чрез Experian на трети страни.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 9cf2a7fa18ecc022ea67f6829f52381ad59f3172
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896360"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="98782-103">Допълване на потребителските профили с демографски данни от Experian (предварителен преглед)</span><span class="sxs-lookup"><span data-stu-id="98782-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="98782-104">Experian е световен лидер в отчитането на потребителски и бизнес кредитен рейтинг и маркетингови услуги.</span><span class="sxs-lookup"><span data-stu-id="98782-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="98782-105">С услугите за допълване на данни на Experian можете да изградите по-задълбочено разбиране на клиентите си, като допълните потребителските си профили с демографски данни, като например размер на домакинството, доходи и други.</span><span class="sxs-lookup"><span data-stu-id="98782-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="98782-106">Предварителни изисквания</span><span class="sxs-lookup"><span data-stu-id="98782-106">Prerequisites</span></span>

<span data-ttu-id="98782-107">За да конфигурирате Experian, трябва да са изпълнени следните изисквания:</span><span class="sxs-lookup"><span data-stu-id="98782-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="98782-108">Да имате активен абонамент за Experian.</span><span class="sxs-lookup"><span data-stu-id="98782-108">You have an active Experian subscription.</span></span> <span data-ttu-id="98782-109">За да получите абонамент, [се свържете с Experian](https://www.experian.com/marketing-services/contact) директно.</span><span class="sxs-lookup"><span data-stu-id="98782-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="98782-110">[Научете повече за допълването на данни на Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="98782-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>

- <span data-ttu-id="98782-111">Връзката на Experian вече е конфигурирана от администратор *или* вие имате разрешения на [администратор](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="98782-111">An Experian connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="98782-112">Необходими са ви също ИД на потребител, ИД на страна и номер на модел за акаунта ви в Secure Transport (ST) с разрешен SSH, който е създаден за вас от Experian.</span><span class="sxs-lookup"><span data-stu-id="98782-112">You also need the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="98782-113">Конфигуриране на допълването</span><span class="sxs-lookup"><span data-stu-id="98782-113">Configure the enrichment</span></span>

1. <span data-ttu-id="98782-114">Отидете в раздела **Данни** > **Допълване** и изберете раздела **Откриване**.</span><span class="sxs-lookup"><span data-stu-id="98782-114">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="98782-115">Изберете **Допълване на моите данни** в плочката Experian.</span><span class="sxs-lookup"><span data-stu-id="98782-115">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="98782-116">![Плочка Experian](media/experian-tile.png "Плочка Experian")</span><span class="sxs-lookup"><span data-stu-id="98782-116">![Experian tile](media/experian-tile.png "Experian tile")</span></span>
   > 

1. <span data-ttu-id="98782-117">Изберете [връзка](connections.md) от падащия списък.</span><span class="sxs-lookup"><span data-stu-id="98782-117">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="98782-118">Свържете се с администратор, ако няма налична връзка.</span><span class="sxs-lookup"><span data-stu-id="98782-118">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="98782-119">Ако сте администратор, може да създадете връзка, като изберете **Добавяне на връзка** и изберете Experian от падащото меню.</span><span class="sxs-lookup"><span data-stu-id="98782-119">If you are an administrator, you can create a connection by selecting **Add connection** and choosing Experian from the drop-down.</span></span> 

1. <span data-ttu-id="98782-120">Изберете **Свързване с Experian**, за да потвърдите избора на връзката.</span><span class="sxs-lookup"><span data-stu-id="98782-120">Select **Connect to Experian** to confirm the connection selection.</span></span>

1.  <span data-ttu-id="98782-121">Изберете **Напред** и изберете **набора от данни на клиента**, който искате да допълните с демографски данни от Experian.</span><span class="sxs-lookup"><span data-stu-id="98782-121">Select **Next** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="98782-122">Можете да изберете **Клиент** обект, за да обогатите всичките си клиентски профили или да изберете сегментен обект, за да обогатите само клиентски профили, съдържащи се в този сегмент.</span><span class="sxs-lookup"><span data-stu-id="98782-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Снимка на екрана при избора на набор от данни за клиенти.":::

1. <span data-ttu-id="98782-124">Изберете **Напред** и дефинирайте кой тип полета от унифицираните профили трябва да се използват за търсене на съответстващи демографски данни от Experian.</span><span class="sxs-lookup"><span data-stu-id="98782-124">Select **Next** and define which type of fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="98782-125">Изисква се поне едно от полетата **Име и адрес**, **Телефон** или **Имейл**.</span><span class="sxs-lookup"><span data-stu-id="98782-125">At least one of the fields **Name and address**, **Phone**, or **Email** is required.</span></span> <span data-ttu-id="98782-126">За по-висока точност на съвпадението могат да се добавят до две други полета.</span><span class="sxs-lookup"><span data-stu-id="98782-126">For a higher match accuracy, up to two other fields can be added.</span></span> <span data-ttu-id="98782-127">Този избор ще повлияе на полетата за съпоставяне, до които имате достъп в следващата стъпка.</span><span class="sxs-lookup"><span data-stu-id="98782-127">This selection will affect the mapping fields you have access to in the next step.</span></span>

    > [!TIP]
    > <span data-ttu-id="98782-128">Повече атрибути на ключови идентификатори, изпратени до Experian, вероятно дават по-висока степен на съвпадение.</span><span class="sxs-lookup"><span data-stu-id="98782-128">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="98782-129">Изберете **Напред**, за да започнете съпоставянето на полета.</span><span class="sxs-lookup"><span data-stu-id="98782-129">Select **Next** to start the field mapping.</span></span>

1. <span data-ttu-id="98782-130">Дефинирайте кои полета от унифицираните профили трябва да се използват за търсене на съответстващи демографски данни от Experian.</span><span class="sxs-lookup"><span data-stu-id="98782-130">Define which fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="98782-131">Задължителните полета са маркирани.</span><span class="sxs-lookup"><span data-stu-id="98782-131">Required fields are marked.</span></span>

1. <span data-ttu-id="98782-132">Въведете име за допълването и име за изходния обект.</span><span class="sxs-lookup"><span data-stu-id="98782-132">Provide a name for the enrichment and a name for the output entity.</span></span>

1. <span data-ttu-id="98782-133">Изберете **Записване на допълването**, след като прегледате избора си.</span><span class="sxs-lookup"><span data-stu-id="98782-133">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-experian"></a><span data-ttu-id="98782-134">Конфигуриране на връзката за Experian</span><span class="sxs-lookup"><span data-stu-id="98782-134">Configure the connection for Experian</span></span> 

<span data-ttu-id="98782-135">Трябва да сте администратор, за да конфигурирате връзки.</span><span class="sxs-lookup"><span data-stu-id="98782-135">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="98782-136">Изберете **Добавяне на връзка**, когато конфигурирате допълването, *или* отидете на **Администратор** > **Връзки** и изберете **Настройка** в плочката на Experian.</span><span class="sxs-lookup"><span data-stu-id="98782-136">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Experian tile.</span></span>

1. <span data-ttu-id="98782-137">Изберете **Първи стъпки**.</span><span class="sxs-lookup"><span data-stu-id="98782-137">Select **Get Started**.</span></span>

1. <span data-ttu-id="98782-138">Въведете име за връзката в полето **Показвано име**.</span><span class="sxs-lookup"><span data-stu-id="98782-138">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="98782-139">Въведете валиден ИД на потребител, ИД на страна и номер на модел за акаунта ви в Experian Secure Transport.</span><span class="sxs-lookup"><span data-stu-id="98782-139">Enter valid User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span>

1. <span data-ttu-id="98782-140">Прегледайте и дайте своето съгласие за **Поверителност и съответствие на данните**, като изберете отметката **Приемам**</span><span class="sxs-lookup"><span data-stu-id="98782-140">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox</span></span>

1. <span data-ttu-id="98782-141">Изберете **Проверка**, за да проверите конфигурацията.</span><span class="sxs-lookup"><span data-stu-id="98782-141">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="98782-142">След като завършите проверката, изберете **Записване**.</span><span class="sxs-lookup"><span data-stu-id="98782-142">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Прозорец за конфигуриране на връзка на Experian.":::

## <a name="enrichment-results"></a><span data-ttu-id="98782-144">Резултати от допълването</span><span class="sxs-lookup"><span data-stu-id="98782-144">Enrichment results</span></span>

<span data-ttu-id="98782-145">За да започнете процеса на допълване, изберете **Стартиране** от командната лента.</span><span class="sxs-lookup"><span data-stu-id="98782-145">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="98782-146">Можете също така да оставите системата да стартира допълването автоматично като част от [планирано обновяване](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="98782-146">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="98782-147">Времето за обработка ще зависи от размера на вашите клиентски данни и процесите на допълване, създадени за вашия акаунт от Experian.</span><span class="sxs-lookup"><span data-stu-id="98782-147">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="98782-148">След като процесът на допълване завърши, можете да прегледате току-що допълнените данни за потребителски профили в **Моите допълвания**.</span><span class="sxs-lookup"><span data-stu-id="98782-148">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="98782-149">Освен това ще намерите часа на последната актуализация и броя на допълнените профили.</span><span class="sxs-lookup"><span data-stu-id="98782-149">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="98782-150">Можете да получите достъп до подробен изглед на всеки допълнен профил, като изберете **Преглед на допълнените данни**.</span><span class="sxs-lookup"><span data-stu-id="98782-150">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="98782-151">Следващи стъпки</span><span class="sxs-lookup"><span data-stu-id="98782-151">Next steps</span></span>

<span data-ttu-id="98782-152">Надградете допълнените клиентски данни.</span><span class="sxs-lookup"><span data-stu-id="98782-152">Build on top of your enriched customer data.</span></span> <span data-ttu-id="98782-153">Създайте [сегменти](segments.md), [мерки](measures.md) и дори [експортирайте данните](export-destinations.md), за да доставите персонализирано изживяване на клиентите си.</span><span class="sxs-lookup"><span data-stu-id="98782-153">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="98782-154">Поверителност и съответствие на данните</span><span class="sxs-lookup"><span data-stu-id="98782-154">Data privacy and compliance</span></span>

<span data-ttu-id="98782-155">Когато активирате Dynamics 365 Customer Insights, за да предавате данни на Experian, разрешавате прехвърляне на данни извън границата за съответствие за Dynamics 365 Customer Insights, включително потенциално чувствителни данни като Лични данни.</span><span class="sxs-lookup"><span data-stu-id="98782-155">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="98782-156">Microsoft ще прехвърли такива данни по ваше указание, но вие носите отговорност да гарантирате, че Experian отговаря на всички задължения за поверителност или сигурност, които може да имате.</span><span class="sxs-lookup"><span data-stu-id="98782-156">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="98782-157">За информация посетете [Декларация за поверителност Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="98782-157">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="98782-158">Вашият администратор на Dynamics 365 Customer Insights да премахнете това обогатяване по всяко време, за да прекратите използването на тази функционалност.</span><span class="sxs-lookup"><span data-stu-id="98782-158">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
