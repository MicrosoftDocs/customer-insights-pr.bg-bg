---
title: Експортирайте данните от Customer Insights в Dynamics 365 Sales
description: Научете как да конфигурирате връзката към Dynamics 365 Sales.
ms.date: 02/01/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0013c4e6a96401d6cdbea55ed38f85f5e10dcc56
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268995"
---
# <a name="connector-for-dynamics-365-sales-preview"></a>Конектор за Dynamics 365 Sales (преглед)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Използвайте клиентските данни, за да създавате маркетингови списъци, работни потоци за последващи действия и за да изпращате съобщения за промоции с Dynamics 365 Sales.

## <a name="prerequisite"></a>Предварително изискване

1. Записите за контакти трябва да присъстват в Dynamics 365 Sales, преди да можете да експортирате сегмент от Customer Insights в Sales. Прочетете повече за това как да поглъщате контакти в [Dynamics 365 Sales с помощта на Common Data Services](connect-power-query.md).

   > [!NOTE]
   > Експортирането на сегменти от аналитични данни за аудитория в Sales няма да създаде нови записи за контакти в екземпляри на Sales. Записите за контакти от Sales трябва да се поглъщат с прозрения за аудиторията и да се използват като източник на данни. Те също трябва да бъдат включени в единния обект на клиента, за да се съпоставят идентификаторите на клиентите с идентификаторите за контакт, преди сегментите да могат да бъдат експортирани.

## <a name="configure-the-connector-for-sales"></a>Конфигуриране на конектора за Продажби

1. В статията за аудиторията отидете на **Администратор** > **Експортиране на местоположения**.

1. Под **Dynamics 365 Sales**, изберете **Настройка**.

1. Въведете разпознаваемо име за местоназначението за експортиране в полето **Показвано име**.

1. Въведете URL адрес на Продажби за вашата организация в полето **Адрес на сървър**.

1. В секцията **Администраторски акаунт на сървъра** изберете **Влизане** и изберете акаунт на Dynamics 365 Sales.

1. Присвояване на поле за ИД на клиент към ИД за връзка на Dynamics 365.

1. Изберете **Напред**.

1. Изберете един или повече сегменти.

1. Изберете **Записване**.

## <a name="export-the-data"></a>Експортиране на данните

Можете да [експортирате данни при поискване](export-destinations.md). Експортирането също ще се изпълнява с всяко [планирано обновяване](system.md#schedule-tab).


[!INCLUDE[footer-include](../includes/footer-banner.md)]