---
title: Експортиране на сегменти в Adobe Experience Platform (визуализация)
description: Научете как да използвате сегментите "Аналитични данни за клиенти" в Adobe Experience Platform.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: fcb43e0956c6d1f0ef36b222dd2b718906364244
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: bg-BG
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195277"
---
# <a name="export-segments-to-adobe-experience-platform-preview"></a>Експортиране на сегменти в Adobe Experience Platform (визуализация)

Експортиране на сегменти, които насочват съответните аудитории към Adobe Experience Platform.

:::image type="content" source="media/AEP-flow.png" alt-text="Схема на процеса на стъпките, описани в тази статия.":::

## <a name="prerequisites"></a>Предварителни изисквания

- Adobe Experience Platform Лиценз.
- Adobe Лиценз за Стандарт на кампанията.
- Име на [акаунт](/azure/storage/blobs/create-data-lake-storage-account) за хранилище за blob в Azure и ключ за акаунт. За да намерите името и ключа, вижте [Управление на настройките на акаунта за съхранение в портала на Azure](/azure/storage/common/storage-account-manage).
- Контейнер [за](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container) съхранение на блоб в Azure.

## <a name="campaign-overview"></a>Общ преглед на кампания

За да разберете по-добре как можете да използвате сегменти от Customer Insights in Adobe Experience Platform, нека разгледаме фиктивна примерна кампания.

Да приемем, че вашата компания предлага месечна услуга, базирана на абонамент, на вашите клиенти в САЩ. Искате да идентифицирате клиенти, чиито абонаменти трябва да бъдат подновени през следващите осем дни, но все още не са подновили абонамента си. За да запазите тези клиенти, искате да им изпратите промоционална оферта по имейл, като използвате Adobe Experience Platform.

В този пример искаме да стартираме промоционалната кампания по имейл веднъж. Тази статия не обхваща случая на използване на провеждането на кампанията повече от веднъж.

## <a name="identify-your-target-audience"></a>Идентифицирайте вашата целева аудитория

В нашия сценарий предполагаме, че имейл адресите на клиентите са достъпни в Customer Insights и промоционалните им предпочитания са анализирани, за да се идентифицират членовете на сегмента.

Сегментът [, който сте дефинирали в Customer Insights](segments.md), се нарича **ChurnProneCustomers** и планирате да изпратите на тези клиенти имейл промоцията.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Екранна снимка на страницата със сегменти със създадения сегмент ChurnProneCustomers.":::

Имейлът с оферта, който искате да изпратите, ще съдържа собствено име, фамилно име, и крайната дата на абонамента на клиента. Той информира клиентите за отстъпката, която ще получат, ако подновят абонамента си, преди да приключи.

## <a name="export-your-target-audience"></a>Експортирайте вашата целева аудитория

Ще конфигурираме експортирането от "Аналитични данни за клиенти" в акаунт за хранилище за блоб в Azure.

### <a name="set-up-connection-to-azure-blob-storage"></a>Настройване на връзка към Хранилище за блоб в Azure

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Отидете на **Администратор** > **Връзки**.

1. Изберете **Добавяне на връзка** и изберете **Хранилище за блоб в Azure**.

1. Въведете разпознаваемо име за връзката в полето **Показвано име**. Показваното име и типът описват тази връзка. Препоръчваме да изберете име, което обяснява целта на връзката.

1. Изберете кой може да използва тази връзка. По подразбиране това са само администратори. За повече информация вижте [Разрешаване на сътрудници да използват връзка за експортиране](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Въведете **Име на акаунт**, **Ключ за акаунт** и **Контейнер** за акаунта в хранилището за BLOB, в което искате да експортирате сегмента.  

   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Екранна снимка на конфигурацията на акаунт за съхранение. ":::

1. Прегледайте поверителността на [данните и съответствието](connections.md#data-privacy-and-compliance) и изберете **Съгласен** съм.

1. Изберете **Записване**, за да завършите връзката.

### <a name="configure-an-export"></a>Конфигуриране на експортиране

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Отидете на **Данни** > **Експортиране**.

1. Изберете **Добавяне на експортиране**.

1. В полето **Връзка за експортиране** изберете връзка от секцията на хранилището за BLOB на Azure. Свържете се с администратор, ако няма налична връзка.

1. Въведете име за експортирането.

1. Изберете сегмента, които искате да експортирате. В този пример е така **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Екранна снимка на потребителския интерфейс за избор на сегмент с избрания сегмент ChurnProneCustomers.":::

1. Изберете **Записване**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!NOTE]
> Уверете се, че броят на записите в експортирания сегмент е в рамките на разрешеното ограничение на лиценза за Adobe Campaign Standard.

Експортираните данни се съхраняват в контейнера за съхранение на блоб в Azure, който сте конфигурирали. Следните пътища на папки се създават автоматично в контейнера:

- За обекти източници и обекти, генерирани от системата:  

  *%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*

  Пример: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

- *model.json* за изнесените обекти се намира на нивото *%ExportDestinationName%*.

  Пример: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>Определете модел на данни за опит (XDM) в Adobe Experience Platform

Преди експортираните данни от Customer Insights да могат да се използват в рамките Adobe Experience Platform на, дефинирайте схемата Модел на данни за опит и [конфигурирайте данните за потребителския профил в реално време](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).

Научете [какво е XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) и разберете [основите на състава на схемата](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).

## <a name="import-data-into-adobe-experience-platform"></a>Импортиране на данни в Adobe Experience Platform

Импортирайте подготвените данни за аудиторията от "Аналитични данни за клиенти" в Adobe Experience Platform.

1. [Създаване на връзка](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started) с източник на хранилище за блоб в Azure.

1. [Конфигуриране на поток](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) от данни за пакетна връзка за съхранение в облак, за да импортирате сегментния изход от "Аналитични данни за клиенти" в Adobe Experience Platform.

## <a name="create-an-audience-in-adobe-campaign-standard"></a>Създаване на аудиторията в Adobe Campaign Standard

За да изпратим имейла за тази кампания, ще използваме Adobe Campaign Standard.

1. [Създайте аудитория](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) в Adobe "Стандарт на кампанията", като използвате данните в Adobe Experience Platform.

1. [Използвайте конструктора на сегменти](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) в Adobe Campaign Standard, за да дефинирате аудитория въз основа на данните в Adobe Experience Platform.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Създаване и изпращане на имейла с помощта на Adobe Campaign Standard

Създайте съдържанието на имейла и след това [тествайте и изпратете](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) имейла си.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Примерен имейл с оферта за подновяване от Adobe Campaign Standard.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
