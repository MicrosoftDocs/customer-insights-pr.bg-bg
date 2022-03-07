---
title: Изпълнение на iOS SDK примера
description: Примерен проект, за да научите за iOS SDK
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 06/23/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: bbe4ba648952a8081af4c8f2610276809fa5efeb
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: bg-BG
ms.lasthandoff: 02/16/2022
ms.locfileid: "8232829"
---
# <a name="run-the-ios-sdk-sample"></a>Изпълнение на iOS SDK примера

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Този примерен проект за iOS ви помага да разберете как работи SDK в приложение. Няма нужда да пишете код. Просто добавете вашия ключ за поглъщане и можете веднага да видите събития в работното си пространство.

## <a name="prerequisites"></a>Предварителни изисквания

- [Xcode, версия 9+](https://developer.apple.com/xcode/downloads/)
- [Ключ за поглъщане](get-started-ios.md)

## <a name="download-the-ios-sdk-sample"></a>Изтегляне на примера за iOS SDK

1. [Изтеглете пример за проследяване на ангажираността на iOS SDK](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-ios-sample.zip).
1. Извлечете компресирания файл `ei-ios-sample.zip`.
1. Отворете примерния проект на приложение в Xcode.
1. В `EIConfig.plist` файл, заменете низа `“YOUR-INGESTION-KEY”` в областта `ingestionKey` с вашия ключ за поглъщане на работното пространство от прозрения за ангажираност под **Администратор** > **Работно пространство** > **Ръководство за инсталиране**.
1. За да започнете примерния проект, изберете **Изпълнение**.
1. Преглеждайте събитията в работното си пространство.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
