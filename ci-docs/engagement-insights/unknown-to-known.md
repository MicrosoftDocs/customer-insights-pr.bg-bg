---
title: Разпознаване на уеб събития от предварително удостоверени посетители с неизвестни към известни
description: Функцията за неизвестни към известни ви позволява да свързвате събития на уеб сайт с посетители, които са се удостоверявали преди това.
ms.reviewer: mhart
ms.author: mkisel
author: mkisel11
ms.date: 7/15/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: overview
ms.manager: shellyha
ms.openlocfilehash: d1bbc3315b55e2ee233dc672456e0c27e4ad0fbd5937af09cc790c96ee274000
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036770"
---
# <a name="recognize-web-events-from-previously-authenticated-visitors"></a>Разпознаване на уеб събития от предварително удостоверени посетители

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Функцията за **неизвестни към известни** във възможността за аналитични данни за ангажираност разрешава свързване на събития на уеб сайт с посетители, които са се удостоверявали по-рано. Ако функцията е дезактивирана, посетителите, които са се удостоверили при по-ранно посещение и след това са излезли, не се идентифицират, ако не се удостоверят отново при влизане. 

Например дадено лице е посетило уеб сайт миналата седмица, влязло е в потребителския си акаунт на сайта и е прегледало продуктовия каталог. Лицето се връща следващата седмица, за да разгледа още продукти, без да влиза в акаунта си. Собственикът на сайта, който използва функцията за **неизвестни към известни**, ще знае, че същото лице се е върнало и какво е направило на сайта. Това позволява по-прецизно отчитане и анализ на дейностите на уеб сайта.

## <a name="enable-unknown-to-known"></a>Разрешаване на неизвестни към известни

Трябва да сте [администратор на работна област](user-roles.md), за да активирате тази функция. 

1. В аналитичните данни за ангажираност отидете на **Администратор** > **Работна област**. 
2. Изберете раздела **Настройки**.
3. В секцията **Неизвестни към известни** задайте превключвателя на **Активирано**.

![Разрешаване на неизвестни към известни](media/U2Ktoggle.png "Разрешаване на неизвестни към известни")

## <a name="adding-javascript-code-to-your-sites-tracking-snippet"></a>Добавяне на код на JavaScript към фрагмента за проследяване на сайта

Уеб сайтът може да улови **authId на потребителя** със следния примерен JavaScript чрез [уеб SDK на аналитичните данни за ангажираност](advanced-SDK-implementation.md). За да работи функцията **неизвестни към известни**, трябва да уловите authId *и* да разрешите userMapping:True във фрагмента на JavaScript, както е показано на примера по-долу.

```
[…]
window, document
{
src:"https://download.pi.dynamics.com/sdk/web/mspi-0.min.js",
name:"myproject",
cfg:{
ingestionKey:<paste your ingestion key>",
autoCapture:{
view:true,
click:true
},
userMapping: true
},
user:{
authId: getLoggedInUserId()*,
email: getLoggedInUserEmail()*,
authType: "MSA",
name: "Alex Jensen"
}
[…]
```

[!INCLUDE[footer-include](../includes/footer-banner.md)]
