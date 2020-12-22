---
title: Обогатяване с помощта на Experian за обогатяване от трети страни
description: Обща информация за обогатяването чрез Experian на трети страни.
ms.date: 09/17/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 60fc49734e54740e83b47a7028be216a0eb81e49
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668788"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="0a32e-103">Допълване на потребителските профили с демографски данни от Experian (предварителен преглед)</span><span class="sxs-lookup"><span data-stu-id="0a32e-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="0a32e-104">Experian е световен лидер в отчитането на потребителски и бизнес кредитен рейтинг и маркетингови услуги.</span><span class="sxs-lookup"><span data-stu-id="0a32e-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="0a32e-105">С услугите за допълване на данни на Experian можете да изградите по-задълбочено разбиране на клиентите си, като допълните потребителските си профили с демографски данни, като например размер на домакинството, доходи и други.</span><span class="sxs-lookup"><span data-stu-id="0a32e-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0a32e-106">Предварителни изисквания</span><span class="sxs-lookup"><span data-stu-id="0a32e-106">Prerequisites</span></span>

<span data-ttu-id="0a32e-107">За да конфигурирате Experian, трябва да са изпълнени следните изисквания:</span><span class="sxs-lookup"><span data-stu-id="0a32e-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="0a32e-108">Да имате активен абонамент за Experian.</span><span class="sxs-lookup"><span data-stu-id="0a32e-108">You have an active Experian subscription.</span></span> <span data-ttu-id="0a32e-109">За да получите абонамент, [се свържете с Experian](https://www.experian.com/marketing-services/contact) директно.</span><span class="sxs-lookup"><span data-stu-id="0a32e-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="0a32e-110">[Научете повече за допълването на данни на Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="0a32e-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>
- <span data-ttu-id="0a32e-111">Да имате потребителски идентификатор, идентификатор на страна и номер на модела за вашия акаунт за защитен транспорт (ST), който поддържа SSH, създаден от Experian за вас.</span><span class="sxs-lookup"><span data-stu-id="0a32e-111">You have the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>
- <span data-ttu-id="0a32e-112">Имате [администраторски](permissions.md#administrator) разрешения в аналитични данни за аудитория.</span><span class="sxs-lookup"><span data-stu-id="0a32e-112">You have [Administrator](permissions.md#administrator) permissions in audience insights.</span></span>

## <a name="configuration"></a><span data-ttu-id="0a32e-113">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="0a32e-113">Configuration</span></span>

1. <span data-ttu-id="0a32e-114">Отидете в раздела **Данни** > **Допълване** и изберете раздела **Откриване**.</span><span class="sxs-lookup"><span data-stu-id="0a32e-114">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="0a32e-115">Изберете **Допълване на моите данни** в плочката Experian.</span><span class="sxs-lookup"><span data-stu-id="0a32e-115">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0a32e-116">![Плочка Experian](media/experian-tile.png "Плочка Experian")</span><span class="sxs-lookup"><span data-stu-id="0a32e-116">![Experian tile](media/experian-tile.png "Experian tile")</span></span>

1. <span data-ttu-id="0a32e-117">Изберете **Първи стъпки** и въведете потребителския идентификатор, идентификатора на страна и номера на модела за вашия акаунт за защитен транспорт на Experian.</span><span class="sxs-lookup"><span data-stu-id="0a32e-117">Select **Get started** and enter the User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span> <span data-ttu-id="0a32e-118">Прегледайте и дайте своето съгласие за **Поверителност и съответствие на данните**, като изберете отметката **Приемам**.</span><span class="sxs-lookup"><span data-stu-id="0a32e-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="0a32e-119">Потвърдете всички въвеждания, като изберете **Прилагане**.</span><span class="sxs-lookup"><span data-stu-id="0a32e-119">Confirm all inputs by selecting **Apply**.</span></span>

## <a name="map-your-fields"></a><span data-ttu-id="0a32e-120">Нанесете полетата</span><span class="sxs-lookup"><span data-stu-id="0a32e-120">Map your fields</span></span>

1. <span data-ttu-id="0a32e-121">Изберете **Добавяне на данни** и изберете ключовите си идентификатори от **Име и адрес**, **Имейл** или **Телефон**, за да изпратите до Experian за разрешаване на самоличността.</span><span class="sxs-lookup"><span data-stu-id="0a32e-121">Select **Add data** and choose your key identifiers from **Name and Address**, **E-mail**, or **Phone** to send to Experian for identity resolution.</span></span>

   > [!TIP]
   > <span data-ttu-id="0a32e-122">Повече атрибути на ключови идентификатори, изпратени до Experian, вероятно дават по-висока степен на съвпадение.</span><span class="sxs-lookup"><span data-stu-id="0a32e-122">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="0a32e-123">Изберете **Следващ** и съпоставете съответните атрибути от вашия обединен клиентски обект за избраните полета за идентификатор на ключ.</span><span class="sxs-lookup"><span data-stu-id="0a32e-123">Select **Next** and map the corresponding attributes from your unified customer entity for the selected key identifier fields.</span></span>

1. <span data-ttu-id="0a32e-124">Изберете **Добавяне на атрибут** за съпоставяне на всички допълнителни атрибути, които искате да изпратите на Experian.</span><span class="sxs-lookup"><span data-stu-id="0a32e-124">Select **Add attribute** to map any additional attributes you would like to send to Experian.</span></span>

1.  <span data-ttu-id="0a32e-125">Изберете **Записване**, за да завършите съпоставянето на полета.</span><span class="sxs-lookup"><span data-stu-id="0a32e-125">Select **Save** to complete the field mapping.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0a32e-126">![Съпоставяне на полета на Experian](media/experian-field-mapping.png "Съпоставяне на полета на Experian")</span><span class="sxs-lookup"><span data-stu-id="0a32e-126">![Experian field mapping](media/experian-field-mapping.png "Experian field mapping")</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="0a32e-127">Резултати от допълването</span><span class="sxs-lookup"><span data-stu-id="0a32e-127">Enrichment results</span></span>

<span data-ttu-id="0a32e-128">За да започнете процеса на допълване, изберете **Стартиране** от командната лента.</span><span class="sxs-lookup"><span data-stu-id="0a32e-128">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="0a32e-129">Можете също така да оставите системата да стартира допълването автоматично като част от [планирано обновяване](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="0a32e-129">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="0a32e-130">Времето за обработка ще зависи от размера на вашите клиентски данни и процесите на допълване, създадени за вашия акаунт от Experian.</span><span class="sxs-lookup"><span data-stu-id="0a32e-130">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="0a32e-131">След като процесът на допълване завърши, можете да прегледате току-що допълнените данни за потребителски профили в **Моите допълвания**.</span><span class="sxs-lookup"><span data-stu-id="0a32e-131">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="0a32e-132">Освен това ще намерите часа на последната актуализация и броя на допълнените профили.</span><span class="sxs-lookup"><span data-stu-id="0a32e-132">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="0a32e-133">Можете да получите достъп до подробен изглед на всеки допълнен профил, като изберете **Преглед на допълнените данни**.</span><span class="sxs-lookup"><span data-stu-id="0a32e-133">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="0a32e-134">Следващи стъпки</span><span class="sxs-lookup"><span data-stu-id="0a32e-134">Next steps</span></span>

<span data-ttu-id="0a32e-135">Надградете допълнените клиентски данни.</span><span class="sxs-lookup"><span data-stu-id="0a32e-135">Build on top of your enriched customer data.</span></span> <span data-ttu-id="0a32e-136">Създайте [сегменти](segments.md), [мерки](measures.md) и дори [експортирайте данните](export-destinations.md), за да доставите персонализирано изживяване на клиентите си.</span><span class="sxs-lookup"><span data-stu-id="0a32e-136">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="0a32e-137">Поверителност и съответствие на данните</span><span class="sxs-lookup"><span data-stu-id="0a32e-137">Data privacy and compliance</span></span>

<span data-ttu-id="0a32e-138">Когато активирате Dynamics 365 Customer Insights, за да предавате данни на Experian, разрешавате прехвърляне на данни извън границата за съответствие за Dynamics 365 Customer Insights, включително потенциално чувствителни данни като Лични данни.</span><span class="sxs-lookup"><span data-stu-id="0a32e-138">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="0a32e-139">Microsoft ще прехвърли такива данни по ваше указание, но вие носите отговорност да гарантирате, че Experian отговаря на всички задължения за поверителност или сигурност, които може да имате.</span><span class="sxs-lookup"><span data-stu-id="0a32e-139">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="0a32e-140">За информация посетете [Декларация за поверителност Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="0a32e-140">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="0a32e-141">Вашият администратор на Dynamics 365 Customer Insights да премахнете това обогатяване по всяко време, за да прекратите използването на тази функционалност.</span><span class="sxs-lookup"><span data-stu-id="0a32e-141">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>
