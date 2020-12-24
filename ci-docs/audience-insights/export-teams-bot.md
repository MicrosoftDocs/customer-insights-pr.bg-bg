---
title: Бот за Microsoft Teams
description: Потърсете единни клиентски профили в Microsoft Teams с помощта на бот.
ms.date: 04/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 45ea23fbefe5f1d44c3961183b76d2cc5c45355e
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405099"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a><span data-ttu-id="71796-103">Бот на Teams за Dynamics 365 Customer Insights (преглед)</span><span class="sxs-lookup"><span data-stu-id="71796-103">Teams bot for Dynamics 365 Customer Insights (preview)</span></span>

<span data-ttu-id="71796-104">Свържете се с Microsoft Teams, за да позволите на бот да търси унифицирани клиентски профили в каналите на Teams.</span><span class="sxs-lookup"><span data-stu-id="71796-104">Connect with Microsoft Teams to let a bot look up unified customer profiles in Teams channels.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="71796-105">![Бот на Teams, показващ клиентски запис](media/teams-bot.png "Бот на Teams, показващ клиентски запис")</span><span class="sxs-lookup"><span data-stu-id="71796-105">![Teams bot showing a customer record](media/teams-bot.png "Teams bot showing a customer record")</span></span>

## <a name="prerequisites"></a><span data-ttu-id="71796-106">Предварителни изисквания</span><span class="sxs-lookup"><span data-stu-id="71796-106">Prerequisites</span></span>

<span data-ttu-id="71796-107">За да настроите и конфигурирате бота, трябва да бъдат изпълнени следните предпоставки:</span><span class="sxs-lookup"><span data-stu-id="71796-107">To set up and configure the bot, the following prerequisites must be met:</span></span>

- <span data-ttu-id="71796-108">Трябва да поне един [източник на данни да е добавен](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="71796-108">There's at least one [data source added](data-sources.md).</span></span>
- <span data-ttu-id="71796-109">Процесът а [унифициране](data-unification.md) е завършен.</span><span class="sxs-lookup"><span data-stu-id="71796-109">The [unification process](data-unification.md) is complete.</span></span>
- <span data-ttu-id="71796-110">Полетата се добавят към [индекс за търсене и филтриране](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="71796-110">Fields are added to the [search and filter index](search-filter-index.md).</span></span>
- <span data-ttu-id="71796-111">Customer Insights и Teams са в една и съща организация.</span><span class="sxs-lookup"><span data-stu-id="71796-111">Customer Insights and Teams are in the same organization.</span></span>

## <a name="configure-the-bot"></a><span data-ttu-id="71796-112">Конфигуриране на бот</span><span class="sxs-lookup"><span data-stu-id="71796-112">Configure the bot</span></span>

1. <span data-ttu-id="71796-113">В статията за аудиторията отидете на **Администратор** > **Експортиране на местоположения**.</span><span class="sxs-lookup"><span data-stu-id="71796-113">In audience insights, go to **Admin** > **Export Destinations**.</span></span>
1. <span data-ttu-id="71796-114">В плочката Microsoft Teams, изберете **Настройка**.</span><span class="sxs-lookup"><span data-stu-id="71796-114">On the Microsoft Teams tile, select **Set up**.</span></span>
1. <span data-ttu-id="71796-115">Пренасочени сте към областта **Приложения** в Teams.</span><span class="sxs-lookup"><span data-stu-id="71796-115">You're redirected to the **Apps** area in Teams.</span></span> <span data-ttu-id="71796-116">Можете също да отворите екипи и да изберете **Приложения** в долния ляв ъгъл или [го вземете от AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) директно.</span><span class="sxs-lookup"><span data-stu-id="71796-116">You can also open Teams and select **Apps** in the bottom-left corner or [get it from AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) directly.</span></span>
1. <span data-ttu-id="71796-117">Търся **Customer Insights** и изберете приложението.</span><span class="sxs-lookup"><span data-stu-id="71796-117">Search for **Customer Insights** and select the app.</span></span>
1. <span data-ttu-id="71796-118">Избери **Добавяне**.</span><span class="sxs-lookup"><span data-stu-id="71796-118">Select **Add**.</span></span>
1. <span data-ttu-id="71796-119">След като влезете в Customer Insights в Teams, ще видите поздравително съобщение и можете да започнете.</span><span class="sxs-lookup"><span data-stu-id="71796-119">After signing in to Customer Insights in Teams, you'll see a welcome message and can get started.</span></span>

## <a name="things-you-can-do-with-the-bot"></a><span data-ttu-id="71796-120">Неща, които можете да правите с бота</span><span class="sxs-lookup"><span data-stu-id="71796-120">Things you can do with the bot</span></span>

<span data-ttu-id="71796-121">Ботът осигурява възможности за търсене на унифицирани потребителски профили.</span><span class="sxs-lookup"><span data-stu-id="71796-121">The bot provides lookup capabilities for unified customer profiles.</span></span>

- <span data-ttu-id="71796-122">Въведете **Търсене** последвано от име, имейл адрес или всяко друго поле в обединения потребителски профил, което се добавя към индекса за търсене и филтриране.</span><span class="sxs-lookup"><span data-stu-id="71796-122">Enter **search** followed by a name, email address, or any other field on the unified customer profile that is added to the search and filter index.</span></span>

  <span data-ttu-id="71796-123">Ще получите карта с до 15 полета от получения потребителски профил.</span><span class="sxs-lookup"><span data-stu-id="71796-123">You'll get a card with up to 15 fields from the resulting customer profile.</span></span> <span data-ttu-id="71796-124">Множество съвпадения връщат списък с резултати, при които можете да изберете профил.</span><span class="sxs-lookup"><span data-stu-id="71796-124">Multiple matches return a list of results where you can select a profile.</span></span> <span data-ttu-id="71796-125">Можете да добавите думата за търсене в двойни кавички, за да търсите точно съвпадение.</span><span class="sxs-lookup"><span data-stu-id="71796-125">You can add the search term in double quotes to look up an exact match.</span></span>

- <span data-ttu-id="71796-126">Ако вашата организация поддържа множество среди на Customer Insights в една и съща организация, можете да въведете **switchinstance**, за да изберете към коя среда искате да свържете бота.</span><span class="sxs-lookup"><span data-stu-id="71796-126">If your organization maintains multiple Customer Insights environments in the same organization, you can enter **switchinstance** to choose which environment you want to connect the bot to.</span></span>

- <span data-ttu-id="71796-127">Въведете **помощ**, за да видите списък с наличните команди за бота.</span><span class="sxs-lookup"><span data-stu-id="71796-127">Enter **help** to see a list of available commands for the bot.</span></span>  