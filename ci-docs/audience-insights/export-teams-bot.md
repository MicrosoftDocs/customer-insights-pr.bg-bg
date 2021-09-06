---
title: Бот за Microsoft Teams
description: Потърсете единни клиентски профили в Microsoft Teams с помощта на бот.
ms.date: 04/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 9bf401124b0ffb21b046954056141e7703386d4911f89f34ffc0fcb84bf0f4be
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032469"
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

## <a name="configure-the-bot"></a>Конфигуриране на бот

1. В статията за аудиторията отидете на **Администратор** > **Експортиране на местоположения**.
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


[!INCLUDE[footer-include](../includes/footer-banner.md)]