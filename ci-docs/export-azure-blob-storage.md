---
title: Експортиране на данни в хранилище за блоб на Azure (визуализация)
description: Научете как да конфигурирате връзката и да експортирате в хранилище за BLOB на Azure.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 22593ed05f403a40fe494e30f807b57658594f01
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: bg-BG
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195691"
---
# <a name="export-data-to-an-azure-blob-storage-preview"></a>Експортиране на данни в хранилище за блоб на Azure (визуализация)

Съхранявайте данните си от Customer Insights в хранилище за BLOB или го използвайте за прехвърляне на данните ви в други приложения.

## <a name="prerequisites"></a>Предварителни изисквания

- Име на [акаунт](/azure/storage/blobs/create-data-lake-storage-account) за хранилище за blob в Azure и ключ за акаунт. За да намерите името и ключа, вижте [Управление на настройките на акаунта за съхранение в портала на Azure](/azure/storage/common/storage-account-manage).
- Контейнер [за](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container) съхранение на блоб в Azure.

## <a name="known-limitations"></a>Известни ограничения

- За Хранилище за блоб на Azure изберете между [Стандартна производителност и Premium производителността на подреждане](/azure/storage/blobs/storage-blob-performance-tiers). Ако изберете ниво на производителност Premium, изберете [първокласните блокови блобове като тип акаунт](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-blob-storage"></a>Настройване на връзка към "Съхранение на блоб"

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Отидете на **Администратор** > **Връзки**.

1. Изберете **Добавяне на връзка** и изберете **Хранилище за блоб в Azure**.

1. Въведете разпознаваемо име за връзката в полето **Показвано име**. Показваното име и типът описват тази връзка. Препоръчваме да изберете име, което обяснява целта на връзката.

1. Изберете кой може да използва тази връзка. По подразбиране това са само администратори. За повече информация вижте [Разрешаване на сътрудници да използват връзка за експортиране](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Въведете **Име на акаунт**, **Ключ за акаунт** и **Контейнер** за акаунта в хранилището за BLOB.

1. Прегледайте поверителността на [данните и съответствието](connections.md#data-privacy-and-compliance) и изберете **Съгласен** съм.

1. Изберете **Записване**, за да завършите връзката.

## <a name="configure-an-export"></a>Конфигуриране на експортиране

За да конфигурирате този износ, трябва да имате [разрешение](export-destinations.md#set-up-a-new-export) за този тип връзка.

> [!IMPORTANT]
> Ако сте включили настройката [за](/azure/storage/blobs/soft-delete-blob-enable) меко изтриване за акаунта за хранилище за blob в Azure, експортирането ще е неуспешно. Изключете временното изтриване, за да експортирате данни в BLOB.

1. Отидете на **Данни** > **Експортиране**.

1. Изберете **Добавяне на експортиране**.

1. В полето **Връзка за експортиране** изберете връзка от секцията на хранилището за BLOB на Azure. Свържете се с администратор, ако няма налична връзка.

1. Въведете име за експортирането.

1. Въведете името на папката за хранилището на Blob.

1. Изберете полето до всеки обект, който искате да експортирате до това местоназначение.

1. Изберете **Записване**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Експортираните данни се съхраняват в контейнера за хранилище за BLOB, който сте конфигурирали. Следните пътища на папки се създават автоматично в контейнера:

- За обекти източници и обекти, генерирани от системата:   
  *%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*  

  Пример: Dynamics365CustomerInsights/CustomerInsights_ abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv
  
  > [!TIP]
  > Експортирането на обекти, които съдържат голямо количество данни, може да доведе до няколко CSV файла в една и съща папка за всеки износ. Разделянето на износа се случва от съображения за производителност, за да се сведе до минимум времето, необходимо за завършването на даден износ.

- Моделът.json за изнесените обекти пребивава на *%ExportDestinationName%* ниво.  
  
  Пример: Dynamics365CustomerInsights/CustomerInsights_ abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json

[!INCLUDE [footer-include](includes/footer-banner.md)]
