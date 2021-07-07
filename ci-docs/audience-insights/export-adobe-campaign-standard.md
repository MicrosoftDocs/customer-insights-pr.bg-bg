---
title: Експортирайте данните от Customer Insights в Adobe Campaign Standard
description: Научете как се използват сегменти с прозрения за аудиторията в Adobe Campaign Standard.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 917ab9559416f3ee0ffd66e471e590e8da3faffc
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305373"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a><span data-ttu-id="d62a0-103">Използване на сегментите Customer Insights в Adobe Campaign Standard (преглед)</span><span class="sxs-lookup"><span data-stu-id="d62a0-103">Use Customer Insights segments in Adobe Campaign Standard (preview)</span></span>

<span data-ttu-id="d62a0-104">Като потребител на прозрения за аудиторията в Dynamics 365 Customer Insights, може да сте създали сегменти, за да направите маркетинговите си кампании по-ефективни, като насочите към съответните аудитории.</span><span class="sxs-lookup"><span data-stu-id="d62a0-104">As a user of audience insights in Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="d62a0-105">За да използвате сегмент от прозрения за аудиторията в Adobe Experience Platform и приложения като Adobe Campaign Standard, трябва да изпълните няколко стъпки, описани в тази статия.</span><span class="sxs-lookup"><span data-stu-id="d62a0-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/ACS-flow.png" alt-text="Схема на процеса на стъпките, описани в тази статия.":::

## <a name="prerequisites"></a><span data-ttu-id="d62a0-107">Предварителни изисквания</span><span class="sxs-lookup"><span data-stu-id="d62a0-107">Prerequisites</span></span>

-   <span data-ttu-id="d62a0-108">Лиценз за Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="d62a0-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="d62a0-109">Лиценз на Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="d62a0-109">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="d62a0-110">Акаунт в Azure Blob Storage</span><span class="sxs-lookup"><span data-stu-id="d62a0-110">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="d62a0-111">Общ преглед на кампания</span><span class="sxs-lookup"><span data-stu-id="d62a0-111">Campaign overview</span></span>

<span data-ttu-id="d62a0-112">За да разберете по-добре как можете да използвате сегменти от прозрения за аудиторията в Adobe Experience Platform, нека разгледаме фиктивна примерна кампания.</span><span class="sxs-lookup"><span data-stu-id="d62a0-112">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="d62a0-113">Да приемем, че вашата компания предлага месечна услуга, базирана на абонамент, на вашите клиенти в САЩ.</span><span class="sxs-lookup"><span data-stu-id="d62a0-113">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="d62a0-114">Искате да идентифицирате клиенти, чиито абонаменти трябва да бъдат подновени през следващите осем дни, но все още не са подновили абонамента си.</span><span class="sxs-lookup"><span data-stu-id="d62a0-114">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="d62a0-115">За да задържите тези клиенти, искате да им изпратите промоционална оферта по имейл, използвайки Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="d62a0-115">To keep these customers, you want to send them a promotional offer via email, using Adobe Campaign Standard.</span></span>

<span data-ttu-id="d62a0-116">В този пример искаме да стартираме промоционалната кампания по имейл веднъж.</span><span class="sxs-lookup"><span data-stu-id="d62a0-116">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="d62a0-117">Тази статия не обхваща случая на използване на провеждането на кампанията повече от веднъж.</span><span class="sxs-lookup"><span data-stu-id="d62a0-117">This article doesn’t cover the use-case of running the campaign more than once.</span></span> <span data-ttu-id="d62a0-118">Статистика за аудиторията и Adobe Campaign Standard обаче могат да бъдат конфигурирани да работят и за повтарящ се сценарий на кампанията.</span><span class="sxs-lookup"><span data-stu-id="d62a0-118">However, audience insights and Adobe Campaign Standard can be configured to work for a recurring campaign scenario too.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="d62a0-119">Идентифицирайте вашата целева аудитория</span><span class="sxs-lookup"><span data-stu-id="d62a0-119">Identify your target audience</span></span>

<span data-ttu-id="d62a0-120">В нашия сценарий предполагаме, че имейл адресите на клиентите са достъпни в статистика за аудиторията и техните промоционални предпочитания са анализирани, за да се идентифицират членовете на сегмента.</span><span class="sxs-lookup"><span data-stu-id="d62a0-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="d62a0-121">[Сегментът, който сте определили в статистика за аудиторията](segments.md) е наречен **ChurnProneCustomers** и планирате да изпратите на тези клиенти промоцията по имейл.</span><span class="sxs-lookup"><span data-stu-id="d62a0-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Екранна снимка на страницата със сегменти със създадения сегмент ChurnProneCustomers.":::

<span data-ttu-id="d62a0-123">Имейлът с оферта, който искате да изпратите, ще съдържа собствено име, фамилно име, и крайната дата на абонамента на клиента.</span><span class="sxs-lookup"><span data-stu-id="d62a0-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="d62a0-124">Той информира клиентите за отстъпката, която ще получат, ако подновят абонамента си, преди да приключи.</span><span class="sxs-lookup"><span data-stu-id="d62a0-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="d62a0-125">Експортирайте вашата целева аудитория</span><span class="sxs-lookup"><span data-stu-id="d62a0-125">Export your target audience</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="d62a0-126">Конфигуриране на връзка</span><span class="sxs-lookup"><span data-stu-id="d62a0-126">Configure a connection</span></span>

<span data-ttu-id="d62a0-127">С идентифицирането на целевата ни аудитория можем да конфигурираме експортирането от статистика за аудиторията в акаунт в Azure Blob Storage.</span><span class="sxs-lookup"><span data-stu-id="d62a0-127">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="d62a0-128">В аналитичните данни за аудиторията отидете на **Администратор** > **Връзки**.</span><span class="sxs-lookup"><span data-stu-id="d62a0-128">In audience insights, go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="d62a0-129">Изберете **Добавяне на връзка** и след това **Adobe Campaign**, за да конфигурирате връзката, или изберете **Настройка** в плочката **Adobe Campaign**.</span><span class="sxs-lookup"><span data-stu-id="d62a0-129">Select **Add connection** and choose **Adobe Campaign** to configure the connection or select **Set up** in the **Adobe Campaign** tile.</span></span>

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Конфигурационна плочка за Adobe Campaign Standard.":::

1. <span data-ttu-id="d62a0-131">Въведете разпознаваемо име за връзката в полето **Показвано име**.</span><span class="sxs-lookup"><span data-stu-id="d62a0-131">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="d62a0-132">Показваното име и типът описват тази връзка.</span><span class="sxs-lookup"><span data-stu-id="d62a0-132">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="d62a0-133">Препоръчваме да изберете име, което обяснява целта на връзката.</span><span class="sxs-lookup"><span data-stu-id="d62a0-133">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="d62a0-134">Изберете кой може да използва тази връзка.</span><span class="sxs-lookup"><span data-stu-id="d62a0-134">Choose who can use this connection.</span></span> <span data-ttu-id="d62a0-135">Ако не предприемете нищо, по подразбиране ще е Администратори.</span><span class="sxs-lookup"><span data-stu-id="d62a0-135">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="d62a0-136">За повече информация вижте [Разрешения, необходими за конфигуриране на експортиране](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="d62a0-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="d62a0-137">Въведете **Име на акаунт**, **Ключ за акаунт** и **Контейнер** на акаунта в хранилището за BLOB на Azure, в което искате да експортирате сегмента.</span><span class="sxs-lookup"><span data-stu-id="d62a0-137">Enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Екранна снимка на конфигурацията на акаунт за съхранение. "::: 

   - <span data-ttu-id="d62a0-139">За да научите повече за това как да намерите името и ключа за акаунта за хранилището за Blob на Azure, вижте [Управление на настройките на акаунта за съхранение в портала на Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="d62a0-139">To learn more about how to find the Azure Blob Storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="d62a0-140">За да научите как да създадете контейнер, вижте [Създаване на контейнер](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="d62a0-140">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="d62a0-141">Изберете **Записване**, за да завършите връзката.</span><span class="sxs-lookup"><span data-stu-id="d62a0-141">Select **Save** to complete the connection.</span></span>

### <a name="configure-an-export"></a><span data-ttu-id="d62a0-142">Конфигуриране на експортиране</span><span class="sxs-lookup"><span data-stu-id="d62a0-142">Configure an export</span></span>

<span data-ttu-id="d62a0-143">Можете да конфигурирате това експортиране, ако имате достъп до връзка от този тип.</span><span class="sxs-lookup"><span data-stu-id="d62a0-143">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="d62a0-144">За повече информация вижте [Разрешения, необходими за конфигуриране на експортиране](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="d62a0-144">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="d62a0-145">Отидете на **Данни** > **Експортиране**.</span><span class="sxs-lookup"><span data-stu-id="d62a0-145">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="d62a0-146">За да създадете ново експортиране, изберете **Добавяне на експортиране**.</span><span class="sxs-lookup"><span data-stu-id="d62a0-146">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="d62a0-147">В полето **Връзка за експортиране** изберете връзка от секцията Adobe Campaign.</span><span class="sxs-lookup"><span data-stu-id="d62a0-147">In the **Connection for export** field, choose a connection from the Adobe Campaign section.</span></span> <span data-ttu-id="d62a0-148">Ако не виждате името на този раздел, тогава няма налични връзки от този тип.</span><span class="sxs-lookup"><span data-stu-id="d62a0-148">If you don't see this section name, then no connections of this type are available to you.</span></span>

1. <span data-ttu-id="d62a0-149">Изберете сегмента, които искате да експортирате.</span><span class="sxs-lookup"><span data-stu-id="d62a0-149">Choose the segment that you want to export.</span></span> <span data-ttu-id="d62a0-150">В този пример е така **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="d62a0-150">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Екранна снимка на потребителския интерфейс за избор на сегмент с избрания сегмент ChurnProneCustomers.":::

1. <span data-ttu-id="d62a0-152">Изберете **Напред**.</span><span class="sxs-lookup"><span data-stu-id="d62a0-152">Select **Next**.</span></span>

1. <span data-ttu-id="d62a0-153">Сега картографираме полета **Източник** от сегмента с прозрения за аудиторията до имената на полета **Цел** в схемата на профила на Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="d62a0-153">Now we map the **Source** fields from the audience insights segment to the **Target** field names in the Adobe Campaign Standard profile schema.</span></span>

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Съпоставяне на полета за конектора на Adobe Campaign Standard.":::

   <span data-ttu-id="d62a0-155">Ако искате да добавите още атрибути, изберете **Добавяне на атрибут**.</span><span class="sxs-lookup"><span data-stu-id="d62a0-155">If you want to add more attributes, select **Add attribute**.</span></span> <span data-ttu-id="d62a0-156">Името на целта може да се различава от името на полето източник, така че все още можете да картографирате изхода на сегменти от прозрения за аудиторията в Adobe Campaign Standard, ако полетата нямат едно и също име в двете системи.</span><span class="sxs-lookup"><span data-stu-id="d62a0-156">The target name can be different from the source field name so you can still map segment output from audience insights to Adobe Campaign Standard if the fields don’t have the same name in the two systems.</span></span>

   > [!NOTE]
   > <span data-ttu-id="d62a0-157">Имейл адресът се използва като поле за идентичност, но можете да използвате всеки друг идентификатор от профила на клиента за прозрения на аудиторията си, за да съпоставите данните с Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="d62a0-157">Email address is used as an identity field but you can use any other identifier from your audience insights customer profile to map data to Adobe Campaign Standard.</span></span>

1. <span data-ttu-id="d62a0-158">Изберете **Записване**.</span><span class="sxs-lookup"><span data-stu-id="d62a0-158">Select **Save**.</span></span>

<span data-ttu-id="d62a0-159">След като запишете местоназначението за експортиране, ще го намерите на **Данни** > **Експортиране**.</span><span class="sxs-lookup"><span data-stu-id="d62a0-159">After saving the export destination, you find it on **Data** > **Exports**.</span></span>

<span data-ttu-id="d62a0-160">Вече можете да [експортирате сегмента при поискване](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="d62a0-160">You can now [export the segment on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="d62a0-161">Експортирането също ще се изпълнява с всяко [планирано обновяване](system.md).</span><span class="sxs-lookup"><span data-stu-id="d62a0-161">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="d62a0-162">Уверете се, че броят на записите в експортирания сегмент е в рамките на разрешеното ограничение от вашия лиценз за Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="d62a0-162">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="d62a0-163">Експортираните данни се съхраняват в контейнера за Хранилище за BLOB на Azure, който сте конфигурирали по-горе.</span><span class="sxs-lookup"><span data-stu-id="d62a0-163">Exported data is stored in the Azure Blob Storage container you configured above.</span></span> <span data-ttu-id="d62a0-164">Следният път на папката се създава автоматично във вашия контейнер:</span><span class="sxs-lookup"><span data-stu-id="d62a0-164">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="d62a0-165">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span><span class="sxs-lookup"><span data-stu-id="d62a0-165">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span></span>

<span data-ttu-id="d62a0-166">Пример: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span><span class="sxs-lookup"><span data-stu-id="d62a0-166">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span></span>

## <a name="configure-adobe-campaign-standard"></a><span data-ttu-id="d62a0-167">Конфигуриране на Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="d62a0-167">Configure Adobe Campaign Standard</span></span>

<span data-ttu-id="d62a0-168">Когато се експортира сегмент от аналитични данни за аудиторията, той съдържа колоните, които сте избрали, докато дефинирате дестинацията за експортиране в предишната стъпка.</span><span class="sxs-lookup"><span data-stu-id="d62a0-168">When a segment from audience insights is exported, it contains the columns you selected while defining the export destination in the previous step.</span></span> <span data-ttu-id="d62a0-169">Тези данни могат да се използват за [създаване на профили в Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span><span class="sxs-lookup"><span data-stu-id="d62a0-169">This data can be used to [create profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span></span>

<span data-ttu-id="d62a0-170">За да използваме сегмента в Adobe Campaign Standard, трябва да разширим схемата на профила в Adobe Campaign Standard, за да включим две допълнителни полета.</span><span class="sxs-lookup"><span data-stu-id="d62a0-170">To use the segment in Adobe Campaign Standard, we need to extend the profile schema in Adobe Campaign Standard to include two additional fields.</span></span> <span data-ttu-id="d62a0-171">Научете как да [разширявате ресурса на профила](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) с нови полета в Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="d62a0-171">Learn how to [extend the profile resource](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) with new fields in Adobe Campaign Standard.</span></span>

<span data-ttu-id="d62a0-172">В нашия пример тези полета са *Име на сегмента и Дата на сегмента (по избор)*.</span><span class="sxs-lookup"><span data-stu-id="d62a0-172">In our example, these fields are *Segment Name and Segment Date (optional)*.</span></span>

<span data-ttu-id="d62a0-173">Ще използваме тези полета, за да идентифицираме профилите в Adobe Campaign Standard, към които искаме да насочим тази кампания.</span><span class="sxs-lookup"><span data-stu-id="d62a0-173">We will use these fields to identify the profiles in Adobe Campaign Standard we want to target for this campaign.</span></span>

<span data-ttu-id="d62a0-174">Ако в Adobe Campaign Standard няма други записи, освен това, което ще импортирате, можете да пропуснете тази стъпка.</span><span class="sxs-lookup"><span data-stu-id="d62a0-174">If there are no other records in Adobe Campaign Standard, other than what you are going to import, you can skip this step.</span></span>

## <a name="import-data-into-adobe-campaign-standard"></a><span data-ttu-id="d62a0-175">Импортирайте данни в Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="d62a0-175">Import data into Adobe Campaign Standard</span></span>

<span data-ttu-id="d62a0-176">Сега, когато всичко е на мястото си, трябва да импортираме подготвените данни за аудиторията от статистика за аудиторията в Adobe Campaign Standard, за да създадете профили.</span><span class="sxs-lookup"><span data-stu-id="d62a0-176">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Campaign Standard to create profiles.</span></span> <span data-ttu-id="d62a0-177">Научете [как да импортирате профили в Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) с използване на работен поток.</span><span class="sxs-lookup"><span data-stu-id="d62a0-177">Learn [how to import profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) using a workflow.</span></span>

<span data-ttu-id="d62a0-178">Работният поток за импортиране в изображението по-долу е конфигуриран да се изпълнява на всеки осем часа и да търси експортирани сегменти с информация за аудиторията (.csv файл в Хранилището за BLOB на Azure).</span><span class="sxs-lookup"><span data-stu-id="d62a0-178">The import workflow in the image below has been configured to run every eight hours and look for exported audience insights segments (.csv file in Azure Blob Storage).</span></span> <span data-ttu-id="d62a0-179">Работният поток извлича съдържанието на .csv файл в определен ред на колони.</span><span class="sxs-lookup"><span data-stu-id="d62a0-179">The workflow extracts the .csv file content in a specified column order.</span></span> <span data-ttu-id="d62a0-180">Този работен процес е създаден, за да извърши основно обработване на грешки и да гарантира, че всеки запис има имейл адрес, преди да хидратира данните в Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="d62a0-180">This workflow has been built to perform basic error handling and ensure that each record has an email address before hydrating the data in Adobe Campaign Standard.</span></span> <span data-ttu-id="d62a0-181">Работният процес също извлича името на сегмента от името на файла, преди да се добави в данните на профила на Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="d62a0-181">The workflow also extracts the segment name from the filename before upserting into Adobe Campaign Standard profile data.</span></span>

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Екранна снимка на работен процес за импортиране в потребителския интерфейс на Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a><span data-ttu-id="d62a0-183">Извличане на аудитория в Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="d62a0-183">Retrieve the audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="d62a0-184">След като данните бъдат импортирани в Adobe Campaign Standard, вие [можете да създадете работен поток](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) и да направите [справка](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) за клиентите въз основа на *Име на сегмента* и *Дата на сегмента*, за да изберете профили, идентифицирани за нашата примерна кампания.</span><span class="sxs-lookup"><span data-stu-id="d62a0-184">Once the data is imported into Adobe Campaign Standard, you [can create a workflow](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) and [query](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) the customers based on the *Segment Name* and *Segment Date* to select profiles that were identified for our sample campaign.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="d62a0-185">Създайте и изпратете имейла с помощта на Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="d62a0-185">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="d62a0-186">Създайте съдържанието на имейла и след това [тествайте и изпратете](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) имейла си.</span><span class="sxs-lookup"><span data-stu-id="d62a0-186">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Примерен имейл с предложение за подновяване от Adobe Campaign Standard.":::
