---
title: Експортиране на данни от Customer Insights в хранилище за BLOB на Azure
description: Научете как да конфигурирате връзката и да експортирате в хранилище за BLOB на Azure.
ms.date: 10/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 5ea8e58822e1bb901552ff1de960d5340d340003
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: bg-BG
ms.lasthandoff: 02/16/2022
ms.locfileid: "8231238"
---
# <a name="export-segment-list-and-other-data-to-azure-blob-storage-preview"></a>Експортиране на списък със сегменти и други данни в хранилище за BLOB на Azure (преглед)

Съхранявайте данните си от Customer Insights в хранилище за BLOB или го използвайте за прехвърляне на данните ви в други приложения.

## <a name="known-limitations"></a>Известни ограничения

1. За Azure Blob Storage можете да избирате между [Стандартно и първокласно изпълнение](/azure/storage/blobs/storage-blob-performance-tiers). Ако изберете ниво на производителност Premium, изберете [първокласните блокови блобове като тип акаунт](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-the-connection-to-blob-storage"></a>Настройване на връзката с хранилище за BLOB

1. Отидете на **Администратор** > **Връзки**.

1. Изберете **Добавяне на връзка** и изберете **хранилище за BLOB на Azure** за конфигуриране на връзката.

1. Въведете разпознаваемо име за връзката в полето **Показвано име**. Показваното име и типът описват тази връзка. Препоръчваме да изберете име, което обяснява целта на връзката.

1. Изберете кой може да използва тази връзка. Ако не предприемете нищо, по подразбиране ще е Администратори. За повече информация вижте [Разрешаване на сътрудници да използват връзка за експортиране](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Въведете **Име на акаунт**, **Ключ за акаунт** и **Контейнер** за акаунта в хранилището за BLOB.
    - За да научите повече за това как да намерите името на акаунта и ключа за акаунта на хранилище за BLOB, вижте [Управление на настройки на акаунт за съхранение в портала на Azure](/azure/storage/common/storage-account-manage).
    - За да научите как да създадете контейнер, вижте [Създаване на контейнер](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Изберете **Записване**, за да завършите връзката. 

## <a name="configure-an-export"></a>Конфигуриране на експортиране

Можете да конфигурирате това експортиране, ако имате достъп до връзка от този тип. За повече информация вижте [Разрешения, необходими за конфигуриране на експортиране](export-destinations.md#set-up-a-new-export).

> [!IMPORTANT]
> Ако сте включили настройката за временно изтриване за акаунта за хранилище за BLOB на Azure, експортирането ще е неуспешно. Изключете временното изтриване, за да експортирате данни в BLOB. За повече информация вижте [Активиране на временно изтриване на BLOB](/azure/storage/blobs/soft-delete-blob-enable.md)

1. Отидете на **Данни** > **Експортиране**.

1. За да създадете ново експортиране, изберете **Добавяне на местоназначение**.

1. В полето **Връзка за експортиране** изберете връзка от секцията на хранилището за BLOB на Azure. Ако не виждате името на този раздел, тогава няма налични връзки от този тип.

1. Изберете полето до всеки обект, който искате да експортирате до това местоназначение.

1. Изберете **Записване**.

Запазването на експортиране не го изпълнява незабавно.

Експортирането се изпълнява с всяко [планирано обновяване](system.md#schedule-tab).     

Може също [да експортирате данни при поискване](export-destinations.md#run-exports-on-demand). 

Експортираните данни се съхраняват в контейнера за хранилище за BLOB, който сте конфигурирали. Следните пътища на папки се създават автоматично в контейнера:

- За обекти източници и обекти, генерирани от системата:   
  `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`  
  - Пример: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`
 
- Model.json за експортираните обекти ще е на ниво %ExportDestinationName%.  
  - Пример: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

[!INCLUDE[footer-include](../includes/footer-banner.md)]
