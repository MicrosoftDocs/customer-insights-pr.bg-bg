---
title: Свързване на данните от Common Data Model към акаунт в Azure Data Lake
description: Работа с данни от Common Data Model с помощта на Azure Data Lake Storage.
ms.date: 05/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 385406b706890d741fec2694c190c0fada7809d7
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596532"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a><span data-ttu-id="91202-103">Свържете с папка на Common Data Model с помощта на акаунт в Azure Data Lake</span><span class="sxs-lookup"><span data-stu-id="91202-103">Connect to a Common Data Model folder using an Azure Data Lake account</span></span>

<span data-ttu-id="91202-104">Тази статия предоставя информация за това как да поглъщате данни от папка Common Data Model с помощта на вашия акаунт в Azure Data Lake Storage Gen2.</span><span class="sxs-lookup"><span data-stu-id="91202-104">This article provides information on how to ingest data from a Common Data Model folder using your Azure Data Lake Storage Gen2 account.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="91202-105">Важни съображения</span><span class="sxs-lookup"><span data-stu-id="91202-105">Important considerations</span></span>

- <span data-ttu-id="91202-106">Данните в Azure Data Lake трябва да следват общия стандарт на Common Data Model.</span><span class="sxs-lookup"><span data-stu-id="91202-106">Data in your Azure Data Lake needs to follow the Common Data Model standard.</span></span> <span data-ttu-id="91202-107">В момента не се поддържат други формати.</span><span class="sxs-lookup"><span data-stu-id="91202-107">Other formats aren't supported at the moment.</span></span>

- <span data-ttu-id="91202-108">Поглъщането на данни поддържа акаунти в Azure Data Lake *Gen2* за съхранение изключително.</span><span class="sxs-lookup"><span data-stu-id="91202-108">Data ingestion supports Azure Data Lake *Gen2* storage accounts exclusively.</span></span> <span data-ttu-id="91202-109">Не можете да използвате акаунти за съхранение на Azure Data Lake Gen1 за поглъщане на данни.</span><span class="sxs-lookup"><span data-stu-id="91202-109">You can't use Azure Data Lake Gen1 storage accounts to ingest data.</span></span>

- <span data-ttu-id="91202-110">За да се удостоверите с принципал на услуга на Azure, уверете се, че е конфигуриран във вашия клиент.</span><span class="sxs-lookup"><span data-stu-id="91202-110">To authenticate with an Azure service principal, make sure it's configured in your tenant.</span></span> <span data-ttu-id="91202-111">За повече информация вижте [Свързване на аналитични данни за аудитория с акаунт в Azure Data Lake Storage Gen2 с принципал на услуга Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="91202-111">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span>

- <span data-ttu-id="91202-112">Azure Data Lake, от което искате да се свържете и поглъщате данни, трябва да бъде в същия регион на Azure като среда на Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="91202-112">The Azure Data Lake you want to connect and ingest data from have to be in the same Azure region as the Dynamics 365 Customer Insights environment.</span></span> <span data-ttu-id="91202-113">Не се поддържат връзки към папка на Common Data Model от хранилището с данни в различен регион на Azure.</span><span class="sxs-lookup"><span data-stu-id="91202-113">Connections to a Common Data Model folder from a data lake in a different Azure region is not supported.</span></span> <span data-ttu-id="91202-114">За да знаете региона на Azure на среда, отидете на **Администратор** > **Система** > **Относно** в прозренията на публиката.</span><span class="sxs-lookup"><span data-stu-id="91202-114">To know the Azure region of the environment, go to **Admin** > **System** > **About** in audience insights.</span></span>

- <span data-ttu-id="91202-115">Данните, съхранявани в онлайн услуги, могат да се съхраняват на място, различно от мястото, където данните се обработват или съхраняват в Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="91202-115">Data stored in online services, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="91202-116"> Чрез импортиране или свързване към данни, съхранявани в онлайн услуги, вие се съгласявате, че данните могат да се прехвърлят и съхраняват в Dynamics 365 Customer Insights. [Научете повече в центъра за сигурност на Microsoft.](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="91202-116"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-model-folder"></a><span data-ttu-id="91202-117">Свързване към папка на Common Data Model</span><span class="sxs-lookup"><span data-stu-id="91202-117">Connect to a Common Data Model folder</span></span>

1. <span data-ttu-id="91202-118">В статията за аудиторията отидете на **Данни** > **Източници на данни**.</span><span class="sxs-lookup"><span data-stu-id="91202-118">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="91202-119">Изберете **Добавяне на източник на данни**.</span><span class="sxs-lookup"><span data-stu-id="91202-119">Select **Add data source**.</span></span>

1. <span data-ttu-id="91202-120">Изберете **Свържете се с папка Common Model Model**, въведете **Име** за източник на данни и изберете **Напред**.</span><span class="sxs-lookup"><span data-stu-id="91202-120">Select **Connect to a Common Data Model folder**, enter a **Name** for the data source, and select **Next**.</span></span> <span data-ttu-id="91202-121">Насоки за име:</span><span class="sxs-lookup"><span data-stu-id="91202-121">Name guidelines:</span></span> 
   - <span data-ttu-id="91202-122">Започнете с буква.</span><span class="sxs-lookup"><span data-stu-id="91202-122">Start with a letter.</span></span>
   - <span data-ttu-id="91202-123">Използвайте само букви и цифри.</span><span class="sxs-lookup"><span data-stu-id="91202-123">Use letters and numbers only.</span></span> <span data-ttu-id="91202-124">Не е разрешено въвеждането на специални знаци и интервали.</span><span class="sxs-lookup"><span data-stu-id="91202-124">Special characters and spaces are not allowed.</span></span>
   - <span data-ttu-id="91202-125">Използвайте между 3 и 64 знака.</span><span class="sxs-lookup"><span data-stu-id="91202-125">Use between 3 and 64 characters.</span></span>

1. <span data-ttu-id="91202-126">Можете да избирате между използване на опция, базирана на ресурси и опция, базирана на абонамент за удостоверяване.</span><span class="sxs-lookup"><span data-stu-id="91202-126">You can choose between using a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="91202-127">За повече информация вижте [Свързване на аналитични данни за аудитория с акаунт в Azure Data Lake Storage Gen2 с принципал на услуга Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="91202-127">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="91202-128">Влезте в информацията **Контейнер** и изберете **Напред**.</span><span class="sxs-lookup"><span data-stu-id="91202-128">Enter the **Container** information and select **Next**.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="91202-129">![Диалогов прозорец за въвеждане на нови подробности за връзката за Azure Data Lake](media/enter-new-storage-details.png)
   > </span><span class="sxs-lookup"><span data-stu-id="91202-129">![Dialog box to enter new connection details for Azure Data Lake](media/enter-new-storage-details.png)
   > </span></span>[!NOTE]
<span data-ttu-id="91202-130">За да можете да се свържете и да създадете източник на данни, имате нужда от една от следните роли или към контейнера, или към акаунта за съхранение:</span><span class="sxs-lookup"><span data-stu-id="91202-130">You need one of the following roles either to the container or the storage account referred above to be able to connect to and create a data source:</span></span>
   >  - <span data-ttu-id="91202-131">Четец на данни за съхранение в Blob</span><span class="sxs-lookup"><span data-stu-id="91202-131">Storage Blob Data Reader</span></span>
   >  - <span data-ttu-id="91202-132">Собственик на данни за съхранение в Blob</span><span class="sxs-lookup"><span data-stu-id="91202-132">Storage Blob Data Owner</span></span>
   >  - <span data-ttu-id="91202-133">Сътрудник за данни за BLOB за съхранение</span><span class="sxs-lookup"><span data-stu-id="91202-133">Storage Blob Data Contributor</span></span>

1. <span data-ttu-id="91202-134">В **Изберете папка на Common Model Model** диалогов прозорец, изберете файла model.json или manifest.json, от който да импортирате данни, и изберете **Напред**.</span><span class="sxs-lookup"><span data-stu-id="91202-134">In the **Select a Common Data Model folder** dialog, select the model.json or manifest.json file to import data from, and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="91202-135">Всеки файл model.json или manifest.json, свързан с друг източник на данни в средата, няма да се показва в списъка.</span><span class="sxs-lookup"><span data-stu-id="91202-135">Any model.json or manifest.json file associated with another data source in the environment won't show in the list.</span></span>

1. <span data-ttu-id="91202-136">Ще получите списък с наличните обекти в избрания файл model.json или manifest.json.</span><span class="sxs-lookup"><span data-stu-id="91202-136">You'll get a list of available entities in the selected model.json or manifest.json file.</span></span> <span data-ttu-id="91202-137">Можете да преглеждате и избирате от списъка с налични обекти и изберете **Запазване**.</span><span class="sxs-lookup"><span data-stu-id="91202-137">You can review and select from the list of available entities and select **Save**.</span></span> <span data-ttu-id="91202-138">Всички от избраните обекти ще бъдат погълнати от новия източник на данни.</span><span class="sxs-lookup"><span data-stu-id="91202-138">All of the selected entities will be ingested from the new data source.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="91202-139">![Диалогов прозорец, показващ списък с обекти от файл model.json](media/review-entities.png)</span><span class="sxs-lookup"><span data-stu-id="91202-139">![Dialog box showing a list of entities from a model.json file](media/review-entities.png)</span></span>

8. <span data-ttu-id="91202-140">Посочете за кои обекти на данни искате да активирате профилирането на данни и изберете **Записване**.</span><span class="sxs-lookup"><span data-stu-id="91202-140">Indicate which data entities you want to enable data profiling and select **Save**.</span></span> <span data-ttu-id="91202-141">Профилирането на данни позволява анализ и други възможности.</span><span class="sxs-lookup"><span data-stu-id="91202-141">Data profiling enables analytics and other capabilities.</span></span> <span data-ttu-id="91202-142">Можете да изберете целия обект, който избира всички атрибути от обекта, или да изберете определени атрибути по ваш избор.</span><span class="sxs-lookup"><span data-stu-id="91202-142">You can select the whole entity, which selects all attributes from the entity, or select certain attributes of your choice.</span></span> <span data-ttu-id="91202-143">По подразбиране не е разрешен обект за профилиране на данни.</span><span class="sxs-lookup"><span data-stu-id="91202-143">By default, no entity is enabled for data profiling.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="91202-144">![Диалогов прозорец, показващ профилиране на данни](media/dataprofiling-entities.png)</span><span class="sxs-lookup"><span data-stu-id="91202-144">![Dialog box showing a data profiling](media/dataprofiling-entities.png)</span></span>

9. <span data-ttu-id="91202-145">След като запишете изборите си, се отваря страницата **Източници на данни**.</span><span class="sxs-lookup"><span data-stu-id="91202-145">After saving your selections, the **Data sources** page opens.</span></span> <span data-ttu-id="91202-146">Сега трябва да видите връзката с папката Common Data Model като източник на данни.</span><span class="sxs-lookup"><span data-stu-id="91202-146">You should now see the Common Data Model folder connection as a data source.</span></span>

> [!NOTE]
> <span data-ttu-id="91202-147">Файлът model.json или manifest.json може да се асоциира само с един източник на данни в същата среда.</span><span class="sxs-lookup"><span data-stu-id="91202-147">A model.json file or manifest.json can only associate with one data source in the same environment.</span></span> <span data-ttu-id="91202-148">Същият файл model.json или manifest.json обаче може да се използва за източници на данни в множество среди.</span><span class="sxs-lookup"><span data-stu-id="91202-148">However, the same model.json or manifest.json file can be used for data sources in multiple environments.</span></span>

## <a name="edit-a-common-data-model-folder-data-source"></a><span data-ttu-id="91202-149">Редактиране на източник на данни на папка на Common Data Model</span><span class="sxs-lookup"><span data-stu-id="91202-149">Edit a Common Data Model folder data source</span></span>

<span data-ttu-id="91202-150">Можете да актуализирате ключа за достъп за акаунта за съхранение, съдържащ папката Common Data Model.</span><span class="sxs-lookup"><span data-stu-id="91202-150">You can update the access key for the storage account containing the Common Data Model folder.</span></span> <span data-ttu-id="91202-151">Можете също така да промените файла model.json или manifest.json.</span><span class="sxs-lookup"><span data-stu-id="91202-151">You may also change the model.json or manifest.json file.</span></span> <span data-ttu-id="91202-152">За да се свържете с различен контейнер от акаунта за съхранение или да промените името на акаунта, трябва [да създадете нова връзка с източник на данни](#connect-to-a-common-data-model-folder).</span><span class="sxs-lookup"><span data-stu-id="91202-152">To connect to a different container from your storage account, or change the account name, [create a new data source connection](#connect-to-a-common-data-model-folder).</span></span>

1. <span data-ttu-id="91202-153">В статията за аудиторията отидете на **Данни** > **Източници на данни**.</span><span class="sxs-lookup"><span data-stu-id="91202-153">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="91202-154">До източника на данни, който искате да актуализирате, изберете многоточието.</span><span class="sxs-lookup"><span data-stu-id="91202-154">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="91202-155">Изберете опцията **Редактиране** от списъка.</span><span class="sxs-lookup"><span data-stu-id="91202-155">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="91202-156">По желание актуализирайте **Ключа за достъп** и изберете **Напред**.</span><span class="sxs-lookup"><span data-stu-id="91202-156">Optionally, update the **Access key** and select **Next**.</span></span>

   ![Диалогов прозорец за редактиране и актуализиране на ключ за достъп за съществуващ източник на данни](media/edit-access-key.png)

5. <span data-ttu-id="91202-158">По желание можете да актуализирате от връзка с ключ на акаунт към базирана на ресурси или базирана на абонамент връзка.</span><span class="sxs-lookup"><span data-stu-id="91202-158">Optionally, you can update from an account key connection to a resource-based or a subscription-based connection.</span></span> <span data-ttu-id="91202-159">За повече информация вижте [Свързване на аналитични данни за аудитория с акаунт в Azure Data Lake Storage Gen2 с принципал на услуга Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="91202-159">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="91202-160">Не можете да се промените информацията **Контейнер** при актуализиране на връзката.</span><span class="sxs-lookup"><span data-stu-id="91202-160">You can't change **Container** information when updating the connection.</span></span>
   > [!div class="mx-imgBorder"]

   > ![Диалогов прозорец за въвеждане на подробности за връзката за Azure Data Lake към съществуващ акаунт за съхранение](media/enter-existing-storage-details.png)

   > [!NOTE]
   > <span data-ttu-id="91202-162">За да можете да се свържете и да създадете източник на данни, имате нужда от една от следните роли или към контейнера, или към акаунта за съхранение:</span><span class="sxs-lookup"><span data-stu-id="91202-162">You need one of the following roles either to the container or the storage account referred above to be able to connect to and create a data source:</span></span>
   >  - <span data-ttu-id="91202-163">Четец на данни за съхранение в Blob</span><span class="sxs-lookup"><span data-stu-id="91202-163">Storage Blob Data Reader</span></span>
   >  - <span data-ttu-id="91202-164">Собственик на данни за съхранение в Blob</span><span class="sxs-lookup"><span data-stu-id="91202-164">Storage Blob Data Owner</span></span>
   >  - <span data-ttu-id="91202-165">Сътрудник за данни за BLOB за съхранение</span><span class="sxs-lookup"><span data-stu-id="91202-165">Storage Blob Data Contributo</span></span>


6. <span data-ttu-id="91202-166">По избор изберете различен файл model.json или manifest.json с различен набор от обекти от контейнера.</span><span class="sxs-lookup"><span data-stu-id="91202-166">Optionally, choose a different model.json or manifest.json file with a different set of entities from the container.</span></span>

7. <span data-ttu-id="91202-167">По желание можете да изберете допълнителни обекти за поглъщане.</span><span class="sxs-lookup"><span data-stu-id="91202-167">Optionally, you can select additional entities to ingest.</span></span> <span data-ttu-id="91202-168">Можете също да премахнете всички вече избрани обекти, ако няма зависимости.</span><span class="sxs-lookup"><span data-stu-id="91202-168">You can also remove any already selected entities if there are no dependencies.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="91202-169">Ако има зависимости от съществуващия файл model.json или manifest.json и набора от обекти, ще видите съобщение за грешка и не можете да изберете различен файл model.json или manifest.json.</span><span class="sxs-lookup"><span data-stu-id="91202-169">If there are dependencies on the existing model.json or manifest.json file and the set of entities, you'll see an error message and can't select a different model.json or manifest.json file.</span></span> <span data-ttu-id="91202-170">Премахнете тези зависимости, преди да промените файла model.json или manifest.json или създайте нов източник на данни с файла model.json или manifest.json, който искате да използвате, за да избегнете премахването на зависимостите.</span><span class="sxs-lookup"><span data-stu-id="91202-170">Remove those dependencies before changing the model.json or manifest.json file or create a new data source with the model.json or manifest.json file that you want to use to avoid removing the dependencies.</span></span>

8. <span data-ttu-id="91202-171">По желание можете да изберете допълнителни атрибути или обекти, за да активирате профилиране на данни или да деактивирате вече избрани.</span><span class="sxs-lookup"><span data-stu-id="91202-171">Optionally, you can select additional attributes or entities to enable data profiling on or disable already selected ones.</span></span>   


[!INCLUDE[footer-include](../includes/footer-banner.md)]