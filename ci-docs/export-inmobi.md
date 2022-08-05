---
title: Експортиране на данни от Аналитични данни за клиенти в InMobi
description: Научете как да конфигурирате връзката и да експортирате в InMobi.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ef486ad6786ef01be977f3d6bda69ce8a2b081c7
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: bg-BG
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195875"
---
# <a name="export-customer-insights-data-to-inmobi-preview"></a>Експортиране на данни от Аналитични данни за клиенти в InMobi (предварителен преглед)

Експортирайте списъци със сегменти или други данни от екземпляра [си "Аналитични данни за клиенти" в InMobi](https://www.inmobi.com/).

## <a name="prerequisites"></a>Предварителни изисквания

- [InMobi акаунт](https://www.inmobi.com/) и администраторски идентификационни данни.
- Име на [акаунт](/azure/storage/blobs/create-data-lake-storage-account) за хранилище за blob в Azure и ключ за акаунт. За да намерите името и ключа, вижте [Управление на настройките на акаунта за съхранение в портала на Azure](/azure/storage/common/storage-account-manage).
- [Azure Blob съхранение контейнер](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container) за експортиране на InMobi данни в.
- InMobi ще създаде директна връзка с вашия Blob Storage, и ще конфигурира автоматично импортиране на вашите данни в InMobi. Свържете се с вашия представител на InMobi, за да инициирате процеса.

## <a name="known-limitations"></a>Известни ограничения

- За Хранилище за блоб на Azure изберете между [Стандартна производителност и Premium производителността на подреждане](/azure/storage/blobs/storage-blob-performance-tiers). Ако изберете ниво на производителност Premium, изберете [първокласните блокови блобове като тип акаунт](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-azure-blob-storage"></a>Настройване на връзка към Хранилище за блоб в Azure

[Настройте връзка с вашето хранилище](export-azure-blob-storage.md) за блоб в Azure.

## <a name="configure-an-export"></a>Конфигуриране на експортиране

[Конфигуриране на експортиране](export-azure-blob-storage.md#configure-an-export).

[!INCLUDE [footer-include](includes/footer-banner.md)]
