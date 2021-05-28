---
title: Експортиране на данни от Customer Insights в хранилище за BLOB на Azure
description: Научете как да конфигурирате връзката и да експортирате в хранилище за BLOB на Azure.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3c19dc6d4956a33a5bd3cea706f8a154198d487f
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976121"
---
# <a name="export-segment-list-and-other-data-to-azure-blob-storage-preview"></a><span data-ttu-id="39a99-103">Експортиране на списък със сегменти и други данни в хранилище за BLOB на Azure (преглед)</span><span class="sxs-lookup"><span data-stu-id="39a99-103">Export segment list and other data to Azure Blob Storage (preview)</span></span>

<span data-ttu-id="39a99-104">Съхранявайте данните си от Customer Insights в хранилище за BLOB или го използвайте за прехвърляне на данните ви в други приложения.</span><span class="sxs-lookup"><span data-stu-id="39a99-104">Store your Customer Insights data in a Blob storage or use it to transfer your data to other applications.</span></span>

## <a name="set-up-the-connection-to-blob-storage"></a><span data-ttu-id="39a99-105">Настройване на връзката с хранилище за BLOB</span><span class="sxs-lookup"><span data-stu-id="39a99-105">Set up the connection to Blob storage</span></span>

1. <span data-ttu-id="39a99-106">Отидете на **Администратор** > **Връзки**.</span><span class="sxs-lookup"><span data-stu-id="39a99-106">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="39a99-107">Изберете **Добавяне на връзка** и изберете **хранилище за BLOB на Azure** за конфигуриране на връзката.</span><span class="sxs-lookup"><span data-stu-id="39a99-107">Select **Add connection** and choose **Azure Blob Storage** to configure the connection.</span></span>

1. <span data-ttu-id="39a99-108">Въведете разпознаваемо име за връзката в полето **Показвано име**.</span><span class="sxs-lookup"><span data-stu-id="39a99-108">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="39a99-109">Показваното име и типът описват тази връзка.</span><span class="sxs-lookup"><span data-stu-id="39a99-109">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="39a99-110">Препоръчваме да изберете име, което обяснява целта на връзката.</span><span class="sxs-lookup"><span data-stu-id="39a99-110">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="39a99-111">Изберете кой може да използва тази връзка.</span><span class="sxs-lookup"><span data-stu-id="39a99-111">Choose who can use this connection.</span></span> <span data-ttu-id="39a99-112">Ако не предприемете нищо, по подразбиране ще е Администратори.</span><span class="sxs-lookup"><span data-stu-id="39a99-112">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="39a99-113">За повече информация вижте [Разрешаване на сътрудници да използват връзка за експортиране](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="39a99-113">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="39a99-114">Въведете **Име на акаунт**, **Ключ за акаунт** и **Контейнер** за акаунта в хранилището за BLOB.</span><span class="sxs-lookup"><span data-stu-id="39a99-114">Enter **Account name**, **Account key**, and **Container** for your Blob storage account.</span></span>
    - <span data-ttu-id="39a99-115">За да научите повече за това как да намерите името на акаунта и ключа за акаунта на хранилище за BLOB, вижте [Управление на настройки на акаунт за съхранение в портала на Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="39a99-115">To learn more about how to find the Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>
    - <span data-ttu-id="39a99-116">За да научите как да създадете контейнер, вижте [Създаване на контейнер](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="39a99-116">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="39a99-117">Изберете **Записване**, за да завършите връзката.</span><span class="sxs-lookup"><span data-stu-id="39a99-117">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="39a99-118">Конфигуриране на експортиране</span><span class="sxs-lookup"><span data-stu-id="39a99-118">Configure an export</span></span>

<span data-ttu-id="39a99-119">Можете да конфигурирате това експортиране, ако имате достъп до връзка от този тип.</span><span class="sxs-lookup"><span data-stu-id="39a99-119">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="39a99-120">За повече информация вижте [Разрешения, необходими за конфигуриране на експортиране](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="39a99-120">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="39a99-121">Отидете на **Данни** > **Експортиране**.</span><span class="sxs-lookup"><span data-stu-id="39a99-121">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="39a99-122">За да създадете ново експортиране, изберете **Добавяне на местоназначение**.</span><span class="sxs-lookup"><span data-stu-id="39a99-122">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="39a99-123">В полето **Връзка за експортиране** изберете връзка от секцията на хранилището за BLOB на Azure.</span><span class="sxs-lookup"><span data-stu-id="39a99-123">In the **Connection for export** field, choose a connection from the Azure Blob Storage section.</span></span> <span data-ttu-id="39a99-124">Ако не виждате името на тази секция, няма достъпни за вас връзки от този тип.</span><span class="sxs-lookup"><span data-stu-id="39a99-124">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="39a99-125">Изберете полето до всеки обект, който искате да експортирате до това местоназначение.</span><span class="sxs-lookup"><span data-stu-id="39a99-125">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="39a99-126">Изберете **Записване**.</span><span class="sxs-lookup"><span data-stu-id="39a99-126">Select **Save**.</span></span>

<span data-ttu-id="39a99-127">Запазването на експортиране не го изпълнява незабавно.</span><span class="sxs-lookup"><span data-stu-id="39a99-127">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="39a99-128">Експортирането се изпълнява с всяко [планирано обновяване](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="39a99-128">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span>     
<span data-ttu-id="39a99-129">Може също [да експортирате данни при поискване](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="39a99-129">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

<span data-ttu-id="39a99-130">Експортираните данни се съхраняват в контейнера за хранилище за BLOB, който сте конфигурирали.</span><span class="sxs-lookup"><span data-stu-id="39a99-130">Exported data is stored in the Blob storage container you configured.</span></span> <span data-ttu-id="39a99-131">Следните пътища на папки се създават автоматично в контейнера:</span><span class="sxs-lookup"><span data-stu-id="39a99-131">The following folder paths are automatically created in your container:</span></span>

- <span data-ttu-id="39a99-132">За обекти източници и обекти, генерирани от системата: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span><span class="sxs-lookup"><span data-stu-id="39a99-132">For source entities and entities generated by the system: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span></span>
  - <span data-ttu-id="39a99-133">Пример: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span><span class="sxs-lookup"><span data-stu-id="39a99-133">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span></span>
- <span data-ttu-id="39a99-134">Model.json за експортираните обекти ще е на ниво %ExportDestinationName%</span><span class="sxs-lookup"><span data-stu-id="39a99-134">The model.json for the exported entities will be at the %ExportDestinationName% level</span></span>
  - <span data-ttu-id="39a99-135">Пример: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span><span class="sxs-lookup"><span data-stu-id="39a99-135">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
