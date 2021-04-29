---
title: Експортирайте данните от Customer Insights в Adobe Experience Platform
description: Научете как се използват сегменти с прозрения за аудиторията в Adobe Experience Platform.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 884f4d30f354bed29909d57be84dce4c8e46965a
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760088"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a>Използване на сегментите Customer Insights в Adobe Experience Platform (преглед)

Като потребител на прозрения за аудиторията за Dynamics 365 Customer Insights, може да сте създали сегменти, за да направите маркетинговите си кампании по-ефективни, като насочите към съответните аудитории. За да използвате сегмент от прозрения за аудиторията в Adobe Experience Platform и приложения като Adobe Campaign Standard, трябва да изпълните няколко стъпки, описани в тази статия.

:::image type="content" source="media/AEP-flow.png" alt-text="Схема на процеса на стъпките, описани в тази статия.":::

## <a name="prerequisites"></a>Предварителни изисквания

-   Лиценз за Dynamics 365 Customer Insights
-   Лиценз за Adobe Experience Platform
-   Лиценз на Adobe Campaign Standard
-   Акаунт в Azure Blob Storage

## <a name="campaign-overview"></a>Общ преглед на кампания

За да разберете по-добре как можете да използвате сегменти от прозрения за аудиторията в Adobe Experience Platform, нека разгледаме фиктивна примерна кампания.

Да приемем, че вашата компания предлага месечна услуга, базирана на абонамент, на вашите клиенти в САЩ. Искате да идентифицирате клиенти, чиито абонаменти трябва да бъдат подновени през следващите осем дни, но все още не са подновили абонамента си. За да задържите тези клиенти, искате да им изпратите промоционална оферта по имейл, използвайки Adobe Experience Platform.

В този пример искаме да стартираме промоционалната кампания по имейл веднъж. Тази статия не обхваща случая на използване на провеждането на кампанията повече от веднъж.

## <a name="identify-your-target-audience"></a>Идентифицирайте вашата целева аудитория

В нашия сценарий предполагаме, че имейл адресите на клиентите са достъпни в статистика за аудиторията и техните промоционални предпочитания са анализирани, за да се идентифицират членовете на сегмента.

[Сегментът, който сте определили в статистика за аудиторията](segments.md) е наречен **ChurnProneCustomers** и планирате да изпратите на тези клиенти промоцията по имейл.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Екранна снимка на страницата със сегменти със създадения сегмент ChurnProneCustomers.":::

Имейлът с оферта, който искате да изпратите, ще съдържа собствено име, фамилно име, и крайната дата на абонамента на клиента. Той информира клиентите за отстъпката, която ще получат, ако подновят абонамента си, преди да приключи.

## <a name="export-your-target-audience"></a>Експортирайте вашата целева аудитория

С идентифицирането на целевата ни аудитория можем да конфигурираме експортирането от статистика за аудиторията в акаунт в Azure Blob Storage.

### <a name="configure-a-connection"></a>Конфигуриране на връзка

1. Отидете на **Администратор** > **Връзки**.

1. Изберете **Добавяне на връзка** и изберете **хранилище за BLOB на Azure** или изберете **Настройка** в плочката **Хранилище за BLOB на Azure**:

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Конфигурационна плочка за Azure Blob Storage."::: за конфигуриране на връзката.

1. Въведете разпознаваемо име за връзката в полето **Показвано име**. Показваното име и типът описват тази връзка. Препоръчваме да изберете име, което обяснява целта на връзката.

1. Изберете кой може да използва тази връзка. Ако не предприемете нищо, по подразбиране ще е Администратори. За повече информация вижте [Разрешаване на сътрудници да използват връзка за експортиране](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Въведете **Име на акаунт**, **Ключ за акаунт** и **Контейнер** за акаунта в хранилището за BLOB, в което искате да експортирате сегмента.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Екранна снимка на конфигурацията на акаунт за съхранение. "::: 
   
    - За да научите повече за това как да намерите името на акаунта и ключа за акаунта на хранилище за BLOB, вижте [Управление на настройки на акаунт за съхранение в портала на Azure](/azure/storage/common/storage-account-manage).
    - За да научите как да създадете контейнер, вижте [Създаване на контейнер](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Изберете **Записване**, за да завършите връзката. 

### <a name="configure-an-export"></a>Конфигуриране на експортиране

Можете да конфигурирате това експортиране, ако имате достъп до връзка от този тип. За повече информация вижте [Разрешения, необходими за конфигуриране на експортиране](export-destinations.md#set-up-a-new-export).

1. Отидете на **Данни** > **Експортиране**.

1. За да създадете ново експортиране, изберете **Добавяне на експортиране**.

1. В полето **Връзка за експортиране** изберете връзка от секцията на хранилището за BLOB на Azure. Ако не виждате името на тази секция, няма достъпни за вас връзки от този тип.

1. Изберете сегмента, които искате да експортирате. В този пример е така **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Екранна снимка на потребителския интерфейс за избор на сегмент с избрания сегмент ChurnProneCustomers.":::

1. Изберете **Записване**.

След като запишете местоназначението за експортиране, ще го намерите на **Данни** > **Експортиране**.

Вече можете да [експортирате сегмента при поискване](export-destinations.md#run-exports-on-demand). Експортирането също ще се изпълнява с всяко [планирано обновяване](system.md).

> [!NOTE]
> Уверете се, че броят на записите в експортирания сегмент е в рамките на разрешеното ограничение от вашия лиценз за Adobe Campaign Standard.

Експортираните данни се съхраняват в контейнера за Azure Blob Storage, който сте конфигурирали по-горе. Следният път на папката се създава автоматично във вашия контейнер:

*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*

Пример: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

*model.json* за изнесените обекти се намира на нивото *%ExportDestinationName%*.

Пример: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>Дефинирайте Experience Data Model (XDM) в Adobe Experience Platform

Преди експортираните данни от статистика за аудиторията да могат да бъдат използвани в рамките на Adobe Experience Platform, трябва да дефинираме схемата на Experience Data Model и да [конфигурирайте данните за потребителския профил в реално време](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).

Научете [какво е XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) и разберете [основите на състава на схемата](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).

## <a name="import-data-into-adobe-experience-platform"></a>Импортирайте данни в Adobe Experience Platform

Сега, когато всичко е на мястото си, трябва да импортираме подготвените данни за аудиторията от статистика за аудиторията в Adobe Experience Platform.

Първо, [създайте източник на връзка на Azure Blob Storage](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).    

След дефиниране на връзката източник, [конфигуриране на поток от данни](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) за пакетна връзка за съхранение в облак за импортиране на изхода на сегмента от прозрения за аудиторията в Adobe Experience Platform.

## <a name="create-an-audience-in-adobe-campaign-standard"></a>Създайте аудитория в Adobe Campaign Standard

За да изпратим имейла за тази кампания, ще използваме Adobe Campaign Standard. След като импортираме данните в Adobe Experience Platform, трябва да [създадете публика](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) в Adobe Campaign Standard, използвайки данните в Adobe Experience Platform.

Научете как да [използвайте конструктор на сегменти](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) в Adobe Campaign Standard за определяне на аудитория въз основа на данните в Adobe Experience Platform.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Създайте и изпратете имейла с помощта на Adobe Campaign Standard

Създайте съдържанието на имейла и след това [тествайте и изпратете](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) имейла си.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Примерен имейл с предложение за подновяване от Adobe Campaign Standard.":::
