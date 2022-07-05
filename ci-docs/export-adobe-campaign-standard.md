---
title: Експортиране на сегменти "Аналитични данни за клиенти" в Adobe "Стандарт за кампания" (визуализация)
description: Научете как да използвате сегментите "Аналитични данни за клиенти" в "Стандарт на Adobe кампанията".
ms.date: 03/29/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 9915591cd969bf825f5d1669de43ed4f9953f898
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: bg-BG
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082338"
---
# <a name="export-customer-insights-segments-to-adobe-campaign-standard-preview"></a>Експортиране на сегменти "Аналитични данни за клиенти" в Adobe "Стандарт за кампания" (визуализация)

Като потребител на Dynamics 365 Customer Insights, може да сте създали сегменти, за да направите маркетинговите си кампании по-ефективни, като насочвате към съответните аудитории. За да използвате сегмент от Customer Insights в Adobe Experience Platform и приложения като Adobe Campaign Standard, трябва да следвате няколко стъпки, очертани в тази статия.

:::image type="content" source="media/ACS-flow.png" alt-text="Схема на процеса на стъпките, описани в тази статия.":::

## <a name="prerequisites"></a>Предварителни изисквания

- Лиценз за Dynamics 365 Customer Insights
- Лиценз за Adobe Campaign Standard
- Акаунт в Azure Blob Storage

## <a name="campaign-overview"></a>Общ преглед на кампания

За да разберете по-добре как можете да използвате сегменти от Customer Insights in Adobe Experience Platform, нека разгледаме фиктивна примерна кампания.

Да приемем, че вашата компания предлага месечна услуга, базирана на абонамент, на вашите клиенти в САЩ. Искате да идентифицирате клиенти, чиито абонаменти трябва да бъдат подновени през следващите осем дни, но все още не са подновили абонамента си. За да запазите тези клиенти, искате да им изпратите промоционална оферта по имейл, като използвате Adobe Campaign Standard.

В този пример искаме да стартираме промоционалната кампания по имейл веднъж. Тази статия не обхваща случая на използване на провеждането на кампанията повече от веднъж. Въпреки това, Аналитични данни за клиенти и Adobe Стандарт на кампанията могат да бъдат конфигурирани да работят за повтарящ се сценарий на кампанията също.

## <a name="identify-your-target-audience"></a>Идентифицирайте вашата целева аудитория

В нашия сценарий предполагаме, че имейл адресите на клиентите са налични в и техните промоционални предпочитания са анализирани, за да се идентифицират членовете на сегмента.

Сегментът [, който сте дефинирали в Customer Insights](segments.md), се нарича **ChurnProneCustomers** и планирате да изпратите на тези клиенти имейл промоцията.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Екранна снимка на страницата със сегменти със създадения сегмент ChurnProneCustomers.":::

Имейлът с оферта, който искате да изпратите, ще съдържа собствено име, фамилно име, и крайната дата на абонамента на клиента. Той информира клиентите за отстъпката, която ще получат, ако подновят абонамента си, преди да приключи.

## <a name="export-your-target-audience"></a>Експортирайте вашата целева аудитория

### <a name="configure-a-connection"></a>Конфигуриране на връзка

С установената ни целева аудитория можем да конфигурираме експортирането в акаунт в Хранилище за блоб в Azure.

1. В "Аналитични данни за клиенти" отидете **на Администраторски** > **връзки**.

1. Изберете **Добавяне на връзка** и след това **Adobe Campaign**, за да конфигурирате връзката, или изберете **Настройка** в плочката **Adobe Campaign**.

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Конфигурационна плочка за Adobe Campaign Standard.":::

1. Въведете разпознаваемо име за връзката в полето **Показвано име**. Показваното име и типът описват тази връзка. Препоръчваме да изберете име, което обяснява целта на връзката.

1. Изберете кой може да използва тази връзка. Ако не предприемете нищо, по подразбиране ще е Администратори. За повече информация вижте [Разрешения, необходими за конфигуриране на експортиране](export-destinations.md#set-up-a-new-export).

1. Въведете **Име на акаунт**, **Ключ за акаунт** и **Контейнер** на акаунта в хранилището за BLOB на Azure, в което искате да експортирате сегмента.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Екранна снимка на конфигурацията на акаунт за съхранение. "::: 

   - За да научите повече за това как да намерите името и ключа за акаунта за хранилището за Blob на Azure, вижте [Управление на настройките на акаунта за съхранение в портала на Azure](/azure/storage/common/storage-account-manage).

   - За да научите как да създадете контейнер, вижте [Създаване на контейнер](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Изберете **Записване**, за да завършите връзката.

### <a name="configure-an-export"></a>Конфигуриране на експортиране

Можете да конфигурирате това експортиране, ако имате достъп до връзка от този тип. За повече информация вижте [Разрешения, необходими за конфигуриране на експортиране](export-destinations.md#set-up-a-new-export).

1. Отидете на **Данни** > **Експортиране**.

1. За да създадете ново експортиране, изберете **Добавяне на експортиране**.

1. В полето **Връзка за експортиране** изберете връзка от секцията Adobe Campaign. Ако не виждате името на този раздел, тогава няма налични връзки от този тип.

1. Изберете сегмента, които искате да експортирате. В този пример е така **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Екранна снимка на потребителския интерфейс за избор на сегмент с избрания сегмент ChurnProneCustomers.":::

1. Изберете **Напред**.

1. Сега съпоставяме **полетата Източник** от сегмента "Аналитични данни за клиенти" в имената на **полетата "Цел"** в схемата на профила "Стандарт на кампанията Adobe ".

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Съпоставяне на полета за конектора Adobe Campaign Standard.":::

   Ако искате да добавите още атрибути, изберете **Добавяне на атрибут**. Целевото име може да бъде различно от името на полето източник, така че все още да можете да нанасяте изход за сегмент от "Аналитични данни Adobe за клиенти" в "Стандарт на кампанията", ако полетата нямат едно и също име в двете системи.

   > [!NOTE]
   > Имейл адресът се използва като поле за самоличност, но можете да използвате всеки друг идентификатор от потребителския профил на клиента, за да съпоставяте данни в Adobe "Стандарт за кампания".

1. Изберете **Записване**.

След като запишете местоназначението за експортиране, ще го намерите на **Данни** > **Експортиране**.

Вече можете да [експортирате сегмента при поискване](export-destinations.md#run-exports-on-demand). Експортирането също ще се изпълнява с всяко [планирано обновяване](system.md).

> [!NOTE]
> Уверете се, че броят на записите в експортирания сегмент е в рамките на разрешеното ограничение на лиценза за Adobe Campaign Standard.

Експортираните данни се съхраняват в контейнера за Хранилище за BLOB на Azure, който сте конфигурирали по-горе. Следният път на папката се създава автоматично във вашия контейнер:

*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*

Пример: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>Конфигуриране на Adobe Campaign Standard

Експортираните сегменти съдържат колоните, които сте избрали, докато дефинирате местоназначението за експортиране в предишната стъпка. Тези данни могат да се използват за [създаване на профили в Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).

За да използвате сегмента в Adobe Campaign Standard, трябва да разширим схемата на профила в Adobe Campaign Standard, за да включва две допълнителни полета. Научете как [да разширите ресурса на профила](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) с нови полета в Adobe Campaign Standard.

В нашия пример тези полета са *Име на сегмента и Дата на сегмента (по избор)*.

Ще използваме тези полета, за да идентифицираме профилите в Adobe Campaign Standard, към който искаме да насочим тази кампания.

Ако няма други записи в Adobe Campaign Standard, освен този, който ще импортирате, можете да пропуснете тази стъпка.

## <a name="import-data-into-adobe-campaign-standard"></a>Импортиране на данни в Adobe Campaign Standard

Сега, когато всичко е на място, трябва да импортираме подготвените данни за аудиторията от Customer Insights в Adobe Campaign Standard, за да създадем профили. Научете [как да импортирате профили в Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) с помощта на работен поток.

Работният поток за импортиране в изображението по-долу е конфигуриран да се изпълнява на всеки осем часа и да търси експортирани сегменти "Аналитични данни за клиенти" (.csv файл в Хранилище за блобове в Azure). Работният поток извлича съдържанието на .csv файл в определен ред на колони. Този работен поток е създаден, за да изпълнява основното обработване на грешки и да гарантира, че всеки запис има имейл адрес, преди да хидратира данните в Adobe Campaign Standard. Работният поток също извлича името на сегмента от името на файла, преди да се добави в данните на профила на Adobe Campaign Standard.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Екранна снимка на работен поток за импортиране в ПИ на Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Извличане на аудиторията в Adobe Campaign Standard

След като данните бъдат импортирани в Adobe Campaign Standard, [може да създадете работен поток](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) и [да отправите заявка](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) към клиентите въз основа на *Име на сегмента* и *Дата на сегмента*, за да изберете профили, идентифицирани за нашата примерна кампания.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Създаване и изпращане на имейла с помощта на Adobe Campaign Standard

Създайте съдържанието на имейла и след това [тествайте и изпратете](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) имейла си.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Примерен имейл с оферта за подновяване от Adobe Campaign Standard.":::
