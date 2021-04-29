---
title: Експортирайте данните от Customer Insights в Marketo
description: Научете как да конфигурирате връзката и да експортирате в Marketo.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 01290d5fae7af1737b73373d75e334ae1ed67d37
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759808"
---
# <a name="export-segments-to-marketo-preview"></a><span data-ttu-id="5c097-103">Експортиране на сегменти в Marketo (преглед)</span><span class="sxs-lookup"><span data-stu-id="5c097-103">Export segments to Marketo (preview)</span></span>

<span data-ttu-id="5c097-104">Експортирайте сегменти на унифицирани клиентски профили, за да генерирате кампании, да предоставяте маркетинг по имейл и да използвате конкретни групи клиенти с Marketo.</span><span class="sxs-lookup"><span data-stu-id="5c097-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="5c097-105">Предварителни изисквания за връзка</span><span class="sxs-lookup"><span data-stu-id="5c097-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="5c097-106">Имате [Акаунт в Marketo](https://login.marketo.com/) и съответните идентификационни данни на администратора.</span><span class="sxs-lookup"><span data-stu-id="5c097-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="5c097-107">В Marketo има съществуващи списъци и съответните идентификатори.</span><span class="sxs-lookup"><span data-stu-id="5c097-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="5c097-108">За повече информация вижте [Списъци на Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="5c097-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="5c097-109">Имате [конфигурирани сегменти](segments.md).</span><span class="sxs-lookup"><span data-stu-id="5c097-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="5c097-110">Единните клиентски профили в експортираните сегменти съдържат поле, представляващо имейл адрес.</span><span class="sxs-lookup"><span data-stu-id="5c097-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="5c097-111">Известни ограничения</span><span class="sxs-lookup"><span data-stu-id="5c097-111">Known limitations</span></span>

- <span data-ttu-id="5c097-112">До 1 милион профила на износ към Marketo.</span><span class="sxs-lookup"><span data-stu-id="5c097-112">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="5c097-113">Експортирането в Marketo е ограничено до сегменти.</span><span class="sxs-lookup"><span data-stu-id="5c097-113">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="5c097-114">Експортирането на сегменти с общо 1 милион профила може да отнеме до 3 часа.</span><span class="sxs-lookup"><span data-stu-id="5c097-114">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="5c097-115">Броят на профилите, които можете да експортирате в Marketo, зависи и е ограничен от вашия договор с Marketo.</span><span class="sxs-lookup"><span data-stu-id="5c097-115">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="set-up-connection-to-marketo"></a><span data-ttu-id="5c097-116">Настройване на връзка към Marketo</span><span class="sxs-lookup"><span data-stu-id="5c097-116">Set up connection to Marketo</span></span>

1. <span data-ttu-id="5c097-117">Отидете на **Администратор** > **Връзки**.</span><span class="sxs-lookup"><span data-stu-id="5c097-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="5c097-118">Изберете **Добавяне на връзка** и изберете **Marketo** за конфигуриране на връзката.</span><span class="sxs-lookup"><span data-stu-id="5c097-118">Select **Add connection** and choose **Marketo** to configure the connection.</span></span>

1. <span data-ttu-id="5c097-119">Въведете разпознаваемо име за връзката в полето **Показвано име**.</span><span class="sxs-lookup"><span data-stu-id="5c097-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="5c097-120">Показваното име и типът описват тази връзка.</span><span class="sxs-lookup"><span data-stu-id="5c097-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="5c097-121">Препоръчваме да изберете име, което обяснява целта на връзката.</span><span class="sxs-lookup"><span data-stu-id="5c097-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="5c097-122">Изберете кой може да използва тази връзка.</span><span class="sxs-lookup"><span data-stu-id="5c097-122">Choose who can use this connection.</span></span> <span data-ttu-id="5c097-123">Ако не предприемете нищо, по подразбиране ще е Администратори.</span><span class="sxs-lookup"><span data-stu-id="5c097-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="5c097-124">За повече информация вижте [Разрешаване на сътрудници да използват връзка за експортиране](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="5c097-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="5c097-125">Въведете своя **[Идентификатор на клиент на Marketo, тайна на клиента и име на хост на крайна точка на REST](https://developers.marketo.com/rest-api/authentication/)**.</span><span class="sxs-lookup"><span data-stu-id="5c097-125">Enter your **[Marketo client ID, Client secret, and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span>

1. <span data-ttu-id="5c097-126">Изберете **Съгласен съм**, за да потвърдите **Поверителност и съответствие на данните** и изберете **Свържете** за инициализиране на връзката с Marketo.</span><span class="sxs-lookup"><span data-stu-id="5c097-126">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="5c097-127">Изберете **Добавете себе си като потребител за експортиране** и предоставете вашите идентификационни данни на Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="5c097-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="5c097-128">Изберете **Записване**, за да завършите връзката.</span><span class="sxs-lookup"><span data-stu-id="5c097-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="5c097-129">Конфигуриране на експортиране</span><span class="sxs-lookup"><span data-stu-id="5c097-129">Configure an export</span></span>

<span data-ttu-id="5c097-130">Можете да конфигурирате това експортиране, ако имате достъп до връзка от този тип.</span><span class="sxs-lookup"><span data-stu-id="5c097-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="5c097-131">За повече информация вижте [Разрешения, необходими за конфигуриране на експортиране](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="5c097-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="5c097-132">Отидете на **Данни** > **Експортиране**.</span><span class="sxs-lookup"><span data-stu-id="5c097-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="5c097-133">За да създадете ново експортиране, изберете **Добавяне на местоназначение**.</span><span class="sxs-lookup"><span data-stu-id="5c097-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="5c097-134">В полето **Връзка за експортиране** изберете връзка от секцията Marketo.</span><span class="sxs-lookup"><span data-stu-id="5c097-134">In the **Connection for export** field, choose a connection from the Marketo section.</span></span> <span data-ttu-id="5c097-135">Ако не виждате името на тази секция, няма достъпни за вас връзки от този тип.</span><span class="sxs-lookup"><span data-stu-id="5c097-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="5c097-136">Въведете своя **[ИД на списъка на Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span><span class="sxs-lookup"><span data-stu-id="5c097-136">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span></span> 

1. <span data-ttu-id="5c097-137">В секцията **Съвпадение на данни** в полето **Имейл** изберете полето във вашия унифициран потребителски профил, което представлява имейл адреса на клиента.</span><span class="sxs-lookup"><span data-stu-id="5c097-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="5c097-138">По желание можете да експортирате **Собствено име**, **Фамилно име**, **Град**, **Щат** и **Държава/регион** за създаване на по-персонализирани имейли.</span><span class="sxs-lookup"><span data-stu-id="5c097-138">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  to create more personalized emails.</span></span> <span data-ttu-id="5c097-139">Изберете **Добавяне на атрибут** за нанасяне на тези полета.</span><span class="sxs-lookup"><span data-stu-id="5c097-139">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="5c097-140">Изберете сегментите, които искате да експортирате.</span><span class="sxs-lookup"><span data-stu-id="5c097-140">Select the segments you want to export.</span></span> <span data-ttu-id="5c097-141">Можете да експортирате до 1 милион потребителски профила общо в Marketo.</span><span class="sxs-lookup"><span data-stu-id="5c097-141">You can export up to 1 million customer profiles in total to Marketo.</span></span>

1. <span data-ttu-id="5c097-142">Изберете **Записване**.</span><span class="sxs-lookup"><span data-stu-id="5c097-142">Select **Save**.</span></span>

<span data-ttu-id="5c097-143">Запазването на експортиране не го изпълнява незабавно.</span><span class="sxs-lookup"><span data-stu-id="5c097-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="5c097-144">Експортирането се изпълнява с всяко [планирано обновяване](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="5c097-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="5c097-145">Може също [да експортирате данни при поискване](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="5c097-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="5c097-146">В Marketo вече можете да намерите своите сегменти под [Списъци на Marketo](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="5c097-146">In Marketo, you can now find your segments under [Marketo lists](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="5c097-147">Поверителност и съответствие на данните</span><span class="sxs-lookup"><span data-stu-id="5c097-147">Data privacy and compliance</span></span>

<span data-ttu-id="5c097-148">Когато активирате Dynamics 365 Customer Insights, за да предавате данни на Marketo, разрешавате прехвърляне на данни извън границата за съответствие за Dynamics 365 Customer Insights, включително потенциално чувствителни данни като Лични данни.</span><span class="sxs-lookup"><span data-stu-id="5c097-148">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="5c097-149">Microsoft ще прехвърли такива данни по ваше указание, но вие носите отговорност да гарантирате, че Marketo отговаря на всички задължения за поверителност или сигурност, които може да имате.</span><span class="sxs-lookup"><span data-stu-id="5c097-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="5c097-150">За информация посетете [Декларация за поверителност Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="5c097-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="5c097-151">Вашият администратор на Dynamics 365 Customer Insights да премахнете това местоназначение за експортиране по всяко време, за да прекратите използването на тази функционалност.</span><span class="sxs-lookup"><span data-stu-id="5c097-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]