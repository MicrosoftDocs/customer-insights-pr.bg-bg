---
title: Експортирайте данните от Customer Insights в Dynamics 365 Marketing
description: Научете как да конфигурирате връзката и да експортирате в Dynamics 365 Marketing.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: a13f6f81f5e2570d3302d88c02755f1d86321a01
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759596"
---
# <a name="use-segments-in-dynamics-365-marketing-preview"></a><span data-ttu-id="32c54-103">Използване на сегменти в Dynamics 365 Marketing (преглед)</span><span class="sxs-lookup"><span data-stu-id="32c54-103">Use segments in Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="32c54-104">Използвайте [сегментите](segments.md), за да генерирате кампании, и се свързвайте с конкретни групи клиенти с Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="32c54-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="32c54-105">За повече информация вижте [Използване на сегменти от Dynamics 365 Customer Insights с Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="32c54-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite-for-a-connection"></a><span data-ttu-id="32c54-106">Предварително изискване за връзка</span><span class="sxs-lookup"><span data-stu-id="32c54-106">Prerequisite for a connection</span></span>

- <span data-ttu-id="32c54-107">Записите за контакти трябва да присъстват в Dynamics 365 Marketing, преди да можете да експортирате сегмент от Customer Insights в Marketing.</span><span class="sxs-lookup"><span data-stu-id="32c54-107">Contact records must be present in Dynamics 365 Marketing before you can export a segment from Customer Insights to Marketing.</span></span> <span data-ttu-id="32c54-108">Прочетете повече за това как да поглъщате контакти в [Dynamics 365 Marketing с помощта на Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="32c54-108">Read more on how to ingest contacts in [Dynamics 365 Marketing using Common Data Services](connect-power-query.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="32c54-109">Експортирането на сегменти от аналитични данни за аудитория в Marketing няма да създаде нови записи за контакти в маркетинговите екземпляри.</span><span class="sxs-lookup"><span data-stu-id="32c54-109">Exporting segments from audience insights to Marketing will not create new contact records in the Marketing instances.</span></span> <span data-ttu-id="32c54-110">Записите за контакти от Marketing трябва да се поглъщат с прозрения за аудиторията и да се използват като източник на данни.</span><span class="sxs-lookup"><span data-stu-id="32c54-110">The contact records from Marketing must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="32c54-111">Те също трябва да бъдат включени в единния обект на клиента, за да се съпоставят идентификаторите на клиентите с идентификаторите за контакт, преди сегментите да могат да бъдат експортирани.</span><span class="sxs-lookup"><span data-stu-id="32c54-111">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="set-up-connection-to-marketing"></a><span data-ttu-id="32c54-112">Настройване на връзка с Marketing</span><span class="sxs-lookup"><span data-stu-id="32c54-112">Set up connection to Marketing</span></span>

1. <span data-ttu-id="32c54-113">Отидете на **Администратор** > **Връзки**.</span><span class="sxs-lookup"><span data-stu-id="32c54-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="32c54-114">Изберете **Добавяне на връзка** и изберете **Dynamics 365 Marketing** за конфигуриране на връзката.</span><span class="sxs-lookup"><span data-stu-id="32c54-114">Select **Add connection** and choose **Dynamics 365 Marketing** to configure the connection.</span></span>

1. <span data-ttu-id="32c54-115">Въведете разпознаваемо име за връзката в полето **Показвано име**.</span><span class="sxs-lookup"><span data-stu-id="32c54-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="32c54-116">Показваното име и типът описват тази връзка.</span><span class="sxs-lookup"><span data-stu-id="32c54-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="32c54-117">Препоръчваме да изберете име, което обяснява целта на връзката.</span><span class="sxs-lookup"><span data-stu-id="32c54-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="32c54-118">Изберете кой може да използва тази връзка.</span><span class="sxs-lookup"><span data-stu-id="32c54-118">Choose who can use this connection.</span></span> <span data-ttu-id="32c54-119">Ако не предприемете нищо, по подразбиране ще е Администратори.</span><span class="sxs-lookup"><span data-stu-id="32c54-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="32c54-120">За повече информация вижте [Разрешаване на сътрудници да използват връзка за експортиране](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="32c54-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="32c54-121">Въведете URL адрес на Marketing за вашата организация в полето **Адрес на сървър**.</span><span class="sxs-lookup"><span data-stu-id="32c54-121">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="32c54-122">В секцията **Администраторски акаунт на сървъра** изберете **Влизане** и изберете акаунт на Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="32c54-122">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="32c54-123">Присвояване на поле за ИД на клиент към ИД за връзка на Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="32c54-123">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="32c54-124">Изберете **Записване**, за да завършите връзката.</span><span class="sxs-lookup"><span data-stu-id="32c54-124">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="32c54-125">Конфигуриране на експортиране</span><span class="sxs-lookup"><span data-stu-id="32c54-125">Configure an export</span></span>

<span data-ttu-id="32c54-126">Можете да конфигурирате това експортиране, ако имате достъп до връзка от този тип.</span><span class="sxs-lookup"><span data-stu-id="32c54-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="32c54-127">За повече информация вижте [Разрешения, необходими за конфигуриране на експортиране](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="32c54-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="32c54-128">Отидете на **Данни** > **Експортиране**.</span><span class="sxs-lookup"><span data-stu-id="32c54-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="32c54-129">За да създадете ново експортиране, изберете **Добавяне на местоназначение**.</span><span class="sxs-lookup"><span data-stu-id="32c54-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="32c54-130">В полето **Връзка за експортиране** изберете връзка от секцията Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="32c54-130">In the **Connection for export** field, choose a connection from the Dynamics 365 Marketing section.</span></span> <span data-ttu-id="32c54-131">Ако не виждате името на тази секция, няма достъпни за вас връзки от този тип.</span><span class="sxs-lookup"><span data-stu-id="32c54-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="32c54-132">Изберете един или повече сегменти.</span><span class="sxs-lookup"><span data-stu-id="32c54-132">Choose one or more segments.</span></span>

1. <span data-ttu-id="32c54-133">Изберете **Записване**.</span><span class="sxs-lookup"><span data-stu-id="32c54-133">Select **Save**.</span></span>

<span data-ttu-id="32c54-134">Запазването на експортиране не го изпълнява незабавно.</span><span class="sxs-lookup"><span data-stu-id="32c54-134">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="32c54-135">Експортирането се изпълнява с всяко [планирано обновяване](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="32c54-135">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="32c54-136">Може също [да експортирате данни при поискване](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="32c54-136">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
