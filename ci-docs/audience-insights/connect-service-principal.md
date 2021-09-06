---
title: Свързване с акаунт на Azure Data Lake Storage с помощта на субект на услуга
description: Използвайте субект на услуга на Azure, за да се свържете с вашето data lake.
ms.date: 07/23/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 845d1f55eb99f2adf9b437124addec4f6d016fec
ms.sourcegitcommit: 1c396394470df8e68c2fafe3106567536ff87194
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 08/30/2021
ms.locfileid: "7461135"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Свързване с акаунт на Azure Data Lake Storage с помощта на субект на услуга на Azure
<!--note from editor: The Cloud Style Guide would have us just use "Azure Data Lake Storage" to mean the current version, unless the old version (Gen1) is mentioned. I've followed this guidance, even though it seems that our docs and Azure docs are all over the map on this.-->
Автоматизираните инструменти, които използват услугите на Azure, винаги трябва да имат ограничени разрешения. Вместо приложенията да влизат като напълно привилегирован потребител, Azure предлага принципали на услуги. Прочетете, за да научите как да свържете Dynamics 365 Customer Insights с акаунт на Azure Data Lake Storage, като използвате субект на услуга на Azure вместо ключове за акаунт за съхранение. 

Можете да използвате субекта на услугата за безопасно [добавяне или редактиране на папка на Common Data Model като източник на данни](connect-common-data-model.md) или за [създаване или актуализиране на среда](get-started-paid.md).<!--note from editor: Suggested. Or it could be ", or create a new environment or update an existing one". I think "new" is implied with "create". The comma is necessary.-->

> [!IMPORTANT]
> - Акаунтът за съхранение на Data Lake, който ще използва<!--note from editor: Suggested. Or perhaps it could be "The Data Lake Storage account to which you want to give access to the service principal..."--> субектът на услугата трябва да има [разрешено йерархично пространство за имена](/azure/storage/blobs/data-lake-storage-namespace).
> - Нуждаете се от администраторски разрешения за вашия абонамент за Azure, за да създадете принципала на услугата.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Създаване на субект на услуга на Azure за Customer Insights

Преди да създадете нов субект на услуга за аналитични данни за аудитория или аналитични данни за ангажираност, проверете дали той вече не съществува в организацията.

### <a name="look-for-an-existing-service-principal"></a>Потърсете съществуващ принципал на услугата

1. Отидете на [Административен портал на Azure](https://portal.azure.com) и влезте във вашата организация.

2. От **Услуги на Azure** изберете **Azure Active Directory**.

3. Под **Управление** изберете **Корпоративни приложения**.

4. Търсене на Microsoft<!--note from editor: Via Microsoft Writing Style Guide.--> ИД на приложение:
   - Аналитични данни за аудитория: `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` с име `Dynamics 365 AI for Customer Insights`
   - Аналитични данни за ангажираност: `ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd` с име `Dynamics 365 AI for Customer Insights engagement insights`

5. Ако намерите съвпадащ запис, това означава, че субектът на услугата вече съществува. 
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Екранна снимка, показваща съществуващ субект на услуга.":::
   
6. Ако не се върнат резултати, създайте нов принципал на услугата.

>[!NOTE]
>За да се възползвате от пълната мощ на Dynamics 365 Customer Insights, предлагаме да добавите и двете приложения към субекта на услугата.<!--note from editor: Using the note format is suggested, just so this doesn't get lost by being tucked up in the step.-->

### <a name="create-a-new-service-principal"></a>Създаване на нова принципал на услуга
<!--note from editor: Some general formatting notes: The MWSG wants bold for text the user enters (in addition to UI strings and the settings users select), but there's plenty of precedent for using code format for entering text in PowerShell so I didn't change that. Note that italic should be used for placeholders, but not much else.-->
1. Инсталирайте най-новата версия на Azure Active Directory PowerShell for Graph. За повече информация отидете на [Инсталиране на Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).

   1. На компютъра изберете клавиша Windows на клавиатурата, потърсете **Windows PowerShell** и изберете **Изпълняване като администратор**.<!--note from editor: Or should this be something like "search for **Windows PowerShell** and, if asked, select **Run as administrator**."?-->
   
   1. В прозореца PowerShell, който се отваря, въведете `Install-Module AzureAD`.

2. Създайте субекта на услугата за Customer Insights с модула на Azure AD PowerShell.

   1. В прозореца PowerShell въведете `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`. Сменете *"[ИД на клиента]"*<!--note from editor: Edit okay? Or should the quotation marks stay in the command line, in which case it would be "Replace *[your tenant ID]* --> с действителния ИД на клиента, където искате да създадете субекта на услугата. Параметърът на име на среда `AzureEnvironmentName` е по избор.
  
   1. Въведете `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Тази команда създава принципа на услугата за прозрения за аудиторията за избрания наемател. 

   1. Въведете `New-AzureADServicePrincipal -AppId "ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd" -DisplayName "Dynamics 365 AI for Customer Insights engagement insights"`. Тази команда създава субекта на услугата за аналитични данни за ангажираност<!--note from editor: Edit okay?--> на избрания клиент.

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Предоставете разрешения на принципала на услугата за достъп до акаунта за съхранение

Отидете на портала на Azure, за да предоставите разрешения на принципала на услугата за акаунта за съхранение, който искате да използвате в статистика за аудиторията.

1. Отидете на [Административен портал на Azure](https://portal.azure.com) и влезте във вашата организация.

1. Отворете акаунта за съхранение, до който искате да има достъп главницата на услугата, за да има прозрения за аудиторията.

1. В левия прозорец изберете **Контрол на достъпа (IAM)**, след което изберете **Добавяне** > **Добавяне на присвояване на роля**.

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Екранна снимка, показваща портала на Azure при добавяне на присвояване на роля.":::

1. В прозореца **Добавяне на присвояване на роля** задайте следните свойства:
   - Роля: **Сътрудник за данни за BLOB за съхранение**
   - Присвояване на достъп до: **Принцип на потребител, група или услуга**
   - Изберете: **Dynamics 365 AI for Customer Insights** и **Аналитични данни за ангажираност на Dynamics 365 AI for Customer Insights** (два [субекта на услуга](#create-a-new-service-principal), които създадохте по-рано в тази процедура)

1.  Изберете **Записване**.

Разпространението на промените може да отнеме до 15 минути.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a>Въведете ИД на ресурса на Azure или подробностите за абонамента за Azure в прикачения файл на акаунта за съхранение към аналитичните данни за аудитория

Можете<!--note from editor: Edit suggested only if this section is optional.--> да прикачите акаунт за съхранение на Data Lake в аналитичните данни за аудитория за [съхраняване на изходни данни](manage-environments.md) или [използване като източник на данни](connect-common-data-service-lake.md). Тази опция ви позволява да избирате между подход, базиран на ресурс или на абонамент. В зависимост от избрания подход, следвайте процедурата в един от следните раздели.<!--note from editor: Suggested.-->

### <a name="resource-based-storage-account-connection"></a>Връзка на акаунт на хранилище, базирана на ресурс

1. Отидете на [Административен портал на Azure](https://portal.azure.com), влезте в абонамента си и отворете акаунта за съхранение.

1. В левия прозорец отидете на **Настройки** > **Свойства**.

1. Копирайте стойността на идентификатора на ресурса на акаунта за съхранение.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Копирайте идентификатора на ресурса на акаунта за съхранение.":::

1. В аналитичните данни за аудитория вмъкнете ИД на ресурса в полето за ресурс, показано на екрана за свързване на акаунт за съхранение.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Въведете информацията за идентификатора на ресурса на акаунта за съхранение.":::   

1. Продължете с останалите стъпки в статистика за аудиторията, за да прикачите акаунта за съхранение.

### <a name="subscription-based-storage-account-connection"></a>Връзка на акаунт на хранилище, базиран на абонамент

1. Отидете на [Административен портал на Azure](https://portal.azure.com), влезте в абонамента си и отворете акаунта за съхранение.

1. В левия прозорец отидете на **Настройки** > **Свойства**.

1. Прегледайте **Абонамент**, **Ресурсна група** и **Име** на акаунта за съхранение, за да сте сигурни, че сте избрали правилните стойности в статистиката за аудиторията.

1. В аналитичните данни за аудитория изберете стойностите за съответните полета, когато прикачвате акаунта за съхранение.

1. Продължете с останалите стъпки в статистика за аудиторията, за да прикачите акаунта за съхранение.


[!INCLUDE[footer-include](../includes/footer-banner.md)]