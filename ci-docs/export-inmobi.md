---
title: Експортиране на данни от Аналитични данни за клиенти в InMobi
description: Научете как да конфигурирате връзката и да експортирате в InMobi.
ms.date: 06/27/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8261c8adfe231792e70fc85432237cf73d5cd5a7
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: bg-BG
ms.lasthandoff: 06/29/2022
ms.locfileid: "9059604"
---
# <a name="export-segment-list-and-other-data-to-inmobi-preview"></a>Експортиране на списък със сегменти и други данни в InMobi (визуализация)

Експортирайте списъци със сегменти или други данни от екземпляра [си "Аналитични данни за клиенти" в InMobi](https://www.inmobi.com/).

## <a name="prerequisites"></a>Предварителни изисквания

1. Имате [InMobi акаунт](https://www.inmobi.com/) и администраторски идентификационни данни.
1. Имате име на акаунт за съхранение на Azure Blob и съответния ключ на акаунта. За повече информация вижте [Управление на настройките на акаунта за съхранение в портала на Azure](/azure/storage/common/storage-account-manage). В акаунта за съхранение има контейнер, в който да експортирате вMobi данни. За повече информация вижте [Създаване на контейнер](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).
1. InMobi ще създаде директна връзка с вашия Blob Storage, и ще конфигурира автоматично импортиране на вашите данни в InMobi. Свържете се с вашия представител на InMobi, за да инициирате процеса.

## <a name="known-limitations"></a>Известни ограничения

1. За Хранилище за блоб на Azure можете да избирате между [Стандартна производителност и Premium производителността tier](/azure/storage/blobs/storage-blob-performance-tiers). Ако изберете ниво на производителност Premium, изберете [първокласните блокови блобове като тип акаунт](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-the-connection-to-azure-blob-storage-and-configure-an-export"></a>Настройване на връзката към Хранилище за блоб в Azure и конфигуриране на експортиране

1. Следвайте инструкциите, за да [настроите връзка към вашето хранилище](export-azure-blob-storage.md) за blob в Azure.
2. Следвайте инструкциите, за да [конфигурирате експортиране](export-azure-blob-storage.md#configure-an-export).

[!INCLUDE [footer-include](includes/footer-banner.md)]
