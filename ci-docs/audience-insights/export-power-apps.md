---
title: Конектор на Power Apps
description: Свързване с Power Apps и Power Automate.
ms.date: 01/19/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: fc0af656cd5b436d9efd65b2a2c75dde9c9deb9dbcdd56ffc6a960f5878a631f
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 08/10/2021
ms.locfileid: "7031736"
---
# <a name="microsoft-power-apps-connector-preview"></a>Конектор на Microsoft Power Apps (преглед)

Включете унифицирани клиентски профили в персонализираните приложения с Power Apps.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Свързване на Power Apps и Dynamics 365 Customer Insights

Customer Insights е сред многото [налични източници за данни в Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).

Вижте документацията на Power Apps, за да научите как да [добавяте връзка за данни към приложение](/powerapps/maker/canvas-apps/add-data-connection). Препоръчваме ви също да прегледате [как Power Apps използва делегиране за обработка на големи набори от данни в приложения за платно](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="available-entities"></a>Свободни обекти

След като добавите Customer Insights като връзка за данни, можете да използвате следните обекти в Power Apps:

- Клиент: за да се използват данни от [унифицирания клиентски профил](customer-profiles.md).
- UnifiedActivity: за показване на [времева линия на дейност](activities.md) в приложението.

## <a name="limitations"></a>Ограничения

### <a name="retrievable-entities"></a>Възможни за извличане обекти

Можете да изтеглите само **Клиент**, **UnifiedActivity** и **Сегменти** обекти чрез Power Apps съединител. Показани са други обекти, защото основният конектор ги поддържа чрез задействания в Power Automate.  

### <a name="delegation"></a>Делегиране

Делегирането работи за обекта на клиента и обекта на UnifiedActivity. 

- Делегация за обекта **Клиент**: За да се използва делегиране за този обект, полетата трябва да бъдат индексирани в [Индекс за търсене и филтриране](search-filter-index.md).  

- Делегиране за **UnifiedActivity**: Делегирането за този обект работи само за полетата **ActivityId** и **Клиентски номер**.  

- За повече информация относно делегирането вижте [делегируеми функции и операции на Power Apps](/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps). 

## <a name="example-gallery-control"></a>Контрола на примерна галерия

Например добавяте потребителски профили към [контрола на галерията](/powerapps/maker/canvas-apps/add-gallery).

1. Добавете контрола **Галерия** към приложението, което създавате.

> [!div class="mx-imgBorder"]
> ![Добавяне на елемент от галерията.](media/connector-powerapps9.png "Добавяне на елемент от галерията")

1. Изберете **Клиент** като източник на данни за елементите.

    > [!div class="mx-imgBorder"]
    > ![Избор на източник на данни.](media/choose-datasource-powerapps.png "Избор на източник на данни")

1. Можете да промените панела с данни вдясно, за да изберете полето за обекта на клиента, което ще бъде показано в галерията.

1. Ако искате да покажете в галерията някое поле от избрания клиент, попълнете свойството „Текст” на етикет: **{Name_of_the_gallery}.Избрано.{property_name}**

    Пример: Gallery1.Selected.address1_city

1. За да се покаже унифицираната времева линия за клиент, добавете елемент от галерията и добавете свойството „Елементи“: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**

    Пример: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)


[!INCLUDE[footer-include](../includes/footer-banner.md)]