---
title: Свързване на Azure Synapse източник на данни (визуализация)
description: Използвайте база данни в Azure Synapse като източник на данни в Dynamics 365 Customer Insights.
ms.date: 07/26/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 54247fbcdc27f6ed8314e0755164083eb461aa64
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 07/28/2022
ms.locfileid: "9206894"
---
# <a name="connect-an-azure-synapse-analytics-data-source-preview"></a>Свързване на Azure Synapse Analytics източник на данни (визуализация)

Azure Synapse Analytics е услуга за анализ на предприятия, която ускорява времето до прозрения в различните складове за данни и системи за големи информационни масиви. Azure Synapse Analytics обединява най-доброто от SQL технологиите, използвани в складирането на корпоративни данни, Spark технологии, използвани за големи данни, Data Explorer за анализ на регистрационни файлове и времеви серии, Тръбопроводи за интегриране на данни и ETL / ELT, и дълбока интеграция с други услуги на Azure като Power BI, Cosmos DB и AzureML.

За повече информация вижте [Azure Synapse общ преглед](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Предварителни изисквания

> [!IMPORTANT]
> Уверете се, че сте задали всички **възлагания на роли** както е описано.  

**В "Аналитични данни за** клиенти":

* Имате **роля на администратор** в "Аналитични данни за клиенти". Научете повече за [потребителските разрешения в "Аналитични данни за](permissions.md#assign-roles-and-permissions) клиенти".

**В Azure**:

- Активен абонамент за Azure.

- Ако използвате нов Azure Data Lake Storage gen2 акаунт, главницата на *услугата за Customer Insights* се нуждае от **разрешения за съхранение Blob Data Contributor**. Научете повече за [свързването Azure Data Lake Storage с принципал на услугата за "Аналитични данни](connect-service-principal.md) за клиенти". Data Lake Storage Gen2 **трябва да има** [ йерархично пространство от имена](/azure/storage/blobs/data-lake-storage-namespace) активирано.

- В групата Azure Synapse ресурси работната област се намира, главницата *на* услугата и *потребителят за Customer Insights* трябва да бъдат присвоени най-малко **читател** разрешения. За повече информация вижте [Присвояване на роли на Azure с помощта на портала на Azure](/azure/role-based-access-control/role-assignments-portal).

- *Потребителят* има нужда от разрешения **Сътрудник на данни за BLOB за съхранение** за акаунт в Azure Data Lake Storage Gen2, където данните се намират и са свързани с Azure Synapse работно пространство. Научете повече за [използване на портала на Azure за присвояване на роля на Azure за достъп до данни за BLOB и опашки](/azure/storage/common/storage-auth-aad-rbac-portal) и [Разрешения за съхранение на сътрудник на данни на Blob](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- *[Самоличността, управлявана от работно пространство на Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)*, има нужда от разрешения **Сътрудник на данни за BLOB за съхранение** за акаунт в Azure Data Lake Storage Gen2, където данните се намират и са свързани с Azure Synapse работно пространство. Научете повече за [използване на портала на Azure за присвояване на роля на Azure за достъп до данни за BLOB и опашки](/azure/storage/common/storage-auth-aad-rbac-portal) и [Разрешения за съхранение на сътрудник на данни на Blob](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- В Azure Synapse работната област главницата на *услугата за "Аналитични данни* за клиенти" се нуждае от **присвоена роля на Администратор** на синапса. За повече информация вижте [Как да настроите контрол на достъпа за вашето работно пространство на Synapse](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="connect-to-the-data-lake-database-in-azure-synapse-analytics"></a>Свързване с базата данни на езерото с данни в Azure Synapse Analytics

1. Отидете на **Данни** > **Източници на данни**.

1. Изберете **Добавяне на източник на данни**.

1. Изберете **Azure Synapse Analytics метода (Визуализация).**

   :::image type="content" source="media/data_sources_synapse.png" alt-text="Диалогов прозорец за свързване с данни от Синапс анализ":::
  
1. Въведете **Име** за източник на данни и незадължително **Описание**.

1. Изберете [налична връзка към](connections.md)Azure Synapse Analytics или създайте нова.

1. Изберете **База** данни от работната област, свързана в избраната Azure Synapse Analytics връзка, и изберете **Напред**. В момента поддържаме само базата данни тип *Lake база* данни.

1. Изберете обектите, които да се погубят от свързаната база данни, и изберете **Напред**.

1. По желание изберете обектите с данни, на които да разрешите профилиране на данни.

1. Изберете **Запиши**, за да приложите селекцията си и да започнете поглъщането на данните от новосъздадените ви източник на данни, свързани с таблиците с бази данни lake в Azure Synapse Analytics. **Отваря се страницата източници на данни**, показваща новия източник на данни в **състояние "Обновяване**".

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Зареждането на данни може да отнеме време. След успешно обновяване, най-търсените данни могат да бъдат прегледани от [**страницата Обекти**](entities.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
