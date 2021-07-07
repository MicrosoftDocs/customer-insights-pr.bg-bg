---
title: Експортирайте данни за Customer Insights в Sendinblue
description: Научете как да конфигурирате връзката и да експортирате в Sendinblue.
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 58ca0ae5ad4a3a291f4336984d14fefb23a58ab3
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314577"
---
# <a name="export-segments-to-sendinblue-preview"></a><span data-ttu-id="9bfd4-103">Експортиране на сегменти в Sendinblue (преглед)</span><span class="sxs-lookup"><span data-stu-id="9bfd4-103">Export segments to Sendinblue (preview)</span></span>

<span data-ttu-id="9bfd4-104">Експортирайте сегментите на унифицирани клиентски профили, за да генерирате кампании, да извършвате маркетинг по имейл и да използвате конкретни групи клиенти със Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="9bfd4-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Sendinblue.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="9bfd4-105">Предварителни изисквания за връзка</span><span class="sxs-lookup"><span data-stu-id="9bfd4-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="9bfd4-106">Имате [Акаунт в Sendinblue](https://www.sendinblue.com/) и съответните идентификационни данни на администратора.</span><span class="sxs-lookup"><span data-stu-id="9bfd4-106">You have a [Sendinblue account](https://www.sendinblue.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="9bfd4-107">В Sendinblue има съществуващи списъци и съответните идентификатори.</span><span class="sxs-lookup"><span data-stu-id="9bfd4-107">There are existing lists in Sendinblue and the corresponding IDs.</span></span>
-   <span data-ttu-id="9bfd4-108">Имате [конфигурирани сегменти](segments.md).</span><span class="sxs-lookup"><span data-stu-id="9bfd4-108">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="9bfd4-109">Единните клиентски профили в експортираните сегменти съдържат поле, представляващо имейл адрес.</span><span class="sxs-lookup"><span data-stu-id="9bfd4-109">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="9bfd4-110">Известни ограничения</span><span class="sxs-lookup"><span data-stu-id="9bfd4-110">Known limitations</span></span>

- <span data-ttu-id="9bfd4-111">До 1 милион профила на износ към Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="9bfd4-111">Up to 1 million profiles per export to Sendinblue.</span></span>
- <span data-ttu-id="9bfd4-112">Експортирането в Sendinblue е ограничено до сегменти.</span><span class="sxs-lookup"><span data-stu-id="9bfd4-112">Exporting to Sendinblue is limited to segments.</span></span>
- <span data-ttu-id="9bfd4-113">Експортирането на сегменти с общо 1 милион профила може да отнеме до 90 минути.</span><span class="sxs-lookup"><span data-stu-id="9bfd4-113">Exporting segments with a total of 1 million profiles can take up to 90 minutes.</span></span> 
- <span data-ttu-id="9bfd4-114">Броят на профилите, които можете да експортирате в Sendinblue, зависи и е ограничен от вашия договор със Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="9bfd4-114">The number of profiles that you can export to Sendinblue is dependent and limited on your contract with Sendinblue.</span></span>

## <a name="set-up-connection-to-sendinblue"></a><span data-ttu-id="9bfd4-115">Настройване на връзка с Sendinblue</span><span class="sxs-lookup"><span data-stu-id="9bfd4-115">Set up connection to Sendinblue</span></span>

1. <span data-ttu-id="9bfd4-116">Отидете на **Администратор** > **Връзки**.</span><span class="sxs-lookup"><span data-stu-id="9bfd4-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="9bfd4-117">Изберете **Добавете връзка** и изберете **Sendinblue** за конфигуриране на връзката.</span><span class="sxs-lookup"><span data-stu-id="9bfd4-117">Select **Add connection** and choose **Sendinblue** to configure the connection.</span></span>

1. <span data-ttu-id="9bfd4-118">Въведете разпознаваемо име за връзката в полето **Показвано име**.</span><span class="sxs-lookup"><span data-stu-id="9bfd4-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="9bfd4-119">Показваното име и типът описват тази връзка.</span><span class="sxs-lookup"><span data-stu-id="9bfd4-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="9bfd4-120">Препоръчваме да изберете име, което обяснява целта на връзката.</span><span class="sxs-lookup"><span data-stu-id="9bfd4-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="9bfd4-121">Изберете кой може да използва тази връзка.</span><span class="sxs-lookup"><span data-stu-id="9bfd4-121">Choose who can use this connection.</span></span> <span data-ttu-id="9bfd4-122">По подразбиране това са само администратори.</span><span class="sxs-lookup"><span data-stu-id="9bfd4-122">By default it's only administrators.</span></span> <span data-ttu-id="9bfd4-123">За повече информация вижте [Разрешаване на сътрудници да използват връзка за експортиране](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="9bfd4-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="9bfd4-124">Въведете своя **[API ключ на SendinBlue](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.</span><span class="sxs-lookup"><span data-stu-id="9bfd4-124">Enter your **[SendinBlue API key](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.</span></span>

1. <span data-ttu-id="9bfd4-125">Изберете **съгласен съм** за да потвърдите **Поверителност и съответствие на данните** и изберете **Свържете** за инициализиране на връзката към Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="9bfd4-125">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Sendinblue.</span></span>

1. <span data-ttu-id="9bfd4-126">Изберете **Добавете себе си като потребител за експортиране** и предоставете вашите идентификационни данни на Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="9bfd4-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="9bfd4-127">Изберете **Записване**, за да завършите връзката.</span><span class="sxs-lookup"><span data-stu-id="9bfd4-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="9bfd4-128">Конфигуриране на експортиране</span><span class="sxs-lookup"><span data-stu-id="9bfd4-128">Configure an export</span></span>

<span data-ttu-id="9bfd4-129">Можете да конфигурирате това експортиране, ако имате достъп до връзка от този тип.</span><span class="sxs-lookup"><span data-stu-id="9bfd4-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="9bfd4-130">За повече информация вижте [Разрешения, необходими за конфигуриране на експортиране](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="9bfd4-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="9bfd4-131">Отидете на **Данни** > **Експортиране**.</span><span class="sxs-lookup"><span data-stu-id="9bfd4-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="9bfd4-132">За да създадете ново експортиране, изберете **Добавяне на местоназначение**.</span><span class="sxs-lookup"><span data-stu-id="9bfd4-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="9bfd4-133">В **Връзка за експортиране** поле, изберете връзка от раздела Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="9bfd4-133">In the **Connection for export** field, choose a connection from the Sendinblue section.</span></span> <span data-ttu-id="9bfd4-134">Ако не виждате името на тази секция, няма достъпни за вас връзки от този тип.</span><span class="sxs-lookup"><span data-stu-id="9bfd4-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="9bfd4-135">Въведете своя **ИД на списък на Sendinblue**</span><span class="sxs-lookup"><span data-stu-id="9bfd4-135">Enter your **Sendinblue list ID**</span></span> 

1. <span data-ttu-id="9bfd4-136">В секцията **Съвпадение на данни** в полето **Имейл** изберете полето във вашия унифициран потребителски профил, което представлява имейл адреса на клиента.</span><span class="sxs-lookup"><span data-stu-id="9bfd4-136">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="9bfd4-137">По желание можете да експортирате **собствено име**, **фамилно име** и **Телефон** за създаване на по-персонализирани имейли.</span><span class="sxs-lookup"><span data-stu-id="9bfd4-137">Optionally, you can export **First name**, **Last name**, and **Phone**  to create more personalized emails.</span></span> <span data-ttu-id="9bfd4-138">Изберете **Добавяне на атрибут** за нанасяне на тези полета.</span><span class="sxs-lookup"><span data-stu-id="9bfd4-138">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="9bfd4-139">Изберете сегментите, които искате да експортирате.</span><span class="sxs-lookup"><span data-stu-id="9bfd4-139">Select the segments you want to export.</span></span> 

1. <span data-ttu-id="9bfd4-140">Изберете **Записване**.</span><span class="sxs-lookup"><span data-stu-id="9bfd4-140">Select **Save**.</span></span>

<span data-ttu-id="9bfd4-141">Запазването на експортиране не го изпълнява незабавно.</span><span class="sxs-lookup"><span data-stu-id="9bfd4-141">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="9bfd4-142">Експортирането се изпълнява с всяко [планирано обновяване](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="9bfd4-142">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="9bfd4-143">Може също [да експортирате данни при поискване](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="9bfd4-143">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="9bfd4-144">Поверителност и съответствие на данните</span><span class="sxs-lookup"><span data-stu-id="9bfd4-144">Data privacy and compliance</span></span>

<span data-ttu-id="9bfd4-145">Когато активирате Dynamics 365 Customer Insights за предаване на данни на Sendinblue, разрешавате прехвърляне на данни извън границата за съответствие за Dynamics 365 Customer Insights, включително потенциално чувствителни данни като Лични данни.</span><span class="sxs-lookup"><span data-stu-id="9bfd4-145">When you enable Dynamics 365 Customer Insights to transmit data to Sendinblue, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="9bfd4-146">Microsoft ще прехвърли такива данни по ваше указание, но вие сте отговорни за това Sendinblue отговаря на всички задължения за поверителност или сигурност, които може да имате.</span><span class="sxs-lookup"><span data-stu-id="9bfd4-146">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Sendinblue meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="9bfd4-147">За информация посетете [Декларация за поверителност Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="9bfd4-147">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="9bfd4-148">Вашият администратор на Dynamics 365 Customer Insights да премахнете това местоназначение за експортиране по всяко време, за да прекратите използването на тази функционалност.</span><span class="sxs-lookup"><span data-stu-id="9bfd4-148">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
