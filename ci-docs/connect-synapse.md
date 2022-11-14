---
title: Свързване на Azure Synapse източник на данни (предварителен преглед)
description: Използвайте база данни в като източник на данни в Azure Synapse Dynamics 365 Customer Insights.
ms.date: 07/26/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 675fd03c44a7a7a492b111895d79c2e77f93a5b5
ms.sourcegitcommit: 4ba74816ebfa46412c64c40a61e1f31c4ccc40f2
ms.translationtype: MT
ms.contentlocale: bg-BG
ms.lasthandoff: 11/03/2022
ms.locfileid: "9738143"
---
# <a name="connect-an-azure-synapse-analytics-data-source-preview"></a>Свързване на Azure Synapse Analytics източник на данни (предварителен преглед)

Azure Synapse Analytics е услуга за корпоративни анализи, която ускорява времето за прозрения в складовете за данни и системите за големи данни. Azure Synapse Analytics обединява най-доброто от SQL технологиите, използвани в корпоративното съхранение на данни, Spark технологиите, използвани за големи данни, Data Explorer за анализ на регистрационни файлове и времеви редове, тръбопроводи за интегриране на данни и ETL / ELT и дълбока интеграция с други услуги на Azure като Power BI, Cosmos DB и AzureML.

За повече информация вижте [Azure Synapse общ преглед](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Предварителни изисквания

> [!NOTE]
> В момента не се поддържат работни области за синапси, които имат [разрешена](/azure/synapse-analytics/security/synapse-workspace-ip-firewall) защитна стена.
> [!IMPORTANT]
> Уверете се, че сте задали всички **възлагания на роли** както е описано.  

**В прозренията на** клиентите:

* Имате администраторска **роля** в "Прозрения за клиентите". Научете повече за потребителските разрешения в "Прозрения за [клиентите](permissions.md#add-users)".

**В Azure**:

- Активен абонамент за Azure.

- Ако използвате нов Azure Data Lake Storage акаунт в Gen2, принципът на *услугата за Customer Insights, който е "Dynamics 365 AI for Customer Insights* ", се нуждае от **разрешения за Storage Blob Data Contributor**. Научете повече за свързването [с доставчик на услуги за Azure Data Lake Storage Customer Insights](connect-service-principal.md). Data Lake Storage Gen2 **трябва да има** [ йерархично пространство от имена](/azure/storage/blobs/data-lake-storage-namespace) активирано.

- В ресурсната група Azure Synapse се намира работната област, принципът *на* услугата, който е "Dynamics 365 AI for Customer Insights" и *потребителят за Customer Insights* трябва да получи поне **разрешения за Reader**. За повече информация вижте [Присвояване на роли на Azure с помощта на портала на Azure](/azure/role-based-access-control/role-assignments-portal).

- *Потребителят* има нужда от разрешения **Сътрудник на данни за BLOB за съхранение** за акаунт в Azure Data Lake Storage Gen2, където данните се намират и са свързани с Azure Synapse работно пространство. Научете повече за [използване на портала на Azure за присвояване на роля на Azure за достъп до данни за BLOB и опашки](/azure/storage/common/storage-auth-aad-rbac-portal) и [Разрешения за съхранение на сътрудник на данни на Blob](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- *[Самоличността, управлявана от работно пространство на Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)*, има нужда от разрешения **Сътрудник на данни за BLOB за съхранение** за акаунт в Azure Data Lake Storage Gen2, където данните се намират и са свързани с Azure Synapse работно пространство. Научете повече за [използване на портала на Azure за присвояване на роля на Azure за достъп до данни за BLOB и опашки](/azure/storage/common/storage-auth-aad-rbac-portal) и [Разрешения за съхранение на сътрудник на данни на Blob](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- В Azure Synapse работната област принципът на услугата за Customer Insights, който е "Dynamics 365 AI for Customer Insights *", се нуждае от* присвоена роля на администратор **на** Synapse. Потребителят **се** нуждае поне от ролята на сътрудник **на** Synapse, присвоена за работната област. За повече информация вижте [Как да настроите контрол на достъпа за вашето работно пространство на Synapse](/azure/synapse-analytics/security/how-to-set-up-access-control).

- Ако вашата среда Customer Insights съхранява данни във вашата [собствена Azure Data Lake Storage](own-data-lake-storage.md), потребителят, който настройва връзката Azure Synapse Analytics, се нуждае поне от вградената **роля Reader** в акаунта за съхранение на данни в Data Lake. За повече информация вижте [Присвояване на роли на Azure с помощта на портала на Azure](/azure/role-based-access-control/role-assignments-portal).

## <a name="connect-to-the-data-lake-database-in-azure-synapse-analytics"></a>Свържете се с базата данни на езерото за данни в Azure Synapse Analytics

1. Отидете на **Данни** > **Източници на данни**.

1. Изберете **Добавяне на източник на данни**.

1. **Azure Synapse Analytics Изберете метода (предварителен преглед).**

   :::image type="content" source="media/data_sources_synapse.png" alt-text="Диалогов прозорец за свързване с данни на Synapse Analytics":::
  
1. **Въведете име** за източник на данни и незадължително **описание**.

1. [Изберете налична връзка](connections.md) или Azure Synapse Analytics [създайте нова](export-azure-synapse-analytics.md#set-up-connection-to-azure-synapse).

1. **Изберете база данни** от работната област, свързана в избраната Azure Synapse Analytics връзка, и изберете **Напред**. В момента поддържаме само базата данни тип *база данни* на езерото.

1. Изберете обектите, които да погълнете от свързаната база данни, и изберете **Напред**.

1. По желание изберете обектите на данните, за да разрешите профилиране на данни.

1. Изберете **Запиши,** за да приложите избора си и да започнете поглъщането на данните от новосъздадената източник на данни, свързана с таблиците на базата данни на езерото в Azure Synapse Analytics. Отваря се страницата Източници **на** данни, показваща новата източник на данни в **състояние Обновяване**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Зареждането на данни може да отнеме време. След успешно обновяване погълнатите данни могат да бъдат прегледани [**от страницата "Обекти**](entities.md) ".

[!INCLUDE [footer-include](includes/footer-banner.md)]
