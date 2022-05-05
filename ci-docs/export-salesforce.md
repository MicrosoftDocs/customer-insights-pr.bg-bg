---
title: Експортирайте данните от Customer Insights в Salesforce Marketing Cloud
description: Научете как да конфигурирате връзката и да експортирате в Salesforce Marketing Cloud.
ms.date: 07/23/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: aaf5c2607099bbfccf7ed75330267da8c3c5fe1b
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: bg-BG
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642424"
---
# <a name="export-segments-and-other-data-to-salesforce-marketing-cloud-preview"></a>Експортиране на сегменти и други данни в Salesforce Marketing Cloud (преглед)

Използвайте данните на клиентите си в Salesforce Marketing Cloud, като ги експортирате чрез местоположението на Secure File Transfer Protocol (SFTP).

## <a name="prerequisites-for-connection"></a>Предварителни изисквания за връзка

- Наличност на SFTP хост и съответни администраторски идентификационни данни. [Как да настроите SFTP местоположения за Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) 

## <a name="set-up-the-connection-to-salesforce-marketing-cloud"></a>Настройте връзката с Salesforce Marketing Cloud

1. Отидете на **Администратор** > **Връзки**.

1. Изберете **Добавете връзка** и изберете **Salesforce Marketing Cloud** за конфигуриране на връзката.

1. Въведете разпознаваемо име за връзката в полето **Показвано име**. Показваното име и типът описват тази връзка. Препоръчваме да изберете име, което обяснява целта на връзката.

1. Изберете кой може да използва тази връзка. Ако не предприемете нищо, по подразбиране ще е Администратори. За повече информация вижте [Разрешаване на сътрудници да използват връзка за експортиране](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Предоставете **Потребителско име**, **Парола** и **Име на хост** и **папка за експортиране** за вашия SFTP акаунт.

1. Изберете **Проверка**, за да тествате връзката.

1. Изберете **Приемам**, за да потвърдите **Поверителност на данните и съответствие**.

1. Изберете **Записване**, за да завършите връзката.

## <a name="configure-an-export"></a>Конфигуриране на експортиране

Можете да конфигурирате това експортиране, ако имате достъп до връзка от този тип. За повече информация вижте [Разрешения, необходими за конфигуриране на експортиране](export-destinations.md#set-up-a-new-export).

1. Отидете на **Данни** > **Експортиране**.

1. За да създадете ново експортиране, изберете **Добавяне на местоназначение**.

1. В полето **Връзка за експортиране** изберете връзка от секцията SFTP. Ако не виждате името на тази секция, няма достъпни за вас връзки от този тип.

1. Изберете дали искате да експортирате данните **архивирани** или **разархивирани** и **разделителя на поле** за експортираните файлове.

1. Изберете обектите, например сегменти, които искате да експортирате.

   > [!NOTE]
   > Всеки избран обект ще се раздели на до пет изходни файла при експортиране. 

1. Изберете **Записване**.

Запазването на експортиране не го изпълнява незабавно.

Експортирането се изпълнява с всяко [планирано обновяване](system.md#schedule-tab). Може също [да експортирате данни при поискване](export-destinations.md#run-exports-on-demand). 

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a>Импортиране на данните от Customer Insights от SFTP местоположение в Salesforce Marketing Cloud

1. Създайте [разширения за данни в Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) за да импортирате файла с данни на Customer Insights от SFTP местоположението.

2. [Импортирайте данните от SFTP местоположението](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) в разширението за данни на Salesforce Marketing Cloud. 

3. Настройте автоматизацията за импортиране на данните в разширенията за данни. Научете повече за [автоматизиране на падането на файлове и автоматизирани програми](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).

   Определете [автоматизация на падането на файлове](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) или [планирана автоматизация](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5). 

Ето пример за [автоматизация със SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).

## <a name="data-privacy-and-compliance"></a>Поверителност и съответствие на данните

Когато активирате Dynamics 365 Customer Insights, за да предавате данни чрез SFTP, разрешавате прехвърляне на данни извън границата за съответствие за Dynamics 365 Customer Insights, включително потенциално чувствителни данни като Лични данни. Microsoft ще прехвърли такива данни по ваше указание, но вие носите отговорност да гарантирате, че местоположението за експортиране отговаря на всички задължения за поверителност или сигурност, които може да имате. За информация посетете [Декларация за поверителност Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Вашият администратор на Dynamics 365 Customer Insights да премахнете това местоназначение за експортиране по всяко време, за да прекратите използването на тази функционалност.

[!INCLUDE [footer-include](includes/footer-banner.md)]
