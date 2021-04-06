---
title: Експортирайте данните от Customer Insights в Adobe Campaign Standard
description: Научете как се използват сегменти с прозрения за аудиторията в Adobe Campaign Standard.
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: a5d0154c3d7c473dcba03fac0847bafcf97de2f2
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596302"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a><span data-ttu-id="1958a-103">Използване на сегментите Customer Insights в Adobe Campaign Standard (преглед)</span><span class="sxs-lookup"><span data-stu-id="1958a-103">Use Customer Insights segments in Adobe Campaign Standard (preview)</span></span>

<span data-ttu-id="1958a-104">Като потребител на прозрения за аудиторията за Dynamics 365 Customer Insights, може да сте създали сегменти, за да направите маркетинговите си кампании по-ефективни, като насочите към съответните аудитории.</span><span class="sxs-lookup"><span data-stu-id="1958a-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="1958a-105">За да използвате сегмент от прозрения за аудиторията в Adobe Experience Platform и приложения като Adobe Campaign Standard, трябва да изпълните няколко стъпки, описани в тази статия.</span><span class="sxs-lookup"><span data-stu-id="1958a-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/ACS-flow.png" alt-text="Схема на процеса на стъпките, описани в тази статия.":::

## <a name="prerequisites"></a><span data-ttu-id="1958a-107">Предварителни изисквания</span><span class="sxs-lookup"><span data-stu-id="1958a-107">Prerequisites</span></span>

-   <span data-ttu-id="1958a-108">Лиценз за Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="1958a-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="1958a-109">Лиценз на Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="1958a-109">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="1958a-110">Акаунт в Azure Blob Storage</span><span class="sxs-lookup"><span data-stu-id="1958a-110">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="1958a-111">Общ преглед на кампания</span><span class="sxs-lookup"><span data-stu-id="1958a-111">Campaign Overview</span></span>

<span data-ttu-id="1958a-112">За да разберете по-добре как можете да използвате сегменти от прозрения за аудиторията в Adobe Experience Platform, нека разгледаме фиктивна примерна кампания.</span><span class="sxs-lookup"><span data-stu-id="1958a-112">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="1958a-113">Да приемем, че вашата компания предлага месечна услуга, базирана на абонамент, на вашите клиенти в САЩ.</span><span class="sxs-lookup"><span data-stu-id="1958a-113">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="1958a-114">Искате да идентифицирате клиенти, чиито абонаменти трябва да бъдат подновени през следващите осем дни, но все още не са подновили абонамента си.</span><span class="sxs-lookup"><span data-stu-id="1958a-114">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="1958a-115">За да задържите тези клиенти, искате да им изпратите промоционална оферта по имейл, използвайки Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="1958a-115">To keep these customers, you want to send them a promotional offer via email, using Adobe Campaign Standard.</span></span>

<span data-ttu-id="1958a-116">В този пример искаме да стартираме промоционалната кампания по имейл веднъж.</span><span class="sxs-lookup"><span data-stu-id="1958a-116">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="1958a-117">Тази статия не обхваща случая на използване на провеждането на кампанията повече от веднъж.</span><span class="sxs-lookup"><span data-stu-id="1958a-117">This article doesn’t cover the use-case of running the campaign more than once.</span></span> <span data-ttu-id="1958a-118">Статистика за аудиторията и Adobe Campaign Standard обаче могат да бъдат конфигурирани да работят и за повтарящ се сценарий на кампанията.</span><span class="sxs-lookup"><span data-stu-id="1958a-118">However, audience insights and Adobe Campaign Standard can be configured to work for a recurring campaign scenario too.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="1958a-119">Идентифицирайте вашата целева аудитория</span><span class="sxs-lookup"><span data-stu-id="1958a-119">Identify your target audience</span></span>

<span data-ttu-id="1958a-120">В нашия сценарий предполагаме, че имейл адресите на клиентите са достъпни в статистика за аудиторията и техните промоционални предпочитания са анализирани, за да се идентифицират членовете на сегмента.</span><span class="sxs-lookup"><span data-stu-id="1958a-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="1958a-121">[Сегментът, който сте определили в статистика за аудиторията](segments.md) е наречен **ChurnProneCustomers** и планирате да изпратите на тези клиенти промоцията по имейл.</span><span class="sxs-lookup"><span data-stu-id="1958a-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Екранна снимка на страницата със сегменти със създадения сегмент ChurnProneCustomers.":::

<span data-ttu-id="1958a-123">Имейлът с оферта, който искате да изпратите, ще съдържа собствено име, фамилно име, и крайната дата на абонамента на клиента.</span><span class="sxs-lookup"><span data-stu-id="1958a-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="1958a-124">Той информира клиентите за отстъпката, която ще получат, ако подновят абонамента си, преди да приключи.</span><span class="sxs-lookup"><span data-stu-id="1958a-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="1958a-125">Експортирайте вашата целева аудитория</span><span class="sxs-lookup"><span data-stu-id="1958a-125">Export your target audience</span></span>

<span data-ttu-id="1958a-126">С идентифицирането на целевата ни аудитория можем да конфигурираме експортирането от статистика за аудиторията в акаунт в Azure Blob Storage.</span><span class="sxs-lookup"><span data-stu-id="1958a-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="1958a-127">В статията за аудиторията отидете на **Администратор** > **Експортиране на местоположения**.</span><span class="sxs-lookup"><span data-stu-id="1958a-127">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="1958a-128">В плочката **Кампания на Adobe** изберете **Настройка**.</span><span class="sxs-lookup"><span data-stu-id="1958a-128">In the **Adobe Campaign** tile, select **Set up**.</span></span>

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Конфигурационна плочка за Adobe Campaign Standard.":::

1. <span data-ttu-id="1958a-130">Предоставете **Показвано име** за тази нова дестинация за износ и след това въведете **Име на акаунта**, **Ключ на акаунта** и **Контейнер** на акаунта на Azure Blob Storage, където искате да експортирате сегмента.</span><span class="sxs-lookup"><span data-stu-id="1958a-130">Provide a **Display name** for this new export destination and then enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Екранна снимка на конфигурацията на акаунт за съхранение. "::: 

   - <span data-ttu-id="1958a-132">За да научите повече за това как да намерите името и ключа за акаунта за хранилището за Blob на Azure, вижте [Управление на настройките на акаунта за съхранение в портала на Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="1958a-132">To learn more about how to find the Azure Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="1958a-133">За да научите как да създадете контейнер, вижте [Създаване на контейнер](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="1958a-133">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="1958a-134">Изберете **Напред**.</span><span class="sxs-lookup"><span data-stu-id="1958a-134">Select **Next**.</span></span>

1. <span data-ttu-id="1958a-135">Изберете сегмента, които искате да експортирате.</span><span class="sxs-lookup"><span data-stu-id="1958a-135">Choose the segment that you want to export.</span></span> <span data-ttu-id="1958a-136">В този пример е така **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="1958a-136">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Екранна снимка на потребителския интерфейс за избор на сегмент с избрания сегмент ChurnProneCustomers.":::

1. <span data-ttu-id="1958a-138">Изберете **Напред**.</span><span class="sxs-lookup"><span data-stu-id="1958a-138">Select **Next**.</span></span>

1. <span data-ttu-id="1958a-139">Сега картографираме полета **Източник** от сегмента с прозрения за аудиторията до имената на полета **Цел** в схемата на профила на Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="1958a-139">Now we map the **Source** fields from the audience insights segment to the **Target** field names in the Adobe Campaign Standard profile schema.</span></span>

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Съпоставяне на полета за конектора на Adobe Campaign Standard.":::

   <span data-ttu-id="1958a-141">Ако искате да добавите още атрибути, изберете **Добавяне на атрибут**.</span><span class="sxs-lookup"><span data-stu-id="1958a-141">If you want to add more attributes, select **Add attribute**.</span></span> <span data-ttu-id="1958a-142">Името на целта може да се различава от името на полето източник, така че все още можете да картографирате изхода на сегменти от прозрения за аудиторията в Adobe Campaign Standard, ако полетата нямат едно и също име в двете системи.</span><span class="sxs-lookup"><span data-stu-id="1958a-142">The target name can be different from the source field name so you can still map segment output from audience insights to Adobe Campaign Standard if the fields don’t have the same name in the two systems.</span></span>

   > [!NOTE]
   > <span data-ttu-id="1958a-143">Имейл адресът се използва като поле за идентичност, но можете да използвате всеки друг идентификатор от профила на клиента за прозрения на аудиторията си, за да съпоставите данните с Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="1958a-143">Email address is used as an identity field but you can use any other identifier from your audience insights customer profile to map data to Adobe Campaign Standard.</span></span>

1. <span data-ttu-id="1958a-144">Изберете **Записване**.</span><span class="sxs-lookup"><span data-stu-id="1958a-144">Select **Save**.</span></span>

<span data-ttu-id="1958a-145">След като запазите дестинацията за износ, ще я намерите на **Администратор** > **Експортиране** > **Моите местоназначения за експортиране**.</span><span class="sxs-lookup"><span data-stu-id="1958a-145">After saving the export destination, you find it on **Admin** > **Exports** > **My export destinations**.</span></span>

:::image type="content" source="media/export-destination-adobe-campaign-standard.png" alt-text="Екранна снимка с подчертан списък на износа и примерен сегмент.":::

<span data-ttu-id="1958a-147">Вече можете да [експортирате сегмента при поискване](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="1958a-147">You can now [export the segment on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="1958a-148">Експортирането също ще се изпълнява с всяко [планирано обновяване](system.md).</span><span class="sxs-lookup"><span data-stu-id="1958a-148">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="1958a-149">Уверете се, че броят на записите в експортирания сегмент е в рамките на разрешеното ограничение от вашия лиценз за Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="1958a-149">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="1958a-150">Експортираните данни се съхраняват в контейнера за Azure Blob Storage, който сте конфигурирали по-горе.</span><span class="sxs-lookup"><span data-stu-id="1958a-150">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="1958a-151">Следният път на папката се създава автоматично във вашия контейнер:</span><span class="sxs-lookup"><span data-stu-id="1958a-151">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="1958a-152">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span><span class="sxs-lookup"><span data-stu-id="1958a-152">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span></span>

<span data-ttu-id="1958a-153">Пример: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span><span class="sxs-lookup"><span data-stu-id="1958a-153">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span></span>

## <a name="configure-adobe-campaign-standard"></a><span data-ttu-id="1958a-154">Конфигуриране на Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="1958a-154">Configure Adobe Campaign Standard</span></span>

<span data-ttu-id="1958a-155">Когато се експортира сегмент от аналитични данни за аудиторията, той съдържа колоните, които сте избрали, докато дефинирате дестинацията за експортиране в предишната стъпка.</span><span class="sxs-lookup"><span data-stu-id="1958a-155">When a segment from audience insights is exported, it contains the columns you selected while defining the export destination in the previous step.</span></span> <span data-ttu-id="1958a-156">Тези данни могат да се използват за [създаване на профили в Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span><span class="sxs-lookup"><span data-stu-id="1958a-156">This data can be used to [create profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span></span>

<span data-ttu-id="1958a-157">За да използваме сегмента в Adobe Campaign Standard, трябва да разширим схемата на профила в Adobe Campaign Standard, за да включим две допълнителни полета.</span><span class="sxs-lookup"><span data-stu-id="1958a-157">To use the segment in Adobe Campaign Standard, we need to extend the profile schema in Adobe Campaign Standard to include two additional fields.</span></span> <span data-ttu-id="1958a-158">Научете как да [разширявате ресурса на профила](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) с нови полета в Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="1958a-158">Learn how to [extend the profile resource](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) with new fields in Adobe Campaign Standard.</span></span>

<span data-ttu-id="1958a-159">В нашия пример тези полета са *Име на сегмента и Дата на сегмента (по избор).*</span><span class="sxs-lookup"><span data-stu-id="1958a-159">In our example, these fields are *Segment Name and Segment Date (optional).*</span></span>

<span data-ttu-id="1958a-160">Ще използваме тези полета, за да идентифицираме профилите в Adobe Campaign Standard, към които искаме да насочим тази кампания.</span><span class="sxs-lookup"><span data-stu-id="1958a-160">We will use these fields to identify the profiles in Adobe Campaign Standard we want to target for this campaign.</span></span>

<span data-ttu-id="1958a-161">Ако в Adobe Campaign Standard няма други записи, освен това, което ще импортирате, можете да пропуснете тази стъпка.</span><span class="sxs-lookup"><span data-stu-id="1958a-161">If there are no other records in Adobe Campaign Standard, other than what you are going to import, you can skip this step.</span></span>

## <a name="import-data-into-adobe-campaign-standard"></a><span data-ttu-id="1958a-162">Импортирайте данни в Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="1958a-162">Import data into Adobe Campaign Standard</span></span>

<span data-ttu-id="1958a-163">Сега, когато всичко е на мястото си, трябва да импортираме подготвените данни за аудиторията от статистика за аудиторията в Adobe Campaign Standard, за да създадете профили.</span><span class="sxs-lookup"><span data-stu-id="1958a-163">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Campaign Standard to create profiles.</span></span> <span data-ttu-id="1958a-164">Научете [как да импортирате профили в Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) с използване на работен поток.</span><span class="sxs-lookup"><span data-stu-id="1958a-164">Learn [how to import profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) using a workflow.</span></span>

<span data-ttu-id="1958a-165">Работният поток за импортиране в изображението по-долу е конфигуриран да се изпълнява на всеки 8 часа и търси експортирани сегменти с прозрения за аудиторията (.csv файл в Azure Blob Storage).</span><span class="sxs-lookup"><span data-stu-id="1958a-165">The import workflow in the image below has been configured to run every 8 hours and looks for exported audience insights segments (.csv file in Azure Blob Storage).</span></span> <span data-ttu-id="1958a-166">Работният поток извлича съдържанието на .csv файл в определен ред на колони.</span><span class="sxs-lookup"><span data-stu-id="1958a-166">The workflow extracts the .csv file content in a specified column order.</span></span> <span data-ttu-id="1958a-167">Този работен процес е създаден, за да извърши основно обработване на грешки и да гарантира, че всеки запис има имейл адрес, преди да хидратира данните в Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="1958a-167">This workflow has been built to perform basic error handling and ensure that each record has an email address before hydrating the data in Adobe Campaign Standard.</span></span> <span data-ttu-id="1958a-168">Работният поток също извлича името на сегмента от името на файла, преди да се добави в данните на профила на ACS.</span><span class="sxs-lookup"><span data-stu-id="1958a-168">The workflow also extracts the segment name from the filename before upserting into ACS Profile data.</span></span>

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Екранна снимка на работен процес за импортиране в потребителския интерфейс на Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a><span data-ttu-id="1958a-170">Извличане на аудитория в Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="1958a-170">Retrieve the audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="1958a-171">След като данните бъдат импортирани в Adobe Campaign Standard, вие [можете да създадете работен поток](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) и да направите [справка](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) за клиентите въз основа на *Име на сегмента* и *Дата на сегмента*, за да изберете профили, идентифицирани за нашата примерна кампания.</span><span class="sxs-lookup"><span data-stu-id="1958a-171">Once the data is imported into Adobe Campaign Standard, you [can create a workflow](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) and [query](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) the customers based on the *Segment Name* and *Segment Date* to select profiles that were identified for our sample campaign.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="1958a-172">Създайте и изпратете имейла с помощта на Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="1958a-172">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="1958a-173">Създайте съдържанието на имейла и след това [тествайте и изпратете](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) имейла си.</span><span class="sxs-lookup"><span data-stu-id="1958a-173">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Примерен имейл с предложение за подновяване от Adobe Campaign Standard.":::