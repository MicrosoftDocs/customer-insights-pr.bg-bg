---
title: Експортирайте данните от Customer Insights в Dynamics 365 Marketing
description: Научете как да конфигурирате връзката към Dynamics 365 Marketing.
ms.date: 02/01/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: a06920b8ff25d7102ccd14ae68cf42fe91fa1ee6
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269041"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a><span data-ttu-id="24bb1-103">Конектор за Dynamics 365 Marketing (преглед)</span><span class="sxs-lookup"><span data-stu-id="24bb1-103">Connector for Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="24bb1-104">Използвайте [сегментите](segments.md), за да генерирате кампании, и се свързвайте с конкретни групи клиенти с Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="24bb1-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="24bb1-105">За повече информация вижте [Използване на сегменти от Dynamics 365 Customer Insights с Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="24bb1-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite"></a><span data-ttu-id="24bb1-106">Предварително изискване</span><span class="sxs-lookup"><span data-stu-id="24bb1-106">Prerequisite</span></span>

- <span data-ttu-id="24bb1-107">Записите за контакти трябва да присъстват в Dynamics 365 Marketing, преди да можете да експортирате сегмент от Customer Insights в Marketing.</span><span class="sxs-lookup"><span data-stu-id="24bb1-107">Contact records must be present in Dynamics 365 Marketing before you can export a segment from Customer Insights to Marketing.</span></span> <span data-ttu-id="24bb1-108">Прочетете повече за това как да поглъщате контакти в [Dynamics 365 Marketing с помощта на Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="24bb1-108">Read more on how to ingest contacts in [Dynamics 365 Marketing using Common Data Services](connect-power-query.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="24bb1-109">Експортирането на сегменти от аналитични данни за аудитория в Marketing няма да създаде нови записи за контакти в маркетинговите екземпляри.</span><span class="sxs-lookup"><span data-stu-id="24bb1-109">Exporting segments from audience insights to Marketing will not create new contact records in the Marketing instances.</span></span> <span data-ttu-id="24bb1-110">Записите за контакти от Marketing трябва да се поглъщат с прозрения за аудиторията и да се използват като източник на данни.</span><span class="sxs-lookup"><span data-stu-id="24bb1-110">The contact records from Marketing must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="24bb1-111">Те също трябва да бъдат включени в единния обект на клиента, за да се съпоставят идентификаторите на клиентите с идентификаторите за контакт, преди сегментите да могат да бъдат експортирани.</span><span class="sxs-lookup"><span data-stu-id="24bb1-111">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="configure-the-connector-for-marketing"></a><span data-ttu-id="24bb1-112">Конфигуриране на конектора за Marketing</span><span class="sxs-lookup"><span data-stu-id="24bb1-112">Configure the connector for Marketing</span></span>

1. <span data-ttu-id="24bb1-113">В статията за аудиторията отидете на **Администратор** > **Експортиране на местоположения**.</span><span class="sxs-lookup"><span data-stu-id="24bb1-113">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="24bb1-114">Под **Dynamics 365 Marketing**, изберете **Настройка**.</span><span class="sxs-lookup"><span data-stu-id="24bb1-114">Under **Dynamics 365 Marketing**, select **Set up**.</span></span>

1. <span data-ttu-id="24bb1-115">Въведете разпознаваемо име за местоназначението за експортиране в полето **Показвано име**.</span><span class="sxs-lookup"><span data-stu-id="24bb1-115">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="24bb1-116">Въведете URL адрес на Marketing за вашата организация в полето **Адрес на сървър**.</span><span class="sxs-lookup"><span data-stu-id="24bb1-116">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="24bb1-117">В секцията **Администраторски акаунт на сървъра** изберете **Влизане** и изберете акаунт на Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="24bb1-117">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="24bb1-118">Присвояване на поле за ИД на клиент към ИД за връзка на Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="24bb1-118">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="24bb1-119">Изберете **Напред**.</span><span class="sxs-lookup"><span data-stu-id="24bb1-119">Select **Next**.</span></span>

1. <span data-ttu-id="24bb1-120">Изберете един или повече сегменти.</span><span class="sxs-lookup"><span data-stu-id="24bb1-120">Choose one or more segments.</span></span>

1. <span data-ttu-id="24bb1-121">Изберете **Записване**.</span><span class="sxs-lookup"><span data-stu-id="24bb1-121">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="24bb1-122">Експортиране на данните</span><span class="sxs-lookup"><span data-stu-id="24bb1-122">Export the data</span></span>

<span data-ttu-id="24bb1-123">Можете да [експортирате данни при поискване](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="24bb1-123">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="24bb1-124">Експортирането също ще се изпълнява с всяко [планирано обновяване](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="24bb1-124">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]