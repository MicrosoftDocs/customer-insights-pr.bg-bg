---
title: Експортиране на сегменти в Dynamics 365 Marketing (визуализация)
description: Научете как да конфигурирате връзката и да експортирате в Dynamics 365 Marketing.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- customerInsights
ms.openlocfilehash: 123b565421a7d096e7341a8f600f91e59aefe8d0
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: bg-BG
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196611"
---
# <a name="export-segments-to-dynamics-365-marketing-preview"></a>Експортиране на сегменти в Dynamics 365 Marketing (визуализация)

Използвайте [сегменти](segments.md), за да генерирате кампании и да се свържете с конкретни групи клиенти с [Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments).

Ако използвате новите възможности на Dynamics 365 Marketing за организиране на пътешествие на клиента в реално време в организация на Dataverse, не е нужно да създавате стандартно експортиране в Dynamics 365 Marketing. Контактите и сегментите от Customer Insights са достъпни директно в Dynamics 365 Marketing след свързване на Маркетингови и Клиентски аналитични данни. Преди да изтриете съществуващия износ, прегледайте документацията [за това как да свържете Клиентските аналитични данни и Dynamics 365 Marketing пътешествие на клиента оркестрация](/dynamics365/marketing/real-time-marketing-ci-profile).

## <a name="prerequisite"></a>Предварително изискване

Записите за контакти трябва да присъстват в Dynamics 365 Marketing, преди да можете да експортирате сегмент от Customer Insights в Marketing. Прочетете повече за това как да поглъщате контакти в [Dynamics 365 Marketing с помощта на Microsoft Dataverse](connect-dataverse-managed-lake.md).

> [!NOTE]
> Експортирането на сегменти от "Аналитични данни за клиенти" в "Маркетинг" няма да създаде нови записи на контакти в екземплярите маркетинг. Записите на контактите от Маркетинг трябва да бъдат вложени в "Аналитични данни за клиенти" и да се използват като източник на данни. Те също трябва да бъдат включени в единния обект на клиента, за да се съпоставят идентификаторите на клиентите с идентификаторите за контакт, преди сегментите да могат да бъдат експортирани.

## <a name="set-up-connection-to-marketing"></a>Настройване на връзка с Marketing

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Отидете на **Администратор** > **Връзки**.

1. Изберете **Добавяне на връзка** и изберете **Dynamics 365 Marketing**.

1. Въведете разпознаваемо име за връзката в полето **Показвано име**. Показваното име и типът описват тази връзка. Препоръчваме да изберете име, което обяснява целта на връзката.

1. Изберете кой може да използва тази връзка. По подразбиране това са само администратори. За повече информация вижте [Разрешаване на сътрудници да използват връзка за експортиране](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Въведете URL адрес на Marketing за вашата организация в полето **Адрес на сървър**.

1. В секцията **Администраторски акаунт на сървъра** изберете **Влизане** и изберете акаунт на Dynamics 365 Marketing.

1. Нанесете полето ИД на контакт в обекта Клиент на ИД на контакт на Dynamics 365.

1. Прегледайте поверителността на [данните и съответствието](connections.md#data-privacy-and-compliance) и изберете **Съгласен** съм.

1. Изберете **Записване**, за да завършите връзката.

## <a name="configure-an-export"></a>Конфигуриране на експортиране

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Отидете на **Данни** > **Експортиране**.

1. Изберете **Добавяне на експортиране**.

1. В полето **Връзка за експортиране** изберете връзка от секцията Dynamics 365 Marketing. Свържете се с администратор, ако няма налична връзка.

1. Въведете име за експортирането.

1. Изберете полето ИД на контакт в обекта Клиент, който отговаря на ИД на контакт на Dynamics 365.

1. Изберете сегментите, които искате да експортирате.

1. Изберете **Записване**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
