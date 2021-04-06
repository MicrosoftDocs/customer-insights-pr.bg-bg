---
title: Експортирайте данните от Customer Insights в Azure Data Lake Storage Gen2
description: Научете как да конфигурирате връзката с Azure Data Lake Storage Gen2.
ms.date: 02/04/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 7c0eef575f745efa6312d7141a6dd96607f9797e
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596624"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a>Конектор за Azure Data Lake Storage Gen2 (преглед)

Съхранявайте данните си от Customer Insights в Azure Data Lake Storage Gen2 или го използвайте за прехвърляне на данните ви в други приложения.

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a>Конфигурирайте конектора за Azure Data Lake Storage Gen2

1. В статията за аудиторията отидете на **Администратор** > **Експортиране на местоположения**.

1. Под **Azure Data Lake Storage Gen2** изберете **Настройка**.

1. Въведете разпознаваемо име за местоназначението в полето **Показвано име**.

1. Въведете **Име на акаунта**, **Ключ на акаунта** и **Контейнер** за вашия Azure Data Lake Storage Gen2.
    - За да научите как да създадете акаунт за съхранение, с който да използвате Azure Data Lake Storage Gen2, вижте [Създайте акаунт за съхранение](/azure/storage/blobs/create-data-lake-storage-account). 
    - За да научите повече за това как да намерите името и ключа на акаунта за съхранение в Azure Data Lake Gen2, вижте [Управлявайте настройките на акаунта за съхранение в портала на Azure](/azure/storage/common/storage-account-manage).

1. Изберете **Напред**.

1. Изберете полето до всеки обект, който искате да експортирате до това местоназначение.

1. Изберете **Записване**.

## <a name="export-the-data"></a>Експортиране на данните

Можете да [експортирате данни при поискване](export-destinations.md#export-data-on-demand). Експортирането също ще се изпълнява с всяко [планирано обновяване](system.md#schedule-tab).