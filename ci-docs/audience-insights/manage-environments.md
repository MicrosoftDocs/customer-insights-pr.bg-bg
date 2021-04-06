---
title: Създаване и управление на среди
description: Научете как да се регистрирате за услугата и как да управлявате среди.
ms.date: 02/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 1c2dfdd2889b5cb6c5285b4d7cc7f52a3d6de4d1
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598280"
---
# <a name="manage-environments"></a><span data-ttu-id="bcbb4-103">Управление на среди</span><span class="sxs-lookup"><span data-stu-id="bcbb4-103">Manage environments</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="bcbb4-104">Тази статия обяснява как да създадете нова организация и как да осигурите среда.</span><span class="sxs-lookup"><span data-stu-id="bcbb4-104">This article explains how to create a new organization and how to provision an environment.</span></span>

## <a name="sign-up-and-create-an-organization"></a><span data-ttu-id="bcbb4-105">Регистрирайте се и създайте организация</span><span class="sxs-lookup"><span data-stu-id="bcbb4-105">Sign up and create an organization</span></span>

1. <span data-ttu-id="bcbb4-106">Отидете в уеб сайта [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/).</span><span class="sxs-lookup"><span data-stu-id="bcbb4-106">Go to the [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) website.</span></span>

2. <span data-ttu-id="bcbb4-107">Изберете **Първи стъпки**.</span><span class="sxs-lookup"><span data-stu-id="bcbb4-107">Select **Get Started**.</span></span>

3. <span data-ttu-id="bcbb4-108">Изберете предпочитания от вас сценарий за регистрация и изберете съответната връзка.</span><span class="sxs-lookup"><span data-stu-id="bcbb4-108">Choose your preferred sign-up scenario and select the corresponding link.</span></span>

4. <span data-ttu-id="bcbb4-109">Приемете правилата и условията и изберете **Продължаване**, за да започнете да създавате организацията.</span><span class="sxs-lookup"><span data-stu-id="bcbb4-109">Accept the terms and conditions and select **Continue** to start creating the organization.</span></span>

5. <span data-ttu-id="bcbb4-110">След създаването на средата ще бъдете пренасочени към [Customer Insights](https://home.ci.ai.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="bcbb4-110">After the environment is created, you'll be redirected to [Customer Insights](https://home.ci.ai.dynamics.com).</span></span>

6. <span data-ttu-id="bcbb4-111">Използвайте демонстрационната среда, за да проучите приложението, или създайте нова среда, като следвате стъпките в следващия раздел.</span><span class="sxs-lookup"><span data-stu-id="bcbb4-111">Use the demo environment to explore the app, or create a new environment by following the steps in the next section.</span></span>

7. <span data-ttu-id="bcbb4-112">След като укажете настройките на средата, изберете **Създаване**.</span><span class="sxs-lookup"><span data-stu-id="bcbb4-112">After specifying the environment settings, select **Create**.</span></span>

8. <span data-ttu-id="bcbb4-113">Ще влезете в системата, след като средата е създадена успешно.</span><span class="sxs-lookup"><span data-stu-id="bcbb4-113">You'll be signed in after the environment was created successfully.</span></span>

## <a name="create-an-environment-in-an-existing-organization"></a><span data-ttu-id="bcbb4-114">Създаване на среда в съществуваща организация</span><span class="sxs-lookup"><span data-stu-id="bcbb4-114">Create an environment in an existing organization</span></span>

<span data-ttu-id="bcbb4-115">Има два начина за създаване на нова среда.</span><span class="sxs-lookup"><span data-stu-id="bcbb4-115">There are two ways to create a new environment.</span></span> <span data-ttu-id="bcbb4-116">Можете да зададете изцяло нова конфигурация или да копирате някои настройки за конфигурация от съществуваща среда.</span><span class="sxs-lookup"><span data-stu-id="bcbb4-116">You can either specify an entirely new configuration, or you can copy some configuration settings from an existing environment.</span></span>

<span data-ttu-id="bcbb4-117">За да създадете среда:</span><span class="sxs-lookup"><span data-stu-id="bcbb4-117">To create an environment:</span></span>

1. <span data-ttu-id="bcbb4-118">Изберете инструмент за избор **Среда** в заглавката на приложението.</span><span class="sxs-lookup"><span data-stu-id="bcbb4-118">Select the **Environment** picker in the header of the app.</span></span>

1. <span data-ttu-id="bcbb4-119">Изберете **Нова**.</span><span class="sxs-lookup"><span data-stu-id="bcbb4-119">Select **New**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="bcbb4-120">![Настройки на среди](media/environment-settings-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="bcbb4-120">![Environment settings](media/environment-settings-dialog.png)</span></span>

1. <span data-ttu-id="bcbb4-121">В диалоговия прозорец **Създаване на нова среда** изберете **Нова среда**.</span><span class="sxs-lookup"><span data-stu-id="bcbb4-121">In the **Create new environment** dialog, select **New environment**.</span></span>

   <span data-ttu-id="bcbb4-122">Ако искате да [копирате данни от текущата среда](#additional-considerations-for-copy-configuration-preview), изберете **Копиране от съществуваща среда**.</span><span class="sxs-lookup"><span data-stu-id="bcbb4-122">If you want to [copy data from the current environment](#additional-considerations-for-copy-configuration-preview), select **Copy from existing environment**.</span></span> <span data-ttu-id="bcbb4-123">Ще видите списък на всички налични среди във вашата организация, от които можете да копирате данни.</span><span class="sxs-lookup"><span data-stu-id="bcbb4-123">You'll see a list of all available environments in your organization where you can copy data from.</span></span>

1. <span data-ttu-id="bcbb4-124">Посочете следните подробности:</span><span class="sxs-lookup"><span data-stu-id="bcbb4-124">Provide the following details:</span></span>
   - <span data-ttu-id="bcbb4-125">**Име**: Името за тази среда.</span><span class="sxs-lookup"><span data-stu-id="bcbb4-125">**Name**: The name for this environment.</span></span> <span data-ttu-id="bcbb4-126">Това поле вече е попълнено, ако сте копирали от съществуваща среда, но можете да го промените.</span><span class="sxs-lookup"><span data-stu-id="bcbb4-126">This field is already filled in if you've copied an existing environment, but you can change it.</span></span>
   - <span data-ttu-id="bcbb4-127">**Регион**: Регионът, в който е внедрена и хоствана услугата.</span><span class="sxs-lookup"><span data-stu-id="bcbb4-127">**Region**: The region into which the service is deployed and hosted.</span></span>
   - <span data-ttu-id="bcbb4-128">**Тип**: Изберете дали искате да създадете производствена среда или среда в ограничителен режим.</span><span class="sxs-lookup"><span data-stu-id="bcbb4-128">**Type**: Select whether you want to create a Production or Sandbox environment.</span></span>

2. <span data-ttu-id="bcbb4-129">Като опция можете по изберете **Разширени настройки**:</span><span class="sxs-lookup"><span data-stu-id="bcbb4-129">Optionally, you can select **Advanced settings**:</span></span>

   - <span data-ttu-id="bcbb4-130">**Запазване на всички данни в**: Посочва къде искате да съхранявате изходните данни, генерирани от Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="bcbb4-130">**Save all data to**: Specifies where you want to store the output data generated from Customer Insights.</span></span> <span data-ttu-id="bcbb4-131">Ще имате две опции: **Съхранение в Customer Insights** (Azure Data Lake, управлявано от екипа на Customer Insights) и **Azure Data Lake Storage Gen2** (собствено Azure Data Lake Storage).</span><span class="sxs-lookup"><span data-stu-id="bcbb4-131">You'll have two options: **Customer Insights storage** (an Azure Data Lake managed by the Customer Insights team) and **Azure Data Lake Storage Gen2** (your own Azure Data Lake Storage).</span></span> <span data-ttu-id="bcbb4-132">По подразбиране е избрана опцията за съхранение в Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="bcbb4-132">By default, the Customer Insights storage option is selected.</span></span>

   > [!NOTE]
   > <span data-ttu-id="bcbb4-133">Като записвате данни в Azure Data Lake Storage, вие се съгласявате, че данните ще бъдат прехвърлени и съхранени в подходящото географско местоположение за този акаунт за съхранение в Azure, което може да се различава от мястото, където се съхраняват данните в Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="bcbb4-133">By saving data to Azure Data Lake Storage, you agree that data will be transferred to and stored in the appropriate geographic location for that Azure storage account, which may differ from where data is stored in Dynamics 365 Customer Insights.</span></span> [<span data-ttu-id="bcbb4-134">Научете повече в центъра за сигурност на Microsoft.</span><span class="sxs-lookup"><span data-stu-id="bcbb4-134">Learn more at the Microsoft Trust Center.</span></span>](https://www.microsoft.com/trust-center)
   >
   > <span data-ttu-id="bcbb4-135">В момента приетите обекти винаги се съхраняват в хранилище за необработени данни, управлявано от Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="bcbb4-135">Currently, ingested entities are always stored in the Customer Insights managed data lake.</span></span>
   > <span data-ttu-id="bcbb4-136">Поддържаме само акаунти за съхранение в Azure Data Lake Gen2 от същия регион на Azure, който сте избрали при създаването на средата.</span><span class="sxs-lookup"><span data-stu-id="bcbb4-136">We support only Azure Data Lake Gen2 storage accounts from the same Azure region you selected when creating the environment.</span></span>
   > <span data-ttu-id="bcbb4-137">Поддържаме само акаунти за съхранение с активирано йерархично пространство за имена (HNS) на Azure Data Lake Gen2.</span><span class="sxs-lookup"><span data-stu-id="bcbb4-137">We support only Azure Data Lake Gen2 Hierarchical Name Space (HNS) enabled storage accounts.</span></span>

   - <span data-ttu-id="bcbb4-138">За опцията за Azure Data Lake Storage Gen2 можете да избирате между използване на опция, базирана на ресурси и опция, базирана на абонамент за удостоверяване.</span><span class="sxs-lookup"><span data-stu-id="bcbb4-138">For the Azure Data Lake Storage Gen2 option, you can choose between a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="bcbb4-139">За повече информация вижте [Свързване на аналитични данни за аудитория с акаунт в Azure Data Lake Storage Gen2 с принципал на услуга Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="bcbb4-139">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="bcbb4-140">Името **Контейнер** не може да бъде променено и ще бъде „customerinsights”.</span><span class="sxs-lookup"><span data-stu-id="bcbb4-140">The **Container** name can't be changed and will be "customerinsights".</span></span>
   
   - <span data-ttu-id="bcbb4-141">Ако искате да използвате [прогнози](predictions.md) или конфигурирайте споделянето на данни с приложения и решения въз основа на Microsoft Dataverse, предоставете Microsoft Dataverse URL на средата под **Конфигурирайте споделянето на данни с Microsoft Dataverse и да активирате допълнителни възможности**.</span><span class="sxs-lookup"><span data-stu-id="bcbb4-141">If you want to use [predictions](predictions.md) or configure data sharing with applications and solutions based on Microsoft Dataverse, provide the Microsoft Dataverse environment URL under **Configure data sharing with Microsoft Dataverse and enable additional capabilities**.</span></span> <span data-ttu-id="bcbb4-142">Изберете **Активирайте споделянето на данни** за споделяне на изходни данни на Customer Insights с управлявано от Microsoft Dataverse хранилище с данни.</span><span class="sxs-lookup"><span data-stu-id="bcbb4-142">Select **Enable data sharing** to share Customer Insights output data with a Microsoft Dataverse Managed Data Lake.</span></span>

     > [!NOTE]
     > - <span data-ttu-id="bcbb4-143">Споделяне на данни с управлявано от Microsoft Dataverse хранилище с данни не се поддържа, когато запазвате всички данни в собствения си Azure Data Lake Storage.</span><span class="sxs-lookup"><span data-stu-id="bcbb4-143">Data sharing with Microsoft Dataverse Managed Data Lake is currently not supported when you save all data to your own Azure Data Lake Storage.</span></span>
     > - <span data-ttu-id="bcbb4-144">[Прогноза на липсващи стойности в обект](predictions.md) понастоящем не се поддържа, когато активирате споделянето на данни с управлявано от Microsoft Dataverse хранилище с данни.</span><span class="sxs-lookup"><span data-stu-id="bcbb4-144">[Prediction of missing values in an entity](predictions.md) is not currently supported when you enable data sharing with Microsoft Dataverse Managed Data Lake.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="bcbb4-145">![Опции за конфигуриране, за да се даде възможност за споделяне на данни с Microsoft Dataverse](media/Datasharing-with-DataverseMDL.png)</span><span class="sxs-lookup"><span data-stu-id="bcbb4-145">![Configuration options to enable data sharing with Microsoft Dataverse](media/Datasharing-with-DataverseMDL.png)</span></span>

   <span data-ttu-id="bcbb4-146">Когато стартирате процеси, като поглъщане на данни или създаване на сегменти, в акаунта за съхранение, който сте посочили по-горе, ще бъдат създадени съответни папки.</span><span class="sxs-lookup"><span data-stu-id="bcbb4-146">When you run processes, such as data ingestion or segment creation, corresponding folders will be created in the storage account you specified above.</span></span> <span data-ttu-id="bcbb4-147">Файлове с данни и модели model.json ще бъдат създадени и добавени към съответните подпапки въз основа на процеса, който стартирате.</span><span class="sxs-lookup"><span data-stu-id="bcbb4-147">Data files and model.json files will be created and added to the respective subfolders based on the process you run.</span></span>

   <span data-ttu-id="bcbb4-148">Ако създадете множество среди на Customer Insights и изберете да запазите изходните обекти от тези среди във вашия акаунт за съхранение, ще бъдат създадени отделни папки за всяка среда с ci_<environmentid> в контейнера.</span><span class="sxs-lookup"><span data-stu-id="bcbb4-148">If you create multiple environments of Customer Insights and choose to save the output entities from those environments in your storage account, separate folders will be created for each environment with ci_<environmentid> in the container.</span></span>

### <a name="additional-considerations-for-copy-configuration-preview"></a><span data-ttu-id="bcbb4-149">Допълнителни съображения за конфигуриране на копие (предварителен преглед)</span><span class="sxs-lookup"><span data-stu-id="bcbb4-149">Additional considerations for copy configuration (preview)</span></span>

<span data-ttu-id="bcbb4-150">Следните настройки за конфигурация се копират:</span><span class="sxs-lookup"><span data-stu-id="bcbb4-150">The following configuration settings are copied:</span></span>

- <span data-ttu-id="bcbb4-151">Конфигурации на функции</span><span class="sxs-lookup"><span data-stu-id="bcbb4-151">Feature configurations</span></span>
- <span data-ttu-id="bcbb4-152">Погълнати/импортирани източници на данни</span><span class="sxs-lookup"><span data-stu-id="bcbb4-152">Ingested/imported data sources</span></span>
- <span data-ttu-id="bcbb4-153">Конфигурация за унифициране на данни (съпоставяне, съвпадение, обединяване)</span><span class="sxs-lookup"><span data-stu-id="bcbb4-153">Data unification (Map, Match, Merge) configuration</span></span>
- <span data-ttu-id="bcbb4-154">Сегменти</span><span class="sxs-lookup"><span data-stu-id="bcbb4-154">Segments</span></span>
- <span data-ttu-id="bcbb4-155">Мерки</span><span class="sxs-lookup"><span data-stu-id="bcbb4-155">Measures</span></span>
- <span data-ttu-id="bcbb4-156">Взаимоотношения</span><span class="sxs-lookup"><span data-stu-id="bcbb4-156">Relationships</span></span>
- <span data-ttu-id="bcbb4-157">Дейности</span><span class="sxs-lookup"><span data-stu-id="bcbb4-157">Activities</span></span>
- <span data-ttu-id="bcbb4-158">Индекс за търсене и филтриране</span><span class="sxs-lookup"><span data-stu-id="bcbb4-158">Search & filter Index</span></span>
- <span data-ttu-id="bcbb4-159">Експортиране на местоназначения</span><span class="sxs-lookup"><span data-stu-id="bcbb4-159">Export destinations</span></span>
- <span data-ttu-id="bcbb4-160">Планирано обновяване</span><span class="sxs-lookup"><span data-stu-id="bcbb4-160">Scheduled refresh</span></span>
- <span data-ttu-id="bcbb4-161">Допълвания</span><span class="sxs-lookup"><span data-stu-id="bcbb4-161">Enrichments</span></span>
- <span data-ttu-id="bcbb4-162">Управление на модели</span><span class="sxs-lookup"><span data-stu-id="bcbb4-162">Model management</span></span>
- <span data-ttu-id="bcbb4-163">Присвоявания на роли</span><span class="sxs-lookup"><span data-stu-id="bcbb4-163">Role assignments</span></span>

<span data-ttu-id="bcbb4-164">Следните настройки *не* се копират:</span><span class="sxs-lookup"><span data-stu-id="bcbb4-164">The following settings are *not* copied:</span></span>

- <span data-ttu-id="bcbb4-165">Профили на клиенти.</span><span class="sxs-lookup"><span data-stu-id="bcbb4-165">Customer profiles.</span></span>
- <span data-ttu-id="bcbb4-166">Идентификационни данни на източник на данни.</span><span class="sxs-lookup"><span data-stu-id="bcbb4-166">Data source credentials.</span></span> <span data-ttu-id="bcbb4-167">Ще трябва да предоставите идентификационните данни за всеки източник на данни и да обновите източниците на данни ръчно.</span><span class="sxs-lookup"><span data-stu-id="bcbb4-167">You'll have to provide the credentials for every data source and refresh the data sources manually.</span></span>
- <span data-ttu-id="bcbb4-168">Източници на данни от папката Common Data Model и управлявано от Common Data Service хранилище.</span><span class="sxs-lookup"><span data-stu-id="bcbb4-168">Data sources from Common Data Model folder and Common Data Service managed lake.</span></span> <span data-ttu-id="bcbb4-169">Ще трябва да създадете тези източници на данни ръчно със същото име като в средата източник.</span><span class="sxs-lookup"><span data-stu-id="bcbb4-169">You'll have to create those data sources manually with the same name as in the source environment.</span></span>

<span data-ttu-id="bcbb4-170">Когато копирате среда, ще видите съобщение за потвърждение, че новата среда е създадена.</span><span class="sxs-lookup"><span data-stu-id="bcbb4-170">When you copy an environment, you'll see a confirmation message that the new environment has been created.</span></span> <span data-ttu-id="bcbb4-171">Изберете **Към източници на данни**, за да видите списъка с източници на данни.</span><span class="sxs-lookup"><span data-stu-id="bcbb4-171">Select **Go to data sources** to see the list of data sources.</span></span>

<span data-ttu-id="bcbb4-172">Всички източници на данни ще показват състояние **Изискват се идентификационни данни**.</span><span class="sxs-lookup"><span data-stu-id="bcbb4-172">All the data sources will show a **Credentials Required** status.</span></span> <span data-ttu-id="bcbb4-173">Редактирайте източниците на данни и въведете идентификационните данни, за да ги опресните.</span><span class="sxs-lookup"><span data-stu-id="bcbb4-173">Edit the data sources and enter the credentials to refresh them.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="bcbb4-174">![Копирани източници на данни](media/data-sources-copied.png)</span><span class="sxs-lookup"><span data-stu-id="bcbb4-174">![Data sources copied](media/data-sources-copied.png)</span></span>

<span data-ttu-id="bcbb4-175">След обновяване на източниците на данни отидете в **Данни** > **Обединяване**.</span><span class="sxs-lookup"><span data-stu-id="bcbb4-175">After refreshing the data sources, go to **Data** > **Unify**.</span></span> <span data-ttu-id="bcbb4-176">Тук ще намерите настройки от средата източник.</span><span class="sxs-lookup"><span data-stu-id="bcbb4-176">Here you'll find settings from the source environment.</span></span> <span data-ttu-id="bcbb4-177">Редактирайте ги според нуждите или изберете **Изпълнение** за стартиране на процеса на обединяване на данни и създаване на обекта на обединен клиент.</span><span class="sxs-lookup"><span data-stu-id="bcbb4-177">Edit them as needed or select **Run** to start the data unification process and create the unified customer entity.</span></span>

<span data-ttu-id="bcbb4-178">Когато обединението на данните приключи, отидете на **Мерки** и **Сегменти**, за да освежите и тях.</span><span class="sxs-lookup"><span data-stu-id="bcbb4-178">When the data unification is complete, go to **Measures** and **Segments** to refresh them too.</span></span>

## <a name="edit-an-existing-environment"></a><span data-ttu-id="bcbb4-179">Редактиране на съществуваща среда</span><span class="sxs-lookup"><span data-stu-id="bcbb4-179">Edit an existing environment</span></span>

<span data-ttu-id="bcbb4-180">Можете да редактирате някои подробности на съществуващите среди.</span><span class="sxs-lookup"><span data-stu-id="bcbb4-180">You can edit some of the details of existing environments.</span></span>

1.  <span data-ttu-id="bcbb4-181">Изберете инструмент за избор **Среда** в заглавката на приложението.</span><span class="sxs-lookup"><span data-stu-id="bcbb4-181">Select the **Environment** picker in the header of the app.</span></span>

2.  <span data-ttu-id="bcbb4-182">Изберете иконата за **редактиране**.</span><span class="sxs-lookup"><span data-stu-id="bcbb4-182">Select the **Edit** icon.</span></span>

3. <span data-ttu-id="bcbb4-183">В полето **Редактиране на средата** можете да актуализирате средата **Показвано име**, но не можете да промените **Регион** или **Тип**.</span><span class="sxs-lookup"><span data-stu-id="bcbb4-183">In the **Edit environment** box, you can update the environment's **Display name**, but you can't change the **Region** or **Type**.</span></span>

4. <span data-ttu-id="bcbb4-184">Ако е конфигурирана среда за съхраняване на данни в Azure Data Lake Storage Gen2, можете да актуализирате **ключа за акаунта**.</span><span class="sxs-lookup"><span data-stu-id="bcbb4-184">If an environment is configured to store data in Azure Data Lake Storage Gen2, you can update the **Account key**.</span></span> <span data-ttu-id="bcbb4-185">Не можете обаче да промените **Име на акаунта** или име на **Контейнер**.</span><span class="sxs-lookup"><span data-stu-id="bcbb4-185">However, you can't change the **Account name** or **Container** name.</span></span>

5. <span data-ttu-id="bcbb4-186">По желание можете да актуализирате от базирана на връзка с ключ на акаунт към базирана на ресурси или базирана на абонамент връзка.</span><span class="sxs-lookup"><span data-stu-id="bcbb4-186">Optionally, you can update from an account key based connection to a resource-based or subscription-based connection.</span></span> <span data-ttu-id="bcbb4-187">След като бъдете надстроени, не можете да се върнете към ключа на акаунта след актуализацията.</span><span class="sxs-lookup"><span data-stu-id="bcbb4-187">Once upgraded, you cannot revert to account key after the update.</span></span> <span data-ttu-id="bcbb4-188">За повече информация вижте [Свързване на аналитични данни за аудитория с акаунт в Azure Data Lake Storage Gen2 с принципал на услуга Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="bcbb4-188">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="bcbb4-189">Не можете да се промените информацията **Контейнер** при актуализиране на връзката.</span><span class="sxs-lookup"><span data-stu-id="bcbb4-189">You can't change **Container** information when updating the connection.</span></span>

## <a name="reset-an-existing-environment"></a><span data-ttu-id="bcbb4-190">Нулиране на съществуваща среда</span><span class="sxs-lookup"><span data-stu-id="bcbb4-190">Reset an existing environment</span></span>

<span data-ttu-id="bcbb4-191">Като администратор можете да нулирате средата в празно състояние, ако искате да изтриете всички конфигурации и да премахнете погълнатите данни.</span><span class="sxs-lookup"><span data-stu-id="bcbb4-191">As an administrator, you can reset an environment to an empty state if you want to delete all configurations and remove the ingested data.</span></span>

1.  <span data-ttu-id="bcbb4-192">Изберете инструмент за избор **Среда** в заглавката на приложението.</span><span class="sxs-lookup"><span data-stu-id="bcbb4-192">Select the **Environment** picker in the header of the app.</span></span> 

2.  <span data-ttu-id="bcbb4-193">Изберете средата, която искате да нулирате, и изберете многоточието **...**.</span><span class="sxs-lookup"><span data-stu-id="bcbb4-193">Select the environment you want to reset and select the ellipsis **...**.</span></span> 

3. <span data-ttu-id="bcbb4-194">Изберете опцията **Нулиране**.</span><span class="sxs-lookup"><span data-stu-id="bcbb4-194">Choose the **Reset** option.</span></span> 

4.  <span data-ttu-id="bcbb4-195">За да потвърдите изтриването, въведете името на средата и изберете **Нулиране**.</span><span class="sxs-lookup"><span data-stu-id="bcbb4-195">To confirm the deletion, enter the environment name and select **Reset**.</span></span>

## <a name="delete-an-existing-environment-available-only-for-admins"></a><span data-ttu-id="bcbb4-196">Изтриване на съществуваща среда (достъпна само за администратори)</span><span class="sxs-lookup"><span data-stu-id="bcbb4-196">Delete an existing environment (available only for admins)</span></span>

<span data-ttu-id="bcbb4-197">Като администратор можете да изтриете среда, която администрирате.</span><span class="sxs-lookup"><span data-stu-id="bcbb4-197">As an administrator, you can delete an environment you administer.</span></span>

1.  <span data-ttu-id="bcbb4-198">Изберете инструмент за избор **Среда** в заглавката на приложението.</span><span class="sxs-lookup"><span data-stu-id="bcbb4-198">Select the **Environment** picker in the header of the app.</span></span>

2.  <span data-ttu-id="bcbb4-199">Изберете средата, която искате да нулирате, и изберете многоточието **...**.</span><span class="sxs-lookup"><span data-stu-id="bcbb4-199">Select the environment you want to reset and select the ellipsis **...**.</span></span> 

3. <span data-ttu-id="bcbb4-200">Изберете опцията **Изтриване**.</span><span class="sxs-lookup"><span data-stu-id="bcbb4-200">Choose the **Delete** option.</span></span> 

4.  <span data-ttu-id="bcbb4-201">За да потвърдите изтриването, въведете името на средата и изберете **Изтриване**.</span><span class="sxs-lookup"><span data-stu-id="bcbb4-201">To confirm the deletion, enter the environment name and select **Delete**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]