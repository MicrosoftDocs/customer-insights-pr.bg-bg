---
title: Експортирайте данните от Customer Insights в Dynamics 365 Marketing
description: Научете как да конфигурирате връзката към Dynamics 365 Marketing.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 163387779b64bd78ef08e2d96a5f1c9615062f28
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643760"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a>Конектор за Dynamics 365 Marketing (преглед)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Използвайте [сегментите](segments.md), за да генерирате кампании, и се свързвайте с конкретни групи клиенти с Dynamics 365 Marketing. За повече информация вижте [Използване на сегменти от Dynamics 365 Customer Insights с Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)

## <a name="prerequisite"></a>Предварително изискване

Записи за контакти [от Dynamics 365 Marketing, погълнати с помощта на Common Data Service](connect-power-query.md).

## <a name="configure-the-connector-for-marketing"></a>Конфигуриране на конектора за Marketing

1. В статията за аудиторията отидете на **Администратор** > **Експортиране на местоположения**.

1. Под **Dynamics 365 Marketing**, изберете **Настройка**.

1. Въведете разпознаваемо име за местоназначението за експортиране в полето **Показвано име**.

1. Въведете URL адрес на Marketing за вашата организация в полето **Адрес на сървър**.

1. В секцията **Администраторски акаунт на сървъра** изберете **Влизане** и изберете акаунт на Dynamics 365 Marketing.

1. Присвояване на поле за ИД на клиент към ИД за връзка на Dynamics 365.

1. Изберете **Напред**.

1. Изберете един или повече сегменти.

1. Изберете **Записване**.

## <a name="export-the-data"></a>Експортиране на данните

Можете да [експортирате данни при поискване](export-destinations.md). Експортирането също ще се изпълнява с всяко [планирано обновяване](system.md#schedule-tab).
