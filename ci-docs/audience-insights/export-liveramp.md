---
title: LiveRamp съединител
description: Научете как да конфигурирате връзката и да експортирате в LiveRamp.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 987457966fe1fc034d9e3cd2a1ce33902c7a84f4
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760314"
---
# <a name="export-segments-to-liverampreg-preview"></a><span data-ttu-id="c8c56-103">Експортиране на сегменти в LiveRamp&reg; (преглед)</span><span class="sxs-lookup"><span data-stu-id="c8c56-103">Export segments to LiveRamp&reg; (preview)</span></span>

<span data-ttu-id="c8c56-104">Активирайте данните си в LiveRamp, за да се свържете с над 500 цифрови, социални и телевизионни платформи.</span><span class="sxs-lookup"><span data-stu-id="c8c56-104">Activate your data in LiveRamp to connect with over 500 platforms across digital, social, and TVs.</span></span> <span data-ttu-id="c8c56-105">Работете с вашите данни в LiveRamp за насочване, потискане и персонализиране на рекламни кампании.</span><span class="sxs-lookup"><span data-stu-id="c8c56-105">Work with your data in LiveRamp to target, suppress, and personalize ad campaigns.</span></span>

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="c8c56-106">Предварителни изисквания за връзка</span><span class="sxs-lookup"><span data-stu-id="c8c56-106">Prerequisites for a connection</span></span>

- <span data-ttu-id="c8c56-107">За да използвате този конектор, се нуждаете от абонамент в LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="c8c56-107">You need a LiveRamp subscription to use this connector.</span></span>
- <span data-ttu-id="c8c56-108">За да получите абонамент, [свържете се с LiveRamp](https://liveramp.com/contact/) директно.</span><span class="sxs-lookup"><span data-stu-id="c8c56-108">To get a subscription, [contact LiveRamp](https://liveramp.com/contact/) directly.</span></span> <span data-ttu-id="c8c56-109">[Научете повече за Въвеждането в LiveRamp](https://liveramp.com/our-platform/data-onboarding/).</span><span class="sxs-lookup"><span data-stu-id="c8c56-109">[Learn more about LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span></span>

## <a name="set-up-connection-to-liveramp"></a><span data-ttu-id="c8c56-110">Настройване на връзка към LiveRamp</span><span class="sxs-lookup"><span data-stu-id="c8c56-110">Set up connection to LiveRamp</span></span>

1. <span data-ttu-id="c8c56-111">Отидете на **Администратор** > **Връзки**.</span><span class="sxs-lookup"><span data-stu-id="c8c56-111">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="c8c56-112">Изберете **Добавяне на връзка** и изберете **LiveRamp** за конфигуриране на връзката.</span><span class="sxs-lookup"><span data-stu-id="c8c56-112">Select **Add connection** and choose **LiveRamp** to configure the connection.</span></span>

1. <span data-ttu-id="c8c56-113">Въведете разпознаваемо име за връзката в полето **Показвано име**.</span><span class="sxs-lookup"><span data-stu-id="c8c56-113">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="c8c56-114">Показваното име и типът описват тази връзка.</span><span class="sxs-lookup"><span data-stu-id="c8c56-114">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="c8c56-115">Препоръчваме да изберете име, което обяснява целта на връзката.</span><span class="sxs-lookup"><span data-stu-id="c8c56-115">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="c8c56-116">Изберете кой може да използва тази връзка.</span><span class="sxs-lookup"><span data-stu-id="c8c56-116">Choose who can use this connection.</span></span> <span data-ttu-id="c8c56-117">Ако не предприемете нищо, по подразбиране ще е Администратори.</span><span class="sxs-lookup"><span data-stu-id="c8c56-117">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="c8c56-118">За повече информация вижте [Разрешаване на сътрудници да използват връзка за експортиране](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="c8c56-118">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="c8c56-119">Въведете **Потребител** и **парола** за вашия акаунт на LiveRamp Secure FTP (SFTP).</span><span class="sxs-lookup"><span data-stu-id="c8c56-119">Provide a **Username** and **Password** for your LiveRamp Secure FTP (SFTP) account.</span></span>
<span data-ttu-id="c8c56-120">Тези идентификационни данни могат да се различават от вашите идентификационни данни за въвеждане в LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="c8c56-120">These credentials may be different from your LiveRamp Onboarding credentials.</span></span>

1. <span data-ttu-id="c8c56-121">Изберете **Проверка**, за да тествате връзката с LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="c8c56-121">Select **Verify** to test the connection to LiveRamp.</span></span>

1. <span data-ttu-id="c8c56-122">След успешна проверка, дайте своето съгласие за **Поверителност и спазване на данните**, като изберете отметката **Съгласявам се**.</span><span class="sxs-lookup"><span data-stu-id="c8c56-122">After successful verification, provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="c8c56-123">Изберете **Записване**, за да завършите връзката.</span><span class="sxs-lookup"><span data-stu-id="c8c56-123">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="c8c56-124">Конфигуриране на експортиране</span><span class="sxs-lookup"><span data-stu-id="c8c56-124">Configure an export</span></span>

<span data-ttu-id="c8c56-125">Можете да конфигурирате това експортиране, ако имате достъп до връзка от този тип.</span><span class="sxs-lookup"><span data-stu-id="c8c56-125">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="c8c56-126">За повече информация вижте [Разрешения, необходими за конфигуриране на експортиране](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="c8c56-126">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="c8c56-127">Отидете на **Данни** > **Експортиране**.</span><span class="sxs-lookup"><span data-stu-id="c8c56-127">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="c8c56-128">За да създадете ново експортиране, изберете **Добавяне на местоназначение**.</span><span class="sxs-lookup"><span data-stu-id="c8c56-128">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="c8c56-129">В полето **Връзка за експортиране** изберете връзка от секцията LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="c8c56-129">In the **Connection for export** field, choose a connection from the LiveRamp section.</span></span> <span data-ttu-id="c8c56-130">Ако не виждате името на тази секция, няма достъпни за вас връзки от този тип.</span><span class="sxs-lookup"><span data-stu-id="c8c56-130">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="c8c56-131">В полето **Изберете своя ключов идентификатор** изберете **електронна поща**, **Име и адрес** или **телефон**, които да изпратите на LiveRamp за разрешаване на самоличността.</span><span class="sxs-lookup"><span data-stu-id="c8c56-131">In the **Choose your key identifier** field, select **Email**,  **Name and address**, or **Phone** to send to LiveRamp for identity resolution.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c8c56-132">![Съединител LiveRamp с нанасяне на атрибути](media/export-liveramp-segments.png "Съединител LiveRamp с нанасяне на атрибути")</span><span class="sxs-lookup"><span data-stu-id="c8c56-132">![LiveRamp connector with attribute mapping](media/export-liveramp-segments.png "LiveRamp connector with attribute mapping")</span></span>

1. <span data-ttu-id="c8c56-133">Нанесете съответните атрибути от обединения клиент за избрания идентификатор на ключ.</span><span class="sxs-lookup"><span data-stu-id="c8c56-133">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>

1. <span data-ttu-id="c8c56-134">Изберете **Добавяне на атрибут**, за да нанесете още атрибути, които да изпратите до LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="c8c56-134">Select **Add attribute** to map more attributes to send to LiveRamp.</span></span>

   > [!TIP]
   > <span data-ttu-id="c8c56-135">Изпращането на повече атрибути на ключови идентификатори на LiveRamp вероятно ще ви осигури по-висока степен на съвпадение.</span><span class="sxs-lookup"><span data-stu-id="c8c56-135">Sending more key identifier attributes to LiveRamp is likely to get you a higher match rate.</span></span>

1. <span data-ttu-id="c8c56-136">Изберете сегментите, които искате да експортирате в LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="c8c56-136">Select the segments you want to export to LiveRamp.</span></span>

1. <span data-ttu-id="c8c56-137">Изберете **Записване**.</span><span class="sxs-lookup"><span data-stu-id="c8c56-137">Select **Save**.</span></span>

<span data-ttu-id="c8c56-138">Запазването на експортиране не го изпълнява незабавно.</span><span class="sxs-lookup"><span data-stu-id="c8c56-138">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="c8c56-139">Експортирането се изпълнява с всяко [планирано обновяване](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="c8c56-139">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="c8c56-140">Може също [да експортирате данни при поискване](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="c8c56-140">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="c8c56-141">Поверителност и съответствие на данните</span><span class="sxs-lookup"><span data-stu-id="c8c56-141">Data privacy and compliance</span></span>

<span data-ttu-id="c8c56-142">Когато активирате Dynamics 365 Customer Insights, за да предавате данни на Liveramp, разрешавате прехвърляне на данни извън границата за съответствие за Dynamics 365 Customer Insights, включително потенциално чувствителни данни като Лични данни.</span><span class="sxs-lookup"><span data-stu-id="c8c56-142">When you enable Dynamics 365 Customer Insights to transmit data to Liveramp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="c8c56-143">Microsoft ще прехвърли такива данни по ваше указание, но вие носите отговорност да гарантирате, че Liveramp отговаря на всички задължения за поверителност или сигурност, които може да имате.</span><span class="sxs-lookup"><span data-stu-id="c8c56-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Liveramp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="c8c56-144">За информация посетете [Декларация за поверителност Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="c8c56-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="c8c56-145">Вашият администратор на Dynamics 365 Customer Insights да премахнете това местоназначение за експортиране по всяко време, за да прекратите използването на тази функционалност.</span><span class="sxs-lookup"><span data-stu-id="c8c56-145">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
