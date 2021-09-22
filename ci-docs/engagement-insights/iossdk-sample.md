---
title: Изпълнение на iOS SDK примера
description: Примерен проект, за да научите за iOS SDK
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 053e626d06d3e17b39b448987410058e45e8ae0385f3ecdef40314cb46ae4bf4
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036815"
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
