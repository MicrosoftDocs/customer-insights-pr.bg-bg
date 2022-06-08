---
title: Експортиране на данни на Customer Insights в Constant Contact
description: Научете как да конфигурирате връзката и да експортирате в Constant Contact.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 310de0355f71829346f0e35508487e5962d6e912
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: bg-BG
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642408"
---
# <a name="export-segments-to-constant-contact-preview"></a>Експортиране на сегменти в Constant Contact (преглед)

Експортирайте сегменти от унифицирани клиентски профили в Constant Contact и ги използвайте за маркетингови дейности. 

## <a name="prerequisites-for-a-connection"></a>Предварителни изисквания за връзка

-   Имате [акаунт в Constant Contact](https://www.constantcontact.com/account-home) и съответните идентификационни данни на администратор.
-   Конфигурирали [сте сегменти](segments.md) в "Аналитични данни за клиенти".
-   Единните клиентски профили в експортираните сегменти съдържат поле, представляващо имейл адрес.

## <a name="known-limitations"></a>Известни ограничения

- Можете да експортирате до 1 милион потребителски профила на експорт в Constant Contact.
- Експортирането в Constant Contact е ограничено до сегменти.
- Експортирането на до 1 милион потребителски профила в Constant Contact може да отнеме до 1 час. 
- Броят на потребителските профили, които можете да експортирате в Constant Contact, зависи и е ограничен от вашия договор с Constant Contact.

## <a name="set-up-connection-to-constant-contact"></a>Задаване на връзка с Constant Contact

1. Отидете на **Администратор** > **Връзки**.

1. Изберете **Добавяне на връзка** и изберете **Constant Contact** за конфигуриране на връзката.

1. Въведете разпознаваемо име за връзката в полето **Показвано име**. Показваното име и типът описват тази връзка. Препоръчваме да изберете име, което обяснява целта на връзката.

1. Изберете кой може да използва тази връзка. Ако не предприемете нищо, по подразбиране ще е Администратори. За повече информация вижте [Разрешаване на сътрудници да използват връзка за експортиране](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Изберете **Приемам**, за да потвърдите **Поверителност на данните и съответствие**.

1. Изберете **Свързване** за инициализиране на връзката с Constant Contact.

1. Изберете **Удостоверяване с Constant Contact** и въведете идентификационните си данни на администратор за Constant Contact. 

1. Изберете **Добавете себе си като потребител за експортиране** и предоставете вашите идентификационни данни на Customer Insights.

1. Изберете **Записване**, за да завършите връзката.

## <a name="configure-an-export"></a>Конфигуриране на експортиране

Можете да конфигурирате това експортиране, ако имате достъп до връзка от този тип. За повече информация вижте [Разрешения, необходими за конфигуриране на експортиране](export-destinations.md#set-up-a-new-export).

1. Отидете на **Данни** > **Експортиране**.

1. За да създадете ново експортиране, изберете **Добавяне на местоназначение**.

1. В полето **Връзка за експортиране** изберете връзка от секцията Constant Contact. Ако не виждате името на тази секция, няма достъпни за вас връзки от този тип.

1. Въведете [**ИД на списък в Constant Contact**](https://app.constantcontact.com/pages/contacts/ui#lists). Отворете списък в Constant Contact, за да намерите ИД на списъка в URL адреса.

1. В **Съвпадение на данните** раздел, в **Имейл** поле, изберете полето, което представлява имейл адреса на клиента. Необходимо е да експортирате сегменти в Constant Contact.

1. По желание можете да експортирате Собствено име и Фамилно име като допълнителни полета за създаване на по-персонализирани имейли. Изберете **Добавяне на атрибут** за нанасяне на тези полета.

1. Изберете сегментите, които искате да експортирате.

1. Изберете **Записване**.

Запазването на експортиране не го изпълнява незабавно.

Експортирането се изпълнява с всяко [планирано обновяване](system.md#schedule-tab). Може също [да експортирате данни при поискване](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Поверителност и съответствие на данните

Когато активирате Dynamics 365 Customer Insights, за да предавате данни към Constant Contact, разрешавате прехвърляне на данни извън границата на съответствие на Dynamics 365 Customer Insights, включително потенциално чувствителни данни като лични данни. Microsoft ще предава такива данни по ваше разпореждане, но вие носите отговорност да гарантирате, че Constant Contact спазва задълженията за поверителност и сигурност, които може да имате. За информация посетете [Декларация за поверителност Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Вашият администратор на Dynamics 365 Customer Insights да премахнете това местоназначение за експортиране по всяко време, за да прекратите използването на тази функционалност.