---
title: Експортирайте данните от Customer Insights в Dynamics 365 Sales
description: Научете как да конфигурирате връзката към Dynamics 365 Sales.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: af0824e69dfdf620a0ac756e32a9bd3dd85e5151
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643805"
---
# <a name="connector-for-dynamics-365-sales-preview"></a><span data-ttu-id="7f8be-103">Конектор за Dynamics 365 Sales (преглед)</span><span class="sxs-lookup"><span data-stu-id="7f8be-103">Connector for Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="7f8be-104">Използвайте клиентските данни, за да създавате маркетингови списъци, работни потоци за последващи действия и за да изпращате съобщения за промоции с Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="7f8be-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite"></a><span data-ttu-id="7f8be-105">Предварително изискване</span><span class="sxs-lookup"><span data-stu-id="7f8be-105">Prerequisite</span></span>

<span data-ttu-id="7f8be-106">Записи за контакти [от Dynamics 365 Sales, погълнати с помощта на Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="7f8be-106">Contact records [from Dynamics 365 Sales ingested using Common Data Service](connect-power-query.md).</span></span>

## <a name="configure-the-connector-for-sales"></a><span data-ttu-id="7f8be-107">Конфигуриране на конектора за Продажби</span><span class="sxs-lookup"><span data-stu-id="7f8be-107">Configure the connector for Sales</span></span>

1. <span data-ttu-id="7f8be-108">В статията за аудиторията отидете на **Администратор** > **Експортиране на местоположения**.</span><span class="sxs-lookup"><span data-stu-id="7f8be-108">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="7f8be-109">Под **Dynamics 365 Sales**, изберете **Настройка**.</span><span class="sxs-lookup"><span data-stu-id="7f8be-109">Under **Dynamics 365 Sales**, select **Set up**.</span></span>

1. <span data-ttu-id="7f8be-110">Въведете разпознаваемо име за местоназначението за експортиране в полето **Показвано име**.</span><span class="sxs-lookup"><span data-stu-id="7f8be-110">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="7f8be-111">Въведете URL адрес на Продажби за вашата организация в полето **Адрес на сървър**.</span><span class="sxs-lookup"><span data-stu-id="7f8be-111">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="7f8be-112">В секцията **Администраторски акаунт на сървъра** изберете **Влизане** и изберете акаунт на Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="7f8be-112">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="7f8be-113">Присвояване на поле за ИД на клиент към ИД за връзка на Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="7f8be-113">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="7f8be-114">Изберете **Напред**.</span><span class="sxs-lookup"><span data-stu-id="7f8be-114">Select **Next**.</span></span>

1. <span data-ttu-id="7f8be-115">Изберете един или повече сегменти.</span><span class="sxs-lookup"><span data-stu-id="7f8be-115">Choose one or more segments.</span></span>

1. <span data-ttu-id="7f8be-116">Изберете **Записване**.</span><span class="sxs-lookup"><span data-stu-id="7f8be-116">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="7f8be-117">Експортиране на данните</span><span class="sxs-lookup"><span data-stu-id="7f8be-117">Export the data</span></span>

<span data-ttu-id="7f8be-118">Можете да [експортирате данни при поискване](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="7f8be-118">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="7f8be-119">Експортирането също ще се изпълнява с всяко [планирано обновяване](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="7f8be-119">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
