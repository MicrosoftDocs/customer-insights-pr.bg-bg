---
title: Експортирайте данните от Customer Insights в Marketo
description: Научете как да конфигурирате връзката и да експортирате в Marketo.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b5a644e286bd44d4ebf7d1837255326c005b48d6
ms.sourcegitcommit: 74cd4fa9cbb784d9dff174c0eec7b4dcb408d66b
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059303"
---
# <a name="export-segments-to-marketo-preview"></a><span data-ttu-id="63aed-103">Експортиране на сегменти в Marketo (преглед)</span><span class="sxs-lookup"><span data-stu-id="63aed-103">Export segments to Marketo (preview)</span></span>

<span data-ttu-id="63aed-104">Експортирайте сегменти на унифицирани клиентски профили, за да генерирате кампании, да предоставяте маркетинг по имейл и да използвате конкретни групи клиенти с Marketo.</span><span class="sxs-lookup"><span data-stu-id="63aed-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="63aed-105">Предварителни изисквания за връзка</span><span class="sxs-lookup"><span data-stu-id="63aed-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="63aed-106">Имате [Акаунт в Marketo](https://login.marketo.com/) и съответните идентификационни данни на администратора.</span><span class="sxs-lookup"><span data-stu-id="63aed-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="63aed-107">В Marketo има съществуващи списъци и съответните идентификатори.</span><span class="sxs-lookup"><span data-stu-id="63aed-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="63aed-108">За повече информация вижте [Списъци на Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="63aed-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="63aed-109">Имате [конфигурирани сегменти](segments.md).</span><span class="sxs-lookup"><span data-stu-id="63aed-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="63aed-110">Единните клиентски профили в експортираните сегменти съдържат поле, представляващо имейл адрес.</span><span class="sxs-lookup"><span data-stu-id="63aed-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="63aed-111">Известни ограничения</span><span class="sxs-lookup"><span data-stu-id="63aed-111">Known limitations</span></span>

- <span data-ttu-id="63aed-112">До 1 милион профила на износ към Marketo.</span><span class="sxs-lookup"><span data-stu-id="63aed-112">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="63aed-113">Експортирането в Marketo е ограничено до сегменти.</span><span class="sxs-lookup"><span data-stu-id="63aed-113">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="63aed-114">Експортирането на сегменти с общо 1 милион профила може да отнеме до 3 часа.</span><span class="sxs-lookup"><span data-stu-id="63aed-114">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="63aed-115">Броят на профилите, които можете да експортирате в Marketo, зависи и е ограничен от вашия договор с Marketo.</span><span class="sxs-lookup"><span data-stu-id="63aed-115">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="set-up-connection-to-marketo"></a><span data-ttu-id="63aed-116">Настройване на връзка към Marketo</span><span class="sxs-lookup"><span data-stu-id="63aed-116">Set up connection to Marketo</span></span>

1. <span data-ttu-id="63aed-117">Отидете на **Администратор** > **Връзки**.</span><span class="sxs-lookup"><span data-stu-id="63aed-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="63aed-118">Изберете **Добавяне на връзка** и изберете **Marketo** за конфигуриране на връзката.</span><span class="sxs-lookup"><span data-stu-id="63aed-118">Select **Add connection** and choose **Marketo** to configure the connection.</span></span>

1. <span data-ttu-id="63aed-119">Въведете разпознаваемо име за връзката в полето **Показвано име**.</span><span class="sxs-lookup"><span data-stu-id="63aed-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="63aed-120">Показваното име и типът описват тази връзка.</span><span class="sxs-lookup"><span data-stu-id="63aed-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="63aed-121">Препоръчваме да изберете име, което обяснява целта на връзката.</span><span class="sxs-lookup"><span data-stu-id="63aed-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="63aed-122">Изберете кой може да използва тази връзка.</span><span class="sxs-lookup"><span data-stu-id="63aed-122">Choose who can use this connection.</span></span> <span data-ttu-id="63aed-123">Ако не предприемете нищо, по подразбиране ще е Администратори.</span><span class="sxs-lookup"><span data-stu-id="63aed-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="63aed-124">За повече информация вижте [Разрешаване на сътрудници да използват връзка за експортиране](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="63aed-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="63aed-125">Въведете своя **[Идентификатор на клиент на Marketo, тайна на клиента и име на хост на крайна точка на REST](https://developers.marketo.com/rest-api/authentication/)**.</span><span class="sxs-lookup"><span data-stu-id="63aed-125">Enter your **[Marketo client ID, Client secret, and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span> <span data-ttu-id="63aed-126">Името на хоста REST Endpoint е само името на хоста, без `https://`.</span><span class="sxs-lookup"><span data-stu-id="63aed-126">The REST Endpoint Hostname is the hostname only, without `https://`.</span></span> <span data-ttu-id="63aed-127">Пример: `xyz-abc-123.mktorest.com`.</span><span class="sxs-lookup"><span data-stu-id="63aed-127">Example: `xyz-abc-123.mktorest.com`.</span></span> 

1. <span data-ttu-id="63aed-128">Изберете **Съгласен съм**, за да потвърдите **Поверителност и съответствие на данните** и изберете **Свържете** за инициализиране на връзката с Marketo.</span><span class="sxs-lookup"><span data-stu-id="63aed-128">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="63aed-129">Изберете **Добавете себе си като потребител за експортиране** и предоставете вашите идентификационни данни на Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="63aed-129">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="63aed-130">Изберете **Записване**, за да завършите връзката.</span><span class="sxs-lookup"><span data-stu-id="63aed-130">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="63aed-131">Конфигуриране на експортиране</span><span class="sxs-lookup"><span data-stu-id="63aed-131">Configure an export</span></span>

<span data-ttu-id="63aed-132">Можете да конфигурирате това експортиране, ако имате достъп до връзка от този тип.</span><span class="sxs-lookup"><span data-stu-id="63aed-132">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="63aed-133">За повече информация вижте [Разрешения, необходими за конфигуриране на експортиране](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="63aed-133">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="63aed-134">Отидете на **Данни** > **Експортиране**.</span><span class="sxs-lookup"><span data-stu-id="63aed-134">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="63aed-135">За да създадете ново експортиране, изберете **Добавяне на местоназначение**.</span><span class="sxs-lookup"><span data-stu-id="63aed-135">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="63aed-136">В полето **Връзка за експортиране** изберете връзка от секцията Marketo.</span><span class="sxs-lookup"><span data-stu-id="63aed-136">In the **Connection for export** field, choose a connection from the Marketo section.</span></span> <span data-ttu-id="63aed-137">Ако не виждате името на тази секция, няма достъпни за вас връзки от този тип.</span><span class="sxs-lookup"><span data-stu-id="63aed-137">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="63aed-138">Въведете своя **[ИД на списъка на Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**.</span><span class="sxs-lookup"><span data-stu-id="63aed-138">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**.</span></span> <span data-ttu-id="63aed-139">ИД на списъка е чисто цифрова стойност.</span><span class="sxs-lookup"><span data-stu-id="63aed-139">The list ID is a purely numerical value.</span></span> <span data-ttu-id="63aed-140">Например, ако идентификаторът ви в списъка Marketo е ST12345A7, премахнете символа преди и след цифрите и въведете `12345`.</span><span class="sxs-lookup"><span data-stu-id="63aed-140">For example, if your Marketo list ID is ST12345A7, remove the character before and after the numerals and enter `12345`.</span></span> 

1. <span data-ttu-id="63aed-141">В секцията **Съвпадение на данни** в полето **Имейл** изберете полето във вашия унифициран потребителски профил, което представлява имейл адреса на клиента.</span><span class="sxs-lookup"><span data-stu-id="63aed-141">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="63aed-142">По желание можете да експортирате **Собствено име**, **Фамилно име**, **Град**, **Щат** и **Държава/регион** за създаване на по-персонализирани имейли.</span><span class="sxs-lookup"><span data-stu-id="63aed-142">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  to create more personalized emails.</span></span> <span data-ttu-id="63aed-143">Изберете **Добавяне на атрибут** за нанасяне на тези полета.</span><span class="sxs-lookup"><span data-stu-id="63aed-143">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="63aed-144">Изберете сегментите, които искате да експортирате.</span><span class="sxs-lookup"><span data-stu-id="63aed-144">Select the segments you want to export.</span></span> <span data-ttu-id="63aed-145">Можете да експортирате до 1 милион потребителски профила общо в Marketo.</span><span class="sxs-lookup"><span data-stu-id="63aed-145">You can export up to 1 million customer profiles in total to Marketo.</span></span>

1. <span data-ttu-id="63aed-146">Изберете **Записване**.</span><span class="sxs-lookup"><span data-stu-id="63aed-146">Select **Save**.</span></span>

<span data-ttu-id="63aed-147">Запазването на експортиране не го изпълнява незабавно.</span><span class="sxs-lookup"><span data-stu-id="63aed-147">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="63aed-148">Експортирането се изпълнява с всяко [планирано обновяване](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="63aed-148">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="63aed-149">Може също [да експортирате данни при поискване](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="63aed-149">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="63aed-150">В Marketo вече можете да намерите своите сегменти под [Списъци на Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="63aed-150">In Marketo, you can now find your segments under [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="63aed-151">Поверителност и съответствие на данните</span><span class="sxs-lookup"><span data-stu-id="63aed-151">Data privacy and compliance</span></span>

<span data-ttu-id="63aed-152">Когато активирате Dynamics 365 Customer Insights, за да предавате данни на Marketo, разрешавате прехвърляне на данни извън границата за съответствие за Dynamics 365 Customer Insights, включително потенциално чувствителни данни като Лични данни.</span><span class="sxs-lookup"><span data-stu-id="63aed-152">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="63aed-153">Microsoft ще прехвърли такива данни по ваше указание, но вие носите отговорност да гарантирате, че Marketo отговаря на всички задължения за поверителност или сигурност, които може да имате.</span><span class="sxs-lookup"><span data-stu-id="63aed-153">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="63aed-154">За информация посетете [Декларация за поверителност Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="63aed-154">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="63aed-155">Вашият администратор на Dynamics 365 Customer Insights да премахнете това местоназначение за експортиране по всяко време, за да прекратите използването на тази функционалност.</span><span class="sxs-lookup"><span data-stu-id="63aed-155">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
