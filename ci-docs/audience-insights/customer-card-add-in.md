---
title: Добавка за карта на клиент за приложения на Dynamics 365
description: Показвайте данни от статистика за аудиторията в приложенията на Dynamics 365 с тази добавка.
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 88492943ddbf9ae30c64d92b261433b74f34f682
ms.sourcegitcommit: d74430270f1b754322287c4f045d7febdae35be2
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059575"
---
# <a name="customer-card-add-in-preview"></a><span data-ttu-id="e7033-103">Добавка за карта на клиент (преглед)</span><span class="sxs-lookup"><span data-stu-id="e7033-103">Customer Card Add-in (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="e7033-104">Получете 360-градусов изглед на вашите клиенти директно в приложенията на Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="e7033-104">Get a 360-degree view of your customers directly in Dynamics 365 apps.</span></span> <span data-ttu-id="e7033-105">С добавката за клиентска карта, инсталирана в поддържано приложение Dynamics 365, можете да изберете да показвате демографски данни, статистика и времеви график за активност.</span><span class="sxs-lookup"><span data-stu-id="e7033-105">With the Customer Card Add-in installed in a supported Dynamics 365 app you can choose to display demographics, insights, and activity timelines.</span></span> <span data-ttu-id="e7033-106">Добавката ще извлича данни от Customer Insights, без да засяга данните в свързаното приложение Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="e7033-106">The add-in will retrieve data from Customer Insights without affecting the data in the connected Dynamics 365 app.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="e7033-107">Предварителни изисквания</span><span class="sxs-lookup"><span data-stu-id="e7033-107">Prerequisites</span></span>

- <span data-ttu-id="e7033-108">Добавката работи само с приложения, задвижвани от Dynamics 365, като Sales или Customer Service, версия 9.0 и по-нови.</span><span class="sxs-lookup"><span data-stu-id="e7033-108">The add-in only works with Dynamics 365 model-driven apps, such as Sales or Customer Service, version 9.0 and later.</span></span>
- <span data-ttu-id="e7033-109">За да могат вашите данни на Dynamics 365 да се съпоставят с прозренията на аудиторията, клиентските профили, които трябва да бъдат [погълнати от приложението Dynamics 365 с помощта на Common Data Service конектор](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="e7033-109">For your Dynamics 365 data to map to the audience insights customer profiles they need to be [ingested from the Dynamics 365 app using the Common Data Service connector](connect-power-query.md).</span></span>
- <span data-ttu-id="e7033-110">Всички потребители на добавката за карта на клиента на Dynamics 365 трябва да бъдат [добавени като потребители](permissions.md) в прозрения за аудиторията, за да видите данните.</span><span class="sxs-lookup"><span data-stu-id="e7033-110">All Dynamics 365 users of the Customer Card Add-in must be [added as users](permissions.md) in audience insights to see the data.</span></span>
- <span data-ttu-id="e7033-111">[Конфигурирани възможности за търсене и филтриране](search-filter-index.md) в аудиторията са необходими прозрения за търсене на данни, за да работят.</span><span class="sxs-lookup"><span data-stu-id="e7033-111">[Configured search and filter capabilities](search-filter-index.md) in audience insights are required for lookup of data to work.</span></span>
- <span data-ttu-id="e7033-112">Всяка контрола за добавка разчита на конкретни данни в статистика за аудиторията:</span><span class="sxs-lookup"><span data-stu-id="e7033-112">Each add-in control relies on specific data in audience insights:</span></span>
  - <span data-ttu-id="e7033-113">Контрол на мярката: Изисква [конфигурирани мерки](measures.md).</span><span class="sxs-lookup"><span data-stu-id="e7033-113">Measure control: Requires [configured measures](measures.md).</span></span>
  - <span data-ttu-id="e7033-114">Контрол на разузнаването: Изисква данни, генерирани с помощта на [прогнози](predictions.md) или [персонализирани модели](custom-models.md).</span><span class="sxs-lookup"><span data-stu-id="e7033-114">Intelligence control: Requires data generated using [predictions](predictions.md) or [custom models](custom-models.md).</span></span>
  - <span data-ttu-id="e7033-115">Демографски контрол: В единния клиентски профил са налични демографски полета (като възраст или пол).</span><span class="sxs-lookup"><span data-stu-id="e7033-115">Demographic control: Demographic fields(such as age or gender) are available in the unified customer profile.</span></span>
  - <span data-ttu-id="e7033-116">Контрола за допълване: Изисква активно [допълване](enrichment-hub.md), приложено към потребителските профили.</span><span class="sxs-lookup"><span data-stu-id="e7033-116">Enrichment control: Requires active [enrichments](enrichment-hub.md) applied to customer profiles.</span></span>
  - <span data-ttu-id="e7033-117">Контрол на времевата линия: Изисква [конфигурирани дейности](activities.md).</span><span class="sxs-lookup"><span data-stu-id="e7033-117">Timeline control: Requires [configured activities](activities.md).</span></span>

## <a name="install-the-customer-card-add-in"></a><span data-ttu-id="e7033-118">Инсталиране на добавката за карта на клиент</span><span class="sxs-lookup"><span data-stu-id="e7033-118">Install the Customer Card Add-in</span></span>

<span data-ttu-id="e7033-119">Добавката за клиентска карта е решение за приложения за ангажиране на клиенти в Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="e7033-119">The Customer Card Add-in is a solution for customer engagement apps in Dynamics 365.</span></span> <span data-ttu-id="e7033-120">За да инсталирате решението, отидете в AppSource и намерете **Динамична карта на клиент**.</span><span class="sxs-lookup"><span data-stu-id="e7033-120">To install the solution, go to AppSource and search for **Dynamics Customer Card**.</span></span> <span data-ttu-id="e7033-121">Изберете [добавката за карта на клиент в AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) и изберете **Изтегляне сега**.</span><span class="sxs-lookup"><span data-stu-id="e7033-121">Select the [Customer Card Add-in on AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) and select **Get It Now**.</span></span>

<span data-ttu-id="e7033-122">Може да се наложи да влезете с администраторските си данни за приложението Dynamics 365, за да инсталирате решението.</span><span class="sxs-lookup"><span data-stu-id="e7033-122">You may need to sign in with your admin credentials for the Dynamics 365 app to install the solution.</span></span>

<span data-ttu-id="e7033-123">Може да отнеме известно време, за да се инсталира решението в средата.</span><span class="sxs-lookup"><span data-stu-id="e7033-123">It can take some time for the solution to be installed to your environment.</span></span>

## <a name="configure-the-customer-card-add-in"></a><span data-ttu-id="e7033-124">Конфигуриране на добавката за карта на клиент</span><span class="sxs-lookup"><span data-stu-id="e7033-124">Configure the Customer Card Add-in</span></span>

1. <span data-ttu-id="e7033-125">Като администратор отидете в секцията **Настройки** в Dynamics 365 и изберете **Решения**.</span><span class="sxs-lookup"><span data-stu-id="e7033-125">As an admin, go to the **Settings** section in Dynamics 365 and select **Solutions**.</span></span>

1. <span data-ttu-id="e7033-126">Изберете връзката **Показвано име** за решението **Добавка за карта на клиент на Dynamics 365 Customer Insights (преглед)**.</span><span class="sxs-lookup"><span data-stu-id="e7033-126">Select the **Display Name** link for the **Dynamics 365 Customer Insights Customer Card Add-in (Preview)** solution.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e7033-127">![Избор на показвано име](media/select-display-name.png "Избор на показвано име")</span><span class="sxs-lookup"><span data-stu-id="e7033-127">![Select display name](media/select-display-name.png "Select display name")</span></span>

1. <span data-ttu-id="e7033-128">Изберете **Влизане** и въведете идентификационните данни за акаунта на администратор, който използвате за конфигуриране на Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="e7033-128">Select **Sign in** and enter the credentials for the admin account you use to configure Customer Insights.</span></span>

   > [!NOTE]
   > <span data-ttu-id="e7033-129">Проверете дали инструментът за блокиране на изскачащи прозорци на браузъра не блокира прозореца за удостоверяване, когато изберете бутона **Влизане**.</span><span class="sxs-lookup"><span data-stu-id="e7033-129">Check that the browser pop-up blocker does not block the authentication window when you select the **Sign in** button.</span></span>

1. <span data-ttu-id="e7033-130">Изберете екземпляра на среди на Customer Insights, от който искате да извлечете данни.</span><span class="sxs-lookup"><span data-stu-id="e7033-130">Select the Customer Insights environment you want to fetch data from.</span></span>

1. <span data-ttu-id="e7033-131">Дефинирайте картографирането на полето към записи в приложението Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="e7033-131">Define the field mapping to records in the Dynamics 365 app.</span></span> <span data-ttu-id="e7033-132">В зависимост от вашите данни в Customer Insights можете да изберете да съпоставите следните опции:</span><span class="sxs-lookup"><span data-stu-id="e7033-132">Depending on your data in Customer Insights you can choose to map the following options:</span></span>
   - <span data-ttu-id="e7033-133">За да картографирате с контакт, изберете полето в обекта на клиента, което съвпада с идентификатора на обекта ви за контакт.</span><span class="sxs-lookup"><span data-stu-id="e7033-133">To map with a contact, select the field in the Customer entity that matches the ID of your contact entity.</span></span>
   - <span data-ttu-id="e7033-134">За да картографирате с акаунт, изберете полето в обекта на клиента, което съвпада с идентификатора на обекта ви за акаунт.</span><span class="sxs-lookup"><span data-stu-id="e7033-134">To map with an account, select the field in the Customer entity that matches the ID of your account entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e7033-135">![Поле за ИД на контакт](media/contact-id-field.png "Поле за ИД на контакт")</span><span class="sxs-lookup"><span data-stu-id="e7033-135">![Contact ID field](media/contact-id-field.png "Contact ID field")</span></span>

1. <span data-ttu-id="e7033-136">Изберете **Записване на конфигурацията**, за да запишете настройките.</span><span class="sxs-lookup"><span data-stu-id="e7033-136">Select **Save configuration** to save the settings.</span></span>

1. <span data-ttu-id="e7033-137">След това трябва да зададете права за достъп в Dynamics 365, така че потребителите да могат да персонализират и да преглеждат картата на клиента.</span><span class="sxs-lookup"><span data-stu-id="e7033-137">Next, you need to assign security roles in Dynamics 365 so users can customize and see the customer card.</span></span> <span data-ttu-id="e7033-138">В Dynamics 365 отидете на **Настройки** > **Защита** > **Потребители**.</span><span class="sxs-lookup"><span data-stu-id="e7033-138">In Dynamics 365, go to **Settings** > **Security** > **Users**.</span></span> <span data-ttu-id="e7033-139">Изберете потребителите, за да редактирате потребителските роли, и изберете **Управление на роли**.</span><span class="sxs-lookup"><span data-stu-id="e7033-139">Select the users to edit user roles and select **Manage roles**.</span></span>

1. <span data-ttu-id="e7033-140">Присвоете **Персонализатор на карти на Customer Insights** роля за потребителите, които ще персонализират съдържанието, показано на картата за цялата организация.</span><span class="sxs-lookup"><span data-stu-id="e7033-140">Assign the **Customer Insights Card Customizer** role to users who will customize the content shown on the card for the whole organization.</span></span>

## <a name="add-customer-card-controls-to-forms"></a><span data-ttu-id="e7033-141">Добавяне на контроли на потребителска карта към формуляри</span><span class="sxs-lookup"><span data-stu-id="e7033-141">Add Customer Card controls to forms</span></span>
  
1. <span data-ttu-id="e7033-142">За да добавите контролите на карта на клиент към формуляра на контакт, отидете на **Настройки** > **Персонализации** в Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="e7033-142">To add the Customer Card controls to your Contact form, go to the **Settings** > **Customizations** in Dynamics 365.</span></span>

1. <span data-ttu-id="e7033-143">Изберете **Персонализиране на системата**</span><span class="sxs-lookup"><span data-stu-id="e7033-143">Select **Customize the System**.</span></span>

1. <span data-ttu-id="e7033-144">Преминете към обекта **Контакт**, разгънете менюто му, след което изберете **Формуляри**.</span><span class="sxs-lookup"><span data-stu-id="e7033-144">Browse to the **Contact** entity, expand it and select **Forms**.</span></span>

1. <span data-ttu-id="e7033-145">Изберете формуляра на контакт, към който искате да добавите контролите на картата на клиент.</span><span class="sxs-lookup"><span data-stu-id="e7033-145">Select the contact form to which you want to add the Customer Card controls.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="e7033-146">![Избор на формуляр на контакт](media/contact-active-forms.png "Избор на формуляр на контакт")</span><span class="sxs-lookup"><span data-stu-id="e7033-146">![Select Contact form](media/contact-active-forms.png "Select Contact form")</span></span>

1. <span data-ttu-id="e7033-147">За да добавите контролата на демографски данни, в редактора на формуляри плъзнете някое поле от **прегледа на полетата** до мястото, където искате да се показва контролата.</span><span class="sxs-lookup"><span data-stu-id="e7033-147">To add a control, in the form editor, drag any field from the **Field Explorer** to where you want the control to appear.</span></span>

1. <span data-ttu-id="e7033-148">Изберете полето във формуляра, който току-що добавихте, и след това изберете **Промяна на свойства**.</span><span class="sxs-lookup"><span data-stu-id="e7033-148">Select the field on the form that you just added, and select **Change Properties**.</span></span>

1. <span data-ttu-id="e7033-149">Отидете на раздела **Контроли** и изберете **Добавяне на контрола**.</span><span class="sxs-lookup"><span data-stu-id="e7033-149">Go to the **Controls** tab and select **Add Control**.</span></span> <span data-ttu-id="e7033-150">Изберете една от наличните персонализирани контроли и изберете **Добавяне**.</span><span class="sxs-lookup"><span data-stu-id="e7033-150">Choose one of the available custom controls and select **Add**.</span></span>

1. <span data-ttu-id="e7033-151">В диалоговия прозорец **Свойства на поле** премахнете отметката от квадратчето **Показване на етикета във формуляра**.</span><span class="sxs-lookup"><span data-stu-id="e7033-151">In the **Field Properties** dialog, clear the **Display label on the form** check box.</span></span>

1. <span data-ttu-id="e7033-152">Изберете опцията **Уеб** за контролата.</span><span class="sxs-lookup"><span data-stu-id="e7033-152">Select the **Web** option for the control.</span></span> <span data-ttu-id="e7033-153">За контролата за допълване изберете кой тип допълване искате да се покаже чрез конфигуриране на полето **enrichmentType**.</span><span class="sxs-lookup"><span data-stu-id="e7033-153">For the Enrichment control, select which enrichment type you want to display by configuring the **enrichmentType** field.</span></span> <span data-ttu-id="e7033-154">Добавете отделен контрол за обогатяване за всеки тип обогатяване.</span><span class="sxs-lookup"><span data-stu-id="e7033-154">Add a separate enrichment control for each enrichment type.</span></span>

1. <span data-ttu-id="e7033-155">Изберете **Записване** и **Публикуване**, за да публикувате актуализирания формуляр на контакт.</span><span class="sxs-lookup"><span data-stu-id="e7033-155">Select **Save** and **Publish** to publish the updated contact form.</span></span>

1. <span data-ttu-id="e7033-156">Отидете на публикувания формуляр на контакт.</span><span class="sxs-lookup"><span data-stu-id="e7033-156">Go to the published contact form.</span></span> <span data-ttu-id="e7033-157">Ще видите току-що добавената контрола.</span><span class="sxs-lookup"><span data-stu-id="e7033-157">You'll see the newly added control.</span></span> <span data-ttu-id="e7033-158">Може да се наложи да влезете при първото използване.</span><span class="sxs-lookup"><span data-stu-id="e7033-158">You might need to sign in the first time you use it.</span></span>

1. <span data-ttu-id="e7033-159">За да персонализирате това, което искате да се показва в персонализираната контрола, изберете бутона за редактиране в горния десен ъгъл.</span><span class="sxs-lookup"><span data-stu-id="e7033-159">To customize what you want to show on the custom control, select the edit button in the upper-right corner.</span></span>

## <a name="upgrade-customer-card-add-in"></a><span data-ttu-id="e7033-160">Надстройка на добавка за карта на клиент</span><span class="sxs-lookup"><span data-stu-id="e7033-160">Upgrade Customer Card Add-in</span></span>
<span data-ttu-id="e7033-161">Добавката за клиентска карта не се надстройва автоматично.</span><span class="sxs-lookup"><span data-stu-id="e7033-161">The Customer Card Add-in doesn't upgrade automatically.</span></span> <span data-ttu-id="e7033-162">За да надстроите до най-новата версия, следвайте тази процедура в приложението Dynamics 365, в което е инсталирана добавката.</span><span class="sxs-lookup"><span data-stu-id="e7033-162">To upgrade to the latest version, follow this procedure in the Dynamics 365 app that has the Add-in installed.</span></span>

1. <span data-ttu-id="e7033-163">В приложението Dynamics 365 отидете на **Настройки** > **Персонализиране** и изберете **Решения**.</span><span class="sxs-lookup"><span data-stu-id="e7033-163">In the Dynamics 365 app, go to **Settings** > **Customization** and select **Solutions**.</span></span>

1. <span data-ttu-id="e7033-164">В таблицата на добавките потърсете **CustomerInsightsCustomerCard** и изберете реда.</span><span class="sxs-lookup"><span data-stu-id="e7033-164">In the table of add-ins look for **CustomerInsightsCustomerCard** and select the row.</span></span>

1. <span data-ttu-id="e7033-165">Изберете **Приложете надстройка на решението** в лентата за действие.</span><span class="sxs-lookup"><span data-stu-id="e7033-165">Select the **Apply Solution Upgrade** in the action bar.</span></span>

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Надстройте решението в областта за персонализиране на приложения на Dynamics 365":::

1. <span data-ttu-id="e7033-167">След стартиране на процеса на надстройка ще видите индикатор за зареждане, докато надстройката завърши.</span><span class="sxs-lookup"><span data-stu-id="e7033-167">After starting the upgrade process, you'll see a loading indicator until the upgrade completes.</span></span> <span data-ttu-id="e7033-168">Ако няма по-нова версия, надстройката ще покаже съобщение за грешка.</span><span class="sxs-lookup"><span data-stu-id="e7033-168">If there's no newer version, the upgrade will show an error message.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
