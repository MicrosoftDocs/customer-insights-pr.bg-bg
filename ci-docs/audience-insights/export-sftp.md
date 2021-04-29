---
title: Експортирайте данните от Customer Insights в SFTP хостове
description: Научете как да конфигурирате връзката и да експортирате в SFTP местоположение.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 96c6026aded315008439740646827ca910cead90
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760406"
---
# <a name="export-segment-lists-and-other-data-to-sftp-preview"></a><span data-ttu-id="a38cc-103">Експортиране на списъци със сегменти и други данни в SFTP (преглед)</span><span class="sxs-lookup"><span data-stu-id="a38cc-103">Export segment lists and other data to SFTP (preview)</span></span>

<span data-ttu-id="a38cc-104">Използвайте клиентските данни в приложения на трети страни, като ги експортирате в местоположение на защитения протокол за предаване на файлове (SFTP).</span><span class="sxs-lookup"><span data-stu-id="a38cc-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol (SFTP) location.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="a38cc-105">Предварителни изисквания за връзка</span><span class="sxs-lookup"><span data-stu-id="a38cc-105">Prerequisites for connection</span></span>

- <span data-ttu-id="a38cc-106">Наличие на SFTP хост и съответни идентификационни данни.</span><span class="sxs-lookup"><span data-stu-id="a38cc-106">Availability of an SFTP host and corresponding credentials.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="a38cc-107">Известни ограничения</span><span class="sxs-lookup"><span data-stu-id="a38cc-107">Known limitations</span></span>

- <span data-ttu-id="a38cc-108">Времетраенето на експортиране зависи от производителността на вашата система.</span><span class="sxs-lookup"><span data-stu-id="a38cc-108">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="a38cc-109">Препоръчваме две ядра на процесора и 1 Gb памет като минимална конфигурация на вашия сървър.</span><span class="sxs-lookup"><span data-stu-id="a38cc-109">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="a38cc-110">Експортирането на обекти с до 100 милиона клиентски профила може да отнеме 90 минути при използване на препоръчителната минимална конфигурация на две ядра на процесора и 1 Gb памет.</span><span class="sxs-lookup"><span data-stu-id="a38cc-110">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration of two CPU cores and 1 Gb of memory.</span></span> 

## <a name="set-up-connection-to-sftp"></a><span data-ttu-id="a38cc-111">Настройване на връзка със SFTP</span><span class="sxs-lookup"><span data-stu-id="a38cc-111">Set up connection to SFTP</span></span>

1. <span data-ttu-id="a38cc-112">Отидете на **Администратор** > **Връзки**.</span><span class="sxs-lookup"><span data-stu-id="a38cc-112">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="a38cc-113">Изберете **Добавяне на връзка** и изберете **SFTP** за конфигуриране на връзката.</span><span class="sxs-lookup"><span data-stu-id="a38cc-113">Select **Add connection** and choose **SFTP** to configure the connection.</span></span>

1. <span data-ttu-id="a38cc-114">Въведете разпознаваемо име за връзката в полето **Показвано име**.</span><span class="sxs-lookup"><span data-stu-id="a38cc-114">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="a38cc-115">Показваното име и типът описват тази връзка.</span><span class="sxs-lookup"><span data-stu-id="a38cc-115">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="a38cc-116">Препоръчваме да изберете име, което обяснява целта на връзката.</span><span class="sxs-lookup"><span data-stu-id="a38cc-116">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="a38cc-117">Изберете кой може да използва тази връзка.</span><span class="sxs-lookup"><span data-stu-id="a38cc-117">Choose who can use this connection.</span></span> <span data-ttu-id="a38cc-118">Ако не предприемете нищо, по подразбиране ще е Администратори.</span><span class="sxs-lookup"><span data-stu-id="a38cc-118">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="a38cc-119">За повече информация вижте [Разрешаване на сътрудници да използват връзка за експортиране](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="a38cc-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="a38cc-120">Предоставете **Потребителско име**, **Парола** и **Име на хост** и **папка за експортиране** за вашия SFTP акаунт.</span><span class="sxs-lookup"><span data-stu-id="a38cc-120">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="a38cc-121">Изберете **Проверка**, за да тествате връзката.</span><span class="sxs-lookup"><span data-stu-id="a38cc-121">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="a38cc-122">Изберете дали искате да експортирате данните **архивирани** или **разархивирани** и **разделителя на поле** за експортираните файлове.</span><span class="sxs-lookup"><span data-stu-id="a38cc-122">Choose if you want to export your data **Gzipped** or **Unzipped** and the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="a38cc-123">Изберете **Приемам**, за да потвърдите **Поверителност на данните и съответствие**.</span><span class="sxs-lookup"><span data-stu-id="a38cc-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="a38cc-124">Изберете **Записване**, за да завършите връзката.</span><span class="sxs-lookup"><span data-stu-id="a38cc-124">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="a38cc-125">Конфигуриране на експортиране</span><span class="sxs-lookup"><span data-stu-id="a38cc-125">Configure an export</span></span>

<span data-ttu-id="a38cc-126">Можете да конфигурирате това експортиране, ако имате достъп до връзка от този тип.</span><span class="sxs-lookup"><span data-stu-id="a38cc-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="a38cc-127">За повече информация вижте [Разрешения, необходими за конфигуриране на експортиране](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="a38cc-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="a38cc-128">Отидете на **Данни** > **Експортиране**.</span><span class="sxs-lookup"><span data-stu-id="a38cc-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="a38cc-129">За да създадете ново експортиране, изберете **Добавяне на местоназначение**.</span><span class="sxs-lookup"><span data-stu-id="a38cc-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="a38cc-130">В полето **Връзка за експортиране** изберете връзка от секцията SFTP.</span><span class="sxs-lookup"><span data-stu-id="a38cc-130">In the **Connection for export** field, choose a connection from the SFTP section.</span></span> <span data-ttu-id="a38cc-131">Ако не виждате името на тази секция, няма достъпни за вас връзки от този тип.</span><span class="sxs-lookup"><span data-stu-id="a38cc-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="a38cc-132">Изберете обектите, например сегменти, които искате да експортирате.</span><span class="sxs-lookup"><span data-stu-id="a38cc-132">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="a38cc-133">Всеки избран обект ще се раздели на до пет изходни файла при експортиране.</span><span class="sxs-lookup"><span data-stu-id="a38cc-133">Each selected entity will be split up into up to five output files when exported.</span></span> 

1. <span data-ttu-id="a38cc-134">Изберете **Записване**.</span><span class="sxs-lookup"><span data-stu-id="a38cc-134">Select **Save**.</span></span>

<span data-ttu-id="a38cc-135">Запазването на експортиране не го изпълнява незабавно.</span><span class="sxs-lookup"><span data-stu-id="a38cc-135">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="a38cc-136">Експортирането се изпълнява с всяко [планирано обновяване](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="a38cc-136">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="a38cc-137">Може също [да експортирате данни при поискване](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="a38cc-137">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="a38cc-138">Поверителност и съответствие на данните</span><span class="sxs-lookup"><span data-stu-id="a38cc-138">Data privacy and compliance</span></span>

<span data-ttu-id="a38cc-139">Когато активирате Dynamics 365 Customer Insights, за да предавате данни чрез SFTP, разрешавате прехвърляне на данни извън границата за съответствие за Dynamics 365 Customer Insights, включително потенциално чувствителни данни като Лични данни.</span><span class="sxs-lookup"><span data-stu-id="a38cc-139">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="a38cc-140">Microsoft ще прехвърли такива данни по ваше указание, но вие носите отговорност да гарантирате, че местоположението за експортиране отговаря на всички задължения за поверителност или сигурност, които може да имате.</span><span class="sxs-lookup"><span data-stu-id="a38cc-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="a38cc-141">За информация посетете [Декларация за поверителност Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="a38cc-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="a38cc-142">Вашият администратор на Dynamics 365 Customer Insights да премахнете това местоназначение за експортиране по всяко време, за да прекратите използването на тази функционалност.</span><span class="sxs-lookup"><span data-stu-id="a38cc-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
