---
title: Поглъщане на данни в реално време и ограничения
description: Обща информация за възможностите в реално време в прозренията на аудиторията.
ms.date: 10/27/2020
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7421ed9d2cb399d546815b2d1b0ea5ec51ca6b6d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270267"
---
# <a name="real-time-data-ingestion-preview"></a><span data-ttu-id="92592-103">Приемане на данни в реално време (преглед)</span><span class="sxs-lookup"><span data-stu-id="92592-103">Real-time data ingestion (preview)</span></span>

<span data-ttu-id="92592-104">Функционалността за работа почти в реално време ви позволява да видите в рамките на секунди най-новите взаимодействия, които вашите клиенти са осъществили с продуктите или услугите.</span><span class="sxs-lookup"><span data-stu-id="92592-104">The near real-time functionality lets you see, within seconds, the latest interactions that your customers have made with your products or services.</span></span>

<span data-ttu-id="92592-105">[Планираните обновявания](system.md#schedule-tab) включват голям брой записи и няколко сложни операции.</span><span class="sxs-lookup"><span data-stu-id="92592-105">[Scheduled refreshes](system.md#schedule-tab) include large numbers of records and several complex operations.</span></span> <span data-ttu-id="92592-106">Първо, данните се извличат от източник на данни.</span><span class="sxs-lookup"><span data-stu-id="92592-106">First, data is pulled from the data source.</span></span> <span data-ttu-id="92592-107">След това данните се обединяват, след което се допълват с допълнителна информация.</span><span class="sxs-lookup"><span data-stu-id="92592-107">Next, the data is unified, and then enriched with additional information.</span></span> <span data-ttu-id="92592-108">Всяко изпълнение на този процес може да отнеме от минути до часове.</span><span class="sxs-lookup"><span data-stu-id="92592-108">Every run of this process can take minutes to hours.</span></span>

<span data-ttu-id="92592-109">Функционалността в реално време предоставя данни незабавно за консумация, докато последващото планирано опресняване изтегли тези данни от източник на данни.</span><span class="sxs-lookup"><span data-stu-id="92592-109">The real-time functionality provides data immediately for consumption, until the subsequent scheduled refresh pulls this data from the data source.</span></span>

<span data-ttu-id="92592-110">Актуализациите в реално време имат време за изтичане, след което те вече не заместват стойността от източника на данни:</span><span class="sxs-lookup"><span data-stu-id="92592-110">Real-time updates have an expiration time after which they no longer override the value from the data source:</span></span>

- <span data-ttu-id="92592-111">Актуализациите на профилите ще се съхраняват в продължение на 4 часа</span><span class="sxs-lookup"><span data-stu-id="92592-111">Profile updates will be kept for 4 hours</span></span>
- <span data-ttu-id="92592-112">Дейностите ще се запазват в продължение на 30 дни</span><span class="sxs-lookup"><span data-stu-id="92592-112">Activities will be kept for 30 days</span></span>

<span data-ttu-id="92592-113">Тези стойности са параметри за API извиквания, които можете да промените.</span><span class="sxs-lookup"><span data-stu-id="92592-113">These values are API call parameters that you can change.</span></span> <span data-ttu-id="92592-114">Целта им е да гарантират, че изходните данни остават източник на достоверни данни.</span><span class="sxs-lookup"><span data-stu-id="92592-114">They aim to ensure that your source data remains your source of truth.</span></span> <span data-ttu-id="92592-115">Ако искате актуализациите в реално време да бъдат включени за по-дълго, трябва да ги добавите към източник на данни, за да бъдат изтеглени по време на следващото планирано опресняване.</span><span class="sxs-lookup"><span data-stu-id="92592-115">If you want real-time updates to be included for longer, you need to add them to a data source so they get pulled during the next scheduled refresh.</span></span>

## <a name="real-time-update-of-the-unified-customer-profile-fields"></a><span data-ttu-id="92592-116">Актуализация в реално време на полетата на унифицирания клиентски профил</span><span class="sxs-lookup"><span data-stu-id="92592-116">Real-time update of the unified customer profile fields</span></span>

<span data-ttu-id="92592-117">Актуализираните профили ще се покажат в изгледа на клиентска карта или всяка друга визуализация в рамките на няколко секунди.</span><span class="sxs-lookup"><span data-stu-id="92592-117">Updated profiles will show in the customer card view, or any other visualization, within a few seconds.</span></span>

<span data-ttu-id="92592-118">Понеже операциите в реално време се извършват след обединяването на данните, те се прилагат само към унифицираните клиентски профили.</span><span class="sxs-lookup"><span data-stu-id="92592-118">Because real-time operations take place after the data unification has happened, they only apply to the unified customer profiles.</span></span> <span data-ttu-id="92592-119">Следователно промените в профила в реално време няма да актуализират мерките, членството в сегменти или допълването.</span><span class="sxs-lookup"><span data-stu-id="92592-119">Consequently, real-time profile changes will not update measures, segment membership, or enrichments.</span></span>

### <a name="limitations"></a><span data-ttu-id="92592-120">Ограничения</span><span class="sxs-lookup"><span data-stu-id="92592-120">Limitations</span></span>

- <span data-ttu-id="92592-121">Клиентските профили могат да бъдат актуализирани, но не създавани или изтривани.</span><span class="sxs-lookup"><span data-stu-id="92592-121">Customer profiles can be updated, but not created or deleted.</span></span>
- <span data-ttu-id="92592-122">Експортиране на актуализации в реално време във външни системи, като например Power BI, не е възможно в момента.</span><span class="sxs-lookup"><span data-stu-id="92592-122">Exporting real-time updates to external systems, like Power BI, is not possible at the moment.</span></span>

## <a name="real-time-creation-of-activities"></a><span data-ttu-id="92592-123">Създаване на дейности в реално време</span><span class="sxs-lookup"><span data-stu-id="92592-123">Real-time creation of activities</span></span>

<span data-ttu-id="92592-124">API в реално време ви позволява да публикувате нова активност от вашата система източник (индивидуален запис на източник) в унифициран клиентски профил.</span><span class="sxs-lookup"><span data-stu-id="92592-124">The real-time API lets you publish a new activity from your source system (an individual source record) to a unified customer profile.</span></span> <span data-ttu-id="92592-125">Новата дейност ще бъде налична като унифицирана дейност във времевата линия на този унифициран клиентски профил в рамките на секунди.</span><span class="sxs-lookup"><span data-stu-id="92592-125">The new activity will be available as a unified activity in that unified customer profile's timeline within seconds.</span></span> <span data-ttu-id="92592-126">Можете да видите времевата линия в изгледа на клиентска карта или всяка друга интеграция на времева линия, която сте конфигурирали.</span><span class="sxs-lookup"><span data-stu-id="92592-126">You can see the timeline in the customer card view or any other timeline integration you configured.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="92592-127">Дейностите са неизменни.</span><span class="sxs-lookup"><span data-stu-id="92592-127">Activities are immutable.</span></span> <span data-ttu-id="92592-128">Те не се променят след създаването им.</span><span class="sxs-lookup"><span data-stu-id="92592-128">They don't change once created.</span></span>
> - <span data-ttu-id="92592-129">В момента сегментите и мерките няма да се актуализират въз основа на новата дейност.</span><span class="sxs-lookup"><span data-stu-id="92592-129">Currently, segments and measures won't update based on the new activity.</span></span>
> - <span data-ttu-id="92592-130">Дейностите, добавени само чрез API в реално време, не са част от експортирането и няма да се показват в PowerBI.</span><span class="sxs-lookup"><span data-stu-id="92592-130">Activities added only through the real-time API are not part of exports and won't show up in PowerBI.</span></span>

<span data-ttu-id="92592-131">Има два начина за свързване с API в реално време:</span><span class="sxs-lookup"><span data-stu-id="92592-131">There are two ways to connect to the real-time API:</span></span>

- <span data-ttu-id="92592-132">[косвено](#connect-via-the-dynamics-365-customer-insights-connector) с помощта на [конектора на Dynamics 365 Customer Insights](https://docs.microsoft.com/connectors/customerinsights/)</span><span class="sxs-lookup"><span data-stu-id="92592-132">[indirectly](#connect-via-the-dynamics-365-customer-insights-connector), using the [Dynamics 365 Customer Insights connector](https://docs.microsoft.com/connectors/customerinsights/)</span></span>
- <span data-ttu-id="92592-133">[пряко](#connect-directly-to-the-real-time-api), с код</span><span class="sxs-lookup"><span data-stu-id="92592-133">[directly](#connect-directly-to-the-real-time-api), with code</span></span>

<span data-ttu-id="92592-134">И двата начина споделят следните предварителни изисквания:</span><span class="sxs-lookup"><span data-stu-id="92592-134">Both ways share the following prerequisites:</span></span>

- <span data-ttu-id="92592-135">Среда на Customer Insights</span><span class="sxs-lookup"><span data-stu-id="92592-135">A Customer Insights environment</span></span>
- <span data-ttu-id="92592-136">Унифицирани клиентски профили</span><span class="sxs-lookup"><span data-stu-id="92592-136">Unified customer profiles</span></span>
- <span data-ttu-id="92592-137">Дейностите са конфигурирани и се изпълняват</span><span class="sxs-lookup"><span data-stu-id="92592-137">Activities configured and run</span></span>
- <span data-ttu-id="92592-138">Разрешения на сътрудник или администратор за удостоверяване на акаунта</span><span class="sxs-lookup"><span data-stu-id="92592-138">Contributor or Administrator permissions to authenticate your account</span></span>

## <a name="connect-via-the-dynamics-365-customer-insights-connector"></a><span data-ttu-id="92592-139">Свързване чрез конектор на Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="92592-139">Connect via the Dynamics 365 Customer Insights connector</span></span>

<span data-ttu-id="92592-140">API в реално време може да приема данни от специализиран конектор на Power Platform, [конектора на Dynamics 365 Customer Insights](https://docs.microsoft.com/connectors/customerinsights/), без да е необходимо да пишете и внедрявате код.</span><span class="sxs-lookup"><span data-stu-id="92592-140">The real-time API can ingest data from a dedicated Power Platform connector, the [Dynamics 365 Customer Insights connector](https://docs.microsoft.com/connectors/customerinsights/), without the need to write and deploy any code.</span></span>    
<span data-ttu-id="92592-141">Конекторът може да извършва същите действия в реално време като API.</span><span class="sxs-lookup"><span data-stu-id="92592-141">The connector can do the same real-time actions as the API.</span></span> <span data-ttu-id="92592-142">Нуждаете се от валиден лиценз за премиалните конектори.</span><span class="sxs-lookup"><span data-stu-id="92592-142">You need a valid license for premium connectors.</span></span> <span data-ttu-id="92592-143">За повече информация вижте [ЧЗВ за лицензите за Power Apps и Power Automate](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq).</span><span class="sxs-lookup"><span data-stu-id="92592-143">For more information, see [Power Apps and Power Automate licensing FAQs](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq).</span></span>

- <span data-ttu-id="92592-144">Power Platform [Power Apps и/или Power Automate](https://docs.microsoft.com/connectors/)</span><span class="sxs-lookup"><span data-stu-id="92592-144">Power Platform [Power Apps and/or Power Automate](https://docs.microsoft.com/connectors/)</span></span>
- <span data-ttu-id="92592-145">Azure [Logic Apps](https://docs.microsoft.com/azure/connectors/apis-list)</span><span class="sxs-lookup"><span data-stu-id="92592-145">Azure [Logic Apps](https://docs.microsoft.com/azure/connectors/apis-list)</span></span>

<span data-ttu-id="92592-146">За подробности относно създаването на потоци вижте [документацията на Power Automate](https://docs.microsoft.com/power-automate/).</span><span class="sxs-lookup"><span data-stu-id="92592-146">For details about creating flows, see the [Power Automate documentation](https://docs.microsoft.com/power-automate/).</span></span>

## <a name="connect-directly-to-the-real-time-api"></a><span data-ttu-id="92592-147">Свързване директно с API в реално време</span><span class="sxs-lookup"><span data-stu-id="92592-147">Connect directly to the real-time API</span></span>

<span data-ttu-id="92592-148">Можете да използвате възможностите в реално време, като изградите свой собствен конвейер и се свържете директно с API в реално време.</span><span class="sxs-lookup"><span data-stu-id="92592-148">You can use the real-time capabilities by building your own pipeline and connecting directly to the real-time API.</span></span>    
<span data-ttu-id="92592-149">Можете да публикувате дейност във формата на изходната система или във формата UnifiedActivity.</span><span class="sxs-lookup"><span data-stu-id="92592-149">You can post an activity in the format of your source system or in the UnifiedActivity format.</span></span> <span data-ttu-id="92592-150">Получете формата, като направите обаждане на API към /api/instances/{instanceId}/manage/entities/UnifiedActivity.</span><span class="sxs-lookup"><span data-stu-id="92592-150">Get the format by making an API call to /api/instances/{instanceId}/manage/entities/UnifiedActivity.</span></span>

<span data-ttu-id="92592-151">Подробности за този API, включително параметри и отговори, можете да намерите в раздела **EntityData** на [Справка за API на Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span><span class="sxs-lookup"><span data-stu-id="92592-151">Details of this API, including parameters and responses, can be found in the **EntityData** section on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="92592-152">За повече информация вижте [Работа с приложни програмни интерфейси (API) на Customer Insights](apis.md).</span><span class="sxs-lookup"><span data-stu-id="92592-152">For more information, see [Work with Customer Insights APIs](apis.md).</span></span>

## <a name="understand-your-real-time-usage-with-telemetry"></a><span data-ttu-id="92592-153">Разберете вашето използване в реално време с телеметрия</span><span class="sxs-lookup"><span data-stu-id="92592-153">Understand your real-time usage with telemetry</span></span>

<span data-ttu-id="92592-154">Получете общ преглед на обема на заявките към API в реално време и информация за проблеми, които системата може да срещне.</span><span class="sxs-lookup"><span data-stu-id="92592-154">Get an overview of the volume of requests to the real-time API and information about issues the system may encounter.</span></span> <span data-ttu-id="92592-155">Можете да осъществите [достъп до телеметрията в реално време](system.md#api-usage-tab).</span><span class="sxs-lookup"><span data-stu-id="92592-155">You can [access the real-time telemetry](system.md#api-usage-tab).</span></span> 


[!INCLUDE[footer-include](../includes/footer-banner.md)]