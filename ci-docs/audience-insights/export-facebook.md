---
title: Експортирайте данните от Customer Insights в Facebook Мениджър за реклами
description: Научете как да конфигурирате връзката към Facebook Мениджър за реклами.
ms.date: 06/05/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3e2b52fe743563e4bf61d870cbf1718e6c752a67
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596662"
---
# <a name="connector-for-facebook-ads-manager-preview"></a><span data-ttu-id="3399b-103">Конектор за Facebook Мениджър за реклами (преглед)</span><span class="sxs-lookup"><span data-stu-id="3399b-103">Connector for Facebook Ads Manager (preview)</span></span>

<span data-ttu-id="3399b-104">Експортирайте сегменти от унифицирани потребителски профили във Facebook Мениджър за реклами за създаване на кампании във Facebook и Instagram.</span><span class="sxs-lookup"><span data-stu-id="3399b-104">Export segments of unified customer profiles to Facebook Ads Manager to create campaigns on Facebook and Instagram.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3399b-105">Предварителни изисквания</span><span class="sxs-lookup"><span data-stu-id="3399b-105">Prerequisites</span></span>

- <span data-ttu-id="3399b-106">Трябва да имате [**акаунт във Facebook Ad**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account), който включва [**акаунт във Facebook Business**](https://business.facebook.com/).</span><span class="sxs-lookup"><span data-stu-id="3399b-106">You need to have a [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) which includes a [**Facebook Business Account**](https://business.facebook.com/).</span></span>
- <span data-ttu-id="3399b-107">Трябва да сте администратор на [**акаунта във Facebook Ad**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span><span class="sxs-lookup"><span data-stu-id="3399b-107">You need to be an administrator on the [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span></span>

## <a name="connect-to-facebook-ads-manager"></a><span data-ttu-id="3399b-108">Свързване към Facebook Мениджър за реклами</span><span class="sxs-lookup"><span data-stu-id="3399b-108">Connect to Facebook Ads Manager</span></span>

1. <span data-ttu-id="3399b-109">Отидете на **Администратор** > **Експортиране на дестинации**.</span><span class="sxs-lookup"><span data-stu-id="3399b-109">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="3399b-110">Под **Facebook Мениджър за реклами** изберете **Настройване**.</span><span class="sxs-lookup"><span data-stu-id="3399b-110">Under **Facebook Ads Manager**, select **Set up**.</span></span>

1. <span data-ttu-id="3399b-111">Въведете разпознаваемо име за местоназначението за експортиране в полето **Показвано име**.</span><span class="sxs-lookup"><span data-stu-id="3399b-111">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="3399b-112">Изберете **Продължаване с Facebook**, за да влезете във вашия акаунт във Facebook Ad.</span><span class="sxs-lookup"><span data-stu-id="3399b-112">Select **Continue with Facebook** to sign in to your Facebook Ad Account.</span></span>

1. <span data-ttu-id="3399b-113">Позволете разрешението **ads_management** след удостоверяване с Facebook.</span><span class="sxs-lookup"><span data-stu-id="3399b-113">Allow the **ads_management** permission after authenticating with Facebook.</span></span>

1. <span data-ttu-id="3399b-114">Изберете **Акаунт във Facebook**, с който искате да работите.</span><span class="sxs-lookup"><span data-stu-id="3399b-114">Select the **Facebook Ads Account** that you want to work with.</span></span>

1. <span data-ttu-id="3399b-115">Изберете **Съществуваща потребителска аудитория** от падащия списък или създайте **Нова потребителска аудитория**.</span><span class="sxs-lookup"><span data-stu-id="3399b-115">Select an **Existing custom audience** from the drop-down list or create a **New custom audience**.</span></span> <span data-ttu-id="3399b-116">За повече информация вижте [**Аудитории във Facebook Мениджър за реклами**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span><span class="sxs-lookup"><span data-stu-id="3399b-116">For more information, see [**Audiences in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span></span>

1. <span data-ttu-id="3399b-117">Изберете **Приемам**, за да потвърдите **Поверителност на данните и съответствие**.</span><span class="sxs-lookup"><span data-stu-id="3399b-117">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="3399b-118">Изберете **Напред**, за да конфигурирате експортирането.</span><span class="sxs-lookup"><span data-stu-id="3399b-118">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="3399b-119">Конфигуриране на конектор</span><span class="sxs-lookup"><span data-stu-id="3399b-119">Configure the connector</span></span>

1. <span data-ttu-id="3399b-120">В **Избор на основно поле за идентификатор** изберете **Имейл**, **Име и адрес** или **Телефон** за изпращане до Facebook Мениджър за реклами.</span><span class="sxs-lookup"><span data-stu-id="3399b-120">In the **Choose your key identifier field**, select **Email**, **Name and address**, or **Phone** to send to Facebook Ads Manager.</span></span>

1. <span data-ttu-id="3399b-121">Нанесете съответните атрибути от обединения клиент за избрания идентификатор на ключ.</span><span class="sxs-lookup"><span data-stu-id="3399b-121">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>
   > <span data-ttu-id="3399b-122">[СЪВЕТ] Най-добрите шансове за съвпадение се появяват, ако изберете **Имейл** като основен идентификатор.</span><span class="sxs-lookup"><span data-stu-id="3399b-122">[TIP] The best chances for a match occur if you select **Email** as key identifier.</span></span> <span data-ttu-id="3399b-123">Добавянето на допълнителни идентификатори може да подобри съвпадението.</span><span class="sxs-lookup"><span data-stu-id="3399b-123">Adding additional identifiers may improve the matching.</span></span>

1. <span data-ttu-id="3399b-124">Изберете **Добавяне на атрибут**, за да съпоставите допълнителни атрибути, които да изпратите на Facebook Мениджър за реклами.</span><span class="sxs-lookup"><span data-stu-id="3399b-124">Select **Add attribute** to map additional attributes to send to Facebook Ads Manager.</span></span> <span data-ttu-id="3399b-125">Атрибути от Facebook Мениджър за реклами се съпоставят със следните лесни за разбиране имена: **FN** = **Собствено име**, **LN** = **Фамилно име**, **FI** = **Първи инициал**, **PHONE** = **Телефон**, **GEN** = **Пол**, **DOB** = **Дата на раждане**, **ST** = **Състояние**, **CT** = **Град**, **ZIP** = **Пощенски код**, **COUNTRY** = **Държава/регион**</span><span class="sxs-lookup"><span data-stu-id="3399b-125">Attributes from Facebook Ads Manager are mapping to the following user friendly names: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / Zip code**, **COUNTRY** = **Country / Region**</span></span>

1. <span data-ttu-id="3399b-126">Изберете сегментите, които искате да експортирате.</span><span class="sxs-lookup"><span data-stu-id="3399b-126">Select the segments you want to export.</span></span>

1. <span data-ttu-id="3399b-127">Изберете **Записване**.</span><span class="sxs-lookup"><span data-stu-id="3399b-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="3399b-128">Експортиране на данните</span><span class="sxs-lookup"><span data-stu-id="3399b-128">Export the data</span></span>

<span data-ttu-id="3399b-129">Можете да [експортирате данни при поискване](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="3399b-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="3399b-130">Експортирането също ще се изпълнява с всяко [планирано обновяване](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="3399b-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="3399b-131">Известни ограничения</span><span class="sxs-lookup"><span data-stu-id="3399b-131">Known limitations</span></span>

- <span data-ttu-id="3399b-132">До 10 милиона клиентски профила на експортиране към Facebook Мениджър за реклами</span><span class="sxs-lookup"><span data-stu-id="3399b-132">Up to 10 million customer profile per export to Facebook Ads Manager</span></span> 
- <span data-ttu-id="3399b-133">Експортирането в Facebook Мениджър за реклами е ограничено до сегменти</span><span class="sxs-lookup"><span data-stu-id="3399b-133">Export to Facebook Ads Manager is limited to segments</span></span>
- <span data-ttu-id="3399b-134">Експортирането на сегменти с общо 10 милион профила може да отнеме до 90 минути</span><span class="sxs-lookup"><span data-stu-id="3399b-134">Exporting segments with a total of 10 million profiles can take up to 90 minutes to complete</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="3399b-135">Поверителност и съответствие на данните</span><span class="sxs-lookup"><span data-stu-id="3399b-135">Data privacy and compliance</span></span>

<span data-ttu-id="3399b-136">Когато активирате Dynamics 365 Customer Insights, за да предавате данни на Facebook Мениджър за реклами, разрешавате прехвърляне на данни извън границата за съответствие за Dynamics 365 Customer Insights, включително потенциално чувствителни данни като Лични данни.</span><span class="sxs-lookup"><span data-stu-id="3399b-136">When you enable Dynamics 365 Customer Insights to transmit data to Facebook Ads Manager, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="3399b-137">Microsoft ще прехвърли такива данни по ваше указание, но вие носите отговорност да гарантирате, че Facebook Ads отговаря на всички задължения за поверителност или сигурност, които може да имате.</span><span class="sxs-lookup"><span data-stu-id="3399b-137">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Facebook Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="3399b-138">За информация посетете [Декларация за поверителност Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="3399b-138">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="3399b-139">Вашият администратор на Dynamics 365 Customer Insights да премахнете това местоназначение за експортиране по всяко време, за да прекратите използването на тази функционалност.</span><span class="sxs-lookup"><span data-stu-id="3399b-139">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]