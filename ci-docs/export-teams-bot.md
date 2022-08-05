---
title: Бот на Teams за Dynamics 365 Customer Insights (преглед)
description: Потърсете единни клиентски профили в Microsoft Teams с помощта на бот.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: d140ae72578b48091a41005c4acafe03bac540da
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: bg-BG
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195829"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a>Бот на Teams за Dynamics 365 Customer Insights (преглед)

Свържете се с Microsoft Teams, за да позволите на бот да търси унифицирани клиентски профили в каналите на Teams.

:::image type="content" source="media/teams-bot.png" alt-text="Бот на Teams, показващ клиентски запис":::

## <a name="prerequisites"></a>Предварителни изисквания

- Поне един [източник на данни добавен](data-sources.md).
- Процесът а [унифициране](data-unification.md) е завършен.
- Полетата се добавят към индекса за [търсене & филтър](search-filter-index.md).
- Customer Insights и Teams са в една и съща организация.
- Вашата среда има основна целева аудитория, настроена за отделни клиенти. Бизнес акаунтите не се поддържат.


> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElj]

## <a name="configure-the-bot"></a>Конфигуриране на бот

1. Отидете на **Администратор** > **Връзки**.
1. В плочката Microsoft Teams, изберете **Настройка**.
1. Пренасочени сте към областта **Приложения** в Teams. Можете също да отворите екипи и да изберете **Приложения** в долния ляв ъгъл или [го вземете от AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) директно.
1. Търся **Customer Insights** и изберете приложението.
1. Избери **Добавяне**.
1. влезте в "Аналитични данни за клиенти" в Екипи. Показва се съобщение за добре дошли.

## <a name="things-you-can-do-with-the-bot"></a>Неща, които можете да правите с бота

Ботът осигурява възможности за търсене на унифицирани потребителски профили.

- Въведете **търсене**, последвано от име, имейл адрес или друго поле в потребителския профил на унифициран клиент, което се добавя към индекса за търсене & филтър.

  Ще получите карта с до 15 полета от получения потребителски профил. Множество съвпадения връщат списък с резултати, при които можете да изберете профил. За да потърсите точно съвпадение, добавете дума за търсене в двойни оферти.

- Ако вашата организация поддържа няколко среди на Customer Insights в една и съща организация, въведете **екземпляр за превключване**, за да изберете към коя среда искате да свържете бота.

- Въведете **помощ**, за да видите списък с наличните команди за бота.  

[!INCLUDE [footer-include](includes/footer-banner.md)]