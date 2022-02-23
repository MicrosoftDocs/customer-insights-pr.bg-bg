---
title: Първи стъпки с iOS SDK
description: Научете как да персонализирате и стартирате iOS SDK
author: britl
ms.reviewer: mhart
ms.custom: intro-internal
ms.author: britl
ms.date: 09/15/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 879a71175a2e7d44a54d25fd8efb9f12927cea5a
ms.sourcegitcommit: bb1ca84bc38e81fb2ff2961c457384b7beb5b5fa
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 01/15/2022
ms.locfileid: "7977493"
---
# <a name="get-started-with-the-ios-sdk"></a>Първи стъпки с iOS SDK

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Този въвеждащ курс ви показва как да добавите към инструментариума си приложението за iOS с SDK за аналитични данни за ангажираността на Dynamics 365 Customer Insights. Ще започнете да виждате събития във вашия портал след пет минути или по-рано.

## <a name="configuration-options"></a>Опции за конфигуриране

Следните опции за конфигуриране могат да бъдат предадени на SDK чрез предоставения `EIConfig.plist` файл:

- **ingestionKey**: Ключът за поглъщане, използван за изпращане на събития към вашия проект.
- **autocollectAction**: Булева стойност за активиране или деактивиране на автоматична инструментация на събитието за действие.
- **autocollectView**: Булева стойност за активиране или деактивиране на автоматична инструментация на събитието за изглед.
- **endpointUrl**: URL адресът на крайната точка, към който ще бъдат насочени събитията.

## <a name="prerequisites"></a>Предварителни изисквания

- Xcode, версия 9+
- iOS, версия 8.2+
- Ключ за поглъщане (вижте инструкциите по-долу, за да получите)

## <a name="integrate-the-sdk-into-your-application"></a>Интегрирайте SDK във вашето приложение

Започнете процеса, като изберете работно пространство, в което да работите, изберете мобилната платформа на iOS и изтеглите SDK.

- Използвайте превключвателя на работното пространство в левия навигационен прозорец, за да изберете работното си пространство.

- Ако нямате съществуващо работно пространство, изберете **Ново работно пространство** и следвайте стъпките за създаване на [ново работно пространство](create-workspace.md).

- След като създадете работно пространство, отидете на **Администратор** > **Работно пространство** и след това изберете **Ръководство за инсталиране**.

## <a name="configure-the-sdk"></a>Конфигуриране на SDK

След като изтеглите SDK, можете да работите с него в Xcode, за да активирате и дефинирате събития. Има два начина да направите това

### <a name="option-1-using-cocoapods-recommended"></a>Вариант 1: Използване на CocoaPods (препоръчително)
CocoaPods е мениджър на зависимости за Swift и Objective-C Cocoa проекти. Използването му улеснява интегрирането на SDK за прозрения за ангажираност за iOS. CocoaPods също така ви позволява да надстроите до най -новата версия на SDK за анализи на ангажираността. Ето как да използвате CocoaPods за интегриране на SDK за прозрения за ангажираност във вашия Xcode проект. 

1. Инсталирайте CocoaPods. 

1. Създайте нов файл, наречен Podfile, в главната директория на вашия проект и добавете следните изявления към него. Заменете YOUR_TARGET_PROJECT_NAME с името на вашия Xcode проект. 
```objectivec
platform :ios, '9.0'  

 target '${YOUR_TARGET_PROJECT_NAME}' do 

     use_frameworks!   

     pod 'EIObjC.framework.debug' 

     pod 'EIObjC.framework.release' 

 end 
```
Конфигурацията на под по-горе съдържа както версиите за отстраняване на грешки, така и версията на SDK. Изберете това, което е най-добро за вашия проект.

1. Инсталирайте под, като изпълните следната команда: `pod install --repo-update `

### <a name="option-2-using-download-link"></a>Вариант 2: Използване на връзка за изтегляне

1. Изтеглете [Аналитични данни за ангажираност на iOS SDK](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-ios-sdk.zip) и поставете `EIObjC.xcframework` файл в папката `Frameworks`.

1. Ако папката `Frameworks` не съществува, създайте такава в папката на проекта.

## <a name="enable-auto-instrumentation"></a>Активиране на автоматичното инструментиране
 
Можете лесно да активирате автоматичното инструментиране без кодиране. Когато проектът се изпълни, той автоматично ще проследи `view` и `action` събития с помощта на конфигурирания ключ за поглъщане. 

1. Актуализирайте и включете предоставеното `EIConfig.plist` файл в папката на вашата директория на проекта за следните полета:
    - ingestionKey = `"Your-Ingestion-Key"`
    - autocollectView = ДА
    - autocollectAction = ДА

2. След това добавете `EIConfig.plist` файл към вашия проект в Xcode. 



За да забраните автоматичното инструментиране, актуализирайте следните полета във включения `EIConfig.plist` файл в папката на вашата директория на проекта. 

```objectivec
'autocollectView' = NO (to disable)
'autocollectAction' = NO (to disable)
```


## <a name="implement-custom-events"></a>Внедряване на персонализирани събития

1. Отворете своя проект в Xcode, и навигирайте до **Общи** настройки. 
1. Добавете `EIObjC.xcframework` към проекта в раздела „Рамки, библиотеки и вградено съдържание“.

1. Импортирайте файла на заглавката за рамката в AppDelegate.m със следния фрагмент:

    ```objectivec
    #import <EIObjC/EIObjC.h>
    ```

1. Инициализирайте аналитичните данни за ангажираност на SDK от приложението: application:didFinishLaunchingWithOptions/
1. Копирайте XML фрагмент от **Ръководство за инсталиране**.

    ```objectivec
    NSError *error = [NSError new];
    id<EIIAnalytics> analytics = [EIAnalyticsProvider analyticsForIngestionKey:nil error:&error];
    ```

1. Проследяване на събитие:

    ```objectivec
    EIEvent *event = [EIEvent new];
    event.name = @"video.log";
    [event setLongValue:320 forKey:@"duration"];
    [event setBoolValue:YES forKey:@"ad_shown"];
    [analytics trackEvent:event];
    ```

## <a name="set-user-details-for-your-event"></a>Задайте потребителски подробности за вашето събитие

SDK ви позволява да дефинирате потребителска информация, която може да бъде изпратена с всяко събитие. Можете да посочите потребителска информация, като се обадите на `setUser:(nonnull EIUser *)user` API на SDK.

Посочване на потребителски подробности в `Analytics` ниво означава, че всички телеметрии ще разполагат с тази информация. Ако обаче посочите на ниво събитие чрез извикване на `setUser:(nonnull EIUser *)user` API на обекта EIEvent, само това конкретно събитие ще съдържа информацията.

Класът данни `EIUser` съдържа следните свойства на NSString:

- **localId**: Локалният идентификатор на потребителя.
- **authId**: Удостовереният потребителски идентификатор.
- **authType**: Типът на удостоверяване, използван за получаване на удостоверения потребителски идентификатор.
- **име**: Потребителското име.
- **имейл**: Имейл адресът на потребителя.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
