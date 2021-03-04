---
title: Експортирайте данни от Customer Insights в хранилище за BLOB на Azure
description: Научете как да конфигурирате връзката към хранилището за BLOB на Azure.
ms.date: 09/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ecacf20365e78ced8859dfa54b1b16cb923c00eb
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269179"
---
# <a name="connector-for-azure-blob-storage-preview"></a>Съединител за хранилище за BLOB на Azure (преглед)

Съхранете данните си на Customer Insights в хранилище за BLOB на Azure или го използвайте, за да прехвърлите данните си в други приложения.

## <a name="configure-the-connector-for-azure-blob-storage"></a>Конфигуриране на конектор за хранилище за BLOB на Azure

1. В статията за аудиторията отидете на **Администратор** > **Експортиране на местоположения**.

1. Под **Хранилище за BLOB на Azure** изберете **Настройка**.

1. Въведете **Име на акаунта**, **Ключ за акаунт** и **Контейнер** за вашия акаунт за хранилище за BLOB на Azure.
    - За да научите повече за това как да намерите името и ключа за акаунта за хранилището за Blob на Azure, вижте [Управление на настройките на акаунта за съхранение в портала на Azure](https://docs.microsoft.com/azure/storage/common/storage-account-manage).
    - За да научите как да създадете контейнер, вижте [Създаване на контейнер](https://docs.microsoft.com/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Въведете разпознаваемо име за местоназначението в полето **Показвано име**.

1. Изберете **Напред**.

1. Изберете полето до всеки обект, който искате да експортирате до това местоназначение.

1. Изберете **Записване**.

Експортираните данни се съхраняват в контейнера за хранилище за BLOB на Azure, който сте конфигурирали. Следните пътища на папки се създават автоматично в контейнера:

- За обекти източници и обекти, генерирани от системата: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`
  - Пример: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`
- Model.json за експортираните обекти ще се намира на ниво %ExportDestinationName%
  - Пример: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

## <a name="export-the-data"></a>Експортиране на данните

Можете да [експортирате данни при поискване](export-destinations.md#export-data-on-demand). Експортирането също ще се изпълнява с всяко [планирано обновяване](system.md#schedule-tab).


[!INCLUDE[footer-include](../includes/footer-banner.md)]