---
title: Първи стъпки с Android SDK
description: Научете как да персонализирате и стартирате Android SDK
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 77e63929bbcc7ecff34a3839af525b76ec3c7f21173ddc5f8f2d69f11c25c441
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036905"
---
# <a name="get-started-with-the-android-sdk"></a>Първи стъпки с Android SDK

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Този въвеждащ курс ви показва как да добавите към приложението си Android приложение с SDK за аналитични данни за ангажираността на Dynamics 365 Customer Insights. Ще започнете да виждате събития във вашия портал след пет минути или по-рано.

## <a name="configuration-options"></a>Опции за конфигуриране
Следните опции за конфигуриране могат да бъдат предадени на SDK:

- **ingestionKey**: Ключът за поглъщане, използван за изпращане на събития към работната ви област.

## <a name="prerequisites"></a>Предварителни изисквания

- Android Studio

- Минимум Android API ниво: 16 (Jelly Bean)

- Ключ за поглъщане (вижте инструкциите по-долу за това как да получите)

## <a name="step-1-integrate-the-sdk-into-your-application"></a>Стъпка 1. Интегрирайте SDK във вашето приложение
Започнете процеса, като изберете работно пространство, изберете мобилната платформа на Android и изтеглите Android SDK.

- Използвайте превключвателя на работното пространство в левия навигационен прозорец, за да изберете работното си пространство.

- Ако нямате съществуващо работно пространство, изберете **Ново работно пространство** и следвайте стъпките за създаване на [ново работно пространство](create-workspace.md).

## <a name="step-2-configure-the-sdk"></a>Стъпка 2. Конфигуриране на SDK

1. След като създадете работно пространство, отидете на **Администратор** > **Работно пространство** и след това изберете **Ръководство за инсталиране**. 

1. Изтеглете [Аналитични данни за ангажираност на AndroidSDK](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-android-sdk.zip) и поставете `eiandroidsdk-debug.aar` файл в папката `libs`.

1. Отворете файла `build.gradle` на ниво проект и добавете следните фрагменти:
    ```gradle
    dependencies {
        implementation(name: 'eiandroidsdk-debug', ext: 'aar')
        api 'com.google.code.gson:gson:2.8.1'
    }

    repositories {
        flatDir {
            dirs 'libs'
        }
    }
    ```

1. Настройте конфигурацията на SDK за анализ на ангажираността чрез вашия `AndroidManifest.xml` файл, намиращ се под `manifests` папка. 
1. Копирайте XML фрагмент от **Ръководство за инсталиране**. `Your-Ingestion-Key` трябва да се попълва автоматично.

   > [!NOTE]
   > Не е необходимо да подменяте `${applicationId}` раздел. Попълва се автоматично.
   

   ```xml
   <application>
   ...
       <provider
           android:authorities="${applicationId}.com.microsoft.engagementinsights.AnalyticsContentProvider"
           android:name="com.microsoft.engagementinsights.AnalyticsContentProvider" />
       <meta-data
           android:name="com.microsoft.engagementinsights.ingestionKey"
           android:value="Your-Ingestion-Key" />
       <meta-data
           android:name="com.microsoft.engagementinsights.autoCapture"
           android:value="true" />
   ...
   </application>
   ```

1. Активирайте или дезактивирайте автоматичното улавяне на `View` събития на преглеждане, като зададете `true` или `false` за полето `autoCapture` по-горе.

1. (По избор) Други конфигурации включват настройка на URL адреса на събирача на крайни точки. Те могат да бъдат добавени под метаданните на ключа за поглъщане в `AndroidManifest.xml`:
    ```xml
        <meta-data
            android:name="com.microsoft.engagementinsights.endpointUrl"
            android:value="https://some-endpoint-url.com" />
    ```

## <a name="step-3-initialize-the-sdk-from-mainactivity"></a>Стъпка 3. Инициализирайте SDK от MainActivity 

След като инициализирате SDK, можете да работите със събития и техните свойства в средата MainActivity.

    
Java:
```java
Analytics analytics = new Analytics();
```

Котлин:
```kotlin
var analytics = Analytics()
```

### <a name="set-property-for-all-events-optional"></a>Задайте свойство за всички събития (по избор)
    
Java:
```java
analytics.setProperty("year", 2021);
```

Котлин:
```kotlin
analytics.setProperty("year", 2021)
```

Следните типове се поддържат за свойства на контекстно събитие:
- String
- Данни
- С двойна точност
- Дълъг
- Boolean
- UUID

### <a name="track-an-event"></a>Проследяване на събитие

Java:
```java
Event event = new Event("video");
event.setProperty("duration", 320);
event.setProperty("ad_shown", true);
analytics.trackEvent(event);
```

Котлин:
```kotlin
var event = Event("video")
event.setProperty("duration", 320)
event.setProperty("ad_shown", true)
analytics.trackEvent(event)
```

### <a name="set-user-details-for-your-event-optional"></a>Задайте потребителски подробности за вашето събитие (опционално)

SDK ви позволява да дефинирате потребителска информация, която може да бъде изпратена с всяко събитие. Можете да посочите потребителска информация, като се обадите на `setUser(user: User)` API на ниво `Analytics`.

Java:
```java
User user = new User();
user.setName("testuser");
user.setEmail("abc@xyz.com");
analytics.setUser(user);
```

Котлин:
```kotlin
var user = User()
user.name = "testuser"
user.email = "abc@xyz.com"
analytics.setUser(user)
```

Класът данни `User` съдържа следните свойства на низ:

- **localId**: Локалният идентификатор на потребителя.
- **authId**: Удостовереният потребителски идентификатор.
- **authType**: Типът на удостоверяване, използван за получаване на удостоверен потребителски идентификатор.
- **име**: Потребителското име.
- **имейл**: Имейл адресът на потребителя.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
