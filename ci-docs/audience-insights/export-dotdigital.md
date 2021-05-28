---
title: Експортирайте данните от Customer Insights в DotDigital
description: Научете как да конфигурирате връзката и да експортирате в DotDigital.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d08504856e1c673ef32433b83bf491d7f4e8cee4
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976833"
---
# <a name="export-segment-lists-to-dotdigital-preview"></a><span data-ttu-id="53615-103">Експортиране на списъци със сегменти в DotDigital (преглед)</span><span class="sxs-lookup"><span data-stu-id="53615-103">Export segment lists to DotDigital (preview)</span></span>

<span data-ttu-id="53615-104">Експортирайте сегменти от унифицирани клиентски профили в адресните книги на DotDigital и ги използвайте за кампании, маркетинг по имейл и за изграждане на клиентски сегменти с DotDigital.</span><span class="sxs-lookup"><span data-stu-id="53615-104">Export segments of unified customer profiles to DotDigital address books and use them for campaigns, email marketing, and to build customer segments with DotDigital.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="53615-105">Предварителни изисквания за връзка</span><span class="sxs-lookup"><span data-stu-id="53615-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="53615-106">Имате [Акаунт в DotDigital](https://dotdigital.com/) и съответните идентификационни данни на администратора.</span><span class="sxs-lookup"><span data-stu-id="53615-106">You have a [DotDigital account](https://dotdigital.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="53615-107">В Google Ads има съществуващи адресни книги в DotDigital и съответните идентификатори.</span><span class="sxs-lookup"><span data-stu-id="53615-107">There are existing address books in DotDigital and the corresponding IDs.</span></span> <span data-ttu-id="53615-108">Идентификаторът може да бъде намерен в URL адреса, когато изберете и отворите адресна книга.</span><span class="sxs-lookup"><span data-stu-id="53615-108">The ID can be found in the URL when you select and open an address book.</span></span> <span data-ttu-id="53615-109">За повече информация вижте [Адресни книги на DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="53615-109">For more information, see [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>
-   <span data-ttu-id="53615-110">Имате [конфигурирани сегменти](segments.md) в аналитични данни за аудитория.</span><span class="sxs-lookup"><span data-stu-id="53615-110">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="53615-111">Единните клиентски профили в експортираните сегменти съдържат поле, представляващо имейл адрес.</span><span class="sxs-lookup"><span data-stu-id="53615-111">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="53615-112">Известни ограничения</span><span class="sxs-lookup"><span data-stu-id="53615-112">Known limitations</span></span>

- <span data-ttu-id="53615-113">До 1 милион профила на износ към DotDigital.</span><span class="sxs-lookup"><span data-stu-id="53615-113">Up to 1 million profiles per export to DotDigital.</span></span>
- <span data-ttu-id="53615-114">Експортирането в DotDigital е ограничено до сегменти.</span><span class="sxs-lookup"><span data-stu-id="53615-114">Exporting to DotDigital is limited to segments.</span></span>
- <span data-ttu-id="53615-115">Експортирането на сегменти с общо 1 милион профила може да отнеме до 3 часа поради ограничения от страна на доставчика.</span><span class="sxs-lookup"><span data-stu-id="53615-115">Exporting segments with a total of 1 million profiles can take up to 3 hours because of limitations on the provider side.</span></span> 
- <span data-ttu-id="53615-116">Броят на профилите, които можете да експортирате в DotDigital, зависи и е ограничен от вашия договор с DotDigital.</span><span class="sxs-lookup"><span data-stu-id="53615-116">The number of profiles that you can export to DotDigital is dependent and limited on your contract with DotDigital.</span></span>

## <a name="set-up-connection-to-dotdigital"></a><span data-ttu-id="53615-117">Настройване на връзка с DotDigital</span><span class="sxs-lookup"><span data-stu-id="53615-117">Set up connection to DotDigital</span></span>

1. <span data-ttu-id="53615-118">Отидете на **Администратор** > **Връзки**.</span><span class="sxs-lookup"><span data-stu-id="53615-118">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="53615-119">Изберете **Добавяне на връзка** и изберете **DotDigital** за конфигуриране на връзката.</span><span class="sxs-lookup"><span data-stu-id="53615-119">Select **Add connection** and choose **DotDigital** to configure the connection.</span></span>

1. <span data-ttu-id="53615-120">Въведете разпознаваемо име за връзката в полето **Показвано име**.</span><span class="sxs-lookup"><span data-stu-id="53615-120">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="53615-121">Показваното име и типът описват тази връзка.</span><span class="sxs-lookup"><span data-stu-id="53615-121">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="53615-122">Препоръчваме да изберете име, което обяснява целта на връзката.</span><span class="sxs-lookup"><span data-stu-id="53615-122">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="53615-123">Изберете кой може да използва тази връзка.</span><span class="sxs-lookup"><span data-stu-id="53615-123">Choose who can use this connection.</span></span> <span data-ttu-id="53615-124">Ако не предприемете нищо, по подразбиране ще е Администратори.</span><span class="sxs-lookup"><span data-stu-id="53615-124">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="53615-125">За повече информация вижте [Разрешаване на сътрудници да използват връзка за експортиране](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="53615-125">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="53615-126">Въведете **потребителско име и парола за DotDigital**.</span><span class="sxs-lookup"><span data-stu-id="53615-126">Enter your **DotDigital username and password**.</span></span>

1. <span data-ttu-id="53615-127">Въведете своя **[Идентификатор на адресната книга на DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span><span class="sxs-lookup"><span data-stu-id="53615-127">Enter your **[DotDigital address book ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span></span>

1. <span data-ttu-id="53615-128">Изберете **Приемам**, за да потвърдите **Поверителност на данните и съответствие**.</span><span class="sxs-lookup"><span data-stu-id="53615-128">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="53615-129">Изберете **Свържете** за инициализиране на връзката с DotDigital.</span><span class="sxs-lookup"><span data-stu-id="53615-129">Select **Connect** to initialize the connection to DotDigital.</span></span>

1. <span data-ttu-id="53615-130">Изберете **Добавете себе си като потребител за експортиране** и предоставете вашите идентификационни данни на Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="53615-130">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="53615-131">Изберете **Записване**, за да завършите връзката.</span><span class="sxs-lookup"><span data-stu-id="53615-131">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="53615-132">Конфигуриране на експортиране</span><span class="sxs-lookup"><span data-stu-id="53615-132">Configure an export</span></span>

<span data-ttu-id="53615-133">Можете да конфигурирате това експортиране, ако имате достъп до връзка от този тип.</span><span class="sxs-lookup"><span data-stu-id="53615-133">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="53615-134">За повече информация вижте [Разрешения, необходими за конфигуриране на експортиране](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="53615-134">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="53615-135">Отидете на **Данни** > **Експортиране**.</span><span class="sxs-lookup"><span data-stu-id="53615-135">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="53615-136">За да създадете ново експортиране, изберете **Добавяне на местоназначение**.</span><span class="sxs-lookup"><span data-stu-id="53615-136">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="53615-137">В полето **Връзка за експортиране** изберете връзка от секцията DotDigital.</span><span class="sxs-lookup"><span data-stu-id="53615-137">In the **Connection for export** field, choose a connection from the DotDigital section.</span></span> <span data-ttu-id="53615-138">Ако не виждате името на тази секция, няма достъпни за вас връзки от този тип.</span><span class="sxs-lookup"><span data-stu-id="53615-138">If you don't see this section name, there are no connections of this type available to you.</span></span>


1. <span data-ttu-id="53615-139">В секцията **Съвпадение на данни** в полето **Имейл** изберете полето във вашия унифициран потребителски профил, което представлява имейл адреса на клиента.</span><span class="sxs-lookup"><span data-stu-id="53615-139">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="53615-140">Повторете същите стъпки за други незадължителни полета, като например **собствено име**, **фамилно име**, **Пълно име**, **Пол** и **Пощенски код**.</span><span class="sxs-lookup"><span data-stu-id="53615-140">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Full name**, **Gender**, and **Post code**.</span></span>

1. <span data-ttu-id="53615-141">Изберете сегментите, които искате да експортирате.</span><span class="sxs-lookup"><span data-stu-id="53615-141">Select the segments you want to export.</span></span> <span data-ttu-id="53615-142">Можете да експортирате до 1 милион потребителски профила общо в DotDigital.</span><span class="sxs-lookup"><span data-stu-id="53615-142">You can export up to 1 million customer profiles in total to DotDigital.</span></span>

1. <span data-ttu-id="53615-143">Изберете **Записване**.</span><span class="sxs-lookup"><span data-stu-id="53615-143">Select **Save**.</span></span>

<span data-ttu-id="53615-144">Запазването на експортиране не го изпълнява незабавно.</span><span class="sxs-lookup"><span data-stu-id="53615-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="53615-145">Експортирането се изпълнява с всяко [планирано обновяване](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="53615-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="53615-146">Може също [да експортирате данни при поискване](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="53615-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 
 
<span data-ttu-id="53615-147">В DotDigital вече можете да намерите своите сегменти в [адресни книги в DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="53615-147">In DotDigital, you can now find your segments in [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="53615-148">Поверителност и съответствие на данните</span><span class="sxs-lookup"><span data-stu-id="53615-148">Data privacy and compliance</span></span>

<span data-ttu-id="53615-149">Когато активирате Dynamics 365 Customer Insights, за да предавате данни на DotDigital, разрешавате прехвърляне на данни извън границата за съответствие за Dynamics 365 Customer Insights, включително потенциално чувствителни данни като Лични данни.</span><span class="sxs-lookup"><span data-stu-id="53615-149">When you enable Dynamics 365 Customer Insights to transmit data to DotDigital, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="53615-150">Microsoft ще прехвърли такива данни по ваше указание, но вие носите отговорност да гарантирате, че DotDigital отговаря на всички задължения за поверителност или сигурност, които може да имате.</span><span class="sxs-lookup"><span data-stu-id="53615-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that DotDigital meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="53615-151">За информация посетете [Декларация за поверителност Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="53615-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="53615-152">Вашият администратор на Dynamics 365 Customer Insights да премахнете това местоназначение за експортиране по всяко време, за да прекратите използването на тази функционалност.</span><span class="sxs-lookup"><span data-stu-id="53615-152">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
