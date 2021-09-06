---
title: Експортирайте данните от Customer Insights в Azure Data Lake Storage Gen2
description: Научете как да конфигурирате връзката с Azure Data Lake Storage Gen2.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: c4408e52550b6648e2a001041dc0acdb5063d6a6ef1b8e4bba3321bf25fefcfc
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 08/10/2021
ms.locfileid: "7031966"
---
# <a name="set-up-the-connection-to-azure-data-lake-storage-gen2-preview"></a>Настройване на връзката с Azure Data Lake Storage Gen2 (преглед)

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
