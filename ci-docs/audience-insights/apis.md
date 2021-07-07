---
title: Работа с API
description: Използвайте API и разберете ограниченията.
ms.date: 05/10/2021
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 9326f821f9970ba2254ab804814e369abb677eb0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304729"
---
# <a name="work-with-customer-insights-apis"></a><span data-ttu-id="23f1b-103">Работа с приложни програмни интерфейси (API) на Customer Insights</span><span class="sxs-lookup"><span data-stu-id="23f1b-103">Work with Customer Insights APIs</span></span>

<span data-ttu-id="23f1b-104">Dynamics 365 Customer Insights предоставя API за изграждане на ваши собствени приложения въз основа на вашите данни в Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="23f1b-104">Dynamics 365 Customer Insights provides APIs to build your own applications based on your data in Customer Insights.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="23f1b-105">Подробности за тези API са изброени в [Справка за API на Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span><span class="sxs-lookup"><span data-stu-id="23f1b-105">Details of these APIs are listed on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="23f1b-106">Те включват допълнителна информация за операции, параметри и отговори.</span><span class="sxs-lookup"><span data-stu-id="23f1b-106">They include additional information about operations, parameters, and responses.</span></span>

<span data-ttu-id="23f1b-107">Тази статия описва как да получите достъп до приложните програмни интерфейси (API) на Customer Insights, да създадете регистрация на Azure App и да започнете с наличните клиентски библиотеки.</span><span class="sxs-lookup"><span data-stu-id="23f1b-107">This article describes how to access the Customer Insights APIs, create an Azure App Registration, and get started with the available client libraries.</span></span>

## <a name="get-started-trying-the-customer-insights-apis"></a><span data-ttu-id="23f1b-108">Започнете да изпробвате API на Customer Insights</span><span class="sxs-lookup"><span data-stu-id="23f1b-108">Get started trying the Customer Insights APIs</span></span>

1. <span data-ttu-id="23f1b-109">[Влезте](https://home.ci.ai.dynamics.com) в Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="23f1b-109">[Sign in](https://home.ci.ai.dynamics.com) to Customer Insights.</span></span> <span data-ttu-id="23f1b-110">Ако все още нямате абонамент, [регистрирайте се за пробна версия на Customer Insights](https://aka.ms/tryci).</span><span class="sxs-lookup"><span data-stu-id="23f1b-110">If you don't have a subscription yet, [sign up for a trial of Customer Insights](https://aka.ms/tryci).</span></span>

1. <span data-ttu-id="23f1b-111">За да активирате приложните програмни интерфейси (API) в средата на Customer Insights, отидете на **Администратор** > **Разрешения**.</span><span class="sxs-lookup"><span data-stu-id="23f1b-111">To enable APIs on your Customer Insights environment, go to **Admin** > **Permissions**.</span></span> <span data-ttu-id="23f1b-112">За това ще са ви необходими администраторски разрешения.</span><span class="sxs-lookup"><span data-stu-id="23f1b-112">You'll need admin permissions to do so.</span></span>

1. <span data-ttu-id="23f1b-113">Отидете на раздел **API** и изберете бутона **Активиране**.</span><span class="sxs-lookup"><span data-stu-id="23f1b-113">Go to the **APIs** tab and select the **Enable** button.</span></span>    
 
   <span data-ttu-id="23f1b-114">Активирането на API създава първичен и вторичен абонаментен ключ за вашия екземпляр, който се използва в заявките за API.</span><span class="sxs-lookup"><span data-stu-id="23f1b-114">Enabling the APIs creates a primary and secondary subscription key for your instance that gets used in the API requests.</span></span> <span data-ttu-id="23f1b-115">Можете да регенерирате клавишите, като изберете **Регенериране на първичен** или **Регенерирайте вторичен** на **Администратор** > **Разрешения** > **API**.</span><span class="sxs-lookup"><span data-stu-id="23f1b-115">You can regenerate the keys by selecting the **Regenerate primary** or **Regenerate secondary** on **Admin** > **Permissions** > **APIs**.</span></span>

   :::image type="content" source="media/enable-apis.gif" alt-text="Активиране на API на Customer Insights":::

1. <span data-ttu-id="23f1b-117">Изберете **Разгледайте нашите API**, за да [изпробвате API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).</span><span class="sxs-lookup"><span data-stu-id="23f1b-117">Select **Explore our APIs** to [try out the APIs](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).</span></span>

1. <span data-ttu-id="23f1b-118">Изберете операция на API и изберете **Изпробване**.</span><span class="sxs-lookup"><span data-stu-id="23f1b-118">Choose an API operation and select **Try it**.</span></span>

1. <span data-ttu-id="23f1b-119">В страничния прозорец задайте стойността в **Разрешение** падащото меню до **имплицитно**.</span><span class="sxs-lookup"><span data-stu-id="23f1b-119">In the side pane, set the value in the **Authorization** dropdown menu to **implicit**.</span></span> <span data-ttu-id="23f1b-120">Заглавката `Authorization` се добавя с токен на носител.</span><span class="sxs-lookup"><span data-stu-id="23f1b-120">The `Authorization` header gets added with a bearer token.</span></span> <span data-ttu-id="23f1b-121">Вашият абонаментен ключ ще бъде попълнен автоматично.</span><span class="sxs-lookup"><span data-stu-id="23f1b-121">Your subscription key will be automatically populated.</span></span>
  
1. <span data-ttu-id="23f1b-122">По желание добавете всички необходими параметри на заявката.</span><span class="sxs-lookup"><span data-stu-id="23f1b-122">Optionally, add all necessary query parameters.</span></span>

1. <span data-ttu-id="23f1b-123">Превъртете до дъното на страничния прозорец и изберете **Изпрати**.</span><span class="sxs-lookup"><span data-stu-id="23f1b-123">Scroll to the bottom of the side pane and select **Send**.</span></span>

<span data-ttu-id="23f1b-124">HTTP отговорът скоро ще се появи по-долу.</span><span class="sxs-lookup"><span data-stu-id="23f1b-124">The HTTP response will soon appear below.</span></span>

   :::image type="content" source="media/try-apis.gif" alt-text="Как да тествате API.":::

## <a name="create-a-new-app-registration-in-the-azure-portal"></a><span data-ttu-id="23f1b-126">Създайте нова регистрация на приложение в портала на Azure</span><span class="sxs-lookup"><span data-stu-id="23f1b-126">Create a new app registration in the Azure portal</span></span>

<span data-ttu-id="23f1b-127">Тези стъпки ви помагат да започнете да използвате API на Customer Insights в приложение на Azure, като използвате делегирани разрешения.</span><span class="sxs-lookup"><span data-stu-id="23f1b-127">These steps help you get started with using the Customer Insights APIs in an Azure application using delegated permissions.</span></span> <span data-ttu-id="23f1b-128">Не забравяйте да попълните [Начална секция](#get-started-trying-the-customer-insights-apis) първо.</span><span class="sxs-lookup"><span data-stu-id="23f1b-128">Make sure to complete the [Getting started section](#get-started-trying-the-customer-insights-apis) first.</span></span>

1. <span data-ttu-id="23f1b-129">Влезте в [Портал на Azure](https://portal.azure.com) с акаунта, който има достъп до данните на Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="23f1b-129">Sign in to the [Azure portal](https://portal.azure.com) with the account that can access the Customer Insights data.</span></span>

1. <span data-ttu-id="23f1b-130">Вляво изберете **Регистрации на приложения**.</span><span class="sxs-lookup"><span data-stu-id="23f1b-130">On the left, select **App registrations**.</span></span>

1. <span data-ttu-id="23f1b-131">Изберете **Нова регистрация** предоставете име на приложение и изберете типа на акаунта.</span><span class="sxs-lookup"><span data-stu-id="23f1b-131">Select **New registration**, provide an application name and choose the account type.</span></span>
 
   <span data-ttu-id="23f1b-132">Като опция добавете URL адрес за пренасочване.</span><span class="sxs-lookup"><span data-stu-id="23f1b-132">Optionally, add a redirect URL.</span></span> <span data-ttu-id="23f1b-133">http://localhost е достатъчно за разработване на приложение на вашия локален компютър.</span><span class="sxs-lookup"><span data-stu-id="23f1b-133">http://localhost is sufficient for developing an application on your local computer.</span></span>

1. <span data-ttu-id="23f1b-134">На новата си регистрация на приложение отидете на **Разрешения за API**.</span><span class="sxs-lookup"><span data-stu-id="23f1b-134">On your new App registration, go to **API permissions**.</span></span>

   :::image type="content" source="media/app-registration-1.gif" alt-text="Как да зададете разрешения за API при регистрация на приложения.":::

1. <span data-ttu-id="23f1b-136">Изберете **Добавете разрешение** и изберете **Customer Insights** в страничния прозорец.</span><span class="sxs-lookup"><span data-stu-id="23f1b-136">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="23f1b-137">За **Тип разрешение**, изберете **Делегирани разрешения** и след това изберете разрешение **user_impersonation**.</span><span class="sxs-lookup"><span data-stu-id="23f1b-137">For **Permission type**, select **Delegated permissions** and then select the **user_impersonation** permission.</span></span>

1. <span data-ttu-id="23f1b-138">Изберете **Добавяне на разрешения**.</span><span class="sxs-lookup"><span data-stu-id="23f1b-138">Select **Add permissions**.</span></span> <span data-ttu-id="23f1b-139">Ако имате нужда от достъп до API, без потребител да влезе, прегледайте [Разрешения за приложение между сървъри](#server-to-server-application-permissions) раздел.</span><span class="sxs-lookup"><span data-stu-id="23f1b-139">If you need to access the API without a user signing in, review the [Server-to-server application permissions](#server-to-server-application-permissions) section.</span></span>

1. <span data-ttu-id="23f1b-140">Изберете **Дайте съгласието на администратора за...**, за да завършите регистрацията на приложението.</span><span class="sxs-lookup"><span data-stu-id="23f1b-140">Select **Grant admin consent for...** to complete the app registration.</span></span>

<span data-ttu-id="23f1b-141">Можете да използвате Приложение/ИД на клиент за регистрацията на това приложение с библиотеката за удостоверяване на Microsoft (MSAL), за да получите токен на носител, който да изпратите с вашата заявка до API.</span><span class="sxs-lookup"><span data-stu-id="23f1b-141">You can use the Application/Client ID for this app registration with the Microsoft Authentication Library (MSAL) to obtain a bearer token to send with your request to the API.</span></span>

:::image type="content" source="media/grant-admin-consent.gif" alt-text="Как да дадете съгласието на администратора.":::

<span data-ttu-id="23f1b-143">За повече информация относно MSAL вижте [Преглед на библиотеката за удостоверяване на Microsoft (MSAL)](/azure/active-directory/develop/msal-overview).</span><span class="sxs-lookup"><span data-stu-id="23f1b-143">For more information about MSAL, see [Overview of Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview).</span></span>

<span data-ttu-id="23f1b-144">За повече информация относно регистрацията на приложения в Azure вижте [Регистрирайте приложение](/azure/active-directory/develop/quickstart-register-app.md#register-an-application).</span><span class="sxs-lookup"><span data-stu-id="23f1b-144">For more information about app registration in Azure, see [Register an application](/azure/active-directory/develop/quickstart-register-app.md#register-an-application).</span></span>

<span data-ttu-id="23f1b-145">За информация относно използването на API в нашите клиентски библиотеки вижте [Клиентски библиотеки на Customer Insights](#customer-insights-client-libraries).</span><span class="sxs-lookup"><span data-stu-id="23f1b-145">For information on using the APIs in our client libraries, see [Customer Insights client libraries](#customer-insights-client-libraries).</span></span>

### <a name="server-to-server-application-permissions"></a><span data-ttu-id="23f1b-146">Разрешения за приложение между сървъри</span><span class="sxs-lookup"><span data-stu-id="23f1b-146">Server-to-server application permissions</span></span>

<span data-ttu-id="23f1b-147">[Разделът за регистрация на приложение](#create-a-new-app-registration-in-the-azure-portal) описва как да регистрирате приложение, което изисква потребител да влезе за удостоверяване.</span><span class="sxs-lookup"><span data-stu-id="23f1b-147">The [app registration section](#create-a-new-app-registration-in-the-azure-portal) outlines how to register an app that requires a user to sign in for authentication.</span></span> <span data-ttu-id="23f1b-148">Научете как да създадете регистрация на приложение, което не се нуждае от взаимодействие с потребителя и може да се стартира на сървър.</span><span class="sxs-lookup"><span data-stu-id="23f1b-148">Learn how to create an app registration that does not need user interaction and can be run on a server.</span></span>

1. <span data-ttu-id="23f1b-149">В регистрацията на вашето приложение в портала на Azure отидете на **Разрешения за API**.</span><span class="sxs-lookup"><span data-stu-id="23f1b-149">On your App registration in the Azure portal, go to **API permissions**.</span></span>

1. <span data-ttu-id="23f1b-150">Изберете **Добавяне на разрешение**.</span><span class="sxs-lookup"><span data-stu-id="23f1b-150">Select **Add a permission**.</span></span> 

1. <span data-ttu-id="23f1b-151">Изберете **API, които моята организация използва** и изберете **AI на Dynamics 365 for Customer Insights** от списъка.</span><span class="sxs-lookup"><span data-stu-id="23f1b-151">Select the **APIs my organization uses** tab and choose **Dynamics 365 AI for Customer Insights** from the list.</span></span> 

1. <span data-ttu-id="23f1b-152">За **Тип разрешение**, изберете **разрешения на приложение** и след това изберете разрешение **CustomerInsights.Api.All**.</span><span class="sxs-lookup"><span data-stu-id="23f1b-152">For **Permission type**, select **Application permissions** and then select the **CustomerInsights.Api.All** permission.</span></span>

1. <span data-ttu-id="23f1b-153">Изберете **Добавяне на разрешения**.</span><span class="sxs-lookup"><span data-stu-id="23f1b-153">Select **Add permissions**.</span></span>

1. <span data-ttu-id="23f1b-154">Върнете се на **Разрешения за API** за регистрацията на приложението ви.</span><span class="sxs-lookup"><span data-stu-id="23f1b-154">Go back to **API permissions** for your app registration.</span></span>

1. <span data-ttu-id="23f1b-155">Изберете **Дайте съгласието на администратора за...**, за да завършите регистрацията на приложението.</span><span class="sxs-lookup"><span data-stu-id="23f1b-155">Select **Grant admin consent for...** to complete the app registration.</span></span>

   :::image type="content" source="media/grant-admin-consent.gif" alt-text="Как да дадете съгласието на администратора.":::

1. <span data-ttu-id="23f1b-157">В заключение трябва да добавим името на регистрацията на приложението като потребител в Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="23f1b-157">To conclude, we have to add the name of the app registration as a user in Customer Insights.</span></span>  
   
   <span data-ttu-id="23f1b-158">Отворете Customer Insights, отидете на **Администратор** > **Разрешения** и изберете **Добавяне на потребител**.</span><span class="sxs-lookup"><span data-stu-id="23f1b-158">Open Customer Insights, go to **Admin** > **Permissions** and select **Add user**.</span></span>

1. <span data-ttu-id="23f1b-159">Потърсете името на регистрацията на вашето приложение, изберете го от резултатите от търсенето и изберете **Запазете**.</span><span class="sxs-lookup"><span data-stu-id="23f1b-159">Search for the name of your app registration, select it from the search results, and select **Save**.</span></span>

## <a name="customer-insights-client-libraries"></a><span data-ttu-id="23f1b-160">Клиентски библиотеки на Customer Insights</span><span class="sxs-lookup"><span data-stu-id="23f1b-160">Customer Insights client libraries</span></span>

<span data-ttu-id="23f1b-161">Този раздел ви помага да започнете да използвате клиентските библиотеки, налични за API на Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="23f1b-161">This section helps you get started using the client libraries available for the Customer Insights APIs.</span></span> <span data-ttu-id="23f1b-162">Всички изходни кодове на библиотеката и примерни приложения могат да бъдат намерени в [Страница на GitHub за Customer Insights](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).</span><span class="sxs-lookup"><span data-stu-id="23f1b-162">All library source code and sample applications can be found on the [Customer Insights GitHub page](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).</span></span> 

### <a name="c-nuget"></a><span data-ttu-id="23f1b-163">C# NuGet</span><span class="sxs-lookup"><span data-stu-id="23f1b-163">C# NuGet</span></span>

<span data-ttu-id="23f1b-164">Научете как да започнете да използвате клиентските библиотеки на C# от NuGet.org. За повече информация относно NuGet пакет, вижте [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span><span class="sxs-lookup"><span data-stu-id="23f1b-164">Learn how to get started using the C# client libraries from NuGet.org. For more information on the NuGet package, see [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span></span> <span data-ttu-id="23f1b-165">Понастоящем този пакет е насочен към рамките netstandard2.0 и netcoreapp2.0.</span><span class="sxs-lookup"><span data-stu-id="23f1b-165">Currently, this package targets the netstandard2.0 and netcoreapp2.0 frameworks.</span></span>

#### <a name="add-the-c-client-library-to-a-c-project"></a><span data-ttu-id="23f1b-166">Добавете клиентската библиотека на C# към проект на C#</span><span class="sxs-lookup"><span data-stu-id="23f1b-166">Add the C# client library to a C# project</span></span>

1. <span data-ttu-id="23f1b-167">Във Visual Studio отворете **Мениджър на пакети на NuGet** за вашия проект.</span><span class="sxs-lookup"><span data-stu-id="23f1b-167">In Visual Studio, open the **NuGet Package Manager** for your project.</span></span>

1. <span data-ttu-id="23f1b-168">Търсете **Microsoft.Dynamics.CustomerInsights.Api**.</span><span class="sxs-lookup"><span data-stu-id="23f1b-168">Search for **Microsoft.Dynamics.CustomerInsights.Api**.</span></span>

1. <span data-ttu-id="23f1b-169">Изберете **Инсталирай**, за да добавите пакета към проекта.</span><span class="sxs-lookup"><span data-stu-id="23f1b-169">Select **Install** to add the package to the project.</span></span>
 
   <span data-ttu-id="23f1b-170">Като алтернатива изпълнете тази команда в **Конзола на Package Manager на NuGet**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span><span class="sxs-lookup"><span data-stu-id="23f1b-170">Alternatively, run this command in the **NuGet Package Manager Console**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span></span>

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Добавяне на пакет на NuGet към проект на Visual Studio":::

#### <a name="use-the-c-client-library"></a><span data-ttu-id="23f1b-172">Използвайте клиентската библиотека на C#</span><span class="sxs-lookup"><span data-stu-id="23f1b-172">Use the C# client library</span></span>

1. <span data-ttu-id="23f1b-173">Използвайте [Библиотека за удостоверяване на Microsoft (MSAL)](/azure/active-directory/develop/msal-overview), за да получите `AccessToken`, като използвате съществуващата си [Регистрация в приложението Azure](#create-a-new-app-registration-in-the-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="23f1b-173">Use the [Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview) to get an `AccessToken` using your existing [Azure app registration](#create-a-new-app-registration-in-the-azure-portal).</span></span>

1. <span data-ttu-id="23f1b-174">След успешно удостоверяване и придобиване на маркер, конструирайте нов или използвайте съществуващ `HttpClient` с допълнителен **DefaultRequestHeaders "Authorization"** с настройка **<access token> на преносител** и **Ocp-Apim-Subscription-Key**, зададени на [**абонаментен ключ** от средата на Customer Insights](#get-started-trying-the-customer-insights-apis).</span><span class="sxs-lookup"><span data-stu-id="23f1b-174">After successfully authenticating and acquiring a token, construct a new or use an existing `HttpClient` with the additional **DefaultRequestHeaders "Authorization"** set to **Bearer <access token>** and **Ocp-Apim-Subscription-Key** set to the [**subscription key** from your Customer Insights environment](#get-started-trying-the-customer-insights-apis).</span></span>   
 
   <span data-ttu-id="23f1b-175">Нулирайте заглавието **Разрешение**, когато е подходящо.</span><span class="sxs-lookup"><span data-stu-id="23f1b-175">Reset the **Authorization** header when appropriate.</span></span> <span data-ttu-id="23f1b-176">Например, когато токенът изтече.</span><span class="sxs-lookup"><span data-stu-id="23f1b-176">For example, when the token expired.</span></span>

1. <span data-ttu-id="23f1b-177">Подайте този `HttpClient` в конструкцията на клиента на `CustomerInsights`.</span><span class="sxs-lookup"><span data-stu-id="23f1b-177">Pass this `HttpClient` into the construction of the `CustomerInsights` client.</span></span>

   :::image type="content" source="media/httpclient-sample.png" alt-text="Пример за httpclient":::

1. <span data-ttu-id="23f1b-179">Осъществявайте обаждания от клиента към „методите за разширение“, например `GetAllInstancesAsync`.</span><span class="sxs-lookup"><span data-stu-id="23f1b-179">Make calls with the client to the "extension methods"—for example, `GetAllInstancesAsync`.</span></span> <span data-ttu-id="23f1b-180">Ако има достъп до основния `Microsoft.Rest.HttpOperationResponse` е за предпочитане, използвайте „методите на http съобщение“, например `GetAllInstancesWithHttpMessagesAsync`.</span><span class="sxs-lookup"><span data-stu-id="23f1b-180">If access to the underlying `Microsoft.Rest.HttpOperationResponse` is preferred, use the "http message methods"—for example, `GetAllInstancesWithHttpMessagesAsync`.</span></span>

1. <span data-ttu-id="23f1b-181">Отговорът вероятно ще бъде от тип `object`, тъй като методът може да върне множество типове (например `IList<InstanceInfo>` и `ApiErrorResult`).</span><span class="sxs-lookup"><span data-stu-id="23f1b-181">The response will likely be of type `object` because the method can return multiple types (for example, `IList<InstanceInfo>` and `ApiErrorResult`).</span></span> <span data-ttu-id="23f1b-182">За да проверите типа на връщане, можете безопасно да прехвърлите обектите в типовете отговори, посочени в [Страница с подробности за API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) за тази операция.</span><span class="sxs-lookup"><span data-stu-id="23f1b-182">To check the return type, you can safely cast the objects into the response types specified on the [API details page](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) for that operation.</span></span>    
   
   <span data-ttu-id="23f1b-183">Ако е необходима повече информация за заявката, използвайте **http методи за съобщения** за достъп до суровия обект на отговор.</span><span class="sxs-lookup"><span data-stu-id="23f1b-183">If more information on the request is needed, use the **http message methods** to access the raw response object.</span></span>

### <a name="nodejs-package"></a><span data-ttu-id="23f1b-184">Пакет NodeJS</span><span class="sxs-lookup"><span data-stu-id="23f1b-184">NodeJS package</span></span>

<span data-ttu-id="23f1b-185">Използвайте клиентските библиотеки на NodeJS, достъпни чрез NPM: https://www.npmjs.com/package/@microsoft/customerinsights</span><span class="sxs-lookup"><span data-stu-id="23f1b-185">Use the NodeJS client libraries available through NPM: https://www.npmjs.com/package/@microsoft/customerinsights</span></span>

### <a name="python-package"></a><span data-ttu-id="23f1b-186">Пакет на Python</span><span class="sxs-lookup"><span data-stu-id="23f1b-186">Python package</span></span>

<span data-ttu-id="23f1b-187">Използвайте клиентските библиотеки на Python, достъпни чрез PyPi: https://pypi.org/project/customerinsights/</span><span class="sxs-lookup"><span data-stu-id="23f1b-187">Use the Python client libraries available through PyPi: https://pypi.org/project/customerinsights/</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
