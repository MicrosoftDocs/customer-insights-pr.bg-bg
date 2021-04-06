---
title: Експортирайте данните от Customer Insights в Adobe Experience Platform
description: Научете как се използват сегменти с прозрения за аудиторията в Adobe Experience Platform.
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: d1856861562be55c6d1d051050fe965560fa42f8
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596256"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a><span data-ttu-id="da507-103">Използване на сегментите Customer Insights в Adobe Experience Platform (преглед)</span><span class="sxs-lookup"><span data-stu-id="da507-103">Use Customer Insights segments in Adobe Experience Platform (preview)</span></span>

<span data-ttu-id="da507-104">Като потребител на прозрения за аудиторията за Dynamics 365 Customer Insights, може да сте създали сегменти, за да направите маркетинговите си кампании по-ефективни, като насочите към съответните аудитории.</span><span class="sxs-lookup"><span data-stu-id="da507-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="da507-105">За да използвате сегмент от прозрения за аудиторията в Adobe Experience Platform и приложения като Adobe Campaign Standard, трябва да изпълните няколко стъпки, описани в тази статия.</span><span class="sxs-lookup"><span data-stu-id="da507-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/AEP-flow.png" alt-text="Схема на процеса на стъпките, описани в тази статия.":::

## <a name="prerequisites"></a><span data-ttu-id="da507-107">Предварителни изисквания</span><span class="sxs-lookup"><span data-stu-id="da507-107">Prerequisites</span></span>

-   <span data-ttu-id="da507-108">Лиценз за Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="da507-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="da507-109">Лиценз за Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="da507-109">Adobe Experience Platform license</span></span>
-   <span data-ttu-id="da507-110">Лиценз на Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="da507-110">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="da507-111">Акаунт в Azure Blob Storage</span><span class="sxs-lookup"><span data-stu-id="da507-111">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="da507-112">Общ преглед на кампания</span><span class="sxs-lookup"><span data-stu-id="da507-112">Campaign Overview</span></span>

<span data-ttu-id="da507-113">За да разберете по-добре как можете да използвате сегменти от прозрения за аудиторията в Adobe Experience Platform, нека разгледаме фиктивна примерна кампания.</span><span class="sxs-lookup"><span data-stu-id="da507-113">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="da507-114">Да приемем, че вашата компания предлага месечна услуга, базирана на абонамент, на вашите клиенти в САЩ.</span><span class="sxs-lookup"><span data-stu-id="da507-114">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="da507-115">Искате да идентифицирате клиенти, чиито абонаменти трябва да бъдат подновени през следващите осем дни, но все още не са подновили абонамента си.</span><span class="sxs-lookup"><span data-stu-id="da507-115">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="da507-116">За да задържите тези клиенти, искате да им изпратите промоционална оферта по имейл, използвайки Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="da507-116">To keep these customers, you want to send them a promotional offer via email, using Adobe Experience Platform.</span></span>

<span data-ttu-id="da507-117">В този пример искаме да стартираме промоционалната кампания по имейл веднъж.</span><span class="sxs-lookup"><span data-stu-id="da507-117">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="da507-118">Тази статия не обхваща случая на използване на провеждането на кампанията повече от веднъж.</span><span class="sxs-lookup"><span data-stu-id="da507-118">This article doesn’t cover the use-case of running the campaign more than once.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="da507-119">Идентифицирайте вашата целева аудитория</span><span class="sxs-lookup"><span data-stu-id="da507-119">Identify your target audience</span></span>

<span data-ttu-id="da507-120">В нашия сценарий предполагаме, че имейл адресите на клиентите са достъпни в статистика за аудиторията и техните промоционални предпочитания са анализирани, за да се идентифицират членовете на сегмента.</span><span class="sxs-lookup"><span data-stu-id="da507-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="da507-121">[Сегментът, който сте определили в статистика за аудиторията](segments.md) е наречен **ChurnProneCustomers** и планирате да изпратите на тези клиенти промоцията по имейл.</span><span class="sxs-lookup"><span data-stu-id="da507-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Екранна снимка на страницата със сегменти със създадения сегмент ChurnProneCustomers.":::

<span data-ttu-id="da507-123">Имейлът с оферта, който искате да изпратите, ще съдържа собствено име, фамилно име, и крайната дата на абонамента на клиента.</span><span class="sxs-lookup"><span data-stu-id="da507-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="da507-124">Той информира клиентите за отстъпката, която ще получат, ако подновят абонамента си, преди да приключи.</span><span class="sxs-lookup"><span data-stu-id="da507-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="da507-125">Експортирайте вашата целева аудитория</span><span class="sxs-lookup"><span data-stu-id="da507-125">Export your target audience</span></span>

<span data-ttu-id="da507-126">С идентифицирането на целевата ни аудитория можем да конфигурираме експортирането от статистика за аудиторията в акаунт в Azure Blob Storage.</span><span class="sxs-lookup"><span data-stu-id="da507-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="da507-127">В статията за аудиторията отидете на **Администратор** > **Експортиране на местоположения**.</span><span class="sxs-lookup"><span data-stu-id="da507-127">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="da507-128">В плочката **Хранилище за BLOB на Azure**, изберете **Настройка**.</span><span class="sxs-lookup"><span data-stu-id="da507-128">In the **Azure Blob Storage** tile, select **Set up**.</span></span>

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Конфигурационна плочка за Azure Blob Storage.":::

1. <span data-ttu-id="da507-130">Предоставете **Показвано име** за тази нова дестинация за износ и след това въведете **Име на акаунта**, **Ключ на акаунта** и **Контейнер** на акаунта на Azure Blob Storage, където искате да експортирате сегмента.</span><span class="sxs-lookup"><span data-stu-id="da507-130">Provide a **Display name** for this new export destination and then enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Екранна снимка на конфигурацията на акаунт за съхранение. "::: 

   - <span data-ttu-id="da507-132">За да научите повече за това как да намерите името и ключа за акаунта за хранилището за Blob на Azure, вижте [Управление на настройките на акаунта за съхранение в портала на Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="da507-132">To learn more about how to find the Azure Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="da507-133">За да научите как да създадете контейнер, вижте [Създаване на контейнер](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="da507-133">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="da507-134">Изберете **Напред**.</span><span class="sxs-lookup"><span data-stu-id="da507-134">Select **Next**.</span></span>

1. <span data-ttu-id="da507-135">Изберете сегмента, които искате да експортирате.</span><span class="sxs-lookup"><span data-stu-id="da507-135">Choose the segment that you want to export.</span></span> <span data-ttu-id="da507-136">В този пример е така **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="da507-136">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Екранна снимка на потребителския интерфейс за избор на сегмент с избрания сегмент ChurnProneCustomers.":::

1. <span data-ttu-id="da507-138">Изберете **Записване**.</span><span class="sxs-lookup"><span data-stu-id="da507-138">Select **Save**.</span></span>

<span data-ttu-id="da507-139">След като запазите дестинацията за износ, ще я намерите на **Администратор** > **Експортиране** > **Моите местоназначения за експортиране**.</span><span class="sxs-lookup"><span data-stu-id="da507-139">After saving the export destination, you find it on **Admin** > **Exports** > **My export destinations**.</span></span>

:::image type="content" source="media/export-destination-azure-blob-storage.png" alt-text="Екранна снимка с подчертан списък на износа и примерен сегмент.":::

<span data-ttu-id="da507-141">Вече можете да [експортирате сегмента при поискване](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="da507-141">You can now [export the segment on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="da507-142">Експортирането също ще се изпълнява с всяко [планирано обновяване](system.md).</span><span class="sxs-lookup"><span data-stu-id="da507-142">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="da507-143">Уверете се, че броят на записите в експортирания сегмент е в рамките на разрешеното ограничение от вашия лиценз за Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="da507-143">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="da507-144">Експортираните данни се съхраняват в контейнера за Azure Blob Storage, който сте конфигурирали по-горе.</span><span class="sxs-lookup"><span data-stu-id="da507-144">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="da507-145">Следният път на папката се създава автоматично във вашия контейнер:</span><span class="sxs-lookup"><span data-stu-id="da507-145">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="da507-146">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span><span class="sxs-lookup"><span data-stu-id="da507-146">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span></span>

<span data-ttu-id="da507-147">Пример: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span><span class="sxs-lookup"><span data-stu-id="da507-147">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span></span>

<span data-ttu-id="da507-148">*model.json* за изнесените обекти се намира на нивото *%ExportDestinationName%*.</span><span class="sxs-lookup"><span data-stu-id="da507-148">The *model.json* for the exported entities resides at the *%ExportDestinationName%* level.</span></span>

<span data-ttu-id="da507-149">Пример: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span><span class="sxs-lookup"><span data-stu-id="da507-149">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span></span>

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a><span data-ttu-id="da507-150">Дефинирайте Experience Data Model (XDM) в Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="da507-150">Define Experience Data Model (XDM) in Adobe Experience Platform</span></span>

<span data-ttu-id="da507-151">Преди експортираните данни от статистика за аудиторията да могат да бъдат използвани в рамките на Adobe Experience Platform, трябва да дефинираме схемата на Experience Data Model и да [конфигурирайте данните за потребителския профил в реално време](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span><span class="sxs-lookup"><span data-stu-id="da507-151">Before the exported data from audience insights can be used within Adobe Experience Platform, we need to define the Experience Data Model schema and [configure the data for the Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span></span>

<span data-ttu-id="da507-152">Научете [какво е XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) и разберете [основите на състава на схемата](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span><span class="sxs-lookup"><span data-stu-id="da507-152">Learn [what XDM is](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) and understand the [basics of schema composition](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span></span>

## <a name="import-data-into-adobe-experience-platform"></a><span data-ttu-id="da507-153">Импортирайте данни в Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="da507-153">Import data into Adobe Experience Platform</span></span>

<span data-ttu-id="da507-154">Сега, когато всичко е на мястото си, трябва да импортираме подготвените данни за аудиторията от статистика за аудиторията в Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="da507-154">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Experience Platform.</span></span>

<span data-ttu-id="da507-155">Първо, [създайте източник на връзка на Azure Blob Storage](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span><span class="sxs-lookup"><span data-stu-id="da507-155">First, [create an Azure Blob Storage source connection](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span></span>    

<span data-ttu-id="da507-156">След дефиниране на връзката източник, [конфигуриране на поток от данни](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) за пакетна връзка за съхранение в облак за импортиране на изхода на сегмента от прозрения за аудиторията в Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="da507-156">After defining the source connection, [configure a dataflow](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) for a cloud storage batch connection to import the segment output from audience insights into Adobe Experience Platform.</span></span>

## <a name="create-an-audience-in-adobe-campaign-standard"></a><span data-ttu-id="da507-157">Създайте аудитория в Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="da507-157">Create an audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="da507-158">За да изпратим имейла за тази кампания, ще използваме Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="da507-158">To send the email for this campaign, we will use Adobe Campaign Standard.</span></span> <span data-ttu-id="da507-159">След като импортираме данните в Adobe Experience Platform, трябва да [създадете публика](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) в Adobe Campaign Standard, използвайки данните в Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="da507-159">After importing the data into Adobe Experience Platform, we need to [create an audience](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) in Adobe Campaign Standard using the data in Adobe Experience Platform.</span></span>

<span data-ttu-id="da507-160">Научете как да [използвайте конструктор на сегменти](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) в Adobe Campaign Standard за определяне на аудитория въз основа на данните в Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="da507-160">Learn how to [use segment builder](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) in Adobe Campaign Standard to define an audience based on the data in Adobe Experience Platform.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="da507-161">Създайте и изпратете имейла с помощта на Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="da507-161">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="da507-162">Създайте съдържанието на имейла и след това [тествайте и изпратете](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) имейла си.</span><span class="sxs-lookup"><span data-stu-id="da507-162">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Примерен имейл с предложение за подновяване от Adobe Campaign Standard.":::