---
title: Експортиране на данни на Customer Insights в Azure Synapse Analytics
description: Научете как да конфигурирате връзката и да експортирате в Azure Synapse Analytics.
ms.date: 04/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 822082d661863e737ea3d3a749a6c878db766967
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 05/04/2021
ms.locfileid: "5977364"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a><span data-ttu-id="778e3-103">Експортиране в Azure Synapse Analytics (преглед)</span><span class="sxs-lookup"><span data-stu-id="778e3-103">Export data to Azure Synapse Analytics (Preview)</span></span>

<span data-ttu-id="778e3-104">Azure Synapse е аналитична услуга, която ускорява времето за вникване в складовете за данни и системите за големи данни.</span><span class="sxs-lookup"><span data-stu-id="778e3-104">Azure Synapse is an analytics service that accelerates time to insight across data warehouses and big data systems.</span></span> <span data-ttu-id="778e3-105">Можете да поглъщате и използвате данните си от Customer Insights в [Azure Synapse](/azure/synapse-analytics/overview-what-is).</span><span class="sxs-lookup"><span data-stu-id="778e3-105">You can ingest and use your Customer Insights data in [Azure Synapse](/azure/synapse-analytics/overview-what-is).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="778e3-106">Предварителни изисквания</span><span class="sxs-lookup"><span data-stu-id="778e3-106">Prerequisites</span></span>

<span data-ttu-id="778e3-107">Следните предпоставки трябва да бъдат изпълнени, за да конфигурирате връзката от Customer Insights към Azure Synapse.</span><span class="sxs-lookup"><span data-stu-id="778e3-107">The following prerequisites must be met to configure the connection from Customer Insights to Azure Synapse.</span></span>

> [!NOTE]
> <span data-ttu-id="778e3-108">Уверете се, че сте задали всички **възлагания на роли** както е описано.</span><span class="sxs-lookup"><span data-stu-id="778e3-108">Make sure to set all **role assignments** as described.</span></span>  

## <a name="prerequisites-in-customer-insights"></a><span data-ttu-id="778e3-109">Предварителни условия в Customer Insights</span><span class="sxs-lookup"><span data-stu-id="778e3-109">Prerequisites in Customer Insights</span></span>

* <span data-ttu-id="778e3-110">Имате роля на **Администратор** в аналитични данни за аудитория.</span><span class="sxs-lookup"><span data-stu-id="778e3-110">You have an **Administrator** role in audience insights.</span></span> <span data-ttu-id="778e3-111">Научете повече за [задаване на потребителски разрешения в статистика за аудиторията](permissions.md#assign-roles-and-permissions)</span><span class="sxs-lookup"><span data-stu-id="778e3-111">Learn more about [setting user permissions in audience insights](permissions.md#assign-roles-and-permissions)</span></span>

<span data-ttu-id="778e3-112">В Azure:</span><span class="sxs-lookup"><span data-stu-id="778e3-112">In Azure:</span></span> 

- <span data-ttu-id="778e3-113">Активен абонамент за Azure.</span><span class="sxs-lookup"><span data-stu-id="778e3-113">An active Azure subscription.</span></span>

- <span data-ttu-id="778e3-114">Ако използвате нов акаунт в Azure Data Lake Storage Gen2, *принципалът на услугата за аналитични данни за аудиторията* има нужда от разрешения **Създател на данни за BLOB за съхранение**.</span><span class="sxs-lookup"><span data-stu-id="778e3-114">If using a new Azure Data Lake Storage Gen2 account, the *service principal for audience insights* needs **Storage Blob Data Contributor** permissions.</span></span> <span data-ttu-id="778e3-115">Научете повече за [свързване към Azure Data Lake Storage Gen2 с принципал на услугата Azure за аналитични данни за аудиторията](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="778e3-115">Learn more on [connecting to an Azure Data Lake Storage Gen2 account with Azure service principal for audience insights](connect-service-principal.md).</span></span> <span data-ttu-id="778e3-116">Data Lake Storage Gen2 **трябва да има** [ йерархично пространство от имена](/azure/storage/blobs/data-lake-storage-namespace) активирано.</span><span class="sxs-lookup"><span data-stu-id="778e3-116">The Data Lake Storage Gen2 **must have** [hierarchical namespace](/azure/storage/blobs/data-lake-storage-namespace) enabled.</span></span>

- <span data-ttu-id="778e3-117">В групата ресурси Azure Synapse се намира работното пространство, *принципал на услугата* и *потребител за аналитични данни за аудиторията* трябва да има присвоени поне разрешения **Читател**.</span><span class="sxs-lookup"><span data-stu-id="778e3-117">On the resource group the Azure Synapse workspace is located, the *service principal* and the *user for audience insights* needs to be assigned at least **Reader** permissions.</span></span> <span data-ttu-id="778e3-118">За повече информация вижте [Присвояване на роли на Azure с помощта на портала на Azure](/azure/role-based-access-control/role-assignments-portal).</span><span class="sxs-lookup"><span data-stu-id="778e3-118">For more information, see [Assign Azure roles using the Azure portal](/azure/role-based-access-control/role-assignments-portal).</span></span>

- <span data-ttu-id="778e3-119">*Потребителят* има нужда от разрешения **Сътрудник на данни за BLOB за съхранение** за акаунт в Azure Data Lake Storage Gen2, където данните се намират и са свързани с Azure Synapse работно пространство.</span><span class="sxs-lookup"><span data-stu-id="778e3-119">The *user* needs **Storage Blob Data Contributor** permissions on the Azure Data Lake Storage Gen2 account where the data is located and linked to the Azure Synapse workspace.</span></span> <span data-ttu-id="778e3-120">Научете повече за [използване на портала на Azure за присвояване на роля на Azure за достъп до данни за BLOB и опашки](/azure/storage/common/storage-auth-aad-rbac-portal) и [Разрешения за съхранение на сътрудник на данни на Blob](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span><span class="sxs-lookup"><span data-stu-id="778e3-120">Learn more about [using the Azure portal to assign an Azure role for access to blob and queue data](/azure/storage/common/storage-auth-aad-rbac-portal) and [Storage Blob Data Contributor permissions](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span></span>

- <span data-ttu-id="778e3-121">*[Самоличността, управлявана от работно пространство на Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)*, има нужда от разрешения **Сътрудник на данни за BLOB за съхранение** за акаунт в Azure Data Lake Storage Gen2, където данните се намират и са свързани с Azure Synapse работно пространство.</span><span class="sxs-lookup"><span data-stu-id="778e3-121">The *[Azure Synapse workspace managed identity](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* needs **Storage Blob Data Contributor** permissions on the Azure Data Lake Storage Gen2 account where the data is located and linked to the Azure Synapse workspace.</span></span> <span data-ttu-id="778e3-122">Научете повече за [използване на портала на Azure за присвояване на роля на Azure за достъп до данни за BLOB и опашки](/azure/storage/common/storage-auth-aad-rbac-portal) и [Разрешения за съхранение на сътрудник на данни на Blob](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span><span class="sxs-lookup"><span data-stu-id="778e3-122">Learn more on [using the Azure portal to assign an Azure role for access to blob and queue data](/azure/storage/common/storage-auth-aad-rbac-portal) and [Storage Blob Data Contributor permissions](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span></span>

- <span data-ttu-id="778e3-123">В работно пространство Azure Synapse, *принципал на услугата за аналитични данни за аудиторията* има нужда от присвоена роля **Администратор на Synapse**.</span><span class="sxs-lookup"><span data-stu-id="778e3-123">On the Azure Synapse workspace, the *service principal for audience insights* needs **Synapse Administrator** role assigned.</span></span> <span data-ttu-id="778e3-124">За повече информация вижте [Как да настроите контрол на достъпа за вашето работно пространство на Synapse](/azure/synapse-analytics/security/how-to-set-up-access-control).</span><span class="sxs-lookup"><span data-stu-id="778e3-124">For more information, see [How to set up access control for your Synapse workspace](/azure/synapse-analytics/security/how-to-set-up-access-control).</span></span>

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a><span data-ttu-id="778e3-125">Настройване на връзката и експортирането в Azure Synapse</span><span class="sxs-lookup"><span data-stu-id="778e3-125">Set up the connection and export to Azure Synapse</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="778e3-126">Конфигуриране на връзка</span><span class="sxs-lookup"><span data-stu-id="778e3-126">Configure a connection</span></span>

1. <span data-ttu-id="778e3-127">Отидете на **Администратор** > **Връзки**.</span><span class="sxs-lookup"><span data-stu-id="778e3-127">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="778e3-128">Изберете **Добавяне на връзка** и изберете **Azure Synapse Analytics** или изберете **Настройка** на плочката **Azure Synapse Analytics**, за да конфигурирате връзката.</span><span class="sxs-lookup"><span data-stu-id="778e3-128">Select **Add connection** and choose **Azure Synapse Analytics** or select the **Set up** on the **Azure Synapse Analytics** tile to configure the connection.</span></span>

1. <span data-ttu-id="778e3-129">Въведете разпознаваемо име за връзката в полето Показвано име.</span><span class="sxs-lookup"><span data-stu-id="778e3-129">Give your connection a recognizable name in the Display name field.</span></span> <span data-ttu-id="778e3-130">Показваното име и типът на връзка описват тази връзка.</span><span class="sxs-lookup"><span data-stu-id="778e3-130">The name and the type of the connection describes this connection.</span></span> <span data-ttu-id="778e3-131">Препоръчваме да изберете име, което обяснява целта на връзката.</span><span class="sxs-lookup"><span data-stu-id="778e3-131">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="778e3-132">Изберете кой може да използва тази връзка.</span><span class="sxs-lookup"><span data-stu-id="778e3-132">Choose who can use this connection.</span></span> <span data-ttu-id="778e3-133">Ако не предприемете нищо, по подразбиране ще е Администратори.</span><span class="sxs-lookup"><span data-stu-id="778e3-133">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="778e3-134">За повече информация вижте [Разрешаване на сътрудници да използват връзка за експортиране](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="778e3-134">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="778e3-135">Изберете или потърсете абонамента, в който искате да използвате данните на Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="778e3-135">Select or search for the subscription you want to use the Customer Insights data in.</span></span> <span data-ttu-id="778e3-136">Веднага след като бъде избран абонамент, можете също да изберете **Работно пространство**, **Акаунт за съхранение** и **Контейнер**.</span><span class="sxs-lookup"><span data-stu-id="778e3-136">As soon as a subscription is selected, you can also select **Workspace**, **Storage account**, and **Container**.</span></span>

1. <span data-ttu-id="778e3-137">Изберете **Записване**, за да запишете връзката.</span><span class="sxs-lookup"><span data-stu-id="778e3-137">Select **Save** to save the connection.</span></span>

### <a name="configure-an-export"></a><span data-ttu-id="778e3-138">Конфигуриране на експортиране</span><span class="sxs-lookup"><span data-stu-id="778e3-138">Configure an export</span></span>

<span data-ttu-id="778e3-139">Можете да конфигурирате това експортиране, ако имате достъп до връзка от този тип.</span><span class="sxs-lookup"><span data-stu-id="778e3-139">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="778e3-140">За повече информация вижте [разрешения, необходими за конфигуриране на експортиране](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="778e3-140">For more information, see [permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="778e3-141">Отидете на **Данни** > **Експортиране**.</span><span class="sxs-lookup"><span data-stu-id="778e3-141">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="778e3-142">За да създадете ново експортиране, изберете **Добавяне на експортиране**.</span><span class="sxs-lookup"><span data-stu-id="778e3-142">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="778e3-143">В полето **Връзка за експортиране** изберете връзка от секцията **Azure Synapse Analytics**.</span><span class="sxs-lookup"><span data-stu-id="778e3-143">In the **Connection for export** field, choose a connection from the **Azure Synapse Analytics** section.</span></span> <span data-ttu-id="778e3-144">Ако не виждате името на тази секция, няма достъпни за вас [връзки](connections.md) от този тип.</span><span class="sxs-lookup"><span data-stu-id="778e3-144">If you don't see this section name, there are no [connections](connections.md) of this type available to you.</span></span>

1. <span data-ttu-id="778e3-145">Осигурете разпознаваем **Показвано име** за вашето експортиране и **Име на базата данни**.</span><span class="sxs-lookup"><span data-stu-id="778e3-145">Provide a recognizable **Display name** for your export and a **Database name**.</span></span>

1. <span data-ttu-id="778e3-146">Изберете към кои обекти искате да експортирате в Azure Synapse Analytics.</span><span class="sxs-lookup"><span data-stu-id="778e3-146">Select which entities you want to export to Azure Synapse Analytics.</span></span>

1. <span data-ttu-id="778e3-147">Изберете **Записване**.</span><span class="sxs-lookup"><span data-stu-id="778e3-147">Select **Save**.</span></span>

<span data-ttu-id="778e3-148">Запазването на експортиране не го изпълнява незабавно.</span><span class="sxs-lookup"><span data-stu-id="778e3-148">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="778e3-149">Експортирането се изпълнява с всяко [планирано обновяване](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="778e3-149">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="778e3-150">Може също [да експортирате данни при поискване](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="778e3-150">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span>

### <a name="update-an-export"></a><span data-ttu-id="778e3-151">Актуализирайте експортиране</span><span class="sxs-lookup"><span data-stu-id="778e3-151">Update an export</span></span>

1. <span data-ttu-id="778e3-152">Отидете на **Данни** > **Експортиране**.</span><span class="sxs-lookup"><span data-stu-id="778e3-152">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="778e3-153">Изберете **Редактиране** в експортирането, което искате да актуализирате.</span><span class="sxs-lookup"><span data-stu-id="778e3-153">Select **Edit** on the export you want to update.</span></span>

   - <span data-ttu-id="778e3-154">**Добавяне** или **Премахване** на обекти от селекцията.</span><span class="sxs-lookup"><span data-stu-id="778e3-154">**Add** or **Remove** entities from the selection.</span></span> <span data-ttu-id="778e3-155">Ако обектите бъдат премахнати от селекцията, те не се изтриват от базата данни Synapse Analytics.</span><span class="sxs-lookup"><span data-stu-id="778e3-155">If entities are removed from the selection, they aren't deleted from the Synapse Analytics database.</span></span> <span data-ttu-id="778e3-156">Въпреки това бъдещите опреснявания на данни няма да актуализират премахнатите обекти в тази база данни.</span><span class="sxs-lookup"><span data-stu-id="778e3-156">However, future data refreshes won't update the removed entities in that database.</span></span>

   - <span data-ttu-id="778e3-157">**Промяна на името на базата данни** създава нова база данни на Synapse Analytics.</span><span class="sxs-lookup"><span data-stu-id="778e3-157">**Changing the Database Name** creates a new Synapse Analytics database.</span></span> <span data-ttu-id="778e3-158">Базата данни с името, което е конфигурирано преди, няма да получава никакви актуализации при бъдещи обновявания.</span><span class="sxs-lookup"><span data-stu-id="778e3-158">The database with the name that was configured before won't receive any updates in future refreshes.</span></span>
