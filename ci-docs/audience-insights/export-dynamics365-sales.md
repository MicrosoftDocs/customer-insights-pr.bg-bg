---
title: Експортирайте данните от Customer Insights в Dynamics 365 Sales
description: Научете как да конфигурирате връзката и да експортирате в Dynamics 365 Sales.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 328bb2f26ebcea234fb645e5225930ab12f82a8b
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976213"
---
# <a name="use-segments-in-dynamics-365-sales-preview"></a><span data-ttu-id="b28ce-103">Използване на сегменти в Dynamics 365 Sales (преглед)</span><span class="sxs-lookup"><span data-stu-id="b28ce-103">Use segments in Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="b28ce-104">Използвайте клиентските данни, за да създавате маркетингови списъци, работни потоци за последващи действия и за да изпращате съобщения за промоции с Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="b28ce-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite-for-connection"></a><span data-ttu-id="b28ce-105">Предварително изискване за връзка</span><span class="sxs-lookup"><span data-stu-id="b28ce-105">Prerequisite for connection</span></span>

1. <span data-ttu-id="b28ce-106">Записите за контакти трябва да присъстват в Dynamics 365 Sales, преди да можете да експортирате сегмент от Customer Insights в Sales.</span><span class="sxs-lookup"><span data-stu-id="b28ce-106">Contact records must be present in Dynamics 365 Sales before you can export a segment from Customer Insights to Sales.</span></span> <span data-ttu-id="b28ce-107">Прочетете повече за това как да поглъщате контакти в [Dynamics 365 Sales с помощта на Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="b28ce-107">Read more on how to ingest contacts in [Dynamics 365 Sales using Common Data Services](connect-power-query.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="b28ce-108">Експортирането на сегменти от аналитични данни за аудитория в Sales няма да създаде нови записи за контакти в екземпляри на Sales.</span><span class="sxs-lookup"><span data-stu-id="b28ce-108">Exporting segments from audience insights to Sales will not create new contact records in the Sales instances.</span></span> <span data-ttu-id="b28ce-109">Записите за контакти от Sales трябва да се поглъщат с прозрения за аудиторията и да се използват като източник на данни.</span><span class="sxs-lookup"><span data-stu-id="b28ce-109">The contact records from Sales must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="b28ce-110">Те също трябва да бъдат включени в единния обект на клиента, за да се съпоставят идентификаторите на клиентите с идентификаторите за контакт, преди сегментите да могат да бъдат експортирани.</span><span class="sxs-lookup"><span data-stu-id="b28ce-110">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="set-up-the-connection-to-sales"></a><span data-ttu-id="b28ce-111">Настройване на връзката със Sales</span><span class="sxs-lookup"><span data-stu-id="b28ce-111">Set up the connection to Sales</span></span>

1. <span data-ttu-id="b28ce-112">Отидете на **Администратор** > **Връзки**.</span><span class="sxs-lookup"><span data-stu-id="b28ce-112">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="b28ce-113">Изберете **Добавяне на връзка** и изберете **Dynamics 365 Sales** за конфигуриране на връзката.</span><span class="sxs-lookup"><span data-stu-id="b28ce-113">Select **Add connection** and choose **Dynamics 365 Sales** to configure the connection.</span></span>

1. <span data-ttu-id="b28ce-114">Въведете разпознаваемо име за връзката в полето **Показвано име**.</span><span class="sxs-lookup"><span data-stu-id="b28ce-114">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="b28ce-115">Показваното име и типът описват тази връзка.</span><span class="sxs-lookup"><span data-stu-id="b28ce-115">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="b28ce-116">Препоръчваме да изберете име, което обяснява целта на връзката.</span><span class="sxs-lookup"><span data-stu-id="b28ce-116">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="b28ce-117">Изберете кой може да използва тази връзка.</span><span class="sxs-lookup"><span data-stu-id="b28ce-117">Choose who can use this connection.</span></span> <span data-ttu-id="b28ce-118">Ако не предприемете нищо, по подразбиране ще е Администратори.</span><span class="sxs-lookup"><span data-stu-id="b28ce-118">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="b28ce-119">За повече информация вижте [Разрешаване на сътрудници да използват връзка за експортиране](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="b28ce-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="b28ce-120">Въведете URL адрес на Продажби за вашата организация в полето **Адрес на сървър**.</span><span class="sxs-lookup"><span data-stu-id="b28ce-120">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="b28ce-121">В секцията **Администраторски акаунт на сървъра** изберете **Влизане** и изберете акаунт на Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="b28ce-121">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="b28ce-122">Присвояване на поле за ИД на клиент към ИД за връзка на Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="b28ce-122">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="b28ce-123">Изберете **Записване**, за да завършите връзката.</span><span class="sxs-lookup"><span data-stu-id="b28ce-123">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="b28ce-124">Конфигуриране на експортиране</span><span class="sxs-lookup"><span data-stu-id="b28ce-124">Configure an export</span></span>

<span data-ttu-id="b28ce-125">Можете да конфигурирате това експортиране, ако имате достъп до връзка от този тип.</span><span class="sxs-lookup"><span data-stu-id="b28ce-125">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="b28ce-126">За повече информация вижте [Разрешения, необходими за конфигуриране на експортиране](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="b28ce-126">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="b28ce-127">Отидете на **Данни** > **Експортиране**.</span><span class="sxs-lookup"><span data-stu-id="b28ce-127">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="b28ce-128">За да създадете ново експортиране, изберете **Добавяне на местоназначение**.</span><span class="sxs-lookup"><span data-stu-id="b28ce-128">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="b28ce-129">В полето **Връзка за експортиране** изберете връзка от секцията Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="b28ce-129">In the **Connection for export** field, choose a connection from the Dynamics 365 Sales section.</span></span> <span data-ttu-id="b28ce-130">Ако не виждате името на тази секция, няма достъпни за вас връзки от този тип.</span><span class="sxs-lookup"><span data-stu-id="b28ce-130">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="b28ce-131">Изберете един или повече сегменти.</span><span class="sxs-lookup"><span data-stu-id="b28ce-131">Choose one or more segments.</span></span>

1. <span data-ttu-id="b28ce-132">Изберете **Записване**</span><span class="sxs-lookup"><span data-stu-id="b28ce-132">Select **Save**</span></span>

<span data-ttu-id="b28ce-133">Запазването на експортиране не го изпълнява незабавно.</span><span class="sxs-lookup"><span data-stu-id="b28ce-133">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="b28ce-134">Експортирането се изпълнява с всяко [планирано обновяване](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="b28ce-134">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="b28ce-135">Може също [да експортирате данни при поискване](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="b28ce-135">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
