---
title: Конектор на Power Apps (преглед)
description: Свързване с Power Apps и Power Automate.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 8807e82e65ea20d1a7f7dc07552229f377927eed
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: bg-BG
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196887"
---
# <a name="power-apps-connector-preview"></a>Конектор на Power Apps (преглед)

Включете унифицирани клиентски профили в персонализираните приложения с Microsoft Power Apps.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Свързване на Power Apps и Dynamics 365 Customer Insights

Customer Insights е сред многото [налични източници за данни в Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).

Вижте документацията на Power Apps, за да научите как да [добавяте връзка за данни към приложение](/powerapps/maker/canvas-apps/add-data-connection). Препоръчваме ви също да прегледате [как Power Apps използва делегиране за обработка на големи набори от данни в приложения за платно](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="available-entities"></a>Свободни обекти

След като добавите "Аналитични данни за клиенти" като връзка с данни, изберете следните обекти в Power Apps:

- **Клиент**: за да се използват данни от [унифицирания клиентски профил](customer-profiles.md).
- **UnifiedActivity**: за показване на [времева линия на дейността](activities.md) в приложението.
- **ContactProfile**: за показване на контактите на клиент. Този обект е достъпен само в среди на Customer Insights за бизнес акаунти.

## <a name="limitations"></a>Ограничения

### <a name="retrievable-entities"></a>Възможни за извличане обекти

Можете само да изтеглите **Клиент**, **UnifiedActivity**, **Сегменти** и **ContactProfile** обекти чрез Power Apps конектор. ContactProfile е достъпен само в среди на Customer Insights за бизнес акаунти. Показани са други обекти, защото основният конектор ги поддържа чрез задействания в Power Automate.

Можете да направите максимум 100 обаждания на 60 секунди. Можете да се обадите на API крайна точка няколко пъти с помощта на параметъра $skip. [Научете повече за параметъра $skip](/connectors/customerinsights/#get-items-from-an-entity).

### <a name="delegation"></a>Делегиране

Делегирането работи за обекта **клиент** и обекта **UnifiedActivity**.

- "Делегиране за **обект клиент** ": За да използвате делегиране за този обект, полетата трябва да бъдат индексирани в [индекса за търсене & филтър](search-filter-index.md).  
- Делегиране за **UnifiedActivity**: Делегирането за този обект работи само за полетата **ActivityId** и **Клиентски номер**.  
- Делегация за **ContactProfile**: Делегирането за този обект работи само за полетата **ContactId** и **CustomerId**. ContactProfile е достъпен само в среди на Customer Insights за бизнес акаунти.

За повече информация относно делегирането, отидете на [делегируеми функции и операции на Power Apps](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="example-gallery-control"></a>Контрола на примерна галерия

По желание добавете профили на клиенти към контрол на [галерия](/powerapps/maker/canvas-apps/add-gallery).

1. Добавете контрола **Галерия** към приложението, което създавате.
  
   :::image type="content" source="media/connector-powerapps9.png" alt-text="Добавяне на елемент от галерията.":::

1. Изберете **Клиент** като източник на данни за елементите.

   :::image type="content" source="media/choose-datasource-powerapps.png" alt-text="Избор на източник на данни.":::

1. Променете панела с данни отдясно, за да изберете кое поле за обекта Клиент да се показва в галерията.

1. Ако искате да покажете в галерията някое поле от избрания клиент, попълнете свойството **Текст** на етикет, като използвате **{Name_of_the_gallery}.Selected.{property_name}**  
    - Например: _Gallery1.Selected.address1_city_

1. За да покажете унифицираната времева линия за клиент, добавете елемент от галерията и добавете свойството **Елементи** с помощта на **Filter('UnifiedActivity', CustomerId = {Customer_Id})**  
    - Например: _Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)_

[!INCLUDE [footer-include](includes/footer-banner.md)]
