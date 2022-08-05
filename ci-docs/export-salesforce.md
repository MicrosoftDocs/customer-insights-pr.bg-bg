---
title: Експортиране на данни в Marketing Cloud на Salesforce (предварителен преглед)
description: Научете как да конфигурирате връзката и да експортирате в Salesforce Marketing Cloud.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 58e76e51c18c25177f9b4551b70b25b41248b142
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: bg-BG
ms.lasthandoff: 07/27/2022
ms.locfileid: "9197025"
---
# <a name="export-data-to-salesforce-marketing-cloud-preview"></a>Експортиране на данни в Marketing Cloud на Salesforce (предварителен преглед)

Използвайте данните на клиентите си в Salesforce Marketing Cloud, като ги експортирате чрез местоположението на Secure File Transfer Protocol (SFTP).

## <a name="prerequisites"></a>Предварителни изисквания

- [SFTP хост за Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) и съответните администраторски идентификационни данни.

## <a name="set-up-connection-to-salesforce-marketing-cloud"></a>Настройване на връзка с Маркетинг облак на Salesforce

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Отидете на **Администратор** > **Връзки**.

1. Изберете **Добавяне на връзка** и изберете **Маркетинг облак на Salesforce**.

1. Въведете разпознаваемо име за връзката в полето **Показвано име**. Показваното име и типът описват тази връзка. Препоръчваме да изберете име, което обяснява целта на връзката.

1. Изберете кой може да използва тази връзка. По подразбиране това са само администратори. За повече информация вижте [Разрешаване на сътрудници да използват връзка за експортиране](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Предоставете **Потребителско име**, **Парола** и **Име на хост** и **папка за експортиране** за вашия SFTP акаунт.

1. Изберете **Проверка**, за да тествате връзката.

1. Прегледайте поверителността на [данните и съответствието](connections.md#data-privacy-and-compliance) и изберете **Съгласен** съм.

1. Изберете **Записване**, за да завършите връзката.

## <a name="configure-an-export"></a>Конфигуриране на експортиране

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Отидете на **Данни** > **Експортиране**.

1. Изберете **Добавяне на експортиране**.

1. В полето **Връзка за експортиране** изберете връзка от секцията SFTP. Свържете се с администратор, ако няма налична връзка.

1. Въведете име за експортирането.

1. Изберете дали искате да експортирате данните **архивирани** или **разархивирани** и **разделителя на поле** за експортираните файлове.

1. Изберете обектите, например сегменти, които искате да експортирате.

   > [!NOTE]
   > Всеки избран обект ще бъде разделен на максимум пет изходни файла, когато се експортира.

1. Изберете **Записване**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a>Импортиране на данните от Customer Insights от SFTP местоположение в Salesforce Marketing Cloud

1. Създайте [разширения за данни в Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) за да импортирате файла с данни на Customer Insights от SFTP местоположението.

2. [Импортирайте данните от SFTP местоположението](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) в разширението за данни на Salesforce Marketing Cloud.

3. Настройте автоматизацията за импортиране на данните в разширенията за данни. Научете повече за [автоматизиране на падането на файлове и автоматизирани програми](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).

   Определете [автоматизация на падането на файлове](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) или [планирана автоматизация](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).

Ето пример за [автоматизация със SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).

[!INCLUDE [footer-include](includes/footer-banner.md)]
