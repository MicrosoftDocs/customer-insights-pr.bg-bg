---
title: Пример за Android SDK
description: Примерен проект, за да научите за Android SDK
author: britl
ms.reviewer: m-hartmann
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: ba51961bc7f9555d7dba5b6a21c8636011438d75cba87bc132b896841c467a33
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035813"
---
# <a name="run-the-android-sdk-sample"></a>Изпълнение на примера на Android SDK

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Този примерен проект за Android ви помага да разберете как работи SDK в приложение. Няма нужда да пишете код. Просто добавете вашия ключ за поглъщане и можете веднага да видите събития в работното си пространство.

## <a name="prerequisites"></a>Предварителни изисквания

- [Android Studio](https://developer.android.com/studio)
- [Ключ за поглъщане](get-started-android.md)

## <a name="download-the-android-sdk-sample"></a>Изтегляне на примера за Android SDK

1. [Изтеглете пример за проследяване на ангажираността на Android SDK](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-android-sample.zip).
1. Извлечете компресирания файл `ei-android-sample.zip`.
1. Отворете разархивираната папка в Android Studio.
1. Във файла `AndroidManifest.xml`, заменете низа `"Your-Ingestion-Key"` с вашия ключ за поглъщане на работното пространство от прозрения за ангажираност под **Администратор** > **Работно пространство** > **Ръководство за инсталиране**. 

   > [!NOTE]
   > Не е необходимо да подменяте `${applicationId}` раздел. Попълва се автоматично.

   ```xml
   <application>
   ...
       <provider
           android:authorities="${applicationId}.com.microsoft.engagementinsights.eiandroidsdk.AnalyticsContentProvider"
           android:name="microsoft.dynamics.engagementinsights.eiandroidsdk.AnalyticsContentProvider" />
       <meta-data
           android:name="com.microsoft.engagementinsights.ingestionKey"
           android:value="Your-Ingestion-Key" />
       <meta-data
           android:name="com.microsoft.engagementinsights.autoCapture"
           android:value="true" />
   ...
   </application>
   ```

1. За да започнете примерния проект, изберете **Изпълнение**.
1. Преглеждайте събитията в работното си пространство.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
