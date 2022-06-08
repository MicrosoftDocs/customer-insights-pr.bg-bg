---
title: Експортирайте данните от Customer Insights в SendGrid
description: Научете как да конфигурирате връзката и да експортирате в SendGrid.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 38dd782fdf06d5970e79e6deb6e8fc94252da585
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: bg-BG
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642381"
---
# <a name="export-segments-to-sendgrid-preview"></a>Експортиране на сегменти в SendGrid (преглед)

Експортирайте сегменти от унифицирани клиентски профили в списъци с контакти на SendGrid и ги използвайте за кампании и маркетинг по имейл в SendGrid. 

## <a name="prerequisites-for-a-connection"></a>Предварителни изисквания за връзка

-   Имате [Акаунт в SendGrid](https://sendgrid.com/) и съответните идентификационни данни на администратора.
-   В SendGrid има съществуващи списъци с контакти и съответните идентификатори. За повече информация вижте [SendGrid – управление на контакти](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).
-   Конфигурирали [сте сегменти](segments.md) в "Аналитични данни за клиенти".
-   Единните клиентски профили в експортираните сегменти съдържат поле, представляващо имейл адрес.

## <a name="known-limitations"></a>Известни ограничения

- До 100 000 потребителски профила общо до SendGrid.
- Експортирането в SendGrid е ограничено до сегменти.
- Експортирането на до 100 000 потребителски профила в SendGrid може да отнеме до няколко часа. 
- Броят на потребителските профили, които можете да експортирате в SendGrid, зависи и е ограничен от вашия договор с SendGrid.

## <a name="set-up-connection-to-sendgrid"></a>Настройване на връзка към SendGrid

1. Отидете на **Администратор** > **Връзки**.

1. Изберете **Добавяне на връзка** и изберете **SendGrid** за конфигуриране на връзката.

1. Въведете разпознаваемо име за връзката в полето **Показвано име**. Показваното име и типът описват тази връзка. Препоръчваме да изберете име, което обяснява целта на връзката.

1. Изберете кой може да използва тази връзка. Ако не предприемете нищо, по подразбиране ще е Администратори. За повече информация вижте [Разрешаване на сътрудници да използват връзка за експортиране](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Въведете своя **API ключ на SendGrid** [API ключ на SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).

1. Изберете **Приемам**, за да потвърдите **Поверителност на данните и съответствие**.

1. Изберете **Свържете** за инициализиране на връзката с SendGrid.

1. Изберете **Добавете себе си като потребител за експортиране** и предоставете вашите идентификационни данни на Customer Insights.

1. Изберете **Записване**, за да завършите връзката.

## <a name="configure-an-export"></a>Конфигуриране на експортиране

Можете да конфигурирате това експортиране, ако имате достъп до връзка от този тип. За повече информация вижте [Разрешения, необходими за конфигуриране на експортиране](export-destinations.md#set-up-a-new-export).

1. Отидете на **Данни** > **Експортиране**.

1. За да създадете ново експортиране, изберете **Добавяне на местоназначение**.

1. В полето **Връзка за експортиране** изберете връзка от секцията SendGrid. Ако не виждате името на тази секция, няма достъпни за вас връзки от този тип.

1. Въведете своя **[ИД на списъка на SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.

1. В **Съвпадение на данните** раздел, в **Имейл** поле, изберете полето, което представлява имейл адреса на клиента. Повторете същите стъпки за други незадължителни полета, като например **собствено име**, **фамилно име**, **Държава/регион**, **Щат**, **Град** и **Пощенски код**.

1. Изберете сегментите, които искате да експортирате. Ние силно **препоръчваме да не експортирате повече от 100 000 потребителски профила общо** към SendGrid. 

1. Изберете **Записване**.

Запазването на експортиране не го изпълнява незабавно.

Експортирането се изпълнява с всяко [планирано обновяване](system.md#schedule-tab). Може също [да експортирате данни при поискване](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Поверителност и съответствие на данните

Когато активирате Dynamics 365 Customer Insights, за да предавате данни на SendGrid, разрешавате прехвърляне на данни извън границата за съответствие за Dynamics 365 Customer Insights, включително потенциално чувствителни данни като Лични данни. Microsoft ще прехвърли такива данни по ваше указание, но вие носите отговорност да гарантирате, че SendGrid отговаря на всички задължения за поверителност или сигурност, които може да имате. За информация посетете [Декларация за поверителност Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Вашият администратор на Dynamics 365 Customer Insights да премахнете това местоназначение за експортиране по всяко време, за да прекратите използването на тази функционалност.


[!INCLUDE [footer-include](includes/footer-banner.md)]