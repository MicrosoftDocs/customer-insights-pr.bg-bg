---
title: Експортирайте данните от Customer Insights в Salesforce Marketing Cloud
description: Научете как да конфигурирате връзката и да експортирате в Salesforce Marketing Cloud.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 123f8b2dbb6140785dec6c1b4164d2f513f66a53
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314576"
---
# <a name="export-segments-and-other-data-to-salesforce-marketing-cloud-preview"></a><span data-ttu-id="2afcc-103">Експортиране на сегменти и други данни в Salesforce Marketing Cloud (преглед)</span><span class="sxs-lookup"><span data-stu-id="2afcc-103">Export segments and other data to Salesforce Marketing Cloud (preview)</span></span>

<span data-ttu-id="2afcc-104">Използвайте данните на клиентите си в Salesforce Marketing Cloud, като ги експортирате чрез местоположението на Secure File Transfer Protocol (SFTP).</span><span class="sxs-lookup"><span data-stu-id="2afcc-104">Use your customer data in Salesforce Marketing Cloud by exporting them through a Secure File Transfer Protocol (SFTP) location.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="2afcc-105">Предварителни изисквания за връзка</span><span class="sxs-lookup"><span data-stu-id="2afcc-105">Prerequisites for connection</span></span>

- <span data-ttu-id="2afcc-106">Наличност на SFTP хост и съответни администраторски идентификационни данни.</span><span class="sxs-lookup"><span data-stu-id="2afcc-106">Availability of an SFTP host and corresponding admin credentials.</span></span> [<span data-ttu-id="2afcc-107">Как да настроите SFTP местоположения за Salesforce Marketing Cloud</span><span class="sxs-lookup"><span data-stu-id="2afcc-107">How to setup SFTP locations for Salesforce Marketing Cloud</span></span>](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) 

## <a name="known-limitations"></a><span data-ttu-id="2afcc-108">Известни ограничения</span><span class="sxs-lookup"><span data-stu-id="2afcc-108">Known limitations</span></span>

- <span data-ttu-id="2afcc-109">Времетраенето на експортиране зависи от производителността на вашата система.</span><span class="sxs-lookup"><span data-stu-id="2afcc-109">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="2afcc-110">Препоръчваме две ядра на процесора и 1 Gb памет като минимална конфигурация на вашия сървър.</span><span class="sxs-lookup"><span data-stu-id="2afcc-110">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="2afcc-111">Експортирането на обекти с до 100 милиона потребителски профила може да отнеме 90 минути при използване на препоръчителната минимална конфигурация.</span><span class="sxs-lookup"><span data-stu-id="2afcc-111">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration.</span></span> 

## <a name="set-up-the-connection-to-salesforce-marketing-cloud"></a><span data-ttu-id="2afcc-112">Настройте връзката с Salesforce Marketing Cloud</span><span class="sxs-lookup"><span data-stu-id="2afcc-112">Set up the connection to Salesforce Marketing Cloud</span></span>

1. <span data-ttu-id="2afcc-113">Отидете на **Администратор** > **Връзки**.</span><span class="sxs-lookup"><span data-stu-id="2afcc-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="2afcc-114">Изберете **Добавете връзка** и изберете **Salesforce Marketing Cloud** за конфигуриране на връзката.</span><span class="sxs-lookup"><span data-stu-id="2afcc-114">Select **Add connection** and choose **Salesforce Marketing Cloud** to configure the connection.</span></span>

1. <span data-ttu-id="2afcc-115">Въведете разпознаваемо име за връзката в полето **Показвано име**.</span><span class="sxs-lookup"><span data-stu-id="2afcc-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="2afcc-116">Показваното име и типът описват тази връзка.</span><span class="sxs-lookup"><span data-stu-id="2afcc-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="2afcc-117">Препоръчваме да изберете име, което обяснява целта на връзката.</span><span class="sxs-lookup"><span data-stu-id="2afcc-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="2afcc-118">Изберете кой може да използва тази връзка.</span><span class="sxs-lookup"><span data-stu-id="2afcc-118">Choose who can use this connection.</span></span> <span data-ttu-id="2afcc-119">Ако не предприемете нищо, по подразбиране ще е Администратори.</span><span class="sxs-lookup"><span data-stu-id="2afcc-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="2afcc-120">За повече информация вижте [Разрешаване на сътрудници да използват връзка за експортиране](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="2afcc-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="2afcc-121">Предоставете **Потребителско име**, **Парола** и **Име на хост** и **папка за експортиране** за вашия SFTP акаунт.</span><span class="sxs-lookup"><span data-stu-id="2afcc-121">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="2afcc-122">Изберете **Проверка**, за да тествате връзката.</span><span class="sxs-lookup"><span data-stu-id="2afcc-122">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="2afcc-123">Изберете **Приемам**, за да потвърдите **Поверителност на данните и съответствие**.</span><span class="sxs-lookup"><span data-stu-id="2afcc-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="2afcc-124">Изберете **Записване**, за да завършите връзката.</span><span class="sxs-lookup"><span data-stu-id="2afcc-124">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="2afcc-125">Конфигуриране на експортиране</span><span class="sxs-lookup"><span data-stu-id="2afcc-125">Configure an export</span></span>

<span data-ttu-id="2afcc-126">Можете да конфигурирате това експортиране, ако имате достъп до връзка от този тип.</span><span class="sxs-lookup"><span data-stu-id="2afcc-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="2afcc-127">За повече информация вижте [Разрешения, необходими за конфигуриране на експортиране](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="2afcc-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="2afcc-128">Отидете на **Данни** > **Експортиране**.</span><span class="sxs-lookup"><span data-stu-id="2afcc-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="2afcc-129">За да създадете ново експортиране, изберете **Добавяне на местоназначение**.</span><span class="sxs-lookup"><span data-stu-id="2afcc-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="2afcc-130">В полето **Връзка за експортиране** изберете връзка от секцията SFTP.</span><span class="sxs-lookup"><span data-stu-id="2afcc-130">In the **Connection for export** field, choose a connection from the SFTP section.</span></span> <span data-ttu-id="2afcc-131">Ако не виждате името на тази секция, няма достъпни за вас връзки от този тип.</span><span class="sxs-lookup"><span data-stu-id="2afcc-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="2afcc-132">Изберете дали искате да експортирате данните **архивирани** или **разархивирани** и **разделителя на поле** за експортираните файлове.</span><span class="sxs-lookup"><span data-stu-id="2afcc-132">Choose if you want to export your data **Gzipped** or **Unzipped** and the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="2afcc-133">Изберете обектите, например сегменти, които искате да експортирате.</span><span class="sxs-lookup"><span data-stu-id="2afcc-133">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="2afcc-134">Всеки избран обект ще се раздели на до пет изходни файла при експортиране.</span><span class="sxs-lookup"><span data-stu-id="2afcc-134">Each selected entity will be split up into up to five output files when exported.</span></span> 

1. <span data-ttu-id="2afcc-135">Изберете **Записване**.</span><span class="sxs-lookup"><span data-stu-id="2afcc-135">Select **Save**.</span></span>

<span data-ttu-id="2afcc-136">Запазването на експортиране не го изпълнява незабавно.</span><span class="sxs-lookup"><span data-stu-id="2afcc-136">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="2afcc-137">Експортирането се изпълнява с всяко [планирано обновяване](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="2afcc-137">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="2afcc-138">Може също [да експортирате данни при поискване](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="2afcc-138">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a><span data-ttu-id="2afcc-139">Импортиране на данните от Customer Insights от SFTP местоположение в Salesforce Marketing Cloud</span><span class="sxs-lookup"><span data-stu-id="2afcc-139">Import Customer Insights data from SFTP location to Salesforce Marketing Cloud</span></span>

1. <span data-ttu-id="2afcc-140">Създайте [разширения за данни в Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) за да импортирате файла с данни на Customer Insights от SFTP местоположението.</span><span class="sxs-lookup"><span data-stu-id="2afcc-140">Create [data extensions in Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) to import the Customer Insights data file from the SFTP location.</span></span>

2. <span data-ttu-id="2afcc-141">[Импортирайте данните от SFTP местоположението](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) в разширението за данни на Salesforce Marketing Cloud.</span><span class="sxs-lookup"><span data-stu-id="2afcc-141">[Import the data from the SFTP location](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) into the Salesforce Marketing Cloud data extension.</span></span> 

3. <span data-ttu-id="2afcc-142">Настройте автоматизацията за импортиране на данните в разширенията за данни.</span><span class="sxs-lookup"><span data-stu-id="2afcc-142">Set up the automation to import the data into the data extensions.</span></span> <span data-ttu-id="2afcc-143">Научете повече за [автоматизиране на падането на файлове и автоматизирани програми](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="2afcc-143">Learn more about [file drop automations and scheduled automations](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).</span></span>

   <span data-ttu-id="2afcc-144">Определете [автоматизация на падането на файлове](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) или [планирана автоматизация](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="2afcc-144">Define a [file drop automation](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) or a  [scheduled automation](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).</span></span> 

<span data-ttu-id="2afcc-145">Ето пример за [автоматизация със SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="2afcc-145">Here's an example of [an automation with SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="2afcc-146">Поверителност и съответствие на данните</span><span class="sxs-lookup"><span data-stu-id="2afcc-146">Data privacy and compliance</span></span>

<span data-ttu-id="2afcc-147">Когато активирате Dynamics 365 Customer Insights, за да предавате данни чрез SFTP, разрешавате прехвърляне на данни извън границата за съответствие за Dynamics 365 Customer Insights, включително потенциално чувствителни данни като Лични данни.</span><span class="sxs-lookup"><span data-stu-id="2afcc-147">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="2afcc-148">Microsoft ще прехвърли такива данни по ваше указание, но вие носите отговорност да гарантирате, че местоположението за експортиране отговаря на всички задължения за поверителност или сигурност, които може да имате.</span><span class="sxs-lookup"><span data-stu-id="2afcc-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="2afcc-149">За информация посетете [Декларация за поверителност Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="2afcc-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="2afcc-150">Вашият администратор на Dynamics 365 Customer Insights да премахнете това местоназначение за експортиране по всяко време, за да прекратите използването на тази функционалност.</span><span class="sxs-lookup"><span data-stu-id="2afcc-150">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
