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
ms.openlocfilehash: 10c338b89a6f9971912d05986c105cba1221b01b
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 04/14/2021
ms.locfileid: "5895992"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="01f74-103">Допълване за потребителски профили (преглед)</span><span class="sxs-lookup"><span data-stu-id="01f74-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="01f74-104">Използвайте данни от източници, като Microsoft и други партньори, за да допълните вашите клиентски данни.</span><span class="sxs-lookup"><span data-stu-id="01f74-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Страница на центъра за обогатяване":::

<span data-ttu-id="01f74-106">В статията за аудиторията отидете на **Данни** > **Обогатяване**, за да работите с възможности за обогатяване.</span><span class="sxs-lookup"><span data-stu-id="01f74-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>    
<span data-ttu-id="01f74-107">За да създавате или редактирате допълвания, трябва да имате разрешения за сътрудник или администратор.</span><span class="sxs-lookup"><span data-stu-id="01f74-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="01f74-108">За повече информация вижте [Разрешения](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="01f74-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="01f74-109">В раздела **Откриване** ще намерите следните допълвания:</span><span class="sxs-lookup"><span data-stu-id="01f74-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="01f74-110">[Марки](enrichment-microsoft.md), предоставени от Microsoft</span><span class="sxs-lookup"><span data-stu-id="01f74-110">[Brands](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="01f74-111">[Интереси](enrichment-microsoft.md), предоставени от Microsoft</span><span class="sxs-lookup"><span data-stu-id="01f74-111">[Interests](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="01f74-112">[Фирмени данни](enrichment-leadspace.md), предоставени от Leadspace</span><span class="sxs-lookup"><span data-stu-id="01f74-112">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="01f74-113">[Демографски данни](enrichment-experian.md), предоставени от Experian</span><span class="sxs-lookup"><span data-stu-id="01f74-113">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="01f74-114">[Данни за местоположението](enrichment-here.md), предоставени от HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="01f74-114">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="01f74-115">[Персонализирани данни](enrichment-SFTP-custom-import.md) чрез Защитен протокол за предаване на файлове (SFTP)</span><span class="sxs-lookup"><span data-stu-id="01f74-115">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="01f74-116">В раздела **Моите допълвания** можете да видите конфигурираните от вас допълвания и да редактирате техните свойства.</span><span class="sxs-lookup"><span data-stu-id="01f74-116">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="01f74-117">Управление на съществуващи обогатявания</span><span class="sxs-lookup"><span data-stu-id="01f74-117">Manage existing enrichments</span></span>

<span data-ttu-id="01f74-118">Отидете на **Моите обогатявания**, за да видите всички конфигурирани обогатявания.</span><span class="sxs-lookup"><span data-stu-id="01f74-118">Go to the **My enrichments** to see all configured enrichments.</span></span> <span data-ttu-id="01f74-119">Всяко обогатяване е представено като ред, който включва допълнителна информация за обогатяването.</span><span class="sxs-lookup"><span data-stu-id="01f74-119">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="01f74-120">Изберете обогатяване, за да видите наличните опции.</span><span class="sxs-lookup"><span data-stu-id="01f74-120">Select an enrichment to see the available options.</span></span> <span data-ttu-id="01f74-121">Можете също да изберете многоточието (...) в елемент от списъка, за да видите опциите.</span><span class="sxs-lookup"><span data-stu-id="01f74-121">You can also select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Опции за управление на обогатяването в списъка на обогатяването":::

- <span data-ttu-id="01f74-123">**Прегледайте** подробности за обогатяване с броя на обогатените потребителски профили.</span><span class="sxs-lookup"><span data-stu-id="01f74-123">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="01f74-124">**Редактирайте** конфигурацията за обогатяване.</span><span class="sxs-lookup"><span data-stu-id="01f74-124">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="01f74-125">**Стартирайте** допълването за актуализиране на клиентски профили с най-новите данни.</span><span class="sxs-lookup"><span data-stu-id="01f74-125">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="01f74-126">**Дезактивирайте** съществуващо обогатяване, за да спре автоматично да се опреснява при всяко планирано опресняване.</span><span class="sxs-lookup"><span data-stu-id="01f74-126">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="01f74-127">Данните от последното успешно опресняване ще продължат да бъдат налични.</span><span class="sxs-lookup"><span data-stu-id="01f74-127">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="01f74-128">**Активирайте** неактивно обогатяване за рестартиране на автоматично опресняване при всяко планирано опресняване.</span><span class="sxs-lookup"><span data-stu-id="01f74-128">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="01f74-129">**Изтриване** на обогатяването.</span><span class="sxs-lookup"><span data-stu-id="01f74-129">**Delete** an enrichment.</span></span>

<span data-ttu-id="01f74-130">Можете да стартирате или дезактивирате няколко допълвания наведнъж, като ги изберете в списъка.</span><span class="sxs-lookup"><span data-stu-id="01f74-130">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="01f74-131">Опциите за преглед и редактиране не са достъпни като групово действие и работят само за едно обогатяване наведнъж.</span><span class="sxs-lookup"><span data-stu-id="01f74-131">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>

## <a name="enrichments-and-connections"></a><span data-ttu-id="01f74-132">Допълвания и връзки</span><span class="sxs-lookup"><span data-stu-id="01f74-132">Enrichments and connections</span></span>

<span data-ttu-id="01f74-133">Допълванията на трети страни се конфигурират с помощта на [връзки](connections.md), които администраторът задава с идентификационни данни и предоставя съгласие за прехвърляне на данни.</span><span class="sxs-lookup"><span data-stu-id="01f74-133">Third-party enrichments are configured using [connections](connections.md), which an administrator sets up with credentials and provides consent for data transfers.</span></span> <span data-ttu-id="01f74-134">Връзката може да се използва от администратори и сътрудници за конфигуриране на допълвания.</span><span class="sxs-lookup"><span data-stu-id="01f74-134">The connection can be used by administrators and contributors to configure enrichments.</span></span>  

## <a name="multiple-enrichments-of-the-same-type"></a><span data-ttu-id="01f74-135">Няколко допълвания от един и същи тип</span><span class="sxs-lookup"><span data-stu-id="01f74-135">Multiple enrichments of the same type</span></span>

<span data-ttu-id="01f74-136">Обектът, който ще се допълва, се посочва по време на конфигурацията на допълването, което ви позволява да допълните само поднабор от профилите.</span><span class="sxs-lookup"><span data-stu-id="01f74-136">The entity to be enriched is specified during the enrichment configuration, which allows you to enrich only a subset of your profiles.</span></span> <span data-ttu-id="01f74-137">Например допълване на данни само за определен сегмент.</span><span class="sxs-lookup"><span data-stu-id="01f74-137">For exmaple, enrich data only for a specific segment.</span></span> <span data-ttu-id="01f74-138">Може да конфигурирате няколко допълвания от един и същи тип и да използвате повторно една и съща връзка.</span><span class="sxs-lookup"><span data-stu-id="01f74-138">You can configure several enrichments of the same type and reuse the same connection.</span></span> <span data-ttu-id="01f74-139">Някои допълвания ще имат ограничения за броя на допълванията от същия тип, които могат да се създадат.</span><span class="sxs-lookup"><span data-stu-id="01f74-139">Some enrichments will have limits to the number of enrichments of the same type that can be created.</span></span> <span data-ttu-id="01f74-140">Ограниченията и текущата употреба може да се видят на страницата **Допълване**.</span><span class="sxs-lookup"><span data-stu-id="01f74-140">The limits and current use can be seen on the **Enrichment** page.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
