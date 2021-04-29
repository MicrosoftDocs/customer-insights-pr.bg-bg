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
ms.openlocfilehash: f431b707e1d65ffe47f8b3aa1c52abaa964e871a
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760038"
---
# <a name="set-up-the-connection-to-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="4a4ea-103">Настройване на връзката с Azure Data Lake Storage Gen2 (преглед)</span><span class="sxs-lookup"><span data-stu-id="4a4ea-103">Set up the connection to Azure Data Lake Storage Gen2 (preview)</span></span>

1. <span data-ttu-id="4a4ea-104">Отидете на **Администратор** > **Връзки**.</span><span class="sxs-lookup"><span data-stu-id="4a4ea-104">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="4a4ea-105">Изберете **Добавяне на връзка** и изберете **Azure Data Lake Gen 2** за конфигуриране на връзката.</span><span class="sxs-lookup"><span data-stu-id="4a4ea-105">Select **Add connection** and choose **Azure Data Lake Gen 2** to configure the connection.</span></span>

1. <span data-ttu-id="4a4ea-106">Въведете разпознаваемо име за връзката в полето **Показвано име**.</span><span class="sxs-lookup"><span data-stu-id="4a4ea-106">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="4a4ea-107">Показваното име и типът описват тази връзка.</span><span class="sxs-lookup"><span data-stu-id="4a4ea-107">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="4a4ea-108">Препоръчваме да изберете име, което обяснява целта на връзката.</span><span class="sxs-lookup"><span data-stu-id="4a4ea-108">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="4a4ea-109">Изберете кой може да използва тази връзка.</span><span class="sxs-lookup"><span data-stu-id="4a4ea-109">Choose who can use this connection.</span></span> <span data-ttu-id="4a4ea-110">Ако не предприемете нищо, по подразбиране ще е Администратори.</span><span class="sxs-lookup"><span data-stu-id="4a4ea-110">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="4a4ea-111">За повече информация вижте [Разрешаване на сътрудници да използват връзка за експортиране](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="4a4ea-111">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="4a4ea-112">Въведете **Име на акаунта**, **Ключ на акаунта** и **Контейнер** за вашия Azure Data Lake Storage Gen2.</span><span class="sxs-lookup"><span data-stu-id="4a4ea-112">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="4a4ea-113">За да научите как да създадете акаунт за съхранение, с който да използвате Azure Data Lake Storage Gen2, вижте [Създайте акаунт за съхранение](/azure/storage/blobs/create-data-lake-storage-account).</span><span class="sxs-lookup"><span data-stu-id="4a4ea-113">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="4a4ea-114">За да научите повече за името на акаунта и ключа за акаунта за съхранение на Azure Data Lake Gen 2, вижте [Управление на настройки на акаунт за съхранение в портала на Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="4a4ea-114">To learn more about Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="4a4ea-115">Изберете **Записване**, за да завършите връзката.</span><span class="sxs-lookup"><span data-stu-id="4a4ea-115">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="4a4ea-116">Конфигуриране на експортиране</span><span class="sxs-lookup"><span data-stu-id="4a4ea-116">Configure an export</span></span>

<span data-ttu-id="4a4ea-117">Можете да конфигурирате това експортиране, ако имате достъп до връзка от този тип.</span><span class="sxs-lookup"><span data-stu-id="4a4ea-117">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="4a4ea-118">За повече информация вижте [Разрешения, необходими за конфигуриране на експортиране](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="4a4ea-118">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="4a4ea-119">Отидете на **Данни** > **Експортиране**.</span><span class="sxs-lookup"><span data-stu-id="4a4ea-119">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="4a4ea-120">За да създадете ново експортиране, изберете **Добавяне на експортиране**.</span><span class="sxs-lookup"><span data-stu-id="4a4ea-120">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="4a4ea-121">В полето **Връзка за експортиране** изберете връзка от секцията **Azure Data Lake**.</span><span class="sxs-lookup"><span data-stu-id="4a4ea-121">In the **Connection for export** field, choose a connection from the **Azure Data Lake** section.</span></span> <span data-ttu-id="4a4ea-122">Ако не виждате името на тази секция, няма достъпни за вас връзки от този тип.</span><span class="sxs-lookup"><span data-stu-id="4a4ea-122">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="4a4ea-123">Изберете полето до всеки обект, който искате да експортирате до това местоназначение.</span><span class="sxs-lookup"><span data-stu-id="4a4ea-123">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="4a4ea-124">Изберете **Записване**.</span><span class="sxs-lookup"><span data-stu-id="4a4ea-124">Select **Save**.</span></span>

<span data-ttu-id="4a4ea-125">Запазването на експортиране не го изпълнява незабавно.</span><span class="sxs-lookup"><span data-stu-id="4a4ea-125">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="4a4ea-126">Експортирането се изпълнява с всяко [планирано обновяване](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="4a4ea-126">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="4a4ea-127">Може също [да експортирате данни при поискване](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="4a4ea-127">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

<span data-ttu-id="4a4ea-128">Експортираните данни се съхраняват в контейнера за съхранение на Azure Data Lake Gen 2, който сте конфигурирали.</span><span class="sxs-lookup"><span data-stu-id="4a4ea-128">Exported data is stored in the Azure Data Lake Gen 2 storage container you configured.</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
