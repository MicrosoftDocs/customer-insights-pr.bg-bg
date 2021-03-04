---
title: Заявки по правата на субекта на данни (DSR) съгласно GDPR | Microsoft Docs
description: Отговорете на заявки за субект на данни за способността за аналитични данни за аудитория на Dynamics 365 Customer Insights.
ms.date: 05/14/2020
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ed9aa09fba938606611c6ce86c2b250c5e19c606
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268673"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a><span data-ttu-id="11da2-103">Правата на субекта на данни (DSR) съгласно GDPR</span><span class="sxs-lookup"><span data-stu-id="11da2-103">Data Subject Rights (DSR) requests under GDPR</span></span>

## <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a><span data-ttu-id="11da2-104">Отговор на заявки за изтриване на субект на данни според GDPR за способността за аналитични данни за аудитория на Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="11da2-104">Responding to GDPR data subject delete requests for Dynamics 365 Customer Insights audience insights capability</span></span>

<span data-ttu-id="11da2-105">„Правото на изтриване” чрез премахване на лични данни от клиентските данни на организацията е ключова защита в Общия регламент относно защитата на данните (GDPR).</span><span class="sxs-lookup"><span data-stu-id="11da2-105">The “right to erasure” by the removal of personal data from an organization’s customer data is a key protection in the General Data Protection Regulation (GDPR).</span></span> <span data-ttu-id="11da2-106">Премахването на лични данни включва премахване на всички лични данни и системно генерирани регистрационни файлове, с изключение на информацията от регистрационни файлове за одит.</span><span class="sxs-lookup"><span data-stu-id="11da2-106">Removing personal data includes removing all personal data and system-generated logs, except audit log information.</span></span>

### <a name="manage-data-subject-delete-requests"></a><span data-ttu-id="11da2-107">Управление на заявки за изтриване на субект на данни</span><span class="sxs-lookup"><span data-stu-id="11da2-107">Manage data subject delete requests</span></span>

<span data-ttu-id="11da2-108">Аналитични данни за аудитория предлага следните функционалности на продуктите за изтриване на лични данни за конкретен клиент или потребител:</span><span class="sxs-lookup"><span data-stu-id="11da2-108">Audience insights offers the following in-product experiences to delete personal data for a specific customer or user:</span></span>

- <span data-ttu-id="11da2-109">**Управление на заявки за изтриване на клиентски данни**: Клиентските данни в Customer Insights се приемат от първоначални източници на данни, външни за Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="11da2-109">**Manage delete requests for customer data**: Customer data in Customer Insights is ingested from original data sources external to Customer Insights.</span></span> <span data-ttu-id="11da2-110">Всички заявки за изтриване съгласно GDPR трябва да се изпълнят в първоначалния източник на данни.</span><span class="sxs-lookup"><span data-stu-id="11da2-110">All GDPR delete requests must be performed in the original data source.</span></span>
- <span data-ttu-id="11da2-111">**Управлявайте заявки за изтриване на потребителски данни на Customer Insights**: Данните за потребителите се създават от Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="11da2-111">**Manage delete requests for Customer Insights user data**: Data for users is created by Customer Insights.</span></span> <span data-ttu-id="11da2-112">Всички заявки за изтриване по GDPR трябва да се изпълнят в Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="11da2-112">All GDPR delete requests must be performed in Customer Insights.</span></span>

#### <a name="manage-delete-requests-for-customer-data"></a><span data-ttu-id="11da2-113">Управление на заявки за изтриване на клиентски данни</span><span class="sxs-lookup"><span data-stu-id="11da2-113">Manage delete requests for customer data</span></span>

<span data-ttu-id="11da2-114">Администратор на Customer Insights може да следва тези стъпки, за да премахне клиентските данни, които са били изтрити в източника на данни:</span><span class="sxs-lookup"><span data-stu-id="11da2-114">A Customer Insights admin can follow these steps to remove customer data that was deleted in the data source:</span></span>

1. <span data-ttu-id="11da2-115">Влезте в Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="11da2-115">Sign in to Dynamics 365 Customer Insights.</span></span>
2. <span data-ttu-id="11da2-116">В статията за аудиторията отидете на **Данни** > **Източници на данни**</span><span class="sxs-lookup"><span data-stu-id="11da2-116">In audience insights, go to **Data** > **Data sources**</span></span>
3. <span data-ttu-id="11da2-117">За всеки източник на данни в списъка, който съдържа изтрити клиентски данни:</span><span class="sxs-lookup"><span data-stu-id="11da2-117">For each data source in the list that contains deleted customer data:</span></span>
   1. <span data-ttu-id="11da2-118">Изберете (...) и след това изберете **Обновяване**.</span><span class="sxs-lookup"><span data-stu-id="11da2-118">Select (...) and then select **Refresh**.</span></span>
   2. <span data-ttu-id="11da2-119">Проверете състоянието на източника на данни под **Състояние**.</span><span class="sxs-lookup"><span data-stu-id="11da2-119">Check the status of the data source under **Status**.</span></span> <span data-ttu-id="11da2-120">Отметката означава, че обновяването е успешно.</span><span class="sxs-lookup"><span data-stu-id="11da2-120">A check mark means the refresh was successful.</span></span> <span data-ttu-id="11da2-121">Предупредителният триъгълник означава, че нещо се е объркало.</span><span class="sxs-lookup"><span data-stu-id="11da2-121">A warning triangle means something went wrong.</span></span> <span data-ttu-id="11da2-122">Ако се покаже предупредителен триъгълник, свържете се с D365CI@microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="11da2-122">If a warning triangle is displayed, contact D365CI@microsoft.com.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="11da2-123">![Обработка на заявки за изтриване съгласно GDPR за клиентски данни](media/gdpr-data-sources.png "Обработка на заявки за изтриване съгласно GDPR за клиентски данни")</span><span class="sxs-lookup"><span data-stu-id="11da2-123">![Handling GDPR delete requests for customer data](media/gdpr-data-sources.png "Handling GDPR delete requests for customer data")</span></span>

#### <a name="manage-delete-requests-for-user-data"></a><span data-ttu-id="11da2-124">Управление на заявки за изтриване на потребителски данни</span><span class="sxs-lookup"><span data-stu-id="11da2-124">Manage delete requests for user data</span></span>

<span data-ttu-id="11da2-125">Администраторът на Customer Insights може да следва тези стъпки, за да изтрие потребителските данни в Customer Insights:</span><span class="sxs-lookup"><span data-stu-id="11da2-125">A Customer Insights admin can follow these steps to delete Customer Insights user data:</span></span>

1. <span data-ttu-id="11da2-126">Влезте в Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="11da2-126">Sign in to Dynamics 365 Customer Insights.</span></span>
2. <span data-ttu-id="11da2-127">В статията за аудиторията отидете на **Администратор** > **Разрешения**.</span><span class="sxs-lookup"><span data-stu-id="11da2-127">In audience insights, go to **Admin** > **Permissions**.</span></span>
3. <span data-ttu-id="11da2-128">Поставете отметка в квадратчето за потребителя, който искате да изтриете.</span><span class="sxs-lookup"><span data-stu-id="11da2-128">Select the check box for the user you want to delete.</span></span>
4. <span data-ttu-id="11da2-129">Изберете **Премахване**.</span><span class="sxs-lookup"><span data-stu-id="11da2-129">Select **Remove**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="11da2-130">![Управление на заявки за изтриване на потребителски данни според GDPR](media/gdpr-permissions.png "Управление на заявки за изтриване за потребителски данни според GDPR")</span><span class="sxs-lookup"><span data-stu-id="11da2-130">![Handling GDPR delete requests foruser data](media/gdpr-permissions.png "Handling GDPR delete requests for user data")</span></span>

## <a name="responding-to-gdpr-data-subject-export-requests"></a><span data-ttu-id="11da2-131">Отговор на заявки за експортиране на субект на данни съгласно GDPR</span><span class="sxs-lookup"><span data-stu-id="11da2-131">Responding to GDPR data subject export requests</span></span>

<span data-ttu-id="11da2-132">Като част от ангажимента ни да си партнираме с вас по пътя към Общия регламент относно защитата на данните (GDPR), разработихме документация, която да ви помогне да се подготвите.</span><span class="sxs-lookup"><span data-stu-id="11da2-132">As part of our commitment to partner with you on your journey to the General Data Protection Regulation (GDPR), we’ve developed documentation to help you prepare.</span></span> <span data-ttu-id="11da2-133">Тази документация описва стъпки, които можете да предприемете днес, за да подкрепите спазването на GDPR, когато използвате статистика за аудиторията.</span><span class="sxs-lookup"><span data-stu-id="11da2-133">This documentation describes steps you can take today to support GDPR compliance when using audience insights.</span></span>

### <a name="manage-export-and-view-requests"></a><span data-ttu-id="11da2-134">Управление на заявки за експортиране и преглед</span><span class="sxs-lookup"><span data-stu-id="11da2-134">Manage export and view requests</span></span>

<span data-ttu-id="11da2-135">Правото на преносимост на данните позволява на субектите на данни да изискат копие от своите лични данни в електронен формат (определен като „структуриран, често използван, машинно четим и оперативно съвместим формат”), който може да бъде предаден на друг администратор на данни.</span><span class="sxs-lookup"><span data-stu-id="11da2-135">The right of data portability allows data subjects to request a copy of their personal data in an electronic format (a “structured, commonly used, machine readable, and interoperable format”) that can be transmitted to another data controller.</span></span>

#### <a name="export-customer-data-tenant-admin"></a><span data-ttu-id="11da2-136">Експортиране на клиентски данни (администратор на клиент)</span><span class="sxs-lookup"><span data-stu-id="11da2-136">Export customer data (tenant admin)</span></span>

<span data-ttu-id="11da2-137">Администраторът на клиент може да следва тези стъпки за експортиране на данни:</span><span class="sxs-lookup"><span data-stu-id="11da2-137">A tenant administrator can follow these steps to export data:</span></span>

1. <span data-ttu-id="11da2-138">Изпратете имейл до D365CI@microsoft.com, за да укажете имейл адреса на клиента в заявката.</span><span class="sxs-lookup"><span data-stu-id="11da2-138">Send an email to D365CI@microsoft.com specifying the customer’s email address in the request.</span></span> <span data-ttu-id="11da2-139">Екипът на Customer Insights ще изпрати имейл на регистрирания имейл адрес на администратора на клиента, който изисква потвърждение за експортирането на данни.</span><span class="sxs-lookup"><span data-stu-id="11da2-139">The Customer Insights team will send an email to the registered tenant admin email address, asking for confirmation to export data.</span></span>
2. <span data-ttu-id="11da2-140">Приемане на потвърждението за експортиране на данните за заявения клиент.</span><span class="sxs-lookup"><span data-stu-id="11da2-140">Acknowledge the confirmation to export the data for the requested customer.</span></span>
3. <span data-ttu-id="11da2-141">Получаване на експортираните данни чрез имейл адреса на администратора на клиента.</span><span class="sxs-lookup"><span data-stu-id="11da2-141">Receive the exported data through the tenant admin email address.</span></span>

#### <a name="export-user-data-tenant-admin"></a><span data-ttu-id="11da2-142">Експортиране на потребителски данни (администратор на клиент)</span><span class="sxs-lookup"><span data-stu-id="11da2-142">Export user data (tenant admin)</span></span>

1. <span data-ttu-id="11da2-143">Изпратете имейл до D365CI@microsoft.com, за да укажете имейл адреса на потребителя в заявката.</span><span class="sxs-lookup"><span data-stu-id="11da2-143">Send an email to D365CI@microsoft.com specifying the user’s email address in the request.</span></span> <span data-ttu-id="11da2-144">Екипът на Customer Insights ще изпрати имейл на регистрирания имейл адрес на администратора на клиента, който изисква потвърждение за експортирането на данни.</span><span class="sxs-lookup"><span data-stu-id="11da2-144">The Customer Insights team will send an email to the registered tenant admin email address, asking for confirmation to export data.</span></span>
2. <span data-ttu-id="11da2-145">Приемане на потвърждението за експортиране на данните за заявения потребител.</span><span class="sxs-lookup"><span data-stu-id="11da2-145">Acknowledge the confirmation to export the data for the requested user.</span></span>
3. <span data-ttu-id="11da2-146">Получаване на експортираните данни чрез имейл адреса на администратора на клиента.</span><span class="sxs-lookup"><span data-stu-id="11da2-146">Receive the exported data through the tenant admin email address.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]