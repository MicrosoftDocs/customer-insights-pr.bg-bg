---
title: Обогатяване на унифицирани клиентски профили
description: Използвайте възможности за обогатяване на вашите клиентски данни.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: c35e73b366fcd5db2ba5a757295ddda6db30efa0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305235"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="452d0-103">Допълване за потребителски профили (преглед)</span><span class="sxs-lookup"><span data-stu-id="452d0-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="452d0-104">Използвайте данни от източници, като Microsoft и други партньори, за да допълните вашите клиентски данни.</span><span class="sxs-lookup"><span data-stu-id="452d0-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Страница на центъра за обогатяване":::

<span data-ttu-id="452d0-106">В статията за аудиторията отидете на **Данни** > **Обогатяване**, за да работите с възможности за обогатяване.</span><span class="sxs-lookup"><span data-stu-id="452d0-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>  

<span data-ttu-id="452d0-107">За да създавате или редактирате допълвания, трябва да имате разрешения за сътрудник или администратор.</span><span class="sxs-lookup"><span data-stu-id="452d0-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="452d0-108">За повече информация вижте [Разрешения](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="452d0-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="452d0-109">В раздела **Откриване** ще намерите следните допълвания:</span><span class="sxs-lookup"><span data-stu-id="452d0-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="452d0-110">[Марки](enrichment-microsoft.md), предоставени от Microsoft</span><span class="sxs-lookup"><span data-stu-id="452d0-110">[Brands](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="452d0-111">[Интереси](enrichment-microsoft.md), предоставени от Microsoft</span><span class="sxs-lookup"><span data-stu-id="452d0-111">[Interests](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="452d0-112">[Подобрени адреси](enrichment-enhanced-addresses.md) предоставено от Microsoft</span><span class="sxs-lookup"><span data-stu-id="452d0-112">[Enhanced addresses](enrichment-enhanced-addresses.md) provided by Microsoft</span></span>
- <span data-ttu-id="452d0-113">[Фирмени данни](enrichment-leadspace.md), предоставени от Leadspace</span><span class="sxs-lookup"><span data-stu-id="452d0-113">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="452d0-114">[Демографски данни](enrichment-experian.md), предоставени от Experian</span><span class="sxs-lookup"><span data-stu-id="452d0-114">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="452d0-115">[Данни за местоположението](enrichment-here.md), предоставени от HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="452d0-115">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="452d0-116">[Персонализирани данни](enrichment-SFTP-custom-import.md) чрез Защитен протокол за предаване на файлове (SFTP)</span><span class="sxs-lookup"><span data-stu-id="452d0-116">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="452d0-117">В раздела **Моите допълвания** можете да видите конфигурираните от вас допълвания и да редактирате техните свойства.</span><span class="sxs-lookup"><span data-stu-id="452d0-117">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="452d0-118">Управление на съществуващи обогатявания</span><span class="sxs-lookup"><span data-stu-id="452d0-118">Manage existing enrichments</span></span>

<span data-ttu-id="452d0-119">Отидете на **Моите обогатявания**, за да видите всички конфигурирани обогатявания.</span><span class="sxs-lookup"><span data-stu-id="452d0-119">Go to the **My enrichments** tab to see all configured enrichments.</span></span> <span data-ttu-id="452d0-120">Всяко обогатяване е представено като ред, който включва допълнителна информация за обогатяването.</span><span class="sxs-lookup"><span data-stu-id="452d0-120">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="452d0-121">Изберете обогатяване, за да видите наличните опции.</span><span class="sxs-lookup"><span data-stu-id="452d0-121">Select an enrichment to see the available options.</span></span> <span data-ttu-id="452d0-122">Можете също да изберете многоточието (...) в елемент от списъка, за да видите опциите.</span><span class="sxs-lookup"><span data-stu-id="452d0-122">You can also select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Опции за управление на обогатяването в списъка на обогатяването":::

- <span data-ttu-id="452d0-124">**Прегледайте** подробности за обогатяване с броя на обогатените потребителски профили.</span><span class="sxs-lookup"><span data-stu-id="452d0-124">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="452d0-125">**Редактирайте** конфигурацията за обогатяване.</span><span class="sxs-lookup"><span data-stu-id="452d0-125">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="452d0-126">**Стартирайте** допълването за актуализиране на клиентски профили с най-новите данни.</span><span class="sxs-lookup"><span data-stu-id="452d0-126">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="452d0-127">**Дезактивирайте** съществуващо обогатяване, за да спре автоматично да се опреснява при всяко планирано опресняване.</span><span class="sxs-lookup"><span data-stu-id="452d0-127">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="452d0-128">Данните от последното успешно опресняване ще продължат да бъдат налични.</span><span class="sxs-lookup"><span data-stu-id="452d0-128">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="452d0-129">**Активирайте** неактивно обогатяване за рестартиране на автоматично опресняване при всяко планирано опресняване.</span><span class="sxs-lookup"><span data-stu-id="452d0-129">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="452d0-130">**Изтриване** на обогатяването.</span><span class="sxs-lookup"><span data-stu-id="452d0-130">**Delete** an enrichment.</span></span>

<span data-ttu-id="452d0-131">Можете да стартирате или дезактивирате няколко допълвания наведнъж, като ги изберете в списъка.</span><span class="sxs-lookup"><span data-stu-id="452d0-131">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="452d0-132">Опциите за преглед и редактиране не са достъпни като групово действие и работят само за едно обогатяване наведнъж.</span><span class="sxs-lookup"><span data-stu-id="452d0-132">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>

## <a name="enrichments-and-connections"></a><span data-ttu-id="452d0-133">Допълвания и връзки</span><span class="sxs-lookup"><span data-stu-id="452d0-133">Enrichments and connections</span></span>

<span data-ttu-id="452d0-134">Допълванията на трети страни се конфигурират с помощта на [връзки](connections.md), които администраторът задава с идентификационни данни и предоставя съгласие за прехвърляне на данни.</span><span class="sxs-lookup"><span data-stu-id="452d0-134">Third-party enrichments are configured using [connections](connections.md), which an administrator sets up with credentials and provides consent for data transfers.</span></span> <span data-ttu-id="452d0-135">Връзката може да се използва от администратори и сътрудници за конфигуриране на допълвания.</span><span class="sxs-lookup"><span data-stu-id="452d0-135">The connection can be used by administrators and contributors to configure enrichments.</span></span>  

## <a name="multiple-enrichments-of-the-same-type"></a><span data-ttu-id="452d0-136">Няколко допълвания от един и същи тип</span><span class="sxs-lookup"><span data-stu-id="452d0-136">Multiple enrichments of the same type</span></span>

<span data-ttu-id="452d0-137">Обектът, който ще се допълва, се посочва по време на конфигурацията на допълването, което ви позволява да допълните само поднабор от профилите.</span><span class="sxs-lookup"><span data-stu-id="452d0-137">The entity to be enriched is specified during the enrichment configuration, which allows you to enrich only a subset of your profiles.</span></span> <span data-ttu-id="452d0-138">Например обогатете данни само за определен сегмент.</span><span class="sxs-lookup"><span data-stu-id="452d0-138">For example, enrich data only for a specific segment.</span></span> <span data-ttu-id="452d0-139">Може да конфигурирате няколко допълвания от един и същи тип и да използвате повторно една и съща връзка.</span><span class="sxs-lookup"><span data-stu-id="452d0-139">You can configure several enrichments of the same type and reuse the same connection.</span></span> <span data-ttu-id="452d0-140">Някои допълвания ще имат ограничения за броя на допълванията от същия тип, които могат да се създадат.</span><span class="sxs-lookup"><span data-stu-id="452d0-140">Some enrichments will have limits to the number of enrichments of the same type that can be created.</span></span> <span data-ttu-id="452d0-141">Ограниченията и текущата употреба може да се видят на страницата **Допълване**.</span><span class="sxs-lookup"><span data-stu-id="452d0-141">The limits and current use can be seen on the **Enrichment** page.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
