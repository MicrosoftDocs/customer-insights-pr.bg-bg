---
title: Експортирайте данните от Customer Insights в SFTP хостове
description: Научете как да конфигурирате връзката към хост SFTP.
ms.date: 01/27/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 9ec14fafa8f99e34b95349371298082e166535d0
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598372"
---
# <a name="connector-for-sftp-preview"></a><span data-ttu-id="fc099-103">Конектор за SFTP (преглед)</span><span class="sxs-lookup"><span data-stu-id="fc099-103">Connector for SFTP (preview)</span></span>

<span data-ttu-id="fc099-104">Използвайте клиентските данни в приложения на трети страни, като ги експортирате в хост със Secure File Transfer Protocol (SFTP).</span><span class="sxs-lookup"><span data-stu-id="fc099-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol (SFTP) host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="fc099-105">Предварителни изисквания</span><span class="sxs-lookup"><span data-stu-id="fc099-105">Prerequisites</span></span>

- <span data-ttu-id="fc099-106">Наличие на SFTP хост и съответни идентификационни данни.</span><span class="sxs-lookup"><span data-stu-id="fc099-106">Availability of an SFTP host and corresponding credentials.</span></span>

## <a name="connect-to-sftp"></a><span data-ttu-id="fc099-107">Свързване с SFTP</span><span class="sxs-lookup"><span data-stu-id="fc099-107">Connect to SFTP</span></span>

1. <span data-ttu-id="fc099-108">Отидете на **Администратор** > **Експортиране на дестинации**.</span><span class="sxs-lookup"><span data-stu-id="fc099-108">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="fc099-109">Под **SFTP** изберете **Настройване**.</span><span class="sxs-lookup"><span data-stu-id="fc099-109">Under **SFTP**, select **Set up**.</span></span>

1. <span data-ttu-id="fc099-110">Въведете разпознаваемо име за местоназначението в полето **Показвано име**.</span><span class="sxs-lookup"><span data-stu-id="fc099-110">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="fc099-111">Предоставете **Потребителско име**, **Парола** и **Име на хост** и **папка за експортиране** за вашия SFTP акаунт.</span><span class="sxs-lookup"><span data-stu-id="fc099-111">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="fc099-112">Изберете **Проверка**, за да тествате връзката.</span><span class="sxs-lookup"><span data-stu-id="fc099-112">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="fc099-113">След успешна проверка изберете дали искате да експортирате данните си **Gzipped** или **Разархивирани** и изберете **разделител на полето** за експортираните файлове.</span><span class="sxs-lookup"><span data-stu-id="fc099-113">After successful verification, choose if you want to export your data **Gzipped** or **Unzipped**, and select the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="fc099-114">Изберете **Приемам**, за да потвърдите **Поверителност на данните и съответствие**.</span><span class="sxs-lookup"><span data-stu-id="fc099-114">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="fc099-115">Изберете **Напред**, за да започнете да конфигурирате експортирането.</span><span class="sxs-lookup"><span data-stu-id="fc099-115">Select **Next** to start configuring the export.</span></span>

## <a name="configure-the-export"></a><span data-ttu-id="fc099-116">Конфигуриране на експортирането</span><span class="sxs-lookup"><span data-stu-id="fc099-116">Configure the export</span></span>

1. <span data-ttu-id="fc099-117">Изберете обектите, например сегменти, които искате да експортирате.</span><span class="sxs-lookup"><span data-stu-id="fc099-117">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="fc099-118">Всеки избран обект ще има до пет изходни файла при експортиране.</span><span class="sxs-lookup"><span data-stu-id="fc099-118">Each selected entity will be up to five output files when exported.</span></span> 

1. <span data-ttu-id="fc099-119">Изберете **Записване**.</span><span class="sxs-lookup"><span data-stu-id="fc099-119">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="fc099-120">Експортиране на данните</span><span class="sxs-lookup"><span data-stu-id="fc099-120">Export the data</span></span>

<span data-ttu-id="fc099-121">Можете да [експортирате данни при поискване](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="fc099-121">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="fc099-122">Експортирането също ще се изпълнява с всяко [планирано обновяване](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="fc099-122">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="fc099-123">Известни ограничения</span><span class="sxs-lookup"><span data-stu-id="fc099-123">Known limitations</span></span>

- <span data-ttu-id="fc099-124">Времетраенето на експортиране зависи от производителността на вашата система.</span><span class="sxs-lookup"><span data-stu-id="fc099-124">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="fc099-125">Препоръчваме две ядра на процесора и 1 Gb памет като минимална конфигурация на вашия сървър.</span><span class="sxs-lookup"><span data-stu-id="fc099-125">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="fc099-126">Експортирането на обекти с до 100 милиона клиентски профила може да отнеме 90 минути при използване на препоръчителната минимална конфигурация на две ядра на процесора и 1 Gb памет.</span><span class="sxs-lookup"><span data-stu-id="fc099-126">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration of two CPU cores and 1 Gb of memory.</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="fc099-127">Поверителност и съответствие на данните</span><span class="sxs-lookup"><span data-stu-id="fc099-127">Data privacy and compliance</span></span>

<span data-ttu-id="fc099-128">Когато активирате Dynamics 365 Customer Insights, за да предавате данни чрез SFTP, разрешавате прехвърляне на данни извън границата за съответствие за Dynamics 365 Customer Insights, включително потенциално чувствителни данни като Лични данни.</span><span class="sxs-lookup"><span data-stu-id="fc099-128">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="fc099-129">Microsoft ще прехвърли такива данни по ваше указание, но вие носите отговорност да гарантирате, че местоположението за експортиране отговаря на всички задължения за поверителност или сигурност, които може да имате.</span><span class="sxs-lookup"><span data-stu-id="fc099-129">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="fc099-130">За информация посетете [Декларация за поверителност Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="fc099-130">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="fc099-131">Вашият администратор на Dynamics 365 Customer Insights да премахнете това местоназначение за експортиране по всяко време, за да прекратите използването на тази функционалност.</span><span class="sxs-lookup"><span data-stu-id="fc099-131">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]