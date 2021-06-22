---
title: Експортиране на данни на Customer Insights в Omnisend
description: Научете как да конфигурирате връзката и да експортирате в Omnisend.
ms.date: 05/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8bd692819fa8451ded5e74191ee717f81f87425d
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124454"
---
# <a name="export-segments-to-omnisend-preview"></a><span data-ttu-id="19c2e-103">Експортиране на сегменти в Omnisend (преглед)</span><span class="sxs-lookup"><span data-stu-id="19c2e-103">Export segments to Omnisend (preview)</span></span>

<span data-ttu-id="19c2e-104">Експортирайте сегменти от унифицирани клиентски профили в Omnisend и ги използвайте за маркетингови дейности.</span><span class="sxs-lookup"><span data-stu-id="19c2e-104">Export segments of unified customer profiles to Omnisend and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="19c2e-105">Предварителни изисквания</span><span class="sxs-lookup"><span data-stu-id="19c2e-105">Prerequisites</span></span>

-   <span data-ttu-id="19c2e-106">Имате [акаунт в Omnisend](https://www.omnisend.com/) и съответните идентификационни данни на администратор.</span><span class="sxs-lookup"><span data-stu-id="19c2e-106">You have an [Omnisend account](https://www.omnisend.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="19c2e-107">Имате [конфигурирани сегменти](segments.md) в аналитични данни за аудитория.</span><span class="sxs-lookup"><span data-stu-id="19c2e-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="19c2e-108">Единните клиентски профили в експортираните сегменти съдържат поле, представляващо имейл адрес.</span><span class="sxs-lookup"><span data-stu-id="19c2e-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="19c2e-109">Известни ограничения</span><span class="sxs-lookup"><span data-stu-id="19c2e-109">Known limitations</span></span>

- <span data-ttu-id="19c2e-110">Можете да експортирате до 1 милион профила на износ в Omnisend и това може да отнеме до 4 часа.</span><span class="sxs-lookup"><span data-stu-id="19c2e-110">You can export up to 1 million profiles per export to Omnisend and it can take up to 4 hours to complete.</span></span>
- <span data-ttu-id="19c2e-111">Експортирането в Omnisend е ограничено до сегменти.</span><span class="sxs-lookup"><span data-stu-id="19c2e-111">Exporting to Omnisend is limited to segments.</span></span>
- <span data-ttu-id="19c2e-112">Броят на профилите, които можете да експортирате в Omnisend, зависи от вашия договор с Omnisend.</span><span class="sxs-lookup"><span data-stu-id="19c2e-112">The number of profiles that you can export to Omnisend depends on your contract with Omnisend.</span></span>

## <a name="set-up-connection-to-omnisend"></a><span data-ttu-id="19c2e-113">Настройване на връзка към Omnisend</span><span class="sxs-lookup"><span data-stu-id="19c2e-113">Set up connection to Omnisend</span></span>

1. <span data-ttu-id="19c2e-114">Отидете на **Администратор** > **Връзки**.</span><span class="sxs-lookup"><span data-stu-id="19c2e-114">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="19c2e-115">Изберете **Добавяне на връзка** и изберете **Omnisend** за конфигуриране на връзката.</span><span class="sxs-lookup"><span data-stu-id="19c2e-115">Select **Add connection** and choose **Omnisend** to configure the connection.</span></span>

1. <span data-ttu-id="19c2e-116">Въведете разпознаваемо име за връзката в полето **Показвано име**.</span><span class="sxs-lookup"><span data-stu-id="19c2e-116">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="19c2e-117">Показваното име и типът описват тази връзка.</span><span class="sxs-lookup"><span data-stu-id="19c2e-117">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="19c2e-118">Препоръчваме да изберете име, което обяснява целта на връзката.</span><span class="sxs-lookup"><span data-stu-id="19c2e-118">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="19c2e-119">Изберете кой може да използва тази връзка.</span><span class="sxs-lookup"><span data-stu-id="19c2e-119">Choose who can use this connection.</span></span> <span data-ttu-id="19c2e-120">По подразбиране това са само администратори.</span><span class="sxs-lookup"><span data-stu-id="19c2e-120">By default it's only administrators.</span></span> <span data-ttu-id="19c2e-121">За повече информация вижте [Разрешаване на сътрудници да използват връзка за експортиране](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="19c2e-121">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="19c2e-122">Въведете [ключа за API за Omnisend](https://support.omnisend.com/en/articles/1061890-generating-api-key).</span><span class="sxs-lookup"><span data-stu-id="19c2e-122">Enter your [Omnisend API key](https://support.omnisend.com/en/articles/1061890-generating-api-key).</span></span>

1. <span data-ttu-id="19c2e-123">Изберете **Приемам**, за да потвърдите **Поверителност на данните и съответствие**.</span><span class="sxs-lookup"><span data-stu-id="19c2e-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="19c2e-124">Изберете **Свързване** за инициализиране на връзката с Omnisend.</span><span class="sxs-lookup"><span data-stu-id="19c2e-124">Select **Connect** to initialize the connection to Omnisend.</span></span>

1. <span data-ttu-id="19c2e-125">Изберете **Добавете себе си като потребител за експортиране** и предоставете вашите идентификационни данни на Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="19c2e-125">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="19c2e-126">Изберете **Записване**, за да завършите връзката.</span><span class="sxs-lookup"><span data-stu-id="19c2e-126">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="19c2e-127">Конфигуриране на експортиране</span><span class="sxs-lookup"><span data-stu-id="19c2e-127">Configure an export</span></span>

<span data-ttu-id="19c2e-128">Можете да конфигурирате това експортиране, ако имате достъп до връзка от този тип.</span><span class="sxs-lookup"><span data-stu-id="19c2e-128">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="19c2e-129">За повече информация вижте [Разрешения, необходими за конфигуриране на експортиране](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="19c2e-129">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="19c2e-130">Отидете на **Данни** > **Експортиране**.</span><span class="sxs-lookup"><span data-stu-id="19c2e-130">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="19c2e-131">За да създадете ново експортиране, изберете **Добавяне на местоназначение**.</span><span class="sxs-lookup"><span data-stu-id="19c2e-131">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="19c2e-132">В полето **Връзка за експортиране** изберете връзка от секцията Omnisend.</span><span class="sxs-lookup"><span data-stu-id="19c2e-132">In the **Connection for export** field, choose a connection from the Omnisend section.</span></span> <span data-ttu-id="19c2e-133">Ако не виждате името на тази секция, няма достъпни за вас връзки от този тип.</span><span class="sxs-lookup"><span data-stu-id="19c2e-133">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="19c2e-134">В секцията **Съвпадение на данни** в полето **Имейл** изберете полето във вашия унифициран потребителски профил, което представлява имейл адреса на клиента.</span><span class="sxs-lookup"><span data-stu-id="19c2e-134">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="19c2e-135">Необходимо е да експортирате сегменти в Omnisend.</span><span class="sxs-lookup"><span data-stu-id="19c2e-135">It's required to export segments to Omnisend.</span></span> <span data-ttu-id="19c2e-136">По желание можете да експортирате Собствено име, Фамилно име, Адрес, Държава/регион, Град, Щат и Пощенски код за създаване на по-персонализирани имейли.</span><span class="sxs-lookup"><span data-stu-id="19c2e-136">Optionally, you can export First name, Last name, Address, Country/Region, State, City, and Post Code to create more personalized emails.</span></span> <span data-ttu-id="19c2e-137">Изберете **Добавяне на атрибут** за нанасяне на тези полета.</span><span class="sxs-lookup"><span data-stu-id="19c2e-137">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="19c2e-138">Изберете **Записване**.</span><span class="sxs-lookup"><span data-stu-id="19c2e-138">Select **Save**.</span></span>

<span data-ttu-id="19c2e-139">Запазването на експортиране не го изпълнява незабавно.</span><span class="sxs-lookup"><span data-stu-id="19c2e-139">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="19c2e-140">Експортирането се изпълнява с всяко [планирано обновяване](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="19c2e-140">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="19c2e-141">Може също [да експортирате данни при поискване](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="19c2e-141">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="19c2e-142">Поверителност и съответствие на данните</span><span class="sxs-lookup"><span data-stu-id="19c2e-142">Data privacy and compliance</span></span>

<span data-ttu-id="19c2e-143">Когато активирате Dynamics 365 Customer Insights, за да предавате данни към Ommisend, разрешавате прехвърляне на данни извън границата на съответствие на Dynamics 365 Customer Insights, включително потенциално чувствителни данни като лични данни.</span><span class="sxs-lookup"><span data-stu-id="19c2e-143">When you enable Dynamics 365 Customer Insights to transmit data to Ommisend, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="19c2e-144">Microsoft ще предава такива данни по ваше разпореждане, но вие носите отговорност да гарантирате, че Ommisend спазва задълженията за поверителност и сигурност, които може да имате.</span><span class="sxs-lookup"><span data-stu-id="19c2e-144">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Omnisend meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="19c2e-145">За информация посетете [Декларация за поверителност Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="19c2e-145">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="19c2e-146">Вашият администратор на Dynamics 365 Customer Insights да премахнете това местоназначение за експортиране по всяко време, за да прекратите използването на тази функционалност.</span><span class="sxs-lookup"><span data-stu-id="19c2e-146">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
