---
title: Експортирайте данните от Customer Insights в Facebook Мениджър за реклами
description: Научете как да конфигурирате връзката и да експортирате в мениджъра за реклами във Facebook.
ms.date: 04/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ca32906a98bc734639fb369d6f5a92e8888fd850
ms.sourcegitcommit: 6d5dd572f75ba4c0303ec77c3b74e4318d52705c
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 04/16/2021
ms.locfileid: "5906797"
---
# <a name="export-segments-list-to-facebook-ads-manager-preview"></a><span data-ttu-id="50b72-103">Експортиране на списък със сегменти в мениджъра за реклами във Facebook (преглед)</span><span class="sxs-lookup"><span data-stu-id="50b72-103">Export segments list to Facebook Ads Manager (preview)</span></span>

<span data-ttu-id="50b72-104">Експортирайте сегменти от унифицирани потребителски профили във Facebook Мениджър за реклами за създаване на кампании във Facebook и Instagram.</span><span class="sxs-lookup"><span data-stu-id="50b72-104">Export segments of unified customer profiles to Facebook Ads Manager to create campaigns on Facebook and Instagram.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="50b72-105">Предварителни изисквания за връзка</span><span class="sxs-lookup"><span data-stu-id="50b72-105">Prerequisites for connection</span></span>

- <span data-ttu-id="50b72-106">Трябва да имате [**акаунт за реклами във Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account), който включва [**бизнес акаунт във Facebook**](https://business.facebook.com/).</span><span class="sxs-lookup"><span data-stu-id="50b72-106">You need to have a [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) that includes a [**Facebook Business Account**](https://business.facebook.com/).</span></span>
- <span data-ttu-id="50b72-107">Трябва да сте администратор на [**акаунта във Facebook Ad**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span><span class="sxs-lookup"><span data-stu-id="50b72-107">You need to be an administrator on the [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="50b72-108">Известни ограничения</span><span class="sxs-lookup"><span data-stu-id="50b72-108">Known limitations</span></span>

- <span data-ttu-id="50b72-109">До 10 милиона клиентски профила на експортиране към мениджъра за реклами във Facebook.</span><span class="sxs-lookup"><span data-stu-id="50b72-109">Up to 10 million customer profile per export to Facebook Ads Manager.</span></span>
- <span data-ttu-id="50b72-110">Експортирането в мениджъра за реклами във Facebook е ограничено до сегменти.</span><span class="sxs-lookup"><span data-stu-id="50b72-110">Export to Facebook Ads Manager is limited to segments.</span></span>
- <span data-ttu-id="50b72-111">Създавайте или актуализирайте персонализирани аудитории във Facebook само от тип *списък с клиенти*.</span><span class="sxs-lookup"><span data-stu-id="50b72-111">Create or update custom audiences in Facebook of type *customer list* only.</span></span>
- <span data-ttu-id="50b72-112">Експортирането на сегменти с общо 10 милион профила може да отнеме до 90 минути.</span><span class="sxs-lookup"><span data-stu-id="50b72-112">Exporting segments with a total of 10 million profiles can take up to 90 minutes to complete.</span></span>

## <a name="set-up-connection-to-facebook-ads-manager"></a><span data-ttu-id="50b72-113">Настройване на връзка с мениджъра за реклами във Facebook</span><span class="sxs-lookup"><span data-stu-id="50b72-113">Set up connection to Facebook Ads Manager</span></span>

<span data-ttu-id="50b72-114">Преди потребителите да създадат експортиране, администраторът трябва да конфигурира връзката с услугата и да позволи на участниците да използват връзката.</span><span class="sxs-lookup"><span data-stu-id="50b72-114">Before users can create an export, an administrator must configure the connection to the service and allow contributors to use the connection.</span></span>

1. <span data-ttu-id="50b72-115">Отидете на **Администратор** > **Връзки**.</span><span class="sxs-lookup"><span data-stu-id="50b72-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="50b72-116">Изберете **Добавяне на връзка** и изберете **Мениджър за реклами във Facebook** за конфигуриране на връзката.</span><span class="sxs-lookup"><span data-stu-id="50b72-116">Select **Add connection** and choose **Facebook Ads Manager** to configure the connection.</span></span>

1. <span data-ttu-id="50b72-117">Въведете разпознаваемо име за връзката в полето **Показвано име**.</span><span class="sxs-lookup"><span data-stu-id="50b72-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="50b72-118">Показваното име и типът описват тази връзка.</span><span class="sxs-lookup"><span data-stu-id="50b72-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="50b72-119">Препоръчваме да изберете име, което обяснява целта на връзката.</span><span class="sxs-lookup"><span data-stu-id="50b72-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="50b72-120">Изберете кой може да използва тази връзка.</span><span class="sxs-lookup"><span data-stu-id="50b72-120">Choose who can use this connection.</span></span> <span data-ttu-id="50b72-121">Ако не предприемете нищо, по подразбиране ще е **Администратори**.</span><span class="sxs-lookup"><span data-stu-id="50b72-121">If you take no action, the default will be **Administrators**.</span></span> <span data-ttu-id="50b72-122">За повече информация вижте [Разрешаване на сътрудници да използват връзка за експортиране](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="50b72-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="50b72-123">Удостоверяване с Facebook Ads:</span><span class="sxs-lookup"><span data-stu-id="50b72-123">Authenticate with Facebook Ads:</span></span> 

   1. <span data-ttu-id="50b72-124">Изберете **Продължаване с Facebook**, за да влезете във вашия акаунт във Facebook Ad.</span><span class="sxs-lookup"><span data-stu-id="50b72-124">Select **Continue with Facebook** to sign in to your Facebook Ad Account.</span></span>

   1. <span data-ttu-id="50b72-125">Позволете разрешението **ads_management** след удостоверяване с Facebook.</span><span class="sxs-lookup"><span data-stu-id="50b72-125">Allow the **ads_management** permission after authenticating with Facebook.</span></span>

   1. <span data-ttu-id="50b72-126">Изберете **Акаунт във Facebook**, с който искате да работите.</span><span class="sxs-lookup"><span data-stu-id="50b72-126">Select the **Facebook Ads Account** that you want to work with.</span></span>

   1. <span data-ttu-id="50b72-127">Изберете **Съществуваща потребителска аудитория** от падащия списък или създайте **Нова потребителска аудитория**.</span><span class="sxs-lookup"><span data-stu-id="50b72-127">Select an **Existing custom audience** from the drop-down list or create a **New custom audience**.</span></span> <span data-ttu-id="50b72-128">За повече информация вижте [**Аудитории във Facebook Мениджър за реклами**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span><span class="sxs-lookup"><span data-stu-id="50b72-128">For more information, see [**Audiences in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span></span>
      > [!NOTE]
      > <span data-ttu-id="50b72-129">Можете само да създавате или актуализирате персонализирани аудитории във Facebook от типа *списък с клиенти* с това експортиране.</span><span class="sxs-lookup"><span data-stu-id="50b72-129">You can only create or update custom audiences on Facebook of the type *customer list* with this export.</span></span> <span data-ttu-id="50b72-130">В някои случаи виждате персонализирани аудитории от различен тип в падащия списък.</span><span class="sxs-lookup"><span data-stu-id="50b72-130">In some cases, you see custom audiences of different types in the drop-down list.</span></span> <span data-ttu-id="50b72-131">Избор на различен тип от *списък с клиенти* ще доведе до неуспешно експортиране.</span><span class="sxs-lookup"><span data-stu-id="50b72-131">Selecting a different type than *customer list* will result in a failing export.</span></span> 

1. <span data-ttu-id="50b72-132">Прегледайте **Поверителност и съответствие на данните** и изберете **Приемам**.</span><span class="sxs-lookup"><span data-stu-id="50b72-132">Review the **Data privacy and compliance** and select **I agree**.</span></span>

1. <span data-ttu-id="50b72-133">Изберете **Записване**, за да завършите връзката.</span><span class="sxs-lookup"><span data-stu-id="50b72-133">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="50b72-134">Конфигуриране на експортиране</span><span class="sxs-lookup"><span data-stu-id="50b72-134">Configure an export</span></span>

<span data-ttu-id="50b72-135">Можете да конфигурирате това експортиране, ако имате достъп до връзка от този тип.</span><span class="sxs-lookup"><span data-stu-id="50b72-135">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="50b72-136">За повече информация вижте [Разрешения, необходими за конфигуриране на експортиране](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="50b72-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="50b72-137">Отидете на **Данни** > **Експортиране**.</span><span class="sxs-lookup"><span data-stu-id="50b72-137">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="50b72-138">За да създадете ново експортиране, изберете **Добавяне на местоназначение**.</span><span class="sxs-lookup"><span data-stu-id="50b72-138">To create a new export, select **Add destination**.</span></span> 

1. <span data-ttu-id="50b72-139">Във **Връзка за експортиране** изберете връзка от секцията **мениджъра за реклами във Facebook**.</span><span class="sxs-lookup"><span data-stu-id="50b72-139">In **Connection for export** choose a connection from the **Facebook Ads Manager** section.</span></span> <span data-ttu-id="50b72-140">Ако не виждате името на тази секция, няма достъпни за вас връзки от този тип.</span><span class="sxs-lookup"><span data-stu-id="50b72-140">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="50b72-141">В **Избор на основно поле за идентификатор** изберете **Имейл**, **Име и адрес** или **Телефон** за изпращане до Facebook Мениджър за реклами.</span><span class="sxs-lookup"><span data-stu-id="50b72-141">In the **Choose your key identifier field**, select **Email**, **Name and address**, or **Phone** to send to Facebook Ads Manager.</span></span> 

1. <span data-ttu-id="50b72-142">Въведете разпознаваемо име за връзката в полето **Показвано име**.</span><span class="sxs-lookup"><span data-stu-id="50b72-142">Give your connection a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="50b72-143">Нанесете съответните атрибути от обединения клиент за избрания идентификатор на ключ.</span><span class="sxs-lookup"><span data-stu-id="50b72-143">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>
   > <span data-ttu-id="50b72-144">[СЪВЕТ] Най-добрите шансове за съвпадение се появяват, ако изберете **Имейл** като основен идентификатор.</span><span class="sxs-lookup"><span data-stu-id="50b72-144">[TIP] The best chances for a match occur if you select **Email** as key identifier.</span></span> <span data-ttu-id="50b72-145">Добавянето на допълнителни идентификатори може да подобри съвпадението.</span><span class="sxs-lookup"><span data-stu-id="50b72-145">Adding additional identifiers may improve the matching.</span></span>

1. <span data-ttu-id="50b72-146">Изберете **Добавяне на атрибут**, за да нанесете още атрибути, които да изпратите до мениджъра за реклами във Facebook.</span><span class="sxs-lookup"><span data-stu-id="50b72-146">Select **Add attribute** to map more attributes to send to Facebook Ads Manager.</span></span> <span data-ttu-id="50b72-147">Атрибутите от мениджъра за реклами във Facebook се съпоставят със следните лесни за разбиране имена: **FN** = **Собствено име**, **LN** = **Фамилно име**, **FI** = **Първи инициал**, **PHONE** = **Телефон**, **GEN** = **Пол**, **DOB** = **Дата на раждане**, **ST** = **Състояние**, **CT** = **Град**, **ZIP** = **Пощенски код**, **COUNTRY** = **Държава/регион**</span><span class="sxs-lookup"><span data-stu-id="50b72-147">Attributes from Facebook Ads Manager are mapping to the following user-friendly names: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / Zip code**, **COUNTRY** = **Country / Region**</span></span>

1. <span data-ttu-id="50b72-148">Изберете сегментите, които искате да експортирате.</span><span class="sxs-lookup"><span data-stu-id="50b72-148">Select the segments you want to export.</span></span>

1. <span data-ttu-id="50b72-149">Изберете **Записване**.</span><span class="sxs-lookup"><span data-stu-id="50b72-149">Select **Save**.</span></span>

<span data-ttu-id="50b72-150">Запазването на експортиране не го изпълнява незабавно.</span><span class="sxs-lookup"><span data-stu-id="50b72-150">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="50b72-151">Експортирането се изпълнява с всяко [планирано обновяване](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="50b72-151">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="50b72-152">Може също [да експортирате данни при поискване](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="50b72-152">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="50b72-153">Поверителност и съответствие на данните</span><span class="sxs-lookup"><span data-stu-id="50b72-153">Data privacy and compliance</span></span>

<span data-ttu-id="50b72-154">Когато активирате Dynamics 365 Customer Insights, за да предавате данни на Facebook Мениджър за реклами, разрешавате прехвърляне на данни извън границата за съответствие за Dynamics 365 Customer Insights, включително потенциално чувствителни данни като Лични данни.</span><span class="sxs-lookup"><span data-stu-id="50b72-154">When you enable Dynamics 365 Customer Insights to transmit data to Facebook Ads Manager, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="50b72-155">Microsoft ще прехвърли такива данни по ваше указание, но вие носите отговорност да гарантирате, че Facebook Ads отговаря на всички задължения за поверителност или сигурност, които може да имате.</span><span class="sxs-lookup"><span data-stu-id="50b72-155">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Facebook Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="50b72-156">За информация посетете [Декларация за поверителност Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="50b72-156">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="50b72-157">Вашият администратор на Dynamics 365 Customer Insights да премахнете това местоназначение за експортиране по всяко време, за да прекратите използването на тази функционалност.</span><span class="sxs-lookup"><span data-stu-id="50b72-157">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
