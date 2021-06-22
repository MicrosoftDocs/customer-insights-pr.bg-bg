---
title: Експортиране на данни на Customer Insights в LinkedIn Ads
description: Научете как да конфигурирате връзката и да експортирате в LinkedIn Ads.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 1c7b0c728bc4d4cf6b5aea79396cf0779fbf298d
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124455"
---
# <a name="export-segments-to-linkedin-ads-preview"></a><span data-ttu-id="d295d-103">Експортиране на сегменти в LinkedIn Ads (преглед)</span><span class="sxs-lookup"><span data-stu-id="d295d-103">Export segments to LinkedIn Ads (preview)</span></span>

<span data-ttu-id="d295d-104">Експортирайте сегменти от унифицирани клиентски профили в LinkedIn Ads, за да създадете съответстващи аудитории.</span><span class="sxs-lookup"><span data-stu-id="d295d-104">Export segments of unified customer profiles to LinkedIn Ads to create matched audiences.</span></span> <span data-ttu-id="d295d-105">Използвайте съответстващите аудитории за насочване към компания и насочване към контакти.</span><span class="sxs-lookup"><span data-stu-id="d295d-105">Use the matched audiences for company targeting and contact targeting.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d295d-106">Предварителни изисквания</span><span class="sxs-lookup"><span data-stu-id="d295d-106">Prerequisites</span></span>

-   <span data-ttu-id="d295d-107">Имате [акаунт в LinkedIn Campaign Manager](https://business.linkedin.com/marketing-solutions/ads) и съответните идентификационни данни на администратор.</span><span class="sxs-lookup"><span data-stu-id="d295d-107">You have an [LinkedIn Campaign Manager account](https://business.linkedin.com/marketing-solutions/ads) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="d295d-108">Имате [конфигурирани сегменти](segments.md) в аналитични данни за аудитория.</span><span class="sxs-lookup"><span data-stu-id="d295d-108">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="d295d-109">Потребителски профили в експортираните сегменти съдържат поле с имейл адрес.</span><span class="sxs-lookup"><span data-stu-id="d295d-109">Customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="d295d-110">Известни ограничения</span><span class="sxs-lookup"><span data-stu-id="d295d-110">Known limitations</span></span>

- <span data-ttu-id="d295d-111">Можете да експортирате до 100 хиляди профила с всяко експортиране в LinkedIn Ads.</span><span class="sxs-lookup"><span data-stu-id="d295d-111">You can export up to 100K profiles per export to LinkedIn Ads.</span></span>
- <span data-ttu-id="d295d-112">Експортирането в LinkedIn Ads е ограничено до сегменти.</span><span class="sxs-lookup"><span data-stu-id="d295d-112">Exporting to LinkedIn Ads is limited to segments.</span></span>
- <span data-ttu-id="d295d-113">Експортирането на до 100 хиляди профила в LinkedIn Ads може да отнеме до 10 минути.</span><span class="sxs-lookup"><span data-stu-id="d295d-113">Exporting up to 100K profiles to LinkedIn Ads can take up to 10 minutes to complete.</span></span> 

## <a name="set-up-the-connection-to-linkedin-ads"></a><span data-ttu-id="d295d-114">Настройване на връзката с хранилище за LinkedIn Ads</span><span class="sxs-lookup"><span data-stu-id="d295d-114">Set up the connection to LinkedIn Ads</span></span>

1. <span data-ttu-id="d295d-115">В аналитичните данни за аудиторията отидете на **Администратор** > **Връзки**.</span><span class="sxs-lookup"><span data-stu-id="d295d-115">In audience insights, go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="d295d-116">Изберете **Добавяне на връзка** и изберете **LinkedIn Ads** за конфигуриране на връзката.</span><span class="sxs-lookup"><span data-stu-id="d295d-116">Select **Add connection** and choose **LinkedIn Ads** to configure the connection.</span></span>

1. <span data-ttu-id="d295d-117">Въведете разпознаваемо име за връзката в полето **Показвано име**.</span><span class="sxs-lookup"><span data-stu-id="d295d-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="d295d-118">Показваното име и типът описват тази връзка.</span><span class="sxs-lookup"><span data-stu-id="d295d-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="d295d-119">Препоръчваме да изберете име, което обяснява целта на връзката.</span><span class="sxs-lookup"><span data-stu-id="d295d-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="d295d-120">Изберете кой може да използва тази връзка.</span><span class="sxs-lookup"><span data-stu-id="d295d-120">Choose who can use this connection.</span></span> <span data-ttu-id="d295d-121">Ако не предприемете нищо, по подразбиране е Администратори.</span><span class="sxs-lookup"><span data-stu-id="d295d-121">If you take no action, the default is administrators.</span></span> <span data-ttu-id="d295d-122">За повече информация вижте [Разрешаване на сътрудници да използват връзка за експортиране](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="d295d-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="d295d-123">Предоставете своя [ИД на акаунт в LinkedIn Campaign Manager](https://www.linkedin.com/help/lms/answer/a424270).</span><span class="sxs-lookup"><span data-stu-id="d295d-123">Provide your [LinkedIn Campaign Manager Account ID](https://www.linkedin.com/help/lms/answer/a424270).</span></span>

1. <span data-ttu-id="d295d-124">Изберете **Приемам**, за да потвърдите **Поверителност на данните и съответствие**.</span><span class="sxs-lookup"><span data-stu-id="d295d-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="d295d-125">Изберете **Свързване** за инициализиране на връзката с Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="d295d-125">Select **Connect** to initialize the connection to Campaign Monitor.</span></span>

1. <span data-ttu-id="d295d-126">Изберете **Удостоверяване с LinkedIn** и предоставете администраторските си данни за LinkedIn Campaign Manager.</span><span class="sxs-lookup"><span data-stu-id="d295d-126">Select **Authenticate with LinkedIn** and provide your admin credentials for LinkedIn Campaign Manager.</span></span>

1. <span data-ttu-id="d295d-127">Изберете **Добавете себе си като потребител за експортиране** и предоставете вашите идентификационни данни на Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="d295d-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="d295d-128">Изберете **Записване**, за да завършите връзката.</span><span class="sxs-lookup"><span data-stu-id="d295d-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="d295d-129">Конфигуриране на експортиране</span><span class="sxs-lookup"><span data-stu-id="d295d-129">Configure an export</span></span>

<span data-ttu-id="d295d-130">Можете да конфигурирате експортиране, ако имате достъп до връзка от този тип.</span><span class="sxs-lookup"><span data-stu-id="d295d-130">You can configure an export if you have access to a connection of this type.</span></span> <span data-ttu-id="d295d-131">За повече информация вижте [Разрешения, необходими за конфигуриране на експортиране](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="d295d-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="d295d-132">Отидете на **Данни** > **Експортиране**.</span><span class="sxs-lookup"><span data-stu-id="d295d-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="d295d-133">За да създадете ново експортиране, изберете **Добавяне на местоназначение**.</span><span class="sxs-lookup"><span data-stu-id="d295d-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="d295d-134">В полето **Връзка за експортиране** изберете връзка от секцията LinkedIn Ads.</span><span class="sxs-lookup"><span data-stu-id="d295d-134">In the **Connection for export** field, choose a connection from the LinkedIn Ads section.</span></span> <span data-ttu-id="d295d-135">Ако не виждате името на тази секция, няма достъпни за вас връзки от този тип.</span><span class="sxs-lookup"><span data-stu-id="d295d-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="d295d-136">Изберете дали искате да експортирате данни в [насочване на контакти](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) или [насочване на компанията](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) в LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="d295d-136">Choose whether you want to export data to do [contact targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) or [company targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) on LinkedIn.</span></span> 

1. <span data-ttu-id="d295d-137">В секцията **Съвпадение на данни** изберете полето във вашия унифициран потребителски профил, което представлява имейл адреса на клиента.</span><span class="sxs-lookup"><span data-stu-id="d295d-137">In the **Data matching** section, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="d295d-138">Необходимо е да експортирате сегменти в LinkedIn Ads.</span><span class="sxs-lookup"><span data-stu-id="d295d-138">It's required to export segments to LinkedIn Ads.</span></span>

1. <span data-ttu-id="d295d-139">Изберете сегментите, които искате да експортирате.</span><span class="sxs-lookup"><span data-stu-id="d295d-139">Select the segments you want to export.</span></span> <span data-ttu-id="d295d-140">Съвпадащите аудитории в LinkedIn Campaign Manager автоматично ще се създаде с името на сегментите, които сте избрали за експортиране.</span><span class="sxs-lookup"><span data-stu-id="d295d-140">The matched audiences in LinkedIn Campaign Manager will automatically be created with the name of the segments that you selected to export.</span></span> <span data-ttu-id="d295d-141">Всеки сегмент ще доведе до отделна съпоставена аудитория.</span><span class="sxs-lookup"><span data-stu-id="d295d-141">Each segment will result in a separate matched audience.</span></span> 

1. <span data-ttu-id="d295d-142">Изберете **Записване**.</span><span class="sxs-lookup"><span data-stu-id="d295d-142">Select **Save**.</span></span>

<span data-ttu-id="d295d-143">Запазването на експортиране не го изпълнява незабавно.</span><span class="sxs-lookup"><span data-stu-id="d295d-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="d295d-144">Експортирането се изпълнява с всяко [планирано обновяване](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="d295d-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="d295d-145">Може също [да експортирате данни при поискване](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="d295d-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="d295d-146">Поверителност и съответствие на данните</span><span class="sxs-lookup"><span data-stu-id="d295d-146">Data privacy and compliance</span></span>

<span data-ttu-id="d295d-147">Когато активирате Dynamics 365 Customer Insights, за да предавате данни към LinkedIn Ads, разрешавате прехвърляне на данни извън границата на съответствие на Dynamics 365 Customer Insights, включително потенциално чувствителни данни като лични данни.</span><span class="sxs-lookup"><span data-stu-id="d295d-147">When you enable Dynamics 365 Customer Insights to transmit data to LinkedIn Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="d295d-148">Microsoft ще предава такива данни по ваше разпореждане, но вие носите отговорност да гарантирате, че LinkedIn Ads спазва задълженията за поверителност и сигурност, които може да имате.</span><span class="sxs-lookup"><span data-stu-id="d295d-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that LinkedIn Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="d295d-149">За информация посетете [Декларация за поверителност Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="d295d-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="d295d-150">Вашият администратор на Dynamics 365 Customer Insights може да премахнете това местоназначение за експортиране по всяко време, за да прекратите използването на тази функционалност.</span><span class="sxs-lookup"><span data-stu-id="d295d-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to stop the use of this functionality.</span></span>
