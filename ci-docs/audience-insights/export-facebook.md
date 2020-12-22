---
title: Експортирайте данните от Customer Insights в Facebook Ads Manager
description: Научете как да конфигурирате връзката към Facebook Ads Manager.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 8260e3b5e529f3d54678d9d6e11aebb2795e27fd
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643670"
---
# <a name="connector-for-facebook-ads-manager-preview"></a><span data-ttu-id="718c5-103">Конектор за Facebook Ads Manager (преглед)</span><span class="sxs-lookup"><span data-stu-id="718c5-103">Connector for Facebook Ads Manager (preview)</span></span>

<span data-ttu-id="718c5-104">Експортирайте сегменти от унифицирани потребителски профили във Facebook Ads Manager за създаване на кампании във Facebook и Instagram.</span><span class="sxs-lookup"><span data-stu-id="718c5-104">Export segments of unified customer profiles to Facebook Ads Manager to create campaigns on Facebook and Instagram.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="718c5-105">Предварителни изисквания</span><span class="sxs-lookup"><span data-stu-id="718c5-105">Prerequisites</span></span>

- <span data-ttu-id="718c5-106">Трябва да имате [**акаунт във Facebook Ad**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account), който включва [**акаунт във Facebook Business**](https://business.facebook.com/).</span><span class="sxs-lookup"><span data-stu-id="718c5-106">You need to have a [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) which includes a [**Facebook Business Account**](https://business.facebook.com/).</span></span>
- <span data-ttu-id="718c5-107">Трябва да сте администратор на [**акаунта във Facebook Ad**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span><span class="sxs-lookup"><span data-stu-id="718c5-107">You need to be an administrator on the [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span></span>

## <a name="connect-to-facebook-ads-manager"></a><span data-ttu-id="718c5-108">Свързване към Facebook Ads Manager</span><span class="sxs-lookup"><span data-stu-id="718c5-108">Connect to Facebook Ads Manager</span></span>

1. <span data-ttu-id="718c5-109">Отидете на **Администратор** > **Експортиране на дестинации**.</span><span class="sxs-lookup"><span data-stu-id="718c5-109">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="718c5-110">Под **Facebook Ads Manager** изберете **Настройване**.</span><span class="sxs-lookup"><span data-stu-id="718c5-110">Under **Facebook Ads Manager**, select **Set up**.</span></span>

1. <span data-ttu-id="718c5-111">Въведете разпознаваемо име за местоназначението за експортиране в полето **Показвано име**.</span><span class="sxs-lookup"><span data-stu-id="718c5-111">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="718c5-112">Изберете **Продължаване с Facebook**, за да влезете във вашия акаунт във Facebook Ad.</span><span class="sxs-lookup"><span data-stu-id="718c5-112">Select **Continue with Facebook** to sign in to your Facebook Ad Account.</span></span>

1. <span data-ttu-id="718c5-113">Позволете разрешението **ads_management** след удостоверяване с Facebook.</span><span class="sxs-lookup"><span data-stu-id="718c5-113">Allow the **ads_management** permission after authenticating with Facebook.</span></span>

1. <span data-ttu-id="718c5-114">Изберете **Акаунт във Facebook**, с който искате да работите.</span><span class="sxs-lookup"><span data-stu-id="718c5-114">Select the **Facebook Ads Account** that you want to work with.</span></span>

1. <span data-ttu-id="718c5-115">Изберете **Съществуваща потребителска аудитория** от падащия списък или създайте **Нова потребителска аудитория**.</span><span class="sxs-lookup"><span data-stu-id="718c5-115">Select an **Existing custom audience** from the drop-down list or create a **New custom audience**.</span></span> <span data-ttu-id="718c5-116">За повече информация вижте [**Аудитории във Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span><span class="sxs-lookup"><span data-stu-id="718c5-116">For more information, see [**Audiences in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span></span>

1. <span data-ttu-id="718c5-117">Изберете **Приемам**, за да потвърдите **Поверителност на данните и съответствие**.</span><span class="sxs-lookup"><span data-stu-id="718c5-117">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="718c5-118">Изберете **Напред**, за да конфигурирате експортирането.</span><span class="sxs-lookup"><span data-stu-id="718c5-118">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="718c5-119">Конфигуриране на конектор</span><span class="sxs-lookup"><span data-stu-id="718c5-119">Configure the connector</span></span>

1. <span data-ttu-id="718c5-120">В **Избор на основно поле за идентификатор** изберете **Имейл**, **Име и адрес** или **Телефон** за изпращане до Facebook Ads Manager.</span><span class="sxs-lookup"><span data-stu-id="718c5-120">In the **Choose your key identifier field**, select **Email**, **Name and address**, or **Phone** to send to Facebook Ads Manager.</span></span>

1. <span data-ttu-id="718c5-121">Нанесете съответните атрибути от обединения клиент за избрания идентификатор на ключ.</span><span class="sxs-lookup"><span data-stu-id="718c5-121">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>
   > <span data-ttu-id="718c5-122">[СЪВЕТ] Най-добрите шансове за съвпадение се появяват, ако изберете **Имейл** като основен идентификатор.</span><span class="sxs-lookup"><span data-stu-id="718c5-122">[TIP] The best chances for a match occur if you select **Email** as key identifier.</span></span> <span data-ttu-id="718c5-123">Добавянето на допълнителни идентификатори може да подобри съвпадението.</span><span class="sxs-lookup"><span data-stu-id="718c5-123">Adding additional identifiers may improve the matching.</span></span>

1. <span data-ttu-id="718c5-124">Изберете **Добавяне на атрибут**, за да съпоставите допълнителни атрибути, които да изпратите на Facebook Ads Manager.</span><span class="sxs-lookup"><span data-stu-id="718c5-124">Select **Add attribute** to map additional attributes to send to Facebook Ads Manager.</span></span> <span data-ttu-id="718c5-125">Атрибути от Facebook Ads Manager се съпоставят със следните лесни за разбиране имена: **FN** = **Собствено име**, **LN** = **Фамилно име**, **FI** = **Първи инициал**, **PHONE** = **Телефон**, **GEN** = **Пол**, **DOB** = **Дата на раждане**, **ST** = **Състояние**, **CT** = **Град**, **ZIP** = **Пощенски код**, **COUNTRY** = **Държава/регион**</span><span class="sxs-lookup"><span data-stu-id="718c5-125">Attributes from Facebook Ads Manager are mapping to the following user friendly names: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / Zip code**, **COUNTRY** = **Country / Region**</span></span>

1. <span data-ttu-id="718c5-126">Изберете сегментите, които искате да експортирате.</span><span class="sxs-lookup"><span data-stu-id="718c5-126">Select the segments you want to export.</span></span>

1. <span data-ttu-id="718c5-127">Изберете **Записване**.</span><span class="sxs-lookup"><span data-stu-id="718c5-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="718c5-128">Експортиране на данните</span><span class="sxs-lookup"><span data-stu-id="718c5-128">Export the data</span></span>

<span data-ttu-id="718c5-129">Можете да [експортирате данни при поискване](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="718c5-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="718c5-130">Експортирането също ще се изпълнява с всяко [планирано обновяване](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="718c5-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="718c5-131">Поверителност и съответствие на данните</span><span class="sxs-lookup"><span data-stu-id="718c5-131">Data privacy and compliance</span></span>

<span data-ttu-id="718c5-132">Когато активирате Dynamics 365 Customer Insights, за да предавате данни на Facebook Ads Manager, разрешавате прехвърляне на данни извън границата за съответствие за Dynamics 365 Customer Insights, включително потенциално чувствителни данни като Лични данни.</span><span class="sxs-lookup"><span data-stu-id="718c5-132">When you enable Dynamics 365 Customer Insights to transmit data to Facebook Ads Manager, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="718c5-133">Microsoft ще прехвърли такива данни по ваше указание, но вие носите отговорност да гарантирате, че Facebook Ads отговаря на всички задължения за поверителност или сигурност, които може да имате.</span><span class="sxs-lookup"><span data-stu-id="718c5-133">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Facebook Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="718c5-134">За информация посетете [Декларация за поверителност Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="718c5-134">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="718c5-135">Вашият администратор на Dynamics 365 Customer Insights да премахнете това местоназначение за експортиране по всяко време, за да прекратите използването на тази функционалност.</span><span class="sxs-lookup"><span data-stu-id="718c5-135">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
