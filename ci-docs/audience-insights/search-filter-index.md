---
title: Търсене и филтриране на потребителски профили
description: Бързо откривайте информация за унифицирани клиентски профили и филтрирайте за конкретни атрибути.
ms.date: 01/19/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: b6cc0ad1a47a6c00e3bf220271f42870fc53621b
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597130"
---
# <a name="customer-profiles-search--filter-index"></a><span data-ttu-id="4ac41-103">Клиентски профили: Индекс за търсене и филтриране</span><span class="sxs-lookup"><span data-stu-id="4ac41-103">Customer profiles: Search & filter index</span></span>

<span data-ttu-id="4ac41-104">Резултатът от обединяването на клиентските данни е обект на клиентски профил, който предоставя единен изглед на общата клиентска база.</span><span class="sxs-lookup"><span data-stu-id="4ac41-104">The result of unifying your customer data is a Customer Profile entity that provides a unified view into your total customer base.</span></span> <span data-ttu-id="4ac41-105">За бързо [намиране на информация за конкретен клиент или група клиенти](customer-profiles.md) можете да конфигурирате възможностите **Търсене** и **Филтър** на страницата **Клиенти**.</span><span class="sxs-lookup"><span data-stu-id="4ac41-105">To quickly [find information on a specific customer or group of customers](customer-profiles.md), you can configure the **Search** and **Filter** capabilities on the **Customers** page.</span></span> <span data-ttu-id="4ac41-106">Прочетете нататък, за да научите как администраторите могат да редактират атрибутите на страницата **Показалец за търсене и филтриране**, които са достъпни за потребителите за търсене и филтриране.</span><span class="sxs-lookup"><span data-stu-id="4ac41-106">Read on to learn how admins can edit the attributes on the **Search & filter index** page, which are available to users for searching and filtering.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="4ac41-107">![Филтър за търсене](media/search-filter.png "Филтър за търсене")</span><span class="sxs-lookup"><span data-stu-id="4ac41-107">![Search filter](media/search-filter.png "Search filter")</span></span>

## <a name="add-fields-and-specify-attributes"></a><span data-ttu-id="4ac41-108">Добавяне на полета и задаване на атрибути</span><span class="sxs-lookup"><span data-stu-id="4ac41-108">Add fields and specify attributes</span></span>

<span data-ttu-id="4ac41-109">Ако за първи път определяте атрибути с възможност за търсене като администратор, първо трябва да дефинирате индексираните полета.</span><span class="sxs-lookup"><span data-stu-id="4ac41-109">If it's the first time you define searchable attributes as an administrator, you need to define indexed fields first.</span></span> <span data-ttu-id="4ac41-110">Препоръчваме да изберете всички атрибути, по които потребителите могат да търсят и филтрират клиенти, на страницата **Клиенти**.</span><span class="sxs-lookup"><span data-stu-id="4ac41-110">We suggest you choose all the attributes by which users can search and filter customers on the **Customers** page.</span></span> <span data-ttu-id="4ac41-111">Можете да зададете само атрибути, които съществуват в обекта на клиентския профил, който сте създали по време на процеса на унифициране на данни.</span><span class="sxs-lookup"><span data-stu-id="4ac41-111">You can only specify attributes that exist in the Customer Profile entity that you created during the data unification process.</span></span>

1. <span data-ttu-id="4ac41-112">Отворете страницата **Клиенти** и изберете **Индекс за търсене и филтриране**.</span><span class="sxs-lookup"><span data-stu-id="4ac41-112">Open the **Customers** page and select **Search & filter index**.</span></span>

2. <span data-ttu-id="4ac41-113">Изберете **+Добавяне**, за да укажете индексираните полета.</span><span class="sxs-lookup"><span data-stu-id="4ac41-113">Select **+ Add** to specify the indexed fields.</span></span>

3. <span data-ttu-id="4ac41-114">Изберете атрибутите в списъка, които искате да добавите като индексирани полета.</span><span class="sxs-lookup"><span data-stu-id="4ac41-114">Select the attributes in the list you want to add as indexed fields.</span></span> <span data-ttu-id="4ac41-115">Винаги можете да добавите още атрибути, като изберете **Добавяне**.</span><span class="sxs-lookup"><span data-stu-id="4ac41-115">You can always add more attributes by selecting **Add**.</span></span> <span data-ttu-id="4ac41-116">Можете също да премахнете всички избрани атрибути, като изберете символа **Премахване**.</span><span class="sxs-lookup"><span data-stu-id="4ac41-116">You can also remove any selected attributes by selecting the **Remove** symbol.</span></span>

## <a name="explore-the-indexed-customer-fields-table"></a><span data-ttu-id="4ac41-117">Разглеждане на таблицата с индексирани полета на клиенти</span><span class="sxs-lookup"><span data-stu-id="4ac41-117">Explore the Indexed customer fields table</span></span>

<span data-ttu-id="4ac41-118">Следната информация е представена в таблицата.</span><span class="sxs-lookup"><span data-stu-id="4ac41-118">The following information is presented in the table.</span></span>

- <span data-ttu-id="4ac41-119">**Име:** Представлява името на атрибута, както се показва в обекта на клиентския профил.</span><span class="sxs-lookup"><span data-stu-id="4ac41-119">**Name**: Represents the attribute's name as it appears in the Customer Profile entity.</span></span>
- <span data-ttu-id="4ac41-120">**Тип данни**: Указва дали типът на данните е низ, число или дата.</span><span class="sxs-lookup"><span data-stu-id="4ac41-120">**Data type**: Specifies whether the data type is a string, a number, or a date.</span></span>
- <span data-ttu-id="4ac41-121">**Включен в търсенето**: Указва дали този атрибут може да се използва за търсене на клиенти на страницата **Клиенти** с помощта на полето **Търсене**.</span><span class="sxs-lookup"><span data-stu-id="4ac41-121">**Included in search**: Specifies whether this attribute can be used for searching customers on the **Customers** page using the **Search** field.</span></span>
- <span data-ttu-id="4ac41-122">**Добавяне на филтър**: Контрола за определяне как този атрибут може да се използва за филтриране на страницата **Клиенти**.</span><span class="sxs-lookup"><span data-stu-id="4ac41-122">**Add Filter**: Control to define how this attribute can be used for filtering on the **Customers** page.</span></span>

## <a name="editing-filtering-options-for-a-given-attribute"></a><span data-ttu-id="4ac41-123">Редактиране на опции за филтриране за даден атрибут</span><span class="sxs-lookup"><span data-stu-id="4ac41-123">Editing filtering options for a given attribute</span></span>

<span data-ttu-id="4ac41-124">Менюто **Филтър** на страницата **Клиенти** може да включва различен брой нива на атрибути (например различни възрастови групи, по които да филтрирате клиентите).</span><span class="sxs-lookup"><span data-stu-id="4ac41-124">The **Filter** menu on the **Customers** page can include a varying number of attribute levels (for example, different age groups to filter customers by).</span></span>

1. <span data-ttu-id="4ac41-125">Изберете **Добавяне на филтър** за даден атрибут на страницата **Показалец за търсене и филтриране**.</span><span class="sxs-lookup"><span data-stu-id="4ac41-125">Select **Add Filter** for a given attribute on the **Search & filter index** page.</span></span> <span data-ttu-id="4ac41-126">Можете да определите броя на резултатите и реда, в който ще бъдат организирани.</span><span class="sxs-lookup"><span data-stu-id="4ac41-126">You can define the number of results and the order in which they'll be organized.</span></span> <span data-ttu-id="4ac41-127">В зависимост от типа данни на атрибута се появява един от следните прозорци.</span><span class="sxs-lookup"><span data-stu-id="4ac41-127">Depending on the attribute's data type, one of the following panes appears.</span></span>

- <span data-ttu-id="4ac41-128">Атрибути от тип низ: Посочете броя на желаните резултати в прозореца **Опции на филтър за низ** и правилата за реда, по който ще бъдат организирани.</span><span class="sxs-lookup"><span data-stu-id="4ac41-128">String-type attributes: Specify the number of desired results on the **String filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="4ac41-129">Атрибути от цифров тип: Посочете включените интервали в прозореца **Опции на филтър за числа** и правилата за реда, по който ще бъдат организирани.</span><span class="sxs-lookup"><span data-stu-id="4ac41-129">Numerical-type attributes: Specify the intervals included on the **Number filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="4ac41-130">Атрибути от тип дата: Посочете включените интервали в прозореца **Опции на филтър за дата** и правилата за реда, по който ще бъдат организирани.</span><span class="sxs-lookup"><span data-stu-id="4ac41-130">Date-type attributes:  Specify the intervals included on the **Date filter options** pane and the order policy by which they'll be organized.</span></span>

2. <span data-ttu-id="4ac41-131">Изберете **Записване**, за да приложите промените.</span><span class="sxs-lookup"><span data-stu-id="4ac41-131">Select **Save** to apply your changes.</span></span>

3. <span data-ttu-id="4ac41-132">Изберете **Изпълнение**, когато сте готови да приложите настройките си.</span><span class="sxs-lookup"><span data-stu-id="4ac41-132">Select **Run** once you're ready to apply your settings.</span></span>

## <a name="next-steps"></a><span data-ttu-id="4ac41-133">Следващи стъпки</span><span class="sxs-lookup"><span data-stu-id="4ac41-133">Next steps</span></span>

<span data-ttu-id="4ac41-134">Отидете на страницата **Клиенти** за търсене на клиентски профили или използвайте индексираните полета, за да видите подмножество от всички клиентски профили.</span><span class="sxs-lookup"><span data-stu-id="4ac41-134">Go to the **Customers** page to search for customer profiles or use the indexed fields to see a subset of all customer profiles.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]