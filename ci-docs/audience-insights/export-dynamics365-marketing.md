---
title: Експортирайте данните от Customer Insights в Dynamics 365 Marketing
description: Научете как да конфигурирате връзката към Dynamics 365 Marketing.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 163387779b64bd78ef08e2d96a5f1c9615062f28
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643760"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a><span data-ttu-id="06592-103">Конектор за Dynamics 365 Marketing (преглед)</span><span class="sxs-lookup"><span data-stu-id="06592-103">Connector for Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="06592-104">Използвайте [сегментите](segments.md), за да генерирате кампании, и се свързвайте с конкретни групи клиенти с Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="06592-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="06592-105">За повече информация вижте [Използване на сегменти от Dynamics 365 Customer Insights с Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="06592-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite"></a><span data-ttu-id="06592-106">Предварително изискване</span><span class="sxs-lookup"><span data-stu-id="06592-106">Prerequisite</span></span>

<span data-ttu-id="06592-107">Записи за контакти [от Dynamics 365 Marketing, погълнати с помощта на Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="06592-107">Contact records [from Dynamics 365 Marketing ingested Common Data Service](connect-power-query.md).</span></span>

## <a name="configure-the-connector-for-marketing"></a><span data-ttu-id="06592-108">Конфигуриране на конектора за Marketing</span><span class="sxs-lookup"><span data-stu-id="06592-108">Configure the connector for Marketing</span></span>

1. <span data-ttu-id="06592-109">В статията за аудиторията отидете на **Администратор** > **Експортиране на местоположения**.</span><span class="sxs-lookup"><span data-stu-id="06592-109">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="06592-110">Под **Dynamics 365 Marketing**, изберете **Настройка**.</span><span class="sxs-lookup"><span data-stu-id="06592-110">Under **Dynamics 365 Marketing**, select **Set up**.</span></span>

1. <span data-ttu-id="06592-111">Въведете разпознаваемо име за местоназначението за експортиране в полето **Показвано име**.</span><span class="sxs-lookup"><span data-stu-id="06592-111">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="06592-112">Въведете URL адрес на Marketing за вашата организация в полето **Адрес на сървър**.</span><span class="sxs-lookup"><span data-stu-id="06592-112">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="06592-113">В секцията **Администраторски акаунт на сървъра** изберете **Влизане** и изберете акаунт на Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="06592-113">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="06592-114">Присвояване на поле за ИД на клиент към ИД за връзка на Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="06592-114">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="06592-115">Изберете **Напред**.</span><span class="sxs-lookup"><span data-stu-id="06592-115">Select **Next**.</span></span>

1. <span data-ttu-id="06592-116">Изберете един или повече сегменти.</span><span class="sxs-lookup"><span data-stu-id="06592-116">Choose one or more segments.</span></span>

1. <span data-ttu-id="06592-117">Изберете **Записване**.</span><span class="sxs-lookup"><span data-stu-id="06592-117">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="06592-118">Експортиране на данните</span><span class="sxs-lookup"><span data-stu-id="06592-118">Export the data</span></span>

<span data-ttu-id="06592-119">Можете да [експортирате данни при поискване](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="06592-119">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="06592-120">Експортирането също ще се изпълнява с всяко [планирано обновяване](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="06592-120">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
