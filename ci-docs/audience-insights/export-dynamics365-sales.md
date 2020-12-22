---
title: Експортирайте данните от Customer Insights в Dynamics 365 Sales
description: Научете как да конфигурирате връзката към Dynamics 365 Sales.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: af0824e69dfdf620a0ac756e32a9bd3dd85e5151
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643805"
---
# <a name="connector-for-dynamics-365-sales-preview"></a>Конектор за Dynamics 365 Sales (преглед)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Използвайте клиентските данни, за да създавате маркетингови списъци, работни потоци за последващи действия и за да изпращате съобщения за промоции с Dynamics 365 Sales.

## <a name="prerequisite"></a>Предварително изискване

Записи за контакти [от Dynamics 365 Sales, погълнати с помощта на Common Data Service](connect-power-query.md).

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
