---
title: Конектор на Power Apps
description: Свързване с Power Apps и Power Automate.
ms.date: 10/01/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: e99d7d4f231eb2ade67f27c9e52c61af3a21b99d
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: bg-BG
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642437"
---
# <a name="microsoft-power-apps-connector-preview"></a>Конектор на Microsoft Power Apps (преглед)

Включете унифицирани клиентски профили в персонализираните приложения с Power Apps.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Свързване на Power Apps и Dynamics 365 Customer Insights

Customer Insights е сред многото [налични източници за данни в Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).

Вижте документацията на Power Apps, за да научите как да [добавяте връзка за данни към приложение](/powerapps/maker/canvas-apps/add-data-connection). Препоръчваме ви също да прегледате [как Power Apps използва делегиране за обработка на големи набори от данни в приложения за платно](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="available-entities"></a>Свободни обекти

След като добавите Customer Insights като връзка за данни, можете да използвате следните обекти в Power Apps:

- **Клиент**: за да се използват данни от [унифицирания клиентски профил](customer-profiles.md).
- **UnifiedActivity**: за показване на [времева линия на дейността](activities.md) в приложението.
- **ContactProfile**: за показване на контактите на клиент. Този обект е достъпен само в среди на Customer Insights за бизнес акаунти.

## <a name="limitations"></a>Ограничения

### <a name="retrievable-entities"></a>Възможни за извличане обекти

Можете само да изтеглите **Клиент**, **UnifiedActivity**, **Сегменти** и **ContactProfile** обекти чрез Power Apps конектор. ContactProfile е наличен само в екземпляр на Customer Insights за бизнес акаунти. Показани са други обекти, защото основният конектор ги поддържа чрез задействания в Power Automate.

Можете да направите максимум 100 обаждания на 60 секунди. Можете да се обадите на API крайна точка няколко пъти с помощта на параметъра $skip. [Научете повече за параметъра $skip](/connectors/customerinsights/#get-items-from-an-entity).

### <a name="delegation"></a>Делегиране

Делегирането работи за обекта **клиент** и обекта **UnifiedActivity**. 

- Делегация за обекта **Клиент**: За да се използва делегиране за този обект, полетата трябва да бъдат индексирани в [Индекс за търсене и филтриране](search-filter-index.md).  
- Делегиране за **UnifiedActivity**: Делегирането за този обект работи само за полетата **ActivityId** и **Клиентски номер**.  
- Делегация за **ContactProfile**: Делегирането за този обект работи само за полетата **ContactId** и **CustomerId**. ContactProfile е достъпен само в среди на Customer Insights за бизнес акаунти.

За повече информация относно делегирането, отидете на [делегируеми функции и операции на Power Apps](/powerapps/maker/canvas-apps/delegation-overview). 

## <a name="example-gallery-control"></a>Контрола на примерна галерия

Можете да добавите потребителски профили към [контрол на галерията](/powerapps/maker/canvas-apps/add-gallery).

1. Добавете контрола **Галерия** към приложението, което създавате.

    > [!div class="mx-imgBorder"]
    > ![Добавяне на елемент от галерията.](media/connector-powerapps9.png "Добавяне на елемент от галерията.")

2. Изберете **Клиент** като източник на данни за елементите.

    > [!div class="mx-imgBorder"]
    > ![Избор на източник на данни.](media/choose-datasource-powerapps.png "Избор на източник на данни.")

3. Можете да промените панела с данни вдясно, за да изберете полето за обекта на клиента, което ще бъде показано в галерията.

4. Ако искате да покажете в галерията някое поле от избрания клиент, попълнете свойството **Текст** на етикет, като използвате **{Name_of_the_gallery}.Selected.{property_name}**  
    - Например: _Gallery1.Selected.address1_city_

5. За да покажете унифицираната времева линия за клиент, добавете елемент от галерията и добавете свойството **Елементи** с помощта на **Filter('UnifiedActivity', CustomerId = {Customer_Id})**  
    - Например: _Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)_


[!INCLUDE [footer-include](includes/footer-banner.md)]
