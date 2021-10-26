---
title: Експортирайте данните от Customer Insights в Azure Data Lake Storage Gen2
description: Научете как да конфигурирате връзката с Azure Data Lake Storage Gen2.
ms.date: 10/06/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 934c396559d4c4be8e640917d2265805753eb62d
ms.sourcegitcommit: 693458e13e4b4d94b6205093559912f6a4dc4a1c
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 10/06/2021
ms.locfileid: "7605890"
---
# <a name="export-segment-list-and-other-data-to-azure-data-lake-storage-gen2-preview"></a>Експортирайте списък със сегменти и други данни в Azure Data Lake Storage Gen2 (преглед)

Съхранявайте данните от Customer Insights в акаунт в Data Lake Storage Gen2 или използвайте хранилището за прехвърляне на данните си в други приложения.

## <a name="known-limitations"></a>Известни ограничения

1. За Azure Data Lake Storage Gen2, между които можете да избирате [Стандартно и първокласно изпълнение](/azure/storage/blobs/create-data-lake-storage-account), когато създавате акаунт за съхранение на вашето езеро с данни. Ако изберете ниво на производителност Premium, изберете първокласните блокови блобове като тип акаунт. 


## <a name="set-up-the-connection-to-azure-data-lake-storage-gen2"></a>Настройване на връзка на Azure Data Lake Storage Gen2 


1. Отидете на **Администратор** > **Връзки**.

1. Изберете **Добавяне на връзка** и изберете **Azure Data Lake Gen 2** за конфигуриране на връзката.

1. Въведете разпознаваемо име за връзката в полето **Показвано име**. Показваното име и типът описват тази връзка. Препоръчваме да изберете име, което обяснява целта на връзката.

1. Изберете кой може да използва тази връзка. Ако не предприемете нищо, по подразбиране ще е Администратори. За повече информация вижте [Разрешаване на сътрудници да използват връзка за експортиране](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Въведете **Име на акаунта**, **Ключ на акаунта** и **Контейнер** за вашия Azure Data Lake Storage Gen2.
    - За да научите как да създадете акаунт за съхранение, с който да използвате Azure Data Lake Storage Gen2, вижте [Създайте акаунт за съхранение](/azure/storage/blobs/create-data-lake-storage-account). 
    - За да научите повече за името на акаунта и ключа за акаунта за съхранение на Azure Data Lake Gen 2, вижте [Управление на настройки на акаунт за съхранение в портала на Azure](/azure/storage/common/storage-account-manage).

1. Изберете **Записване**, за да завършите връзката. 

## <a name="configure-an-export"></a>Конфигуриране на експортиране

Можете да конфигурирате това експортиране, ако имате достъп до връзка от този тип. За повече информация вижте [Разрешения, необходими за конфигуриране на експортиране](export-destinations.md#set-up-a-new-export).

1. Отидете на **Данни** > **Експортиране**.

1. За да създадете ново експортиране, изберете **Добавяне на експортиране**.

1. В полето **Връзка за експортиране** изберете връзка от секцията **Azure Data Lake**. Ако не виждате името на тази секция, няма достъпни за вас връзки от този тип.

1. Изберете полето до всеки обект, който искате да експортирате до това местоназначение.

1. Изберете **Записване**.

Запазването на експортиране не го изпълнява незабавно.

Експортирането се изпълнява с всяко [планирано обновяване](system.md#schedule-tab). Може също [да експортирате данни при поискване](export-destinations.md#run-exports-on-demand). 

Експортираните данни се съхраняват в контейнера за съхранение на Azure Data Lake Gen 2, който сте конфигурирали. 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
