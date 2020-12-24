---
title: Работа с API
description: Използвайте API и разберете ограниченията.
ms.date: 12/04/2020
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 5a03e916676800afdd8692da865a1060952d5c4f
ms.sourcegitcommit: b50c754481d0af6d0cf4b550775d7b31d95846ef
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 12/06/2020
ms.locfileid: "4689117"
---
# <a name="work-with-customer-insights-apis"></a><span data-ttu-id="73588-103">Работа с приложни програмни интерфейси (API) на Customer Insights</span><span class="sxs-lookup"><span data-stu-id="73588-103">Work with Customer Insights APIs</span></span>

<span data-ttu-id="73588-104">Dynamics 365 Customer Insights предоставя API за изграждане на ваши собствени приложения, базирани на вашите данни в Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="73588-104">Dynamics 365 Customer Insights provides APIs to build your own applications based you data in Customer Insights.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="73588-105">Подробности за тези API са изброени в [Справка за API на Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span><span class="sxs-lookup"><span data-stu-id="73588-105">Details of these APIs, are listed on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="73588-106">Те включват допълнителна информация за операции, параметри и отговори.</span><span class="sxs-lookup"><span data-stu-id="73588-106">They include additional information about operations, parameters, and responses.</span></span>

<span data-ttu-id="73588-107">Тази статия ви насочва към достъп до приложните програмни интерфейси (API) на Customer Insights, създаване на регистрация на Azure App и ви помага да започнете с наличните клиентски библиотеки.</span><span class="sxs-lookup"><span data-stu-id="73588-107">This article guides you to access to the Customer Insights APIs, create an Azure App Registration, and help you get started with the available client libraries.</span></span>

## <a name="get-started-trying-the-customer-insights-apis"></a><span data-ttu-id="73588-108">Започнете да изпробвате API на Customer Insights</span><span class="sxs-lookup"><span data-stu-id="73588-108">Get started trying the Customer Insights APIs</span></span>

1. <span data-ttu-id="73588-109">[Влезте](https://home.ci.ai.dynamics.com) в Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="73588-109">[Sign in](https://home.ci.ai.dynamics.com) to Customer Insights.</span></span> <span data-ttu-id="73588-110">Ако все още нямате абонамент, [регистрирайте се за пробна версия на Customer Insights](https://aka.ms/tryci).</span><span class="sxs-lookup"><span data-stu-id="73588-110">If you don't have a subscription yet, [sign up for a trial of Customer Insights](https://aka.ms/tryci).</span></span>

1. <span data-ttu-id="73588-111">За да активирате приложните програмни интерфейси (API) в средата на Customer Insights, отидете на **Администратор** > **Разрешения**.</span><span class="sxs-lookup"><span data-stu-id="73588-111">To enable APIs on your Customer Insights environment, go to **Admin** > **Permissions**.</span></span> <span data-ttu-id="73588-112">За това ще са ви необходими администраторски разрешения.</span><span class="sxs-lookup"><span data-stu-id="73588-112">You'll need admin permissions to do so.</span></span>

1. <span data-ttu-id="73588-113">Отидете на раздел **API** и изберете бутона **Активиране**.</span><span class="sxs-lookup"><span data-stu-id="73588-113">Go to the **APIs** tab and select the **Enable** button.</span></span>    
   <span data-ttu-id="73588-114">Активирането на API създава първичен и вторичен абонаментен ключ за вашия екземпляр, който се използва в заявките за API.</span><span class="sxs-lookup"><span data-stu-id="73588-114">Enabling the APIs creates a primary and secondary subscription key for your instance that gets used in the API requests.</span></span> <span data-ttu-id="73588-115">Можете да регенерирате клавишите, като изберете **Регенериране на първичен** или **Регенерирайте вторичен** на **Администратор** > **Разрешения** > **API**.</span><span class="sxs-lookup"><span data-stu-id="73588-115">You can regenerate the keys by selecting the **Regenerate primary** or **Regenerate secondary** on **Admin** > **Permissions** > **APIs**.</span></span>

   :::image type="content" source="media/enable-apis.gif" alt-text="Активиране на API на Customer Insights":::

1. <span data-ttu-id="73588-117">Изберете **Разгледайте нашите API**, за да изпробвате API.</span><span class="sxs-lookup"><span data-stu-id="73588-117">Select **Explore our APIs** to try out the APIs.</span></span>

1. <span data-ttu-id="73588-118">Изберете операция на API и изберете **Изпробване**.</span><span class="sxs-lookup"><span data-stu-id="73588-118">Choose an API operation and select **Try it**.</span></span>

1. <span data-ttu-id="73588-119">В страничния прозорец задайте стойността в падащо меню **Разрешение** на **Имплицитно**.</span><span class="sxs-lookup"><span data-stu-id="73588-119">In the side pane, set the value in the **Authorization** drop-down menu to **implicit**.</span></span> <span data-ttu-id="73588-120">Заглавката `Authorization` се получава с добавен маркер на носител.</span><span class="sxs-lookup"><span data-stu-id="73588-120">The `Authorization` header gets with a bearer token added.</span></span> <span data-ttu-id="73588-121">Вашият абонаментен ключ ще бъде попълнен автоматично.</span><span class="sxs-lookup"><span data-stu-id="73588-121">Your subscription key will be automatically populated.</span></span>
  
1. <span data-ttu-id="73588-122">По желание добавете всички необходими параметри на заявката.</span><span class="sxs-lookup"><span data-stu-id="73588-122">Optionally, add all necessary query parameters.</span></span>

1. <span data-ttu-id="73588-123">Превъртете до дъното на страничния прозорец и изберете **Изпрати**.</span><span class="sxs-lookup"><span data-stu-id="73588-123">Scroll to the bottom of the side pane and select **Send**.</span></span>

<span data-ttu-id="73588-124">HTTP отговорът скоро ще се появи по-долу.</span><span class="sxs-lookup"><span data-stu-id="73588-124">The HTTP response will soon appear below.</span></span>

## <a name="create-a-new-app-registration-in-the-azure-portal"></a><span data-ttu-id="73588-125">Създайте нова регистрация на приложение в портала на Azure</span><span class="sxs-lookup"><span data-stu-id="73588-125">Create a new app registration in the Azure portal</span></span>

<span data-ttu-id="73588-126">Тези стъпки ви помагат да започнете да използвате API на Customer Insights в приложение на Azure, като използвате делегирани разрешения.</span><span class="sxs-lookup"><span data-stu-id="73588-126">These steps help you get started in using the Customer Insights APIs in an Azure application using delegated permissions.</span></span> <span data-ttu-id="73588-127">Уверете се, че първо сте завършили [Секцията Начало](#get-started-trying-the-customer-insights-apis).</span><span class="sxs-lookup"><span data-stu-id="73588-127">Make sure to have completed [Getting started section](#get-started-trying-the-customer-insights-apis) first.</span></span>

1. <span data-ttu-id="73588-128">Влезте в [Портал на Azure](https://portal.azure.com) с акаунта, който има достъп до данните на Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="73588-128">Sign in to the [Azure portal](https://portal.azure.com) with the account that can access the Customer Insights data.</span></span>

1. <span data-ttu-id="73588-129">Вляво изберете **Регистрации на приложения**.</span><span class="sxs-lookup"><span data-stu-id="73588-129">On the left, select **App registrations**.</span></span>

1. <span data-ttu-id="73588-130">Изберете **Нова регистрация** предоставете име на приложение и изберете типа на акаунта.</span><span class="sxs-lookup"><span data-stu-id="73588-130">Select **New registration** provide an application name and choose the account type.</span></span>
   <span data-ttu-id="73588-131">Като опция добавете URL адрес за пренасочване.</span><span class="sxs-lookup"><span data-stu-id="73588-131">Optionally, add a redirect URL.</span></span> <span data-ttu-id="73588-132">http://localhost е достатъчно за разработване на приложение на вашия локален компютър.</span><span class="sxs-lookup"><span data-stu-id="73588-132">http://localhost is sufficient for developing an application on your local computer.</span></span>

1. <span data-ttu-id="73588-133">На новата си регистрация на приложение отидете на **Разрешения за API**.</span><span class="sxs-lookup"><span data-stu-id="73588-133">On your new App registration, go to **API permissions**.</span></span>

1. <span data-ttu-id="73588-134">Изберете **Добавете разрешение** и изберете **Customer Insights** в страничния прозорец.</span><span class="sxs-lookup"><span data-stu-id="73588-134">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="73588-135">За **Тип разрешение**, изберете **Делегирани разрешения** и изберете **user_impersonation** разрешение.</span><span class="sxs-lookup"><span data-stu-id="73588-135">For **Permission type**, select **Delegated permissions** and select the **user_impersonation** permission.</span></span>

1. <span data-ttu-id="73588-136">Изберете **Добавяне на разрешения**.</span><span class="sxs-lookup"><span data-stu-id="73588-136">Select **Add permissions**.</span></span> <span data-ttu-id="73588-137">Ако имате нужда от достъп до API, без потребител да влезе, прегледайте [Разрешения за приложение между сървъри](#server-to-server-application-permissions) раздел.</span><span class="sxs-lookup"><span data-stu-id="73588-137">If you need to access the API without a user signing in, review the [Server-to-server application permissions](#server-to-server-application-permissions) section.</span></span>

1. <span data-ttu-id="73588-138">Изберете **Дайте съгласието на администратора за...**, за да завършите регистрацията на приложението.</span><span class="sxs-lookup"><span data-stu-id="73588-138">Select **Grant admin consent for...** to complete the app registration.</span></span>

<span data-ttu-id="73588-139">Можете да използвате Приложение/ИД на клиент за регистрацията на това приложение с библиотеката за удостоверяване на Microsoft (MSAL), за да получите токен на носител, който да изпратите с вашата заявка до API.</span><span class="sxs-lookup"><span data-stu-id="73588-139">You can use the Application/Client ID for this app registration with the Microsoft Authentication Library (MSAL) to obtain a bearer token to send with your request to the API.</span></span>

<span data-ttu-id="73588-140">За повече информация относно MSAL вижте [Преглед на библиотеката за удостоверяване на Microsoft (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview).</span><span class="sxs-lookup"><span data-stu-id="73588-140">For more information about MSAL, see [Overview of Microsoft Authentication Library (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview).</span></span>

<span data-ttu-id="73588-141">За повече информация относно регистрацията на приложения в Azure вижте [Новият опит за регистрация на приложения на портала Azure](https://docs.microsoft.com/azure/active-directory/develop/app-registration-portal-training-guide).</span><span class="sxs-lookup"><span data-stu-id="73588-141">For more information about app registration in Azure, see [The new Azure portal app registration experience](https://docs.microsoft.com/azure/active-directory/develop/app-registration-portal-training-guide).</span></span>

<span data-ttu-id="73588-142">За информация относно използването на API на нашите клиентски библиотеки вижте [Клиентски библиотеки на Customer Insights](#customer-insights-client-libraries).</span><span class="sxs-lookup"><span data-stu-id="73588-142">For information on using the APIs our client libraries, see [Customer Insights client libraries](#customer-insights-client-libraries).</span></span>

### <a name="server-to-server-application-permissions"></a><span data-ttu-id="73588-143">Разрешения за приложение между сървъри</span><span class="sxs-lookup"><span data-stu-id="73588-143">Server-to-server application permissions</span></span>

<span data-ttu-id="73588-144">[Разделът за регистрация на приложение](#create-a-new-app-registration-in-the-azure-portal) описва как да регистрирате приложение, което изисква потребител да влезе за удостоверяване.</span><span class="sxs-lookup"><span data-stu-id="73588-144">The [app registration section](#create-a-new-app-registration-in-the-azure-portal) outlines how to register an app that requires a user to sign in for authentication.</span></span> <span data-ttu-id="73588-145">Научете как да създадете регистрация на приложение, което не се нуждае от взаимодействие с потребителя и може да се стартира на сървър.</span><span class="sxs-lookup"><span data-stu-id="73588-145">Learn how to create an app registration that does not need user interaction and can be run on a server.</span></span>

1. <span data-ttu-id="73588-146">В регистрацията на вашето приложение в портала на Azure отидете на **Разрешения за API**.</span><span class="sxs-lookup"><span data-stu-id="73588-146">On your App registration in the Azure portal, go to **API permissions**.</span></span>

1. <span data-ttu-id="73588-147">Изберете **Добавете разрешение** и изберете **Customer Insights** в страничния прозорец.</span><span class="sxs-lookup"><span data-stu-id="73588-147">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="73588-148">За **Тип разрешение**, изберете **Разрешения на приложение** и изберете разрешение **CustomerInsights.Api.All**.</span><span class="sxs-lookup"><span data-stu-id="73588-148">For **Permission type**, select **Application permissions** and select the **CustomerInsights.Api.All** permission.</span></span>

1. <span data-ttu-id="73588-149">Изберете **Добавяне на разрешения**.</span><span class="sxs-lookup"><span data-stu-id="73588-149">Select **Add permissions**.</span></span>

1. <span data-ttu-id="73588-150">За да дадете съгласието на администратора за това приложение, трябва да добавите Принципал на услугата.</span><span class="sxs-lookup"><span data-stu-id="73588-150">To give admin consent on this Application permission, you need to add a Service Principal.</span></span>

   1. <span data-ttu-id="73588-151">Инсталирайте модула PowerShell на Azure Active Directory (AD): `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`</span><span class="sxs-lookup"><span data-stu-id="73588-151">Install the Azure Active Directory (AD) PowerShell module: `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`</span></span>
   1. <span data-ttu-id="73588-152">Свързване към акаунта си в AD: `Connect-AzureAD -TenantId <your tenant id>`.</span><span class="sxs-lookup"><span data-stu-id="73588-152">Connect to your AD account: `Connect-AzureAD -TenantId <your tenant id>`.</span></span> <span data-ttu-id="73588-153">Можете да намерите ИД на клиента си **Общ преглед** > **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="73588-153">You can find your tenant ID on **Overview** > **Azure Active Directory**.</span></span>
   1. <span data-ttu-id="73588-154">Изпълнете следната команда, за да добавите Принципал на услугата на Azure AD:`New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"` Параметърът AppId се отнася до приложението API на Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="73588-154">Run the following command to add an Azure AD Service Principal: `New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"` The AppId parameter pertains to the Customer Insights API app.</span></span>

   :::image type="content" source="media/azureAD-service-principal.png" alt-text="Пример за принципал на услуга":::

1. <span data-ttu-id="73588-156">Върнете се на **Разрешения за API** за регистрацията на приложението ви.</span><span class="sxs-lookup"><span data-stu-id="73588-156">Go back to **API permissions** for your app registration.</span></span>

1. <span data-ttu-id="73588-157">Изберете **Дайте съгласието на администратора за...**, за да завършите регистрацията на приложението.</span><span class="sxs-lookup"><span data-stu-id="73588-157">Select **Grant admin consent for...** to complete the app registration.</span></span>

1. <span data-ttu-id="73588-158">В заключение трябва да добавим името на регистрацията на приложението като потребител в Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="73588-158">To conclude, we have to add the name of the app registration as a user in Customer Insights.</span></span>    
   <span data-ttu-id="73588-159">Отворете Customer Insights, отидете на **Администратор** > **Разрешения** и изберете **Добавяне на потребител**.</span><span class="sxs-lookup"><span data-stu-id="73588-159">Open Customer Insights, go to **Admin** > **Permissions** and select **Add user**.</span></span>

1. <span data-ttu-id="73588-160">Потърсете името на регистрацията на вашето приложение, изберете го от резултатите от търсенето и изберете **Запазете**.</span><span class="sxs-lookup"><span data-stu-id="73588-160">Search for the name of your app registration, select it from the search results, and select **Save**.</span></span>

## <a name="customer-insights-client-libraries"></a><span data-ttu-id="73588-161">Клиентски библиотеки на Customer Insights</span><span class="sxs-lookup"><span data-stu-id="73588-161">Customer Insights client libraries</span></span>

<span data-ttu-id="73588-162">Този раздел ви помага да започнете да използвате клиентските библиотеки, налични за API на Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="73588-162">This section helps you get started using the client libraries available for the Customer Insights APIs.</span></span>

### <a name="c-nuget"></a><span data-ttu-id="73588-163">C# NuGet</span><span class="sxs-lookup"><span data-stu-id="73588-163">C# NuGet</span></span>

<span data-ttu-id="73588-164">Научете как да започнете да използвате клиентските библиотеки на C# от NuGet.org. За повече информация относно NuGet пакет, вижте [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span><span class="sxs-lookup"><span data-stu-id="73588-164">Learn how to get started using the C# client libraries from NuGet.org. For more information on the NuGet package, see [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span></span> <span data-ttu-id="73588-165">Понастоящем този пакет е насочен към рамките netstandard2.0 и netcoreapp2.0.</span><span class="sxs-lookup"><span data-stu-id="73588-165">Currently, this package targets the netstandard2.0 and netcoreapp2.0 frameworks.</span></span>

#### <a name="add-the-c-client-library-to-a-c-project"></a><span data-ttu-id="73588-166">Добавете клиентската библиотека на C# към проект на C#</span><span class="sxs-lookup"><span data-stu-id="73588-166">Add the C# client library to a C# project</span></span>

1. <span data-ttu-id="73588-167">Във Visual Studio отворете **Мениджър на пакети на NuGet** за вашия проект.</span><span class="sxs-lookup"><span data-stu-id="73588-167">In Visual Studio, open the **NuGet Package Manager** for your project.</span></span>

1. <span data-ttu-id="73588-168">Търсете **Microsoft.Dynamics.CustomerInsights.Api**.</span><span class="sxs-lookup"><span data-stu-id="73588-168">Search for **Microsoft.Dynamics.CustomerInsights.Api**.</span></span>

1. <span data-ttu-id="73588-169">Изберете **Инсталирай**, за да добавите пакета към проекта.</span><span class="sxs-lookup"><span data-stu-id="73588-169">Select **Install** to add the package to the project.</span></span>
   <span data-ttu-id="73588-170">Като алтернатива изпълнете тази команда в **Конзола на Package Manager на NuGet**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span><span class="sxs-lookup"><span data-stu-id="73588-170">Alternatively, run this command in the **NuGet Package Manager Console**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span></span>

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Добавяне на пакет на NuGet към проект на Visual Studio":::

#### <a name="use-the-c-client-library"></a><span data-ttu-id="73588-172">Използвайте клиентската библиотека на C#</span><span class="sxs-lookup"><span data-stu-id="73588-172">Use the C# client library</span></span>

1. <span data-ttu-id="73588-173">Използвайте [Библиотека за удостоверяване на Microsoft (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview), за да получите `AccessToken`, като използвате съществуващата си [Регистрация в приложението Azure](#create-a-new-app-registration-in-the-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="73588-173">Use the [Microsoft Authentication Library (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview) to get an `AccessToken` using your existing [Azure app registration](#create-a-new-app-registration-in-the-azure-portal).</span></span>

1. <span data-ttu-id="73588-174">След успешно удостоверяване и придобиване на маркер, конструирайте нов или използвайте съществуващ `HttpClient` с допълнителен **DefaultRequestHeaders "Authorization"** с настройка **<access token> на преносител** и **Ocp-Apim-Subscription-Key**, зададени на [**абонаментен ключ** от средата на Customer Insights](#get-started-trying-the-customer-insights-apis).</span><span class="sxs-lookup"><span data-stu-id="73588-174">After successfully authenticating and acquiring a token, construct a new or use an existing `HttpClient` with the additional **DefaultRequestHeaders "Authorization"** set to **Bearer <access token>** and **Ocp-Apim-Subscription-Key** set to the [**subscription key** from your Customer Insights environment](#get-started-trying-the-customer-insights-apis).</span></span>    
   <span data-ttu-id="73588-175">Нулирайте заглавието **Разрешение**, когато е подходящо.</span><span class="sxs-lookup"><span data-stu-id="73588-175">Reset the **Authorization** header when appropriate.</span></span> <span data-ttu-id="73588-176">Например, когато токенът изтече.</span><span class="sxs-lookup"><span data-stu-id="73588-176">For example, when the token expired.</span></span>

1. <span data-ttu-id="73588-177">Подайте този `HttpClient` в конструкцията на клиента на `CustomerInsights`.</span><span class="sxs-lookup"><span data-stu-id="73588-177">Pass this `HttpClient` into the construction of the `CustomerInsights` client.</span></span>

   :::image type="content" source="media/httpclient-sample.png" alt-text="Пример за httpclient":::

1. <span data-ttu-id="73588-179">Осъществявайте обаждания от клиента към „методите за разширение“, например `GetAllInstancesAsync`.</span><span class="sxs-lookup"><span data-stu-id="73588-179">Make calls with the client to the "extension methods", for example, `GetAllInstancesAsync`.</span></span> <span data-ttu-id="73588-180">Ако има достъп до основния `Microsoft.Rest.HttpOperationResponse` е за предпочитане, използвайте например „методите на http съобщение“ `GetAllInstancesWithHttpMessagesAsync`.</span><span class="sxs-lookup"><span data-stu-id="73588-180">If access to the underlying `Microsoft.Rest.HttpOperationResponse` is preferred, use the "http message methods", for example `GetAllInstancesWithHttpMessagesAsync`.</span></span>

1. <span data-ttu-id="73588-181">Отговорът вероятно ще бъде от тип `object`, тъй като методът може да върне множество типове (например `IList<InstanceInfo>` и `ApiErrorResult`).</span><span class="sxs-lookup"><span data-stu-id="73588-181">The response will likely be of type `object` because the method can return multiple types (for example, `IList<InstanceInfo>` and `ApiErrorResult`).</span></span> <span data-ttu-id="73588-182">За да проверите типа на връщане, можете безопасно да прехвърлите обектите в типовете отговори, посочени в [Страница с подробности за API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) за тази операция.</span><span class="sxs-lookup"><span data-stu-id="73588-182">To check the return type, you can safely cast the objects into the response types specified on the [API details page](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) for that operation.</span></span>    
   <span data-ttu-id="73588-183">Ако е необходима повече информация за заявката, използвайте **http методи за съобщения** за достъп до суровия обект на отговор.</span><span class="sxs-lookup"><span data-stu-id="73588-183">If more information on the request is needed, use the **http message methods** to access the raw response object.</span></span>