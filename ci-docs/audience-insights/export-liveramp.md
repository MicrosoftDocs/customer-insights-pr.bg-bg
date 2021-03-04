---
title: LiveRamp съединител
description: Научете как да експортирате данни към LiveRamp.
ms.date: 12/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 64d781f52e8124fc3e83a7b84f468830c5249cfd
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270145"
---
# <a name="liverampreg-connector-preview"></a><span data-ttu-id="f06ab-103">Конектор на LiveRamp&reg; (преглед)</span><span class="sxs-lookup"><span data-stu-id="f06ab-103">LiveRamp&reg; connector (preview)</span></span>

<span data-ttu-id="f06ab-104">Активирайте данните си в LiveRamp, за да се свържете с над 500 платформи в цифрови, социални и телевизионни екосистеми.</span><span class="sxs-lookup"><span data-stu-id="f06ab-104">Activate your data in LiveRamp to connect with over 500 platforms across digital, social, and TV ecosystems.</span></span> <span data-ttu-id="f06ab-105">Работете с вашите данни в LiveRamp за насочване, потискане и персонализиране на рекламни кампании.</span><span class="sxs-lookup"><span data-stu-id="f06ab-105">Work with your data in LiveRamp to target, suppress, and personalize ad campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f06ab-106">Предварителни изисквания</span><span class="sxs-lookup"><span data-stu-id="f06ab-106">Prerequisites</span></span>

- <span data-ttu-id="f06ab-107">За да използвате този конектор, се нуждаете от абонамент в LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="f06ab-107">You need a LiveRamp subscription to use this connector.</span></span>
- <span data-ttu-id="f06ab-108">За да получите абонамент, [свържете се с LiveRamp](https://liveramp.com/contact/) директно.</span><span class="sxs-lookup"><span data-stu-id="f06ab-108">To get a subscription, [contact LiveRamp](https://liveramp.com/contact/) directly.</span></span> <span data-ttu-id="f06ab-109">[Научете повече за Въвеждането в LiveRamp](https://liveramp.com/our-platform/data-onboarding/).</span><span class="sxs-lookup"><span data-stu-id="f06ab-109">[Learn more about LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span></span>

## <a name="connect-to-liveramp"></a><span data-ttu-id="f06ab-110">Свържете се с LiveRamp</span><span class="sxs-lookup"><span data-stu-id="f06ab-110">Connect to LiveRamp</span></span>

1. <span data-ttu-id="f06ab-111">В статията за аудиторията отидете на **Администратор** > **Експортиране на местоположения**.</span><span class="sxs-lookup"><span data-stu-id="f06ab-111">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="f06ab-112">В плочката **LiveRamp** изберете **Настройка**.</span><span class="sxs-lookup"><span data-stu-id="f06ab-112">In the **LiveRamp** tile, select **Set up**.</span></span>

1. <span data-ttu-id="f06ab-113">Въведете разпознаваемо име за местоназначението в полето **Показвано име**.</span><span class="sxs-lookup"><span data-stu-id="f06ab-113">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="f06ab-114">Въведете **Потребител** и **парола** за вашия акаунт на LiveRamp Secure FTP (SFTP).</span><span class="sxs-lookup"><span data-stu-id="f06ab-114">Provide a **Username** and **Password** for your LiveRamp Secure FTP (SFTP) account.</span></span>
<span data-ttu-id="f06ab-115">Тези идентификационни данни могат да се различават от вашите идентификационни данни за въвеждане в LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="f06ab-115">These credentials may be different from your LiveRamp Onboarding credentials.</span></span>

1. <span data-ttu-id="f06ab-116">Изберете **Проверка**, за да тествате връзката с LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="f06ab-116">Select **Verify** to test the connection to LiveRamp.</span></span>

1. <span data-ttu-id="f06ab-117">След успешна проверка, дайте своето съгласие за **Поверителност и спазване на данните**, като изберете отметката **Съгласявам се**.</span><span class="sxs-lookup"><span data-stu-id="f06ab-117">After successful verification, provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="f06ab-118">Изберете **Напред**, за да настроите конектора на LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="f06ab-118">Select **Next** to set up the LiveRamp connector.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="f06ab-119">Конфигуриране на конектор</span><span class="sxs-lookup"><span data-stu-id="f06ab-119">Configure the connector</span></span>

1. <span data-ttu-id="f06ab-120">В полето **Изберете своя ключов идентификатор** изберете **електронна поща**, **Име и адрес** или **телефон**, които да изпратите на LiveRamp за разрешаване на самоличността.</span><span class="sxs-lookup"><span data-stu-id="f06ab-120">In the **Choose your key identifier** field, select **Email**,  **Name and address**, or **Phone** to send to LiveRamp for identity resolution.</span></span>

1. <span data-ttu-id="f06ab-121">Нанесете съответните атрибути от обединения клиент за избрания идентификатор на ключ.</span><span class="sxs-lookup"><span data-stu-id="f06ab-121">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>

1. <span data-ttu-id="f06ab-122">Изберете **Добавяне на атрибут**, за да нанесете допълнителни атрибути, които да изпратите към LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="f06ab-122">Select **Add attribute** to map additional attributes to send to LiveRamp.</span></span>

   > [!TIP]
   > <span data-ttu-id="f06ab-123">Изпращането на повече атрибути на ключови идентификатори на LiveRamp вероятно ще ви осигури по-висока степен на съвпадение.</span><span class="sxs-lookup"><span data-stu-id="f06ab-123">Sending more key identifier attributes to LiveRamp is likely to get you a higher match rate.</span></span>

1. <span data-ttu-id="f06ab-124">Изберете сегментите, които искате да експортирате в LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="f06ab-124">Select the segments you want to export to LiveRamp.</span></span>

1. <span data-ttu-id="f06ab-125">Изберете **Записване**.</span><span class="sxs-lookup"><span data-stu-id="f06ab-125">Select **Save**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="f06ab-126">![Съединител LiveRamp с нанасяне на атрибути](media/export-liveramp-segments.png "Съединител LiveRamp с нанасяне на атрибути")</span><span class="sxs-lookup"><span data-stu-id="f06ab-126">![LiveRamp connector with attribute mapping](media/export-liveramp-segments.png "LiveRamp connector with attribute mapping")</span></span>

## <a name="export-the-data"></a><span data-ttu-id="f06ab-127">Експортиране на данните</span><span class="sxs-lookup"><span data-stu-id="f06ab-127">Export the data</span></span>

<span data-ttu-id="f06ab-128">Експортирането ще започне скоро, ако са изпълнени всички предпоставки за експортиране.</span><span class="sxs-lookup"><span data-stu-id="f06ab-128">The export will start shortly if all prerequisites for export have been completed.</span></span> <span data-ttu-id="f06ab-129">Експортирането също ще се изпълнява с всяко [планирано обновяване](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="f06ab-129">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
<span data-ttu-id="f06ab-130">След като експортирането приключи успешно, можете да влезете във Въвеждане в LiveRamp, за да активирате и разпространите вашите данни.</span><span class="sxs-lookup"><span data-stu-id="f06ab-130">Once the export is successfully completed, you can sign in to LiveRamp Onboarding to activate and distribute your data.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="f06ab-131">Поверителност и съответствие на данните</span><span class="sxs-lookup"><span data-stu-id="f06ab-131">Data privacy and compliance</span></span>

<span data-ttu-id="f06ab-132">Когато активирате Dynamics 365 Customer Insights, за да предавате данни на Liveramp, разрешавате прехвърляне на данни извън границата за съответствие за Dynamics 365 Customer Insights, включително потенциално чувствителни данни като Лични данни.</span><span class="sxs-lookup"><span data-stu-id="f06ab-132">When you enable Dynamics 365 Customer Insights to transmit data to Liveramp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="f06ab-133">Microsoft ще прехвърли такива данни по ваше указание, но вие носите отговорност да гарантирате, че Liveramp отговаря на всички задължения за поверителност или сигурност, които може да имате.</span><span class="sxs-lookup"><span data-stu-id="f06ab-133">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Liveramp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="f06ab-134">За информация посетете [Декларация за поверителност Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="f06ab-134">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="f06ab-135">Вашият администратор на Dynamics 365 Customer Insights да премахнете това местоназначение за експортиране по всяко време, за да прекратите използването на тази функционалност.</span><span class="sxs-lookup"><span data-stu-id="f06ab-135">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]