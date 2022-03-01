---
title: Изпълнение на уеб SDK проба
description: Научете как да персонализирате и стартирате уеб SDK проба.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 10/30/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 97e50a51231bcf05f3e381397f0cf41e49afc10e3c3674d7c709c8f521979e12
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036590"
---
# <a name="run-the-web-sdk-sample-for-dynamics-365-customer-insights-engagement-insights-capability"></a>Стартирайте пробата за уеб SDK за способността аналитични данни на ангажираността на Dynamics 365 Customer Insights

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Web SDK библиотеката с възможности за проследяване на ангажираността е библиотека на JavaScript с примерен код, който можете да използвате на вашия уебсайт.

## <a name="prerequisites"></a>Предварителни изисквания

- Инсталирайте [код на Visual Studio](https://code.visualstudio.com/).
- [Инсталирайте разширението Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) в код на Visual Studio и се запознайте с това как да стартирате Live Server.
- Трябва да имате [ключ за поглъщане](instrument-website.md).

## <a name="run-sample"></a>Изпълнение на проба

1. [Изтеглете пробата за уеб SDK](https://download.pi.dynamics.com/sdk/EngagementInsightsSamples/ei_websdk_sample.zip).

1. Извлечете компресирания файл `ei_websdk_sample.zip`.

1. Отворете разархивираната папка в Код на Visual Studio.

1. Във файла `ei_websdk_sample.html`, заменете низа "INGESTION_KEY" с вашия ключ за поглъщане от портала за способности за проследяване на ангажираността, а низът "ИМЕ" с глобалното име, в което искате да се създаде инстанция на SDK. Уверете се, че замествате всички случаи.

1. Отворете `ei_websdk_sample.html` файл с помощта на Код на Visual Studio, като изберете **Отидете на живо** от лентата на състоянието.

1. При отваряне на страницата събитие за преглед трябва да бъде изпратено автоматично. Кликването върху някой от бутоните на страницата ще изпрати събития за действие. Бутонът **Проследяване на събития** също ще изпрати персонализирани събития. Избиране на **Отидете в Bing** бутон ще изпрати събитие за действие, преди да отидете до уебсайта на Bing.

1. Погледнете събитията, които протичат, когато навигирате до работното си пространство. Това работно пространство е свързано с ключа за поглъщане, въведен в стъпка 4.


[!INCLUDE[footer-include](../includes/footer-banner.md)]