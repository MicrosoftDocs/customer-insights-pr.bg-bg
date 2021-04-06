---
title: Обогатяване на унифицирани клиентски профили
description: Използвайте възможности за обогатяване на вашите клиентски данни.
ms.date: 11/02/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 36e6f7f8fcd64fc2591e913910918b83bf27567b
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597682"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="f8432-103">Допълване за потребителски профили (преглед)</span><span class="sxs-lookup"><span data-stu-id="f8432-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="f8432-104">Използвайте данни от източници, като Microsoft и други партньори, за да допълните вашите клиентски данни.</span><span class="sxs-lookup"><span data-stu-id="f8432-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Страница на центъра за обогатяване":::

<span data-ttu-id="f8432-106">В статията за аудиторията отидете на **Данни** > **Обогатяване**, за да работите с възможности за обогатяване.</span><span class="sxs-lookup"><span data-stu-id="f8432-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>    
<span data-ttu-id="f8432-107">За да създавате или редактирате допълвания, трябва да имате разрешения за сътрудник или администратор.</span><span class="sxs-lookup"><span data-stu-id="f8432-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="f8432-108">За повече информация вижте [Разрешения](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="f8432-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="f8432-109">В раздела **Откриване** ще намерите следните допълвания:</span><span class="sxs-lookup"><span data-stu-id="f8432-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="f8432-110">[Марки](enrichment-microsoft-graph.md), предоставени от Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="f8432-110">[Brands](enrichment-microsoft-graph.md) provided by Microsoft Graph</span></span>
- <span data-ttu-id="f8432-111">[Интереси](enrichment-microsoft-graph.md), предоставени от Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="f8432-111">[Interests](enrichment-microsoft-graph.md) provided by Microsoft Graph</span></span>
- <span data-ttu-id="f8432-112">[Фирмени данни](enrichment-leadspace.md), предоставени от Leadspace</span><span class="sxs-lookup"><span data-stu-id="f8432-112">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="f8432-113">[Демографски данни](enrichment-experian.md), предоставени от Experian</span><span class="sxs-lookup"><span data-stu-id="f8432-113">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="f8432-114">[Данни за местоположението](enrichment-here.md), предоставени от HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="f8432-114">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="f8432-115">[Персонализирани данни](enrichment-SFTP-custom-import.md) чрез Защитен протокол за предаване на файлове (SFTP)</span><span class="sxs-lookup"><span data-stu-id="f8432-115">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="f8432-116">В раздела **Моите допълвания** можете да видите конфигурираните от вас допълвания и да редактирате техните свойства.</span><span class="sxs-lookup"><span data-stu-id="f8432-116">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="f8432-117">Управление на съществуващи обогатявания</span><span class="sxs-lookup"><span data-stu-id="f8432-117">Manage existing enrichments</span></span>

<span data-ttu-id="f8432-118">Отидете на **Моите обогатявания**, за да видите всички конфигурирани обогатявания.</span><span class="sxs-lookup"><span data-stu-id="f8432-118">Go to the **My enrichments** to see all configured enrichments.</span></span> <span data-ttu-id="f8432-119">Всяко обогатяване е представено като ред, който включва допълнителна информация за обогатяването.</span><span class="sxs-lookup"><span data-stu-id="f8432-119">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="f8432-120">Изберете обогатяване, за да видите наличните опции.</span><span class="sxs-lookup"><span data-stu-id="f8432-120">Select an enrichment to see the available options.</span></span> <span data-ttu-id="f8432-121">Като алтернатива можете да изберете многоточието (...) на елемент от списъка, за да видите опциите.</span><span class="sxs-lookup"><span data-stu-id="f8432-121">Alternatively, you can select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Опции за управление на обогатяването в списъка на обогатяването":::

- <span data-ttu-id="f8432-123">**Прегледайте** подробности за обогатяване с броя на обогатените потребителски профили.</span><span class="sxs-lookup"><span data-stu-id="f8432-123">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="f8432-124">**Редактирайте** конфигурацията за обогатяване.</span><span class="sxs-lookup"><span data-stu-id="f8432-124">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="f8432-125">**Стартирайте** допълването за актуализиране на клиентски профили с най-новите данни.</span><span class="sxs-lookup"><span data-stu-id="f8432-125">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="f8432-126">**Дезактивирайте** съществуващо обогатяване, за да спре автоматично да се опреснява при всяко планирано опресняване.</span><span class="sxs-lookup"><span data-stu-id="f8432-126">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="f8432-127">Данните от последното успешно опресняване ще продължат да бъдат налични.</span><span class="sxs-lookup"><span data-stu-id="f8432-127">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="f8432-128">**Активирайте** неактивно обогатяване за рестартиране на автоматично опресняване при всяко планирано опресняване.</span><span class="sxs-lookup"><span data-stu-id="f8432-128">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="f8432-129">**Изтриване** на обогатяването.</span><span class="sxs-lookup"><span data-stu-id="f8432-129">**Delete** an enrichment.</span></span>

<span data-ttu-id="f8432-130">Можете да стартирате или дезактивирате няколко допълвания наведнъж, като ги изберете в списъка.</span><span class="sxs-lookup"><span data-stu-id="f8432-130">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="f8432-131">Опциите за преглед и редактиране не са достъпни като групово действие и работят само за едно обогатяване наведнъж.</span><span class="sxs-lookup"><span data-stu-id="f8432-131">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]