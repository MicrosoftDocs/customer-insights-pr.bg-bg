---
title: Експортиране на сегменти "Аналитични данни за клиенти" в Adobe "Стандарт за кампания" (визуализация)
description: Научете как да използвате сегментите "Аналитични данни за клиенти" в "Стандарт на Adobe кампанията".
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 834880cac9c5023157983081ff2513d9b051491f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: bg-BG
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195507"
---
# <a name="export-customer-insights-segments-to-adobe-campaign-standard-preview"></a>Експортиране на сегменти "Аналитични данни за клиенти" в Adobe "Стандарт за кампания" (визуализация)

Експортиране на сегменти, които насочват съответните аудитории към Adobe Стандарт на кампанията.

:::image type="content" source="media/ACS-flow.png" alt-text="Схема на процеса на стъпките, описани в тази статия.":::

## <a name="prerequisites"></a>Предварителни изисквания

- Adobe Лиценз за Стандарт на кампанията.
- Име на [акаунт](/azure/storage/blobs/create-data-lake-storage-account) за хранилище за blob в Azure и ключ за акаунт. За да намерите името и ключа, вижте [Управление на настройките на акаунта за съхранение в портала на Azure](/azure/storage/common/storage-account-manage).
- Контейнер [за](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container) съхранение на блоб в Azure.

## <a name="campaign-overview"></a>Общ преглед на кампания

За да разберете по-добре как можете да използвате сегменти от Customer Insights in Adobe Experience Platform, нека разгледаме фиктивна примерна кампания.

Да приемем, че вашата компания предлага месечна услуга, базирана на абонамент, на вашите клиенти в САЩ. Искате да идентифицирате клиенти, чиито абонаменти трябва да бъдат подновени през следващите осем дни, но все още не са подновили абонамента си. За да запазите тези клиенти, искате да им изпратите промоционална оферта по имейл, като използвате Adobe Campaign Standard.

В този пример искаме да стартираме промоционалната кампания по имейл веднъж. Тази статия не обхваща случая на използване на провеждането на кампанията повече от веднъж. Въпреки това, Аналитични данни за клиенти и Adobe Стандарт на кампанията могат да бъдат конфигурирани да работят за повтарящ се сценарий на кампанията също.

## <a name="identify-your-target-audience"></a>Идентифицирайте вашата целева аудитория

В нашия сценарий предполагаме, че имейл адресите на клиентите са достъпни в Customer Insights и промоционалните им предпочитания са анализирани, за да се идентифицират членовете на сегмента.

Сегментът [, който сте дефинирали в Customer Insights](segments.md), се нарича **ChurnProneCustomers** и планирате да изпратите на тези клиенти имейл промоцията.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Екранна снимка на страницата със сегменти със създадения сегмент ChurnProneCustomers.":::

Имейлът с оферта, който искате да изпратите, ще съдържа собствено име, фамилно име, и крайната дата на абонамента на клиента. Той информира клиентите за отстъпката, която ще получат, ако подновят абонамента си, преди да приключи.

## <a name="export-your-target-audience"></a>Експортирайте вашата целева аудитория

### <a name="set-up-connection-to-adobe-campaign"></a>Настройване на връзка с Adobe Кампания

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Отидете на **Администратор** > **Връзки**.

1. Изберете **Добавяне на връзка** и изберете **Adobe Кампания**.

1. Въведете разпознаваемо име за връзката в полето **Показвано име**. Показваното име и типът описват тази връзка. Препоръчваме да изберете име, което обяснява целта на връзката.

1. Изберете кой може да използва тази връзка. По подразбиране това са само администратори. За повече информация вижте [Разрешаване на сътрудници да използват връзка за експортиране](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Въведете името **на** профила, **ключа** Акаунт и **Контейнера** за вашия Blob Storage акаунт.  

   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Екранна снимка на конфигурацията на акаунт за съхранение. ":::

1. Прегледайте поверителността на [данните и съответствието](connections.md#data-privacy-and-compliance) и изберете **Съгласен** съм.

1. Изберете **Записване**, за да завършите връзката.

### <a name="configure-an-export"></a>Конфигуриране на експортиране

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Отидете на **Данни** > **Експортиране**.

1. Изберете **Добавяне на експортиране**.

1. В полето **Връзка за експортиране** изберете връзка от секцията Adobe Campaign. Свържете се с администратор, ако няма налична връзка.

1. Въведете име за експортирането.

1. Изберете сегмента, които искате да експортирате. В този пример е така **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Екранна снимка на потребителския интерфейс за избор на сегмент с избрания сегмент ChurnProneCustomers.":::

1. Изберете **Напред**.

1. Съпоставяне на **полетата Източник** от сегмента "Аналитични данни за клиенти" в имената на **полетата "Цел"** в схемата на профила "Стандарт за Adobe кампания".

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Съпоставяне на полета за конектора Adobe Campaign Standard.":::

   Ако искате да добавите още атрибути, изберете **Добавяне на атрибут**. Целевото име може да бъде различно от името на полето източник, така че все още да можете да нанасяте изход за сегмент от "Аналитични данни Adobe за клиенти" в "Стандарт на кампанията", ако полетата нямат едно и също име в двете системи.

   > [!NOTE]
   > Имейл адресът се използва като поле за самоличност, но можете да използвате всеки друг идентификатор от потребителския профил на клиента, за да съпоставяте данни в Adobe "Стандарт за кампания".

1. Изберете **Записване**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!NOTE]
> Уверете се, че броят на записите в експортирания сегмент е в рамките на разрешеното ограничение на лиценза за Adobe Campaign Standard.

Експортираните данни се съхраняват в контейнера за Хранилище за BLOB на Azure, който сте конфигурирали по-горе. В контейнера ви автоматично се създава следният път до папката: *%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*

Пример: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>Конфигуриране на Adobe Campaign Standard

Експортираните сегменти съдържат колоните, които сте избрали, докато конфигурирате експортирането. Тези данни могат да се използват за [създаване на профили в Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).

За да използвате сегмента в Adobe "Стандарт за кампания", разширете схемата [на профила в](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) "Стандарт на кампанията", Adobe за да включите две допълнителни полета.

В нашия пример тези полета са Име на сегмент и Дата на сегмента. Ще използваме тези полета, за да идентифицираме профилите в Adobe Campaign Standard, към който искаме да насочим тази кампания.

Ако в Campaign Standard няма други записи Adobe, освен това, което ще импортирате, пропуснете тази стъпка.

## <a name="import-data-into-adobe-campaign-standard"></a>Импортиране на данни в Adobe Campaign Standard

Импортирайте подготвените данни за аудиторията от "Аналитични данни за клиенти" в Adobe "Стандарт на кампанията", за да [създадете профили с помощта на работен поток](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences).

Работният поток за импортиране в изображението по-долу е конфигуриран да се изпълнява на всеки осем часа и да търси експортирани сегменти "Аналитични данни за клиенти" (.csv файл в Хранилище за блобове в Azure). Работният поток извлича съдържанието на .csv файл в определен ред на колони. Този работен поток е създаден, за да изпълнява основното обработване на грешки и да гарантира, че всеки запис има имейл адрес, преди да хидратира данните в Adobe Campaign Standard. Работният поток също извлича името на сегмента от името на файла, преди да се добави в данните на профила на Adobe Campaign Standard.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Екранна снимка на работен поток за импортиране в ПИ на Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Извличане на аудиторията в Adobe Campaign Standard

След като данните бъдат импортирани в Adobe Стандарт на кампанията, [създайте работен поток](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) и [заявка](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) към клиентите въз основа на Името на сегмента и Датата на сегмента, за да изберете профили, които са били идентифицирани за примерната ни кампания.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Създаване и изпращане на имейла с помощта на Adobe Campaign Standard

Създайте съдържанието на имейла и след това [тествайте и изпратете](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) имейла си.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Примерен имейл с оферта за подновяване от Adobe Campaign Standard.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
