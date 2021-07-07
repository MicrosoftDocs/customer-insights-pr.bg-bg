---
title: Експортирайте данните от Customer Insights в Adobe Experience Platform
description: Научете как да използвате сегменти със статистика за аудиторията в Adobe Experience Platform.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 1045d0e373fd5ea8987684e51bd9a07b7b535ee3
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305511"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a><span data-ttu-id="1f8ed-103">Използване на сегментите Customer Insights в Adobe Experience Platform (преглед)</span><span class="sxs-lookup"><span data-stu-id="1f8ed-103">Use Customer Insights segments in Adobe Experience Platform (preview)</span></span>

<span data-ttu-id="1f8ed-104">Като потребител на прозрения за аудиторията в Dynamics 365 Customer Insights, може да сте създали сегменти, за да направите маркетинговите си кампании по-ефективни, като насочите към съответните аудитории.</span><span class="sxs-lookup"><span data-stu-id="1f8ed-104">As a user of audience insights in Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="1f8ed-105">За да използвате сегмент от прозрения за аудиторията в Adobe Experience Platform и приложения като Adobe Campaign Standard, трябва да изпълните няколко стъпки, описани в тази статия.</span><span class="sxs-lookup"><span data-stu-id="1f8ed-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/AEP-flow.png" alt-text="Схема на процеса на стъпките, описани в тази статия.":::

## <a name="prerequisites"></a><span data-ttu-id="1f8ed-107">Предварителни изисквания</span><span class="sxs-lookup"><span data-stu-id="1f8ed-107">Prerequisites</span></span>

-   <span data-ttu-id="1f8ed-108">Лиценз за Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="1f8ed-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="1f8ed-109">Лиценз за Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="1f8ed-109">Adobe Experience Platform license</span></span>
-   <span data-ttu-id="1f8ed-110">Лиценз на Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="1f8ed-110">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="1f8ed-111">Акаунт в Azure Blob Storage</span><span class="sxs-lookup"><span data-stu-id="1f8ed-111">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="1f8ed-112">Общ преглед на кампания</span><span class="sxs-lookup"><span data-stu-id="1f8ed-112">Campaign Overview</span></span>

<span data-ttu-id="1f8ed-113">За да разберете по-добре как можете да използвате сегменти от прозрения за аудиторията в Adobe Experience Platform, нека разгледаме фиктивна примерна кампания.</span><span class="sxs-lookup"><span data-stu-id="1f8ed-113">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="1f8ed-114">Да приемем, че вашата компания предлага месечна услуга, базирана на абонамент, на вашите клиенти в САЩ.</span><span class="sxs-lookup"><span data-stu-id="1f8ed-114">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="1f8ed-115">Искате да идентифицирате клиенти, чиито абонаменти трябва да бъдат подновени през следващите осем дни, но все още не са подновили абонамента си.</span><span class="sxs-lookup"><span data-stu-id="1f8ed-115">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="1f8ed-116">За да задържите тези клиенти, искате да им изпратите промоционална оферта по имейл, използвайки Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="1f8ed-116">To keep these customers, you want to send them a promotional offer via email, using Adobe Experience Platform.</span></span>

<span data-ttu-id="1f8ed-117">В този пример искаме да стартираме промоционалната кампания по имейл веднъж.</span><span class="sxs-lookup"><span data-stu-id="1f8ed-117">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="1f8ed-118">Тази статия не обхваща случая на използване на провеждането на кампанията повече от веднъж.</span><span class="sxs-lookup"><span data-stu-id="1f8ed-118">This article doesn’t cover the use-case of running the campaign more than once.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="1f8ed-119">Идентифицирайте вашата целева аудитория</span><span class="sxs-lookup"><span data-stu-id="1f8ed-119">Identify your target audience</span></span>

<span data-ttu-id="1f8ed-120">В нашия сценарий предполагаме, че имейл адресите на клиентите са достъпни в статистика за аудиторията и техните промоционални предпочитания са анализирани, за да се идентифицират членовете на сегмента.</span><span class="sxs-lookup"><span data-stu-id="1f8ed-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="1f8ed-121">[Сегментът, който сте определили в статистика за аудиторията](segments.md) е наречен **ChurnProneCustomers** и планирате да изпратите на тези клиенти промоцията по имейл.</span><span class="sxs-lookup"><span data-stu-id="1f8ed-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Екранна снимка на страницата със сегменти със създадения сегмент ChurnProneCustomers.":::

<span data-ttu-id="1f8ed-123">Имейлът с оферта, който искате да изпратите, ще съдържа собствено име, фамилно име, и крайната дата на абонамента на клиента.</span><span class="sxs-lookup"><span data-stu-id="1f8ed-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="1f8ed-124">Той информира клиентите за отстъпката, която ще получат, ако подновят абонамента си, преди да приключи.</span><span class="sxs-lookup"><span data-stu-id="1f8ed-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="1f8ed-125">Експортирайте вашата целева аудитория</span><span class="sxs-lookup"><span data-stu-id="1f8ed-125">Export your target audience</span></span>

<span data-ttu-id="1f8ed-126">С идентифицирането на целевата ни аудитория можем да конфигурираме експортирането от статистика за аудиторията в акаунт в Azure Blob Storage.</span><span class="sxs-lookup"><span data-stu-id="1f8ed-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="1f8ed-127">Конфигуриране на връзка</span><span class="sxs-lookup"><span data-stu-id="1f8ed-127">Configure a connection</span></span>

1. <span data-ttu-id="1f8ed-128">Отидете на **Администратор** > **Връзки**.</span><span class="sxs-lookup"><span data-stu-id="1f8ed-128">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="1f8ed-129">Изберете **Добавете връзка** и изберете **Хранилище за BLOB на Azure** или изберете **Настройвам** в **Хранилище за BLOB на Azure** за конфигуриране на връзката.</span><span class="sxs-lookup"><span data-stu-id="1f8ed-129">Select **Add connection** and choose **Azure Blob Storage** or select **Set up** in the **Azure Blob Storage** tile to configure the connection.</span></span>

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Конфигурационна плочка за Azure Blob Storage."::: 

1. <span data-ttu-id="1f8ed-131">Въведете разпознаваемо име за връзката в полето **Показвано име**.</span><span class="sxs-lookup"><span data-stu-id="1f8ed-131">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="1f8ed-132">Показваното име и типът описват тази връзка.</span><span class="sxs-lookup"><span data-stu-id="1f8ed-132">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="1f8ed-133">Препоръчваме да изберете име, което обяснява целта на връзката.</span><span class="sxs-lookup"><span data-stu-id="1f8ed-133">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="1f8ed-134">Изберете кой може да използва тази връзка.</span><span class="sxs-lookup"><span data-stu-id="1f8ed-134">Choose who can use this connection.</span></span> <span data-ttu-id="1f8ed-135">Ако не предприемете нищо, по подразбиране ще е Администратори.</span><span class="sxs-lookup"><span data-stu-id="1f8ed-135">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="1f8ed-136">За повече информация вижте [Разрешаване на сътрудници да използват връзка за експортиране](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="1f8ed-136">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="1f8ed-137">Въведете **Име на акаунт**, **Ключ за акаунт** и **Контейнер** за акаунта в хранилището за BLOB, в което искате да експортирате сегмента.</span><span class="sxs-lookup"><span data-stu-id="1f8ed-137">Enter **Account name**, **Account key**, and **Container** for your Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Екранна снимка на конфигурацията на акаунт за съхранение. "::: 
   
    - <span data-ttu-id="1f8ed-139">За да научите повече за това как да намерите името на акаунта и ключа за акаунта на хранилище за BLOB, вижте [Управление на настройки на акаунт за съхранение в портала на Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="1f8ed-139">To learn more about how to find the Blob Storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>
    - <span data-ttu-id="1f8ed-140">За да научите как да създадете контейнер, вижте [Създаване на контейнер](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="1f8ed-140">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="1f8ed-141">Изберете **Записване**, за да завършите връзката.</span><span class="sxs-lookup"><span data-stu-id="1f8ed-141">Select **Save** to complete the connection.</span></span> 

### <a name="configure-an-export"></a><span data-ttu-id="1f8ed-142">Конфигуриране на експортиране</span><span class="sxs-lookup"><span data-stu-id="1f8ed-142">Configure an export</span></span>

<span data-ttu-id="1f8ed-143">Можете да конфигурирате това експортиране, ако имате достъп до връзка от този тип.</span><span class="sxs-lookup"><span data-stu-id="1f8ed-143">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="1f8ed-144">За повече информация вижте [Разрешения, необходими за конфигуриране на експортиране](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="1f8ed-144">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="1f8ed-145">Отидете на **Данни** > **Експортиране**.</span><span class="sxs-lookup"><span data-stu-id="1f8ed-145">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="1f8ed-146">За да създадете ново експортиране, изберете **Добавяне на експортиране**.</span><span class="sxs-lookup"><span data-stu-id="1f8ed-146">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="1f8ed-147">В полето **Връзка за експортиране** изберете връзка от секцията на хранилището за BLOB на Azure.</span><span class="sxs-lookup"><span data-stu-id="1f8ed-147">In the **Connection for export** field, choose a connection from the Azure Blob Storage section.</span></span> <span data-ttu-id="1f8ed-148">Ако не виждате името на този раздел, тогава няма налични връзки от този тип.</span><span class="sxs-lookup"><span data-stu-id="1f8ed-148">If you don't see this section name, then no connections of this type are available to you.</span></span>

1. <span data-ttu-id="1f8ed-149">Изберете сегмента, които искате да експортирате.</span><span class="sxs-lookup"><span data-stu-id="1f8ed-149">Choose the segment that you want to export.</span></span> <span data-ttu-id="1f8ed-150">В този пример е така **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="1f8ed-150">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Екранна снимка на потребителския интерфейс за избор на сегмент с избрания сегмент ChurnProneCustomers.":::

1. <span data-ttu-id="1f8ed-152">Изберете **Записване**.</span><span class="sxs-lookup"><span data-stu-id="1f8ed-152">Select **Save**.</span></span>

<span data-ttu-id="1f8ed-153">След като запишете местоназначението за експортиране, ще го намерите на **Данни** > **Експортиране**.</span><span class="sxs-lookup"><span data-stu-id="1f8ed-153">After saving the export destination, you find it on **Data** > **Exports**.</span></span>

<span data-ttu-id="1f8ed-154">Вече можете да [експортирате сегмента при поискване](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="1f8ed-154">You can now [export the segment on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="1f8ed-155">Експортирането също ще се изпълнява с всяко [планирано обновяване](system.md).</span><span class="sxs-lookup"><span data-stu-id="1f8ed-155">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="1f8ed-156">Уверете се, че броят на записите в експортирания сегмент е в рамките на разрешеното ограничение от вашия лиценз за Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="1f8ed-156">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="1f8ed-157">Експортираните данни се съхраняват в контейнера за Хранилище за BLOB на Azure, който сте конфигурирали по-горе.</span><span class="sxs-lookup"><span data-stu-id="1f8ed-157">Exported data is stored in the Azure Blob Storage container you configured above.</span></span> <span data-ttu-id="1f8ed-158">Следният път на папката се създава автоматично във вашия контейнер:</span><span class="sxs-lookup"><span data-stu-id="1f8ed-158">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="1f8ed-159">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span><span class="sxs-lookup"><span data-stu-id="1f8ed-159">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span></span>

<span data-ttu-id="1f8ed-160">Пример: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span><span class="sxs-lookup"><span data-stu-id="1f8ed-160">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span></span>

<span data-ttu-id="1f8ed-161">*model.json* за изнесените обекти се намира на нивото *%ExportDestinationName%*.</span><span class="sxs-lookup"><span data-stu-id="1f8ed-161">The *model.json* for the exported entities resides at the *%ExportDestinationName%* level.</span></span>

<span data-ttu-id="1f8ed-162">Пример: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span><span class="sxs-lookup"><span data-stu-id="1f8ed-162">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span></span>

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a><span data-ttu-id="1f8ed-163">Дефинирайте Experience Data Model (XDM) в Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="1f8ed-163">Define Experience Data Model (XDM) in Adobe Experience Platform</span></span>

<span data-ttu-id="1f8ed-164">Преди експортираните данни от статистика за аудиторията да могат да бъдат използвани в рамките на Adobe Experience Platform, трябва да дефинираме схемата на Experience Data Model и да [конфигурирайте данните за потребителския профил в реално време](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span><span class="sxs-lookup"><span data-stu-id="1f8ed-164">Before the exported data from audience insights can be used within Adobe Experience Platform, we need to define the Experience Data Model schema and [configure the data for the Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span></span>

<span data-ttu-id="1f8ed-165">Научете [какво е XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) и разберете [основите на състава на схемата](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span><span class="sxs-lookup"><span data-stu-id="1f8ed-165">Learn [what XDM is](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) and understand the [basics of schema composition](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span></span>

## <a name="import-data-into-adobe-experience-platform"></a><span data-ttu-id="1f8ed-166">Импортирайте данни в Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="1f8ed-166">Import data into Adobe Experience Platform</span></span>

<span data-ttu-id="1f8ed-167">Сега, когато всичко е на мястото си, трябва да импортираме подготвените данни за аудиторията от статистика за аудиторията в Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="1f8ed-167">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Experience Platform.</span></span>

<span data-ttu-id="1f8ed-168">Първо, [създайте източник на връзка на Azure Blob Storage](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span><span class="sxs-lookup"><span data-stu-id="1f8ed-168">First, [create an Azure Blob Storage source connection](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span></span>    

<span data-ttu-id="1f8ed-169">След дефиниране на връзката източник, [конфигуриране на поток от данни](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) за пакетна връзка за съхранение в облак за импортиране на изхода на сегмента от прозрения за аудиторията в Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="1f8ed-169">After defining the source connection, [configure a dataflow](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) for a cloud storage batch connection to import the segment output from audience insights into Adobe Experience Platform.</span></span>

## <a name="create-an-audience-in-adobe-campaign-standard"></a><span data-ttu-id="1f8ed-170">Създайте аудитория в Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="1f8ed-170">Create an audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="1f8ed-171">За да изпратим имейла за тази кампания, ще използваме Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="1f8ed-171">To send the email for this campaign, we'll use Adobe Campaign Standard.</span></span> <span data-ttu-id="1f8ed-172">След като импортираме данните в Adobe Experience Platform, трябва да [създадете публика](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) в Adobe Campaign Standard, използвайки данните в Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="1f8ed-172">After importing the data into Adobe Experience Platform, we need to [create an audience](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) in Adobe Campaign Standard using the data in Adobe Experience Platform.</span></span>


<span data-ttu-id="1f8ed-173">Научете как да [използвайте конструктор на сегменти](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) в Adobe Campaign Standard за определяне на аудитория въз основа на данните в Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="1f8ed-173">Learn how to [use segment builder](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) in Adobe Campaign Standard to define an audience based on the data in Adobe Experience Platform.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="1f8ed-174">Създайте и изпратете имейла с помощта на Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="1f8ed-174">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="1f8ed-175">Създайте съдържанието на имейла и след това [тествайте и изпратете](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) имейла си.</span><span class="sxs-lookup"><span data-stu-id="1f8ed-175">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Примерен имейл с предложение за подновяване от Adobe Campaign Standard.":::
