---
title: Инсталиране и конфигуриране на добавката за карта на клиент
description: Инсталиране и конфигуриране на добавка за карта на клиент за Dynamics 365 Customer Insights.
ms.date: 08/04/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: aab5deaf89b4b019f6688a1bca950ec2277ad5fb
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644030"
---
# <a name="customer-card-add-in-preview"></a><span data-ttu-id="76bde-103">Добавка за карта на клиент (преглед)</span><span class="sxs-lookup"><span data-stu-id="76bde-103">Customer Card Add-in (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="76bde-104">Получете 360-градусов изглед на вашите клиенти директно в приложенията на Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="76bde-104">Get a 360-degree view of your customers directly in Dynamics 365 apps.</span></span> <span data-ttu-id="76bde-105">Преглеждайте демографски данни, аналитични данни и времеви линии на дейности с добавката за карта на клиент.</span><span class="sxs-lookup"><span data-stu-id="76bde-105">View demographics, insights, and activity timelines with the Customer Card Add-in.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="76bde-106">Предварителни изисквания</span><span class="sxs-lookup"><span data-stu-id="76bde-106">Prerequisites</span></span>

- <span data-ttu-id="76bde-107">Приложение Dynamics 365 (като Център за продажби или Център за обслужване на клиенти), версия 9.0 и по-нова версия с включен Унифициран интерфейс.</span><span class="sxs-lookup"><span data-stu-id="76bde-107">Dynamics 365 app (such as Sales Hub or Customer Service Hub), version 9.0 and later with Unified Interface enabled.</span></span>
- <span data-ttu-id="76bde-108">Профили на клиенти, [погълнати от приложението Dynamics 365 с помощта на Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="76bde-108">Customer profiles [ingested from the Dynamics 365 app using Common Data Service](connect-power-query.md).</span></span>
- <span data-ttu-id="76bde-109">Потребителите на добавката за клиентска карта трябва да бъдат [добавени като потребители](permissions.md) в аналитичните данни за аудитория.</span><span class="sxs-lookup"><span data-stu-id="76bde-109">Users of the Customer Card Add-in need to be [added as users](permissions.md) in audience insights.</span></span>
- <span data-ttu-id="76bde-110">[Конфигурирани възможности за търсене и филтриране](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="76bde-110">[Configured search and filter capabilities](search-filter-index.md).</span></span>
- <span data-ttu-id="76bde-111">Демографски контрол: В единния клиентски профил са налични демографски полета, като възраст или пол.</span><span class="sxs-lookup"><span data-stu-id="76bde-111">Demographic control: Demographic fields, such as age or gender are available in the unified customer profile.</span></span>
- <span data-ttu-id="76bde-112">Контрола за допълване: Изисква активно [допълване](enrichment-hub.md), приложено към потребителските профили.</span><span class="sxs-lookup"><span data-stu-id="76bde-112">Enrichment control: Requires active [enrichments](enrichment-hub.md) applied to customer profiles.</span></span>
- <span data-ttu-id="76bde-113">Управление на разузнаването: Изисква данни, генерирани с помощта на Azure Machine Learning ([Прогнози](predictions.md) или [Персонализирани модели](custom-models.md))</span><span class="sxs-lookup"><span data-stu-id="76bde-113">Intelligence control: Requires data generated using Azure Machine Learning ([Predictions](predictions.md) or [Custom Models](custom-models.md))</span></span>
- <span data-ttu-id="76bde-114">Контрол на мярката: Изисква [конфигурирани мерки](measures.md).</span><span class="sxs-lookup"><span data-stu-id="76bde-114">Measure control: Requires [configured measures](measures.md).</span></span>
- <span data-ttu-id="76bde-115">Контрол на времевата линия: Изисква [конфигурирани дейности](activities.md).</span><span class="sxs-lookup"><span data-stu-id="76bde-115">Timeline control: Requires [configured activities](activities.md).</span></span>

## <a name="install-the-customer-card-add-in"></a><span data-ttu-id="76bde-116">Инсталиране на добавката за карта на клиент</span><span class="sxs-lookup"><span data-stu-id="76bde-116">Install the Customer Card Add-in</span></span>

<span data-ttu-id="76bde-117">Добавката за клиентска карта е решение за приложения за ангажиране на клиенти в Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="76bde-117">The Customer Card Add-in is a solution for customer engagement apps in Dynamics 365.</span></span> <span data-ttu-id="76bde-118">За да инсталирате решението, отидете в AppSource и намерете **Динамична карта на клиент**.</span><span class="sxs-lookup"><span data-stu-id="76bde-118">To install the solution, go to AppSource and search for **Dynamics Customer Card**.</span></span> <span data-ttu-id="76bde-119">Изберете [добавката за карта на клиент в AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) и изберете **Изтегляне сега**.</span><span class="sxs-lookup"><span data-stu-id="76bde-119">Select the [Customer Card Add-in on AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) and select **Get It Now**.</span></span>

<span data-ttu-id="76bde-120">Може да се наложи да влезете с администраторските си данни за приложението Dynamics 365, за да инсталирате решението.</span><span class="sxs-lookup"><span data-stu-id="76bde-120">You may need to sign in with your admin credentials for the Dynamics 365 app to install the solution.</span></span>

<span data-ttu-id="76bde-121">Може да отнеме известно време, за да се инсталира решението в средата.</span><span class="sxs-lookup"><span data-stu-id="76bde-121">It can take some time for the solution to be installed to your environment.</span></span>

## <a name="configure-the-customer-card-add-in"></a><span data-ttu-id="76bde-122">Конфигуриране на добавката за карта на клиент</span><span class="sxs-lookup"><span data-stu-id="76bde-122">Configure the Customer Card Add-in</span></span>

1. <span data-ttu-id="76bde-123">Като администратор отидете в секцията **Настройки** в Dynamics 365 и изберете **Решения**.</span><span class="sxs-lookup"><span data-stu-id="76bde-123">As an admin, go to the **Settings** section in Dynamics 365 and select **Solutions**.</span></span>

1. <span data-ttu-id="76bde-124">Изберете връзката **Показвано име** за решението **Добавка за карта на клиент на Dynamics 365 Customer Insights (преглед)**.</span><span class="sxs-lookup"><span data-stu-id="76bde-124">Select the **Display Name** link for the **Dynamics 365 Customer Insights Customer Card Add-in (Preview)** solution.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="76bde-125">![Избор на показвано име](media/select-display-name.png "Избор на показвано име")</span><span class="sxs-lookup"><span data-stu-id="76bde-125">![Select display name](media/select-display-name.png "Select display name")</span></span>

1. <span data-ttu-id="76bde-126">Изберете **Влизане** и въведете идентификационните данни за акаунта на администратор, който използвате за конфигуриране на Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="76bde-126">Select **Sign in** and enter the credentials for the admin account you use to configure Customer Insights.</span></span>

   > [!NOTE]
   > <span data-ttu-id="76bde-127">Проверете дали инструментът за блокиране на изскачащи прозорци на браузъра не блокира прозореца за удостоверяване, когато изберете бутона **Влизане**.</span><span class="sxs-lookup"><span data-stu-id="76bde-127">Check that the browser pop-up blocker does not block the authentication window when you select the **Sign in** button.</span></span>

1. <span data-ttu-id="76bde-128">Изберете средата, от която искате да извлечете данни.</span><span class="sxs-lookup"><span data-stu-id="76bde-128">Select the environment you want to fetch data from.</span></span>

1. <span data-ttu-id="76bde-129">Определете кое поле на полето да се записва в приложението Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="76bde-129">Define which the field mapping to records in the Dynamics 365 app.</span></span>
   - <span data-ttu-id="76bde-130">За да картографирате с контакт, изберете полето в обекта на клиента, което съвпада с идентификатора на обекта ви за контакт.</span><span class="sxs-lookup"><span data-stu-id="76bde-130">To map with a contact, select the field in the Customer entity that matches the ID of your contact entity.</span></span>
   - <span data-ttu-id="76bde-131">За да картографирате с акаунт, изберете полето в обекта на клиента, което съвпада с идентификатора на обекта ви за акаунт.</span><span class="sxs-lookup"><span data-stu-id="76bde-131">To map with an account, select the field in the Customer entity that matches the ID of your account entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="76bde-132">![Поле за ИД на контакт](media/contact-id-field.png "Поле за ИД на контакт")</span><span class="sxs-lookup"><span data-stu-id="76bde-132">![Contact ID field](media/contact-id-field.png "Contact ID field")</span></span>

1. <span data-ttu-id="76bde-133">Изберете **Записване на конфигурацията**, за да запишете настройките.</span><span class="sxs-lookup"><span data-stu-id="76bde-133">Select **Save configuration** to save the settings.</span></span>

1. <span data-ttu-id="76bde-134">След това трябва да зададете права за достъп в Dynamics 365, така че потребителите да могат да персонализират и да преглеждат картата на клиента.</span><span class="sxs-lookup"><span data-stu-id="76bde-134">Next, you need to assign security roles in Dynamics 365 so users can customize and see the customer card.</span></span> <span data-ttu-id="76bde-135">В Dynamics 365 отидете на **Настройки** > **Защита** > **Потребители**.</span><span class="sxs-lookup"><span data-stu-id="76bde-135">In Dynamics 365, go to **Settings** > **Security** > **Users**.</span></span> <span data-ttu-id="76bde-136">Изберете потребителите, за да редактирате потребителските роли, и изберете **Управление на роли**.</span><span class="sxs-lookup"><span data-stu-id="76bde-136">Select the users to edit user roles and select **Manage roles**.</span></span>

1. <span data-ttu-id="76bde-137">Присвоете **Персонализатор на карти на Customer Insights** роля за потребителите, които ще персонализират съдържанието, показано на картата за цялата организация.</span><span class="sxs-lookup"><span data-stu-id="76bde-137">Assign the **Customer Insights Card Customizer** role to users who will customize the content shown on the card for the whole organization.</span></span>

## <a name="add-customer-card-controls-to-forms"></a><span data-ttu-id="76bde-138">Добавяне на контроли на потребителска карта към формуляри</span><span class="sxs-lookup"><span data-stu-id="76bde-138">Add Customer Card controls to forms</span></span>
  
1. <span data-ttu-id="76bde-139">За да добавите контролите на карта на клиент към формуляра на контакт, отидете на **Настройки** > **Персонализации** в Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="76bde-139">To add the Customer Card controls to your Contact form, go to the **Settings** > **Customizations** in Dynamics 365.</span></span>

1. <span data-ttu-id="76bde-140">Изберете **Персонализиране на системата**</span><span class="sxs-lookup"><span data-stu-id="76bde-140">Select **Customize the System**.</span></span>

1. <span data-ttu-id="76bde-141">Преминете към обекта **Контакт**, разгънете менюто му, след което изберете **Формуляри**.</span><span class="sxs-lookup"><span data-stu-id="76bde-141">Browse to the **Contact** entity, expand it and select **Forms**.</span></span>

1. <span data-ttu-id="76bde-142">Изберете формуляра на контакт, към който искате да добавите контролите на картата на клиент.</span><span class="sxs-lookup"><span data-stu-id="76bde-142">Select the contact form to which you want to add the Customer Card controls.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="76bde-143">![Избор на формуляр на контакт](media/contact-active-forms.png "Избор на формуляр на контакт")</span><span class="sxs-lookup"><span data-stu-id="76bde-143">![Select Contact form](media/contact-active-forms.png "Select Contact form")</span></span>

1. <span data-ttu-id="76bde-144">За да добавите контролата на демографски данни, в редактора на формуляри плъзнете някое поле от **прегледа на полетата** до мястото, където искате да се показва контролата.</span><span class="sxs-lookup"><span data-stu-id="76bde-144">To add a control, in the form editor, drag any field from the **Field Explorer** to where you want the control to appear.</span></span>

1. <span data-ttu-id="76bde-145">Изберете полето във формуляра, който току-що добавихте, и след това изберете **Промяна на свойства**.</span><span class="sxs-lookup"><span data-stu-id="76bde-145">Select the field on the form that you just added, and select **Change Properties**.</span></span>

1. <span data-ttu-id="76bde-146">Отидете на раздела **Контроли** и изберете **Добавяне на контрола**.</span><span class="sxs-lookup"><span data-stu-id="76bde-146">Go to the **Controls** tab and select **Add Control**.</span></span> <span data-ttu-id="76bde-147">Изберете една от наличните персонализирани контроли и изберете **Добавяне**.</span><span class="sxs-lookup"><span data-stu-id="76bde-147">Choose one of the available custom controls and select **Add**.</span></span>

1. <span data-ttu-id="76bde-148">В диалоговия прозорец **Свойства на поле** премахнете отметката от квадратчето **Показване на етикета във формуляра**.</span><span class="sxs-lookup"><span data-stu-id="76bde-148">In the **Field Properties** dialog, clear the **Display label on the form** check box.</span></span>

1. <span data-ttu-id="76bde-149">Изберете опцията **Уеб** за контролата.</span><span class="sxs-lookup"><span data-stu-id="76bde-149">Select the **Web** option for the control.</span></span> <span data-ttu-id="76bde-150">За контролата за допълване изберете кой тип допълване искате да се покаже чрез конфигуриране на полето **enrichmentType**.</span><span class="sxs-lookup"><span data-stu-id="76bde-150">For the Enrichment control, select which enrichment type you want to display by configuring the **enrichmentType** field.</span></span> <span data-ttu-id="76bde-151">Трябва да добавите отделна контрола за допълване за всеки тип допълване.</span><span class="sxs-lookup"><span data-stu-id="76bde-151">You need to add a separate enrichment control for each enrichment type.</span></span>

1. <span data-ttu-id="76bde-152">Изберете **Записване** и **Публикуване**, за да публикувате актуализирания формуляр на контакт.</span><span class="sxs-lookup"><span data-stu-id="76bde-152">Select **Save** and **Publish** to publish the updated contact form.</span></span>

1. <span data-ttu-id="76bde-153">Отидете на публикувания формуляр на контакт.</span><span class="sxs-lookup"><span data-stu-id="76bde-153">Go to the published contact form.</span></span> <span data-ttu-id="76bde-154">Ще видите току-що добавената контрола.</span><span class="sxs-lookup"><span data-stu-id="76bde-154">You'll see the newly added control.</span></span> <span data-ttu-id="76bde-155">Може да се наложи да влезете при първото използване.</span><span class="sxs-lookup"><span data-stu-id="76bde-155">You might need to sign in the first time you use it.</span></span>

1. <span data-ttu-id="76bde-156">За да персонализирате това, което искате да се показва в персонализираната контрола, изберете бутона за редактиране в горния десен ъгъл.</span><span class="sxs-lookup"><span data-stu-id="76bde-156">To customize what you want to show on the custom control, select the edit button in the upper-right corner.</span></span>