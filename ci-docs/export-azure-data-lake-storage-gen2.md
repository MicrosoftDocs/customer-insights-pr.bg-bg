---
title: Експортиране на данни в Azure Data Lake Storage Gen2 (визуализация)
description: Научете как да конфигурирате връзката с Azure Data Lake Storage Gen2.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 55a61e4d9166df7809a64aeb1168a730402aaed6
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: bg-BG
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196427"
---
# <a name="export-data-to-azure-data-lake-storage-gen2-preview"></a>Експортиране на данни в Azure Data Lake Storage Gen2 (визуализация)

Съхранявайте данните от Customer Insights в акаунт в Data Lake Storage Gen2 или използвайте хранилището за прехвърляне на данните си в други приложения.

## <a name="prerequisites"></a>Предварителни изисквания

- Акаунт за [съхранение, който да се използва с Azure Data Lake Gen2](/azure/storage/blobs/create-data-lake-storage-account). За да намерите името и ключа на акаунта за съхранение, вижте [Управление на настройките на акаунта за съхранение в портала на Azure](/azure/storage/common/storage-account-manage).
- Контейнер [за](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container) съхранение на блоб в Azure.

## <a name="known-limitations"></a>Известни ограничения

- За Azure Data Lake Storage Gen2 изберете между [Стандартна производителност и Premium производителност tier](/azure/storage/blobs/create-data-lake-storage-account). Ако изберете ниво на производителност Premium, изберете [първокласните блокови блобове като тип акаунт](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-azure-data-lake-storage-gen2"></a>Настройване на връзка с Azure Data Lake Storage Gen2

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Отидете на **Администратор** > **Връзки**.

1. Изберете **Добавяне на връзка** и изберете **Azure данни езеро Gen 2**.

1. Въведете разпознаваемо име за връзката в полето **Показвано име**. Показваното име и типът описват тази връзка. Препоръчваме да изберете име, което обяснява целта на връзката.

1. Изберете кой може да използва тази връзка. По подразбиране това са само администратори. За повече информация вижте [Разрешаване на сътрудници да използват връзка за експортиране](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Въведете **Име на акаунта**, **Ключ на акаунта** и **Контейнер** за вашия Azure Data Lake Storage Gen2.

1. Прегледайте поверителността на [данните и съответствието](connections.md#data-privacy-and-compliance) и изберете **Съгласен** съм.

1. Изберете **Записване**, за да завършите връзката.

## <a name="configure-an-export"></a>Конфигуриране на експортиране

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Отидете на **Данни** > **Експортиране**.

1. Изберете **Добавяне на експортиране**.

1. В полето **Връзка за експортиране** изберете връзка от azure data lake раздел. Свържете се с администратор, ако няма налична връзка.

1. Въведете име за експортирането.

1. Въведете името на папката за място за Azure Data Lake Storage съхранение Gen2.

1. Изберете полето до всеки обект, който искате да експортирате до това местоназначение.

1. Изберете **Записване**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Експортираните данни се съхраняват в контейнера за съхранение на Azure Data Lake Gen 2, който сте конфигурирали.

> [!TIP]
> Експортирането на обекти, които съдържат голямо количество данни, може да доведе до няколко CSV файла в една и съща папка за всеки износ. Разделянето на износа се случва от съображения за производителност, за да се сведе до минимум времето, необходимо за завършването на даден износ.

[!INCLUDE [footer-include](includes/footer-banner.md)]
