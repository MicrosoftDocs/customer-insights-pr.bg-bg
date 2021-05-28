---
title: Експортирайте данните от Customer Insights в SendGrid
description: Научете как да конфигурирате връзката и да експортирате в SendGrid.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 5d3d61d2b5b68079c7717e41dee5a2f698f2b62c
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976903"
---
# <a name="export-segments-to-sendgrid-preview"></a><span data-ttu-id="23166-103">Експортиране на сегменти в SendGrid (преглед)</span><span class="sxs-lookup"><span data-stu-id="23166-103">Export segments to SendGrid (preview)</span></span>

<span data-ttu-id="23166-104">Експортирайте сегменти от унифицирани клиентски профили в списъци с контакти на SendGrid и ги използвайте за кампании и маркетинг по имейл в SendGrid.</span><span class="sxs-lookup"><span data-stu-id="23166-104">Export segments of unified customer profiles to SendGrid contact lists and use them for campaigns and email marketing in SendGrid.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="23166-105">Предварителни изисквания за връзка</span><span class="sxs-lookup"><span data-stu-id="23166-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="23166-106">Имате [Акаунт в SendGrid](https://sendgrid.com/) и съответните идентификационни данни на администратора.</span><span class="sxs-lookup"><span data-stu-id="23166-106">You have a [SendGrid account](https://sendgrid.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="23166-107">В SendGrid има съществуващи списъци с контакти и съответните идентификатори.</span><span class="sxs-lookup"><span data-stu-id="23166-107">There are existing contact lists in SendGrid and the corresponding IDs.</span></span> <span data-ttu-id="23166-108">За повече информация вижте [SendGrid – управление на контакти](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span><span class="sxs-lookup"><span data-stu-id="23166-108">For more information, see [SendGrid - Manage contacts](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span></span>
-   <span data-ttu-id="23166-109">Имате [конфигурирани сегменти](segments.md) в аналитични данни за аудитория.</span><span class="sxs-lookup"><span data-stu-id="23166-109">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="23166-110">Единните клиентски профили в експортираните сегменти съдържат поле, представляващо имейл адрес.</span><span class="sxs-lookup"><span data-stu-id="23166-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="23166-111">Известни ограничения</span><span class="sxs-lookup"><span data-stu-id="23166-111">Known limitations</span></span>

- <span data-ttu-id="23166-112">Общо до 100'000 профила в SendGrid.</span><span class="sxs-lookup"><span data-stu-id="23166-112">Up to 100'000 profiles in total to SendGrid.</span></span>
- <span data-ttu-id="23166-113">Експортирането в SendGrid е ограничено до сегменти.</span><span class="sxs-lookup"><span data-stu-id="23166-113">Exporting to SendGrid is limited to segments.</span></span>
- <span data-ttu-id="23166-114">Експортирането на до 100 000 профила в SendGrid може да отнеме до няколко часа.</span><span class="sxs-lookup"><span data-stu-id="23166-114">Exporting up to 100'000 profiles to SendGrid can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="23166-115">Броят на профилите, които можете да експортирате в SendGrid, зависи и е ограничен от вашия договор с SendGrid.</span><span class="sxs-lookup"><span data-stu-id="23166-115">The number of profiles that you can export to SendGrid is dependent and limited on your contract with SendGrid.</span></span>

## <a name="set-up-connection-to-sendgrid"></a><span data-ttu-id="23166-116">Настройване на връзка към SendGrid</span><span class="sxs-lookup"><span data-stu-id="23166-116">Set up connection to SendGrid</span></span>

1. <span data-ttu-id="23166-117">Отидете на **Администратор** > **Връзки**.</span><span class="sxs-lookup"><span data-stu-id="23166-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="23166-118">Изберете **Добавяне на връзка** и изберете **SendGrid** за конфигуриране на връзката.</span><span class="sxs-lookup"><span data-stu-id="23166-118">Select **Add connection** and choose **SendGrid** to configure the connection.</span></span>

1. <span data-ttu-id="23166-119">Въведете разпознаваемо име за връзката в полето **Показвано име**.</span><span class="sxs-lookup"><span data-stu-id="23166-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="23166-120">Показваното име и типът описват тази връзка.</span><span class="sxs-lookup"><span data-stu-id="23166-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="23166-121">Препоръчваме да изберете име, което обяснява целта на връзката.</span><span class="sxs-lookup"><span data-stu-id="23166-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="23166-122">Изберете кой може да използва тази връзка.</span><span class="sxs-lookup"><span data-stu-id="23166-122">Choose who can use this connection.</span></span> <span data-ttu-id="23166-123">Ако не предприемете нищо, по подразбиране ще е Администратори.</span><span class="sxs-lookup"><span data-stu-id="23166-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="23166-124">За повече информация вижте [Разрешаване на сътрудници да използват връзка за експортиране](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="23166-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="23166-125">Въведете своя **API ключ на SendGrid** [API ключ на SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span><span class="sxs-lookup"><span data-stu-id="23166-125">Enter your **SendGrid API key** [SendGrid API key](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span></span>

1. <span data-ttu-id="23166-126">Изберете **Приемам**, за да потвърдите **Поверителност на данните и съответствие**.</span><span class="sxs-lookup"><span data-stu-id="23166-126">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="23166-127">Изберете **Свържете** за инициализиране на връзката с SendGrid.</span><span class="sxs-lookup"><span data-stu-id="23166-127">Select **Connect** to initialize the connection to SendGrid.</span></span>

1. <span data-ttu-id="23166-128">Изберете **Добавете себе си като потребител за експортиране** и предоставете вашите идентификационни данни на Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="23166-128">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="23166-129">Изберете **Записване**, за да завършите връзката.</span><span class="sxs-lookup"><span data-stu-id="23166-129">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="23166-130">Конфигуриране на експортиране</span><span class="sxs-lookup"><span data-stu-id="23166-130">Configure an export</span></span>

<span data-ttu-id="23166-131">Можете да конфигурирате това експортиране, ако имате достъп до връзка от този тип.</span><span class="sxs-lookup"><span data-stu-id="23166-131">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="23166-132">За повече информация вижте [Разрешения, необходими за конфигуриране на експортиране](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="23166-132">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="23166-133">Отидете на **Данни** > **Експортиране**.</span><span class="sxs-lookup"><span data-stu-id="23166-133">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="23166-134">За да създадете ново експортиране, изберете **Добавяне на местоназначение**.</span><span class="sxs-lookup"><span data-stu-id="23166-134">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="23166-135">В полето **Връзка за експортиране** изберете връзка от секцията SendGrid.</span><span class="sxs-lookup"><span data-stu-id="23166-135">In the **Connection for export** field, choose a connection from the SendGrid section.</span></span> <span data-ttu-id="23166-136">Ако не виждате името на тази секция, няма достъпни за вас връзки от този тип.</span><span class="sxs-lookup"><span data-stu-id="23166-136">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="23166-137">Въведете своя **[ИД на списъка на SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span><span class="sxs-lookup"><span data-stu-id="23166-137">Enter your **[SendGrid list ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span></span>

1. <span data-ttu-id="23166-138">В секцията **Съвпадение на данни** в полето **Имейл** изберете полето във вашия унифициран потребителски профил, което представлява имейл адреса на клиента.</span><span class="sxs-lookup"><span data-stu-id="23166-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="23166-139">Повторете същите стъпки за други незадължителни полета, като например **собствено име**, **фамилно име**, **Държава/регион**, **Щат**, **Град** и **Пощенски код**.</span><span class="sxs-lookup"><span data-stu-id="23166-139">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Country/Region**, **State**, **City**, and **Post code**.</span></span>

1. <span data-ttu-id="23166-140">Изберете сегментите, които искате да експортирате.</span><span class="sxs-lookup"><span data-stu-id="23166-140">Select the segments you want to export.</span></span> <span data-ttu-id="23166-141">Ние силно **препоръчваме да не експортирате повече от 100 000 потребителски профила общо** към SendGrid.</span><span class="sxs-lookup"><span data-stu-id="23166-141">We strongly **recommend to not export more than 100'000 customer profiles in total** to SendGrid.</span></span> 

1. <span data-ttu-id="23166-142">Изберете **Записване**.</span><span class="sxs-lookup"><span data-stu-id="23166-142">Select **Save**.</span></span>

<span data-ttu-id="23166-143">Запазването на експортиране не го изпълнява незабавно.</span><span class="sxs-lookup"><span data-stu-id="23166-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="23166-144">Експортирането се изпълнява с всяко [планирано обновяване](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="23166-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="23166-145">Може също [да експортирате данни при поискване](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="23166-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="23166-146">Поверителност и съответствие на данните</span><span class="sxs-lookup"><span data-stu-id="23166-146">Data privacy and compliance</span></span>

<span data-ttu-id="23166-147">Когато активирате Dynamics 365 Customer Insights, за да предавате данни на SendGrid, разрешавате прехвърляне на данни извън границата за съответствие за Dynamics 365 Customer Insights, включително потенциално чувствителни данни като Лични данни.</span><span class="sxs-lookup"><span data-stu-id="23166-147">When you enable Dynamics 365 Customer Insights to transmit data to SendGrid, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="23166-148">Microsoft ще прехвърли такива данни по ваше указание, но вие носите отговорност да гарантирате, че SendGrid отговаря на всички задължения за поверителност или сигурност, които може да имате.</span><span class="sxs-lookup"><span data-stu-id="23166-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that SendGrid meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="23166-149">За информация посетете [Декларация за поверителност Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="23166-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="23166-150">Вашият администратор на Dynamics 365 Customer Insights да премахнете това местоназначение за експортиране по всяко време, за да прекратите използването на тази функционалност.</span><span class="sxs-lookup"><span data-stu-id="23166-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]