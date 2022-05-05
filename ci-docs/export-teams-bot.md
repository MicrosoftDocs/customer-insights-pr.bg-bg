---
title: Бот за Microsoft Teams
description: Потърсете единни клиентски профили в Microsoft Teams с помощта на бот.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 89a293d5b6f9f5452b2ccba495d2475002806019
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: bg-BG
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642429"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a>Бот на Teams за Dynamics 365 Customer Insights (преглед)

Свържете се с Microsoft Teams, за да позволите на бот да търси унифицирани клиентски профили в каналите на Teams.

> [!div class="mx-imgBorder"]
> ![Бот на Teams, показващ клиентски запис.](media/teams-bot.png "Бот на Teams, показващ клиентски запис")

## <a name="prerequisites"></a>Предварителни изисквания

За да настроите и конфигурирате бота, трябва да бъдат изпълнени следните предпоставки:

- Трябва да поне един [източник на данни да е добавен](data-sources.md).
- Процесът а [унифициране](data-unification.md) е завършен.
- Полетата се добавят към [индекс за търсене и филтриране](search-filter-index.md).
- Customer Insights и Teams са в една и съща организация.
- Вашата среда има основна целева аудитория, настроена за отделни клиенти. Бизнес акаунтите не се поддържат.


> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElj]

## <a name="configure-the-bot"></a>Конфигуриране на бот

1. Отидете на **Дестинации за adminExport** > **·**.
1. В плочката Microsoft Teams, изберете **Настройка**.
1. Пренасочени сте към областта **Приложения** в Teams. Можете също да отворите екипи и да изберете **Приложения** в долния ляв ъгъл или [го вземете от AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) директно.
1. Търся **Customer Insights** и изберете приложението.
1. Избери **Добавяне**.
1. След като влезете в Customer Insights в Teams, ще видите поздравително съобщение и можете да започнете.

## <a name="things-you-can-do-with-the-bot"></a>Неща, които можете да правите с бота

Ботът осигурява възможности за търсене на унифицирани потребителски профили.

- Въведете **Търсене** последвано от име, имейл адрес или всяко друго поле в обединения потребителски профил, което се добавя към индекса за търсене и филтриране.

  Ще получите карта с до 15 полета от получения потребителски профил. Множество съвпадения връщат списък с резултати, при които можете да изберете профил. Можете да добавите думата за търсене в двойни кавички, за да търсите точно съвпадение.

- Ако вашата организация поддържа множество среди на Customer Insights в една и съща организация, можете да въведете **switchinstance**, за да изберете към коя среда искате да свържете бота.

- Въведете **помощ**, за да видите списък с наличните команди за бота.  


[!INCLUDE [footer-include](includes/footer-banner.md)]