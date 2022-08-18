---
title: Експортиране на данни в Azure Synapse Analytics (визуализация)
description: Научете как да конфигурирате връзката към Azure Synapse Analytics.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 0e953cfff12df433d033717d58b28c2834468916
ms.sourcegitcommit: 086f75136132d561cd78a4c2cb1e1933e2301f32
ms.translationtype: MT
ms.contentlocale: bg-BG
ms.lasthandoff: 08/11/2022
ms.locfileid: "9259831"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>Експортиране на данни в Azure Synapse Analytics (визуализация)

Azure Synapse е аналитична услуга, която ускорява времето за вникване в складовете за данни и системите за големи данни. Можете да поглъщате и използвате данните си от Customer Insights в [Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Предварителни изисквания

> [!NOTE]
> Уверете се, че сте задали всички **възлагания на роли** както е описано.

- В "Аналитични данни за клиенти" вашият Azure Active Directory (AD) потребителски акаунт трябва да има [роля на Администратор](permissions.md#add-users).

В Azure:

- Активен абонамент за Azure.

- Ако използвате нов Azure Data Lake Storage акаунт gen2, главницата на [услугата за Клиентски аналитични данни](connect-service-principal.md) има **разрешения за съхранение Blob Data Contributor**. Data Lake Storage Gen2 **трябва да има** [ йерархично пространство от имена](/azure/storage/blobs/data-lake-storage-namespace) активирано.

- В групата ресурси, където Azure Synapse се намира работната област, на главницата *на* услугата и *Azure AD на потребителя с администраторски разрешения в "Аналитични данни* за клиенти" трябва да бъдат присвоени **поне** разрешения на [Читателя](/azure/role-based-access-control/role-assignments-portal).

- *Azure AD Потребителят с администраторски разрешения в Customer Insights* има **разрешения за съхранение Blob Data Contributor** на Azure Data Lake Storage gen2 акаунт, където данните се намират и свързани с Azure Synapse работната област. Научете повече за [използване на портала на Azure за присвояване на роля на Azure за достъп до данни за BLOB и опашки](/azure/storage/common/storage-auth-aad-rbac-portal) и [Разрешения за съхранение на сътрудник на данни на Blob](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Управляваната *[Azure Synapse самоличност](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* на работната област има **разрешения за Съхранение на Blob Data Contributor** в Azure Data Lake Storage профила Gen2, където данните се намират и са свързани с Azure Synapse работната област. Научете повече за [използване на портала на Azure за присвояване на роля на Azure за достъп до данни за BLOB и опашки](/azure/storage/common/storage-auth-aad-rbac-portal) и [Разрешения за съхранение на сътрудник на данни на Blob](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- В Azure Synapse работната област главницата на *услугата за "Аналитични данни* за клиенти" има **присвоена** роля на Администратор [на](/azure/synapse-analytics/security/how-to-set-up-access-control) синапса.

- Ако вашата среда на Customer Insights съхранява данните сами по себе [си Azure Data Lake Storage](own-data-lake-storage.md)– потребителят, който настройва връзката, за да се Azure Synapse Analytics нуждае поне от вградената **роля на Reader** в акаунта за съхранение на езерото за данни. За повече информация вижте [Присвояване на роли на Azure с помощта на портала на Azure](/azure/role-based-access-control/role-assignments-portal).

## <a name="set-up-connection-to-azure-synapse"></a>Настройване на връзка към Azure Synapse

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Отидете на **Администратор** > **Връзки**.

1. Изберете **Добавяне на връзка** и изберете **Azure Synapse Analytics**.

1. Въведете разпознаваемо име за връзката в полето **Показвано име**. Показваното име и типът на връзка описват тази връзка. Препоръчваме да изберете име, което обяснява целта на връзката.

1. Изберете кой може да използва тази връзка. По подразбиране това са само администратори. За повече информация вижте [Разрешаване на сътрудници да използват връзка за експортиране](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Изберете или потърсете абонамента, в който искате да използвате данните на Customer Insights. Веднага след като бъде избран абонамент, можете също да изберете **Работно пространство**, **Акаунт за съхранение** и **Контейнер**.

1. Прегледайте поверителността на [данните и съответствието](connections.md#data-privacy-and-compliance) и изберете **Съгласен** съм.

1. Изберете **Записване**, за да завършите връзката.

## <a name="configure-an-export"></a>Конфигуриране на експортиране

[!INCLUDE [export-permission-include](includes/export-permission.md)] За да конфигурирате експортирането със споделена връзка, ви трябват поне **разрешения за сътрудник** в "Аналитични данни за клиенти".

1. Отидете на **Данни** > **Експортиране**.

1. Изберете **Добавяне на експортиране**.

1. В полето **Връзка за експортиране** изберете връзка от секцията Azure Synapse Analytics. Свържете се с администратор, ако няма налична връзка.

1. Осигурете разпознаваем **Показвано име** за вашето експортиране и **Име на базата данни**. Експортирането ще създаде нова [Azure Synapse база](/azure/synapse-analytics/database-designer/concepts-lake-database) данни на езерото в работната област, дефинирана във връзката.

1. Изберете в кои обекти искате да експортирате Azure Synapse Analytics.
   > [!NOTE]
   > Източници на данни, базирани на [папка на Common Data Model](connect-common-data-model.md), не се поддържат.

1. Изберете **Записване**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

За да направите заявка за данни, които са експортирани в Synapse Analytics, имате нужда от **Съхранение Blob Data Reader** достъп до мястото за съхранение на местоназначение в работната област на износа.

## <a name="update-an-export"></a>Актуализирайте експортиране

1. Отидете на **Данни** > **Експортиране**.

1. Изберете **Редактиране** в експортирането, което искате да актуализирате.

   - **Добавяне** или **Премахване** на обекти от селекцията. Ако обектите бъдат премахнати от селекцията, те не се изтриват от базата данни Synapse Analytics. Въпреки това бъдещите опреснявания на данни няма да актуализират премахнатите обекти в тази база данни.

   - **Промяна на името на базата данни** създава нова база данни на Synapse Analytics. Базата данни с името, което е конфигурирано преди, няма да получава никакви актуализации при бъдещи обновявания.

[!INCLUDE [footer-include](includes/footer-banner.md)]
