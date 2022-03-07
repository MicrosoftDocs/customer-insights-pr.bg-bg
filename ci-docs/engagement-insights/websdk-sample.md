---
title: Изпълнение на уеб SDK проба
description: Научете как да персонализирате и стартирате уеб SDK проба.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: a50a10db784ec7c1943c94e74000713309787e5c
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: bg-BG
ms.lasthandoff: 02/16/2022
ms.locfileid: "8225318"
---
# <a name="run-the-web-sdk-sample-for-dynamics-365-customer-insights-engagement-insights-capability"></a>Стартирайте пробата за уеб SDK за способността аналитични данни на ангажираността на Dynamics 365 Customer Insights

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Web SDK библиотеката с възможности за проследяване на ангажираността е библиотека на JavaScript с примерен код, който можете да използвате на вашия уебсайт.

## <a name="prerequisites"></a>Предварителни изисквания

- Инсталирайте [код на Visual Studio](https://code.visualstudio.com/).
- [Инсталирайте разширението Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) в код на Visual Studio и се запознайте с това как да стартирате Live Server.
- Трябва да имате [работно пространство за ангажименти](create-workspace.md).

## <a name="run-sample"></a>Изпълнение на проба

1. [Изтеглете пробата за уеб SDK](https://download.pi.dynamics.com/sdk/EngagementInsightsSamples/ei_websdk_sample.zip).

1. Извлечете компресирания файл `ei_websdk_sample.zip`.

1. Отворете разархивираната папка в Код на Visual Studio.

1. Отидете на портала за анализи на ангажираността за вашето работно пространство. Изберете **Администратор** > **Работно пространство** и след това **Ръководство за инсталиране**. Следвайте първата опция и изберете **Копирайте кода**, за да копирате JavaScript фрагмент от код.

1. Във файла `ei_websdk_sample.html`, поставете фрагмент от код, който току-що сте копирали под този ред:

   - <-- ПОСТАВЕТЕ ФРАГМЕНТА ОТ КОД НА JAVASCRIPT ОТ ПОРТАЛА НА АНАЛИТИЧНИ ДАННИ ЗА АНГАЖИРАНОСТ ТУК ПОД ТОЗИ РЕД -->

1. Отворете `ei_websdk_sample.html` файл с помощта на Код на Visual Studio, като изберете **Отидете на живо** от лентата на състоянието.

1. При отваряне на страницата събитие за преглед трябва да бъде изпратено автоматично. Кликването върху някой от бутоните на страницата ще изпрати събития за действие. Бутонът **Проследяване на събития** също ще изпрати персонализирани събития. Избиране на **Отидете в Bing** бутон ще изпрати събитие за действие, преди да отидете до уебсайта на Bing.

1. Погледнете събитията, които протичат, когато навигирате до работното си пространство. Това работно пространство е свързано с ключа за поглъщане, въведен в стъпка 4.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
