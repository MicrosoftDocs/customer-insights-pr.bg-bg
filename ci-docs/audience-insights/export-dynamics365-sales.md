---
title: Експортирайте данните от Customer Insights в Dynamics 365 Sales
description: Научете как да конфигурирате връзката към Dynamics 365 Sales.
ms.date: 02/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 39ecdf528c6be4d8fb420a52a6ed998317e43bcd
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598096"
---
# <a name="connector-for-dynamics-365-sales-preview"></a><span data-ttu-id="73750-103">Конектор за Dynamics 365 Sales (преглед)</span><span class="sxs-lookup"><span data-stu-id="73750-103">Connector for Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="73750-104">Използвайте клиентските данни, за да създавате маркетингови списъци, работни потоци за последващи действия и за да изпращате съобщения за промоции с Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="73750-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite"></a><span data-ttu-id="73750-105">Предварително изискване</span><span class="sxs-lookup"><span data-stu-id="73750-105">Prerequisite</span></span>

1. <span data-ttu-id="73750-106">Записите за контакти трябва да присъстват в Dynamics 365 Sales, преди да можете да експортирате сегмент от Customer Insights в Sales.</span><span class="sxs-lookup"><span data-stu-id="73750-106">Contact records must be present in Dynamics 365 Sales before you can export a segment from Customer Insights to Sales.</span></span> <span data-ttu-id="73750-107">Прочетете повече за това как да поглъщате контакти в [Dynamics 365 Sales с помощта на Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="73750-107">Read more on how to ingest contacts in [Dynamics 365 Sales using Common Data Services](connect-power-query.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="73750-108">Експортирането на сегменти от аналитични данни за аудитория в Sales няма да създаде нови записи за контакти в екземпляри на Sales.</span><span class="sxs-lookup"><span data-stu-id="73750-108">Exporting segments from audience insights to Sales will not create new contact records in the Sales instances.</span></span> <span data-ttu-id="73750-109">Записите за контакти от Sales трябва да се поглъщат с прозрения за аудиторията и да се използват като източник на данни.</span><span class="sxs-lookup"><span data-stu-id="73750-109">The contact records from Sales must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="73750-110">Те също трябва да бъдат включени в единния обект на клиента, за да се съпоставят идентификаторите на клиентите с идентификаторите за контакт, преди сегментите да могат да бъдат експортирани.</span><span class="sxs-lookup"><span data-stu-id="73750-110">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="configure-the-connector-for-sales"></a><span data-ttu-id="73750-111">Конфигуриране на конектора за Продажби</span><span class="sxs-lookup"><span data-stu-id="73750-111">Configure the connector for Sales</span></span>

1. <span data-ttu-id="73750-112">В статията за аудиторията отидете на **Администратор** > **Експортиране на местоположения**.</span><span class="sxs-lookup"><span data-stu-id="73750-112">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="73750-113">Под **Dynamics 365 Sales**, изберете **Настройка**.</span><span class="sxs-lookup"><span data-stu-id="73750-113">Under **Dynamics 365 Sales**, select **Set up**.</span></span>

1. <span data-ttu-id="73750-114">Въведете разпознаваемо име за местоназначението за експортиране в полето **Показвано име**.</span><span class="sxs-lookup"><span data-stu-id="73750-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="73750-115">Въведете URL адрес на Продажби за вашата организация в полето **Адрес на сървър**.</span><span class="sxs-lookup"><span data-stu-id="73750-115">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="73750-116">В секцията **Администраторски акаунт на сървъра** изберете **Влизане** и изберете акаунт на Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="73750-116">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="73750-117">Присвояване на поле за ИД на клиент към ИД за връзка на Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="73750-117">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="73750-118">Изберете **Напред**.</span><span class="sxs-lookup"><span data-stu-id="73750-118">Select **Next**.</span></span>

1. <span data-ttu-id="73750-119">Изберете един или повече сегменти.</span><span class="sxs-lookup"><span data-stu-id="73750-119">Choose one or more segments.</span></span>

1. <span data-ttu-id="73750-120">Изберете **Записване**.</span><span class="sxs-lookup"><span data-stu-id="73750-120">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="73750-121">Експортиране на данните</span><span class="sxs-lookup"><span data-stu-id="73750-121">Export the data</span></span>

<span data-ttu-id="73750-122">Можете да [експортирате данни при поискване](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="73750-122">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="73750-123">Експортирането също ще се изпълнява с всяко [планирано обновяване](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="73750-123">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]