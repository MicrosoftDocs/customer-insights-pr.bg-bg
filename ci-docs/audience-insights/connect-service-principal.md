---
title: Свържете се с акаунт в Azure Data Lake Storage Gen2 с принципал на услугата
description: използвайте принципа на услугата Azure за прозрения за аудиторията, за да се свържете със собственото си езеро с данни, когато го прикачите към прозрения за аудиторията.
ms.date: 11/24/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: c2fae278d34fa02b9168ac70dfa8dd351653245e
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644075"
---
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a><span data-ttu-id="12d69-103">Свържете се с акаунт в Azure Data Lake Storage Gen2 с принципал на услуга Azure за аналитични данни за аудиторията</span><span class="sxs-lookup"><span data-stu-id="12d69-103">Connect to an Azure Data Lake Storage Gen2 account with an Azure service principal for audience insights</span></span>

<span data-ttu-id="12d69-104">Автоматизираните инструменти, които използват услугите на Azure, винаги трябва да имат ограничени разрешения.</span><span class="sxs-lookup"><span data-stu-id="12d69-104">Automated tools that use Azure services should always have restricted permissions.</span></span> <span data-ttu-id="12d69-105">Вместо приложенията да влизат като напълно привилегирован потребител, Azure предлага принципали на услуги.</span><span class="sxs-lookup"><span data-stu-id="12d69-105">Instead of having applications sign in as a fully privileged user, Azure offers service principals.</span></span> <span data-ttu-id="12d69-106">Прочетете, за да научите как да свържете прозренията на аудиторията с акаунт в Azure Data Lake Storage Gen2, използващ принципал на услугата Azure вместо ключове на акаунта за съхранение.</span><span class="sxs-lookup"><span data-stu-id="12d69-106">Read on to learn how to connect audience insights with an Azure Data Lake Storage Gen2 account using an Azure service principal instead of storage account keys.</span></span> 

<span data-ttu-id="12d69-107">Можете да използвате принципала на услугата за сигурно [добавяне или редактиране на папката Common Data Model като източник на данни](connect-common-data-model.md) или [създайте нова или актуализирайте съществуваща среда](manage-environments.md#create-an-environment-in-an-existing-organization).</span><span class="sxs-lookup"><span data-stu-id="12d69-107">You can use the service principal to securely [add or edit a Common Data Model folder as a data source](connect-common-data-model.md) or [create a new or update an existing environment](manage-environments.md#create-an-environment-in-an-existing-organization).</span></span>

<span data-ttu-id="12d69-108">Нуждаете се от администраторски разрешения за вашия абонамент за Azure, за да създадете принципала на услугата.</span><span class="sxs-lookup"><span data-stu-id="12d69-108">You need admin permissions for your Azure subscription to create the service principal.</span></span>

## <a name="create-azure-service-principal-for-audience-insights"></a><span data-ttu-id="12d69-109">Създайте принципа на услугата Azure за прозрения за аудиторията</span><span class="sxs-lookup"><span data-stu-id="12d69-109">Create Azure service principal for audience insights</span></span>

<span data-ttu-id="12d69-110">Преди да създадете нов принцип на услугата за прозрения за аудиторията, проверете дали той вече съществува във вашата организация.</span><span class="sxs-lookup"><span data-stu-id="12d69-110">Before creating a new service principal for audience insights, check if it already exists in your organization.</span></span>

### <a name="look-for-an-existing-service-principal"></a><span data-ttu-id="12d69-111">Потърсете съществуващ принципал на услугата</span><span class="sxs-lookup"><span data-stu-id="12d69-111">Look for an existing service principal</span></span>

1. <span data-ttu-id="12d69-112">Отидете на [Административен портал на Azure](https://portal.azure.com) и влезте във вашата организация.</span><span class="sxs-lookup"><span data-stu-id="12d69-112">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

2. <span data-ttu-id="12d69-113">Изберете **Azure Active Directory** от услугите на Azure.</span><span class="sxs-lookup"><span data-stu-id="12d69-113">Select **Azure Active Directory** from the Azure services.</span></span>

3. <span data-ttu-id="12d69-114">Под **Управление** изберете **Корпоративни приложения**.</span><span class="sxs-lookup"><span data-stu-id="12d69-114">Under **Manage**, select **Enterprise Applications**.</span></span>

4. <span data-ttu-id="12d69-115">Потърсете прозрения за аудиторията на идентификатор на първоначално приложение `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` или името `Dynamics 365 AI for Customer Insights`.</span><span class="sxs-lookup"><span data-stu-id="12d69-115">Search for the audience insights first party application ID `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` or the name `Dynamics 365 AI for Customer Insights`.</span></span>

5. <span data-ttu-id="12d69-116">Ако намерите съвпадащ запис, това означава, че съществува принципа на услугата за прозрения за аудиторията.</span><span class="sxs-lookup"><span data-stu-id="12d69-116">If you find a matching record, it means that the service principal for audience insights exists.</span></span> <span data-ttu-id="12d69-117">Не е необходимо да създавате повторно.</span><span class="sxs-lookup"><span data-stu-id="12d69-117">You don't need to create it again.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Снимка на екрана, показваща съществуващия принципал на услугата.":::
   
6. <span data-ttu-id="12d69-119">Ако не се върнат резултати, създайте нов принципал на услугата.</span><span class="sxs-lookup"><span data-stu-id="12d69-119">If no results are returned, create a new service principal.</span></span>

### <a name="create-a-new-service-principal"></a><span data-ttu-id="12d69-120">Създаване на нова принципал на услуга</span><span class="sxs-lookup"><span data-stu-id="12d69-120">Create a new service principal</span></span>

1. <span data-ttu-id="12d69-121">Инсталирайте най-новата версия на **Azure Active Directory PowerShell за графика**.</span><span class="sxs-lookup"><span data-stu-id="12d69-121">Install the latest version of the **Azure Active Directory PowerShell for Graph**.</span></span> <span data-ttu-id="12d69-122">За повече информация вижте [Инсталиране на Azure Active Directory PowerShell за графика](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span><span class="sxs-lookup"><span data-stu-id="12d69-122">For more information, see [Install Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span></span>
   - <span data-ttu-id="12d69-123">На вашия компютър изберете клавиша Windows на клавиатурата и потърсете **Windows PowerShell** и **Изпълни като администратор**.</span><span class="sxs-lookup"><span data-stu-id="12d69-123">On your PC, select the Windows key on your keyboard and search for **Windows PowerShell** and **Run as Administrator**.</span></span>
   
   - <span data-ttu-id="12d69-124">В прозореца PowerShell, който се отваря, въведете `Install-Module AzureAD`.</span><span class="sxs-lookup"><span data-stu-id="12d69-124">In the PowerShell window that opens, enter `Install-Module AzureAD`.</span></span>

2. <span data-ttu-id="12d69-125">Създайте принципа на услугата за прозрения за аудиторията с Azure AD Модул PowerShell.</span><span class="sxs-lookup"><span data-stu-id="12d69-125">Create the  service principal for audience insights with the Azure AD PowerShell Module.</span></span>
   - <span data-ttu-id="12d69-126">В прозореца PowerShell въведете `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span><span class="sxs-lookup"><span data-stu-id="12d69-126">In the PowerShell window, enter `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span></span> <span data-ttu-id="12d69-127">Заменете "вашия идентификатор на наемател" с действителния идентификатор на наемателя, където искате да създадете принципала на услугата.</span><span class="sxs-lookup"><span data-stu-id="12d69-127">Replace “your tenant ID” with the actual ID of your tenant where you want to create the service principal.</span></span> <span data-ttu-id="12d69-128">Параметърът на име на среда `AzureEnvironmentName` е опционален.</span><span class="sxs-lookup"><span data-stu-id="12d69-128">The environment name parameter `AzureEnvironmentName` is optional.</span></span>
  
   - <span data-ttu-id="12d69-129">Въведете `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span><span class="sxs-lookup"><span data-stu-id="12d69-129">Enter `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span></span> <span data-ttu-id="12d69-130">Тази команда създава принципа на услугата за прозрения за аудиторията за избрания наемател.</span><span class="sxs-lookup"><span data-stu-id="12d69-130">This command creates the service principal for audience insights on the selected tenant.</span></span>  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a><span data-ttu-id="12d69-131">Предоставете разрешения на принципала на услугата за достъп до акаунта за съхранение</span><span class="sxs-lookup"><span data-stu-id="12d69-131">Grant permissions to the service principal to access the storage account</span></span>

<span data-ttu-id="12d69-132">Отидете на портала на Azure, за да предоставите разрешения на принципала на услугата за акаунта за съхранение, който искате да използвате в статистика за аудиторията.</span><span class="sxs-lookup"><span data-stu-id="12d69-132">Go to the Azure portal to grant permissions to the service principal for the storage account you want to use in audience insights.</span></span>

1. <span data-ttu-id="12d69-133">Отидете на [Административен портал на Azure](https://portal.azure.com) и влезте във вашата организация.</span><span class="sxs-lookup"><span data-stu-id="12d69-133">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

1. <span data-ttu-id="12d69-134">Отворете акаунта за съхранение, до който искате да има достъп главницата на услугата, за да има прозрения за аудиторията.</span><span class="sxs-lookup"><span data-stu-id="12d69-134">Open the storage account you want the service principal for audience insights to have access to.</span></span>

1. <span data-ttu-id="12d69-135">Изберете **Контрол на достъпа (IAM)** от навигационния екран и изберете **Добавяне** > **Добавете назначение на роля**.</span><span class="sxs-lookup"><span data-stu-id="12d69-135">Select **Access control (IAM)** from the navigation pane and select **Add** > **Add role assignment**.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Снимка на екрана, показваща портала на Azure, докато добавяте назначение на роля.":::
   
1. <span data-ttu-id="12d69-137">В екрана **Добавете назначение на роля**, задайте следните свойства:</span><span class="sxs-lookup"><span data-stu-id="12d69-137">In the **Add role assignment** pane, set the following properties:</span></span>
   - <span data-ttu-id="12d69-138">Роля: *Сътрудник за данни за BLOB за съхранение*</span><span class="sxs-lookup"><span data-stu-id="12d69-138">Role: *Storage Blob Data Contributor*</span></span>
   - <span data-ttu-id="12d69-139">Присвояване на достъп до: *Принцип на потребител, група или услуга*</span><span class="sxs-lookup"><span data-stu-id="12d69-139">Assign access to: *User, group, or service principal*</span></span>
   - <span data-ttu-id="12d69-140">Изберете: *AI на Dynamics 365 for Customer Insights* ([принципа на услугата, който сте създали](#create-a-new-service-principal))</span><span class="sxs-lookup"><span data-stu-id="12d69-140">Select: *Dynamics 365 AI for Customer Insights* (the [service principal you created](#create-a-new-service-principal))</span></span>

1.  <span data-ttu-id="12d69-141">Изберете **Записване**.</span><span class="sxs-lookup"><span data-stu-id="12d69-141">Select **Save**.</span></span>

<span data-ttu-id="12d69-142">Разпространението на промените може да отнеме до 15 минути.</span><span class="sxs-lookup"><span data-stu-id="12d69-142">It can take up to 15 minutes to propagate the changes.</span></span>

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a><span data-ttu-id="12d69-143">Въведете идентификационния номер на ресурса на Azure или подробностите за абонамента за Azure в прикачения акаунт за съхранение към Audience Insights.</span><span class="sxs-lookup"><span data-stu-id="12d69-143">Enter the Azure Resource ID or the Azure Subscription details in the storage account attachment to Audience Insights.</span></span>

<span data-ttu-id="12d69-144">Прикачете акаунт за съхранение в Azure Data Lake в статистика за аудиторията, за да [съхраните изходни данни](manage-environments.md), или [го използвайте като източник на данни](connect-common-data-service-lake.md).</span><span class="sxs-lookup"><span data-stu-id="12d69-144">Attach an Azure Data Lake storage account in audience insights to [store output data](manage-environments.md) or [use it as a data source](connect-common-data-service-lake.md).</span></span> <span data-ttu-id="12d69-145">Изборът на опцията Azure Data Lake ви позволява да избирате между базиран на ресурси или базиран на абонамент подход.</span><span class="sxs-lookup"><span data-stu-id="12d69-145">Choosing the Azure Data Lake option lets you choose between a resource-based or a subscription-based based approach.</span></span>

<span data-ttu-id="12d69-146">Следвайте стъпките по-долу, за да предоставите необходимата информация за избрания подход.</span><span class="sxs-lookup"><span data-stu-id="12d69-146">Follow the below steps to provide the required information on the selected approach.</span></span>

### <a name="resounce-based-storage-account-connection"></a><span data-ttu-id="12d69-147">Връзка на акаунт на хранилище, базиран на ресурс</span><span class="sxs-lookup"><span data-stu-id="12d69-147">Resounce-based storage account connection</span></span>

1. <span data-ttu-id="12d69-148">Отидете на [Административен портал на Azure](https://portal.azure.com), влезте в абонамента си и отворете акаунта за съхранение.</span><span class="sxs-lookup"><span data-stu-id="12d69-148">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="12d69-149">Отидете на **Настройки** > **Свойства** в навигационния екран.</span><span class="sxs-lookup"><span data-stu-id="12d69-149">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="12d69-150">Копирайте стойността на идентификатора на ресурса на акаунта за съхранение.</span><span class="sxs-lookup"><span data-stu-id="12d69-150">Copy the storage account resource ID value.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Копирайте идентификатора на ресурса на акаунта за съхранение.":::

1. <span data-ttu-id="12d69-152">В статистика за аудиторията вмъкнете идентификатора на ресурса в полето на ресурса, показано на екрана за връзка на акаунта за съхранение.</span><span class="sxs-lookup"><span data-stu-id="12d69-152">In audience insights, insert the resource ID in the resource field displayed in the storage account connection screen.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Въведете информацията за идентификатора на ресурса на акаунта за съхранение.":::   
   
1. <span data-ttu-id="12d69-154">Продължете с останалите стъпки в статистика за аудиторията, за да прикачите акаунта за съхранение.</span><span class="sxs-lookup"><span data-stu-id="12d69-154">Continue with the remaining steps in audience insights to attach the storage account.</span></span>

### <a name="subscription-based-storage-account-connection"></a><span data-ttu-id="12d69-155">Връзка на акаунт на хранилище, базиран на абонамент</span><span class="sxs-lookup"><span data-stu-id="12d69-155">Subscription-based storage account connection</span></span>

1. <span data-ttu-id="12d69-156">Отидете на [Административен портал на Azure](https://portal.azure.com), влезте в абонамента си и отворете акаунта за съхранение.</span><span class="sxs-lookup"><span data-stu-id="12d69-156">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="12d69-157">Отидете на **Настройки** > **Свойства** в навигационния екран.</span><span class="sxs-lookup"><span data-stu-id="12d69-157">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="12d69-158">Прегледайте **Абонамент**, **Ресурсна група** и **Име** на акаунта за съхранение, за да сте сигурни, че сте избрали правилните стойности в статистиката за аудиторията.</span><span class="sxs-lookup"><span data-stu-id="12d69-158">Review the **Subscription**, **Resource group**, and the **Name** of the storage account to make sure you select the right values in audience insights.</span></span>

1. <span data-ttu-id="12d69-159">В статистиката за аудиторията изберете стойностите или за съответните полета, когато прикачвате акаунта за съхранение.</span><span class="sxs-lookup"><span data-stu-id="12d69-159">In audience insights, choose the values or for the corresponding fields when attaching the storage account.</span></span>

   :::image type="content" source="media/ADLS-SP-SubscriptionConnection.png" alt-text="Въведете информацията за идентификатора на ресурса на акаунта за съхранение.":::
   
1. <span data-ttu-id="12d69-161">Продължете с останалите стъпки в статистика за аудиторията, за да прикачите акаунта за съхранение.</span><span class="sxs-lookup"><span data-stu-id="12d69-161">Continue with the remaining steps in audience insights to attach the storage account.</span></span>