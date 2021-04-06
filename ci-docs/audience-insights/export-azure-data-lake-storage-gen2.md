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
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="ed9e9-103">Конектор за Azure Data Lake Storage Gen2 (преглед)</span><span class="sxs-lookup"><span data-stu-id="ed9e9-103">Connector for Azure Data Lake Storage Gen2 (preview)</span></span>

<span data-ttu-id="ed9e9-104">Съхранявайте данните си от Customer Insights в Azure Data Lake Storage Gen2 или го използвайте за прехвърляне на данните ви в други приложения.</span><span class="sxs-lookup"><span data-stu-id="ed9e9-104">Store your Customer Insights data in Azure Data Lake Storage Gen2 or use it to transfer your data to other applications.</span></span>

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a><span data-ttu-id="ed9e9-105">Конфигурирайте конектора за Azure Data Lake Storage Gen2</span><span class="sxs-lookup"><span data-stu-id="ed9e9-105">Configure the connector for Azure Data Lake Storage Gen2</span></span>

1. <span data-ttu-id="ed9e9-106">В статията за аудиторията отидете на **Администратор** > **Експортиране на местоположения**.</span><span class="sxs-lookup"><span data-stu-id="ed9e9-106">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="ed9e9-107">Под **Azure Data Lake Storage Gen2** изберете **Настройка**.</span><span class="sxs-lookup"><span data-stu-id="ed9e9-107">Under **Azure Data Lake Storage Gen2**, select **Set up**.</span></span>

1. <span data-ttu-id="ed9e9-108">Въведете разпознаваемо име за местоназначението в полето **Показвано име**.</span><span class="sxs-lookup"><span data-stu-id="ed9e9-108">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="ed9e9-109">Въведете **Име на акаунта**, **Ключ на акаунта** и **Контейнер** за вашия Azure Data Lake Storage Gen2.</span><span class="sxs-lookup"><span data-stu-id="ed9e9-109">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="ed9e9-110">За да научите как да създадете акаунт за съхранение, с който да използвате Azure Data Lake Storage Gen2, вижте [Създайте акаунт за съхранение](/azure/storage/blobs/create-data-lake-storage-account).</span><span class="sxs-lookup"><span data-stu-id="ed9e9-110">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="ed9e9-111">За да научите повече за това как да намерите името и ключа на акаунта за съхранение в Azure Data Lake Gen2, вижте [Управлявайте настройките на акаунта за съхранение в портала на Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="ed9e9-111">To learn more about how to find the Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="ed9e9-112">Изберете **Напред**.</span><span class="sxs-lookup"><span data-stu-id="ed9e9-112">Select **Next**.</span></span>

1. <span data-ttu-id="ed9e9-113">Изберете полето до всеки обект, който искате да експортирате до това местоназначение.</span><span class="sxs-lookup"><span data-stu-id="ed9e9-113">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="ed9e9-114">Изберете **Записване**.</span><span class="sxs-lookup"><span data-stu-id="ed9e9-114">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="ed9e9-115">Експортиране на данните</span><span class="sxs-lookup"><span data-stu-id="ed9e9-115">Export the data</span></span>

<span data-ttu-id="ed9e9-116">Можете да [експортирате данни при поискване](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="ed9e9-116">You can [export data on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="ed9e9-117">Експортирането също ще се изпълнява с всяко [планирано обновяване](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="ed9e9-117">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>