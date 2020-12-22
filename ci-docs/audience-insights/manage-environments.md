---
title: Създаване и управление на среди
description: Научете как да се регистрирате за услугата и как да управлявате среди.
ms.date: 11/10/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
ms.reviewer: nimagen
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 010336445d0825a7ff82d1b7a65702fc12245788
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644120"
---
# <a name="manage-environments"></a><span data-ttu-id="5e82d-103">Управление на среди</span><span class="sxs-lookup"><span data-stu-id="5e82d-103">Manage environments</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="5e82d-104">Тази статия обяснява как да създадете нова организация и как да осигурите среда.</span><span class="sxs-lookup"><span data-stu-id="5e82d-104">This article explains how to create a new organization and how to provision an environment.</span></span>

## <a name="sign-up-and-create-an-organization"></a><span data-ttu-id="5e82d-105">Регистрирайте се и създайте организация</span><span class="sxs-lookup"><span data-stu-id="5e82d-105">Sign up and create an organization</span></span>

1. <span data-ttu-id="5e82d-106">Отидете в уеб сайта [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/).</span><span class="sxs-lookup"><span data-stu-id="5e82d-106">Go to the [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) website.</span></span>

2. <span data-ttu-id="5e82d-107">Изберете **Първи стъпки**.</span><span class="sxs-lookup"><span data-stu-id="5e82d-107">Select **Get Started**.</span></span>

3. <span data-ttu-id="5e82d-108">Изберете предпочитания от вас сценарий за регистрация и изберете съответната връзка.</span><span class="sxs-lookup"><span data-stu-id="5e82d-108">Choose your preferred sign-up scenario and select the corresponding link.</span></span>

4. <span data-ttu-id="5e82d-109">Приемете правилата и условията и изберете **Продължаване**, за да започнете да създавате организацията.</span><span class="sxs-lookup"><span data-stu-id="5e82d-109">Accept the terms and conditions and select **Continue** to start creating the organization.</span></span>

5. <span data-ttu-id="5e82d-110">След създаването на средата ще бъдете пренасочени към [Customer Insights](https://home.ci.ai.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="5e82d-110">After the environment is created, you'll be redirected to [Customer Insights](https://home.ci.ai.dynamics.com).</span></span>

6. <span data-ttu-id="5e82d-111">Използвайте демонстрационната среда, за да проучите приложението, или създайте нова среда, като следвате стъпките в следващия раздел.</span><span class="sxs-lookup"><span data-stu-id="5e82d-111">Use the demo environment to explore the app, or create a new environment by following the steps in the next section.</span></span>

7. <span data-ttu-id="5e82d-112">След като укажете настройките на средата, изберете **Създаване**.</span><span class="sxs-lookup"><span data-stu-id="5e82d-112">After specifying the environment settings, select **Create**.</span></span>

8. <span data-ttu-id="5e82d-113">Ще влезете в системата, след като средата е създадена успешно.</span><span class="sxs-lookup"><span data-stu-id="5e82d-113">You'll be signed in after the environment was created successfully.</span></span>

## <a name="create-an-environment-in-an-existing-organization"></a><span data-ttu-id="5e82d-114">Създаване на среда в съществуваща организация</span><span class="sxs-lookup"><span data-stu-id="5e82d-114">Create an environment in an existing organization</span></span>

<span data-ttu-id="5e82d-115">Има два начина за създаване на нова среда.</span><span class="sxs-lookup"><span data-stu-id="5e82d-115">There are two ways to create a new environment.</span></span> <span data-ttu-id="5e82d-116">Можете да зададете изцяло нова конфигурация или да копирате някои настройки за конфигурация от съществуваща среда.</span><span class="sxs-lookup"><span data-stu-id="5e82d-116">You can either specify an entirely new configuration, or you can copy some configuration settings from an existing environment.</span></span>

<span data-ttu-id="5e82d-117">За да създадете среда:</span><span class="sxs-lookup"><span data-stu-id="5e82d-117">To create an environment:</span></span>

1. <span data-ttu-id="5e82d-118">Изберете символа **Настройки** в заглавката на приложението.</span><span class="sxs-lookup"><span data-stu-id="5e82d-118">Select the **Settings** symbol in the header of the app.</span></span>

1. <span data-ttu-id="5e82d-119">Изберете **Нова среда**.</span><span class="sxs-lookup"><span data-stu-id="5e82d-119">Select **New environment**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="5e82d-120">![Настройки на среди](media/environment-settings-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="5e82d-120">![Environment settings](media/environment-settings-dialog.png)</span></span>

1. <span data-ttu-id="5e82d-121">В диалоговия прозорец **Създаване на нова среда** изберете **Нова среда**.</span><span class="sxs-lookup"><span data-stu-id="5e82d-121">In the **Create new environment** dialog, select **New environment**.</span></span>

   <span data-ttu-id="5e82d-122">Ако искате да [копирате данни от текущата среда](#additional-considerations-for-copy-configuration-preview), изберете **Копиране от съществуваща среда**.</span><span class="sxs-lookup"><span data-stu-id="5e82d-122">If you want to [copy data from the current environment](#additional-considerations-for-copy-configuration-preview), select **Copy from existing environment**.</span></span> <span data-ttu-id="5e82d-123">Ще видите списък на всички налични среди във вашата организация, от които можете да копирате данни.</span><span class="sxs-lookup"><span data-stu-id="5e82d-123">You'll see a list of all available environments in your organization where you can copy data from.</span></span>

1. <span data-ttu-id="5e82d-124">Посочете следните подробности:</span><span class="sxs-lookup"><span data-stu-id="5e82d-124">Provide the following details:</span></span>
   - <span data-ttu-id="5e82d-125">**Име**: Името за тази среда.</span><span class="sxs-lookup"><span data-stu-id="5e82d-125">**Name**: The name for this environment.</span></span> <span data-ttu-id="5e82d-126">Това поле вече е попълнено, ако сте копирали от съществуваща среда, но можете да го промените.</span><span class="sxs-lookup"><span data-stu-id="5e82d-126">This field is already filled in if you've copied an existing environment, but you can change it.</span></span>
   - <span data-ttu-id="5e82d-127">**Регион**: Регионът, в който е внедрена и хоствана услугата.</span><span class="sxs-lookup"><span data-stu-id="5e82d-127">**Region**: The region into which the service is deployed and hosted.</span></span>
   - <span data-ttu-id="5e82d-128">**Тип**: Изберете дали искате да създадете производствена среда или среда в ограничителен режим.</span><span class="sxs-lookup"><span data-stu-id="5e82d-128">**Type**: Select whether you want to create a Production or Sandbox environment.</span></span>

2. <span data-ttu-id="5e82d-129">Като опция можете по изберете **Разширени настройки**:</span><span class="sxs-lookup"><span data-stu-id="5e82d-129">Optionally, you can select **Advanced settings**:</span></span>

   - <span data-ttu-id="5e82d-130">**Запазване на всички данни в**: Посочва къде искате да съхранявате изходните данни, генерирани от Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="5e82d-130">**Save all data to**: Specifies where you want to store the output data generated from Customer Insights.</span></span> <span data-ttu-id="5e82d-131">Ще имате две опции: **Съхранение в Customer Insights** (Azure Data Lake, управлявано от екипа на Customer Insights) и **Azure Data Lake Storage Gen2** (собствено Azure Data Lake Storage).</span><span class="sxs-lookup"><span data-stu-id="5e82d-131">You'll have two options: **Customer Insights storage** (an Azure Data Lake managed by the Customer Insights team) and **Azure Data Lake Storage Gen2** (your own Azure Data Lake Storage).</span></span> <span data-ttu-id="5e82d-132">По подразбиране е избрана опцията за съхранение в Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="5e82d-132">By default, the Customer Insights storage option is selected.</span></span>

   > [!NOTE]
   > <span data-ttu-id="5e82d-133">Като записвате данни в Azure Data Lake Storage, вие се съгласявате, че данните ще бъдат прехвърлени и съхранени в подходящото географско местоположение за този акаунт за съхранение в Azure, което може да се различава от мястото, където се съхраняват данните в Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="5e82d-133">By saving data to Azure Data Lake Storage, you agree that data will be transferred to and stored in the appropriate geographic location for that Azure storage account, which may differ from where data is stored in Dynamics 365 Customer Insights.</span></span> [<span data-ttu-id="5e82d-134">Научете повече в центъра за сигурност на Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5e82d-134">Learn more at the Microsoft Trust Center.</span></span>](https://www.microsoft.com/trust-center)
   >
   > <span data-ttu-id="5e82d-135">В момента приетите обекти винаги се съхраняват в хранилище за необработени данни, управлявано от Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="5e82d-135">Currently, ingested entities are always stored in the Customer Insights managed data lake.</span></span>
   > <span data-ttu-id="5e82d-136">Поддържаме само акаунти за съхранение в Azure Data Lake Gen2 от същия регион на Azure, който сте избрали при създаването на средата.</span><span class="sxs-lookup"><span data-stu-id="5e82d-136">We support only Azure Data Lake Gen2 storage accounts from the same Azure region you selected when creating the environment.</span></span>
   > <span data-ttu-id="5e82d-137">Поддържаме само акаунти за съхранение с активирано йерархично пространство за имена (HNS) на Azure Data Lake Gen2.</span><span class="sxs-lookup"><span data-stu-id="5e82d-137">We support only Azure Data Lake Gen2 Hierarchical Name Space (HNS) enabled storage accounts.</span></span>

   - <span data-ttu-id="5e82d-138">За опцията за Azure Data Lake Storage Gen2 можете да избирате между използване на опция, базирана на ресурси и опция, базирана на абонамент за удостоверяване.</span><span class="sxs-lookup"><span data-stu-id="5e82d-138">For the Azure Data Lake Storage Gen2 option, you can choose between a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="5e82d-139">За повече информация вижте [Свързване на аналитични данни за аудитория с акаунт в Azure Data Lake Storage Gen2 с принципал на услуга Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="5e82d-139">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="5e82d-140">Името **Контейнер** не може да бъде променено и ще бъде „customerinsights”.</span><span class="sxs-lookup"><span data-stu-id="5e82d-140">The **Container** name can't be changed and will be "customerinsights".</span></span>
   
   - <span data-ttu-id="5e82d-141">Ако искате да използвате [прогнози](predictions.md), влезте в URL адреса на екземпляра на Common Data Service в полето **Адрес на сървъра** под **Използвайте прогнози**.</span><span class="sxs-lookup"><span data-stu-id="5e82d-141">If you want to use [predictions](predictions.md), enter the Common Data Service instance URL in the **Server address** field under **Use predictions**.</span></span>

   <span data-ttu-id="5e82d-142">Когато стартирате процеси, като поглъщане на данни или създаване на сегменти, в акаунта за съхранение, който сте посочили по-горе, ще бъдат създадени съответни папки.</span><span class="sxs-lookup"><span data-stu-id="5e82d-142">When you run processes, such as data ingestion or segment creation, corresponding folders will be created in the storage account you specified above.</span></span> <span data-ttu-id="5e82d-143">Файлове с данни и модели model.json ще бъдат създадени и добавени към съответните подпапки въз основа на процеса, който стартирате.</span><span class="sxs-lookup"><span data-stu-id="5e82d-143">Data files and model.json files will be created and added to the respective subfolders based on the process you run.</span></span>

   <span data-ttu-id="5e82d-144">Ако създадете множество среди на Customer Insights и изберете да запазите изходните обекти от тези среди във вашия акаунт за съхранение, ще бъдат създадени отделни папки за всяка среда с ci_<environmentid> в контейнера.</span><span class="sxs-lookup"><span data-stu-id="5e82d-144">If you create multiple environments of Customer Insights and choose to save the output entities from those environments in your storage account, separate folders will be created for each environment with ci_<environmentid> in the container.</span></span>

### <a name="additional-considerations-for-copy-configuration-preview"></a><span data-ttu-id="5e82d-145">Допълнителни съображения за конфигуриране на копие (предварителен преглед)</span><span class="sxs-lookup"><span data-stu-id="5e82d-145">Additional considerations for copy configuration (preview)</span></span>

<span data-ttu-id="5e82d-146">Следните настройки за конфигурация се копират:</span><span class="sxs-lookup"><span data-stu-id="5e82d-146">The following configuration settings are copied:</span></span>

- <span data-ttu-id="5e82d-147">Конфигурации на функции</span><span class="sxs-lookup"><span data-stu-id="5e82d-147">Feature configurations</span></span>
- <span data-ttu-id="5e82d-148">Приети/импортирани източници на данни</span><span class="sxs-lookup"><span data-stu-id="5e82d-148">Inegsted/imported data sources</span></span>
- <span data-ttu-id="5e82d-149">Конфигурация за унифициране на данни (съпоставяне, съвпадение, обединяване)</span><span class="sxs-lookup"><span data-stu-id="5e82d-149">Data unification (Map, Match, Merge) configuration</span></span>
- <span data-ttu-id="5e82d-150">Сегменти</span><span class="sxs-lookup"><span data-stu-id="5e82d-150">Segments</span></span>
- <span data-ttu-id="5e82d-151">Мерки</span><span class="sxs-lookup"><span data-stu-id="5e82d-151">Measures</span></span>
- <span data-ttu-id="5e82d-152">Взаимоотношения</span><span class="sxs-lookup"><span data-stu-id="5e82d-152">Relationships</span></span>
- <span data-ttu-id="5e82d-153">Дейности</span><span class="sxs-lookup"><span data-stu-id="5e82d-153">Activities</span></span>
- <span data-ttu-id="5e82d-154">Индекс за търсене и филтриране</span><span class="sxs-lookup"><span data-stu-id="5e82d-154">Search & filter Index</span></span>
- <span data-ttu-id="5e82d-155">Експортиране на местоназначения</span><span class="sxs-lookup"><span data-stu-id="5e82d-155">Export destinations</span></span>
- <span data-ttu-id="5e82d-156">Планирано обновяване</span><span class="sxs-lookup"><span data-stu-id="5e82d-156">Scheduled refresh</span></span>
- <span data-ttu-id="5e82d-157">Допълвания</span><span class="sxs-lookup"><span data-stu-id="5e82d-157">Enrichments</span></span>
- <span data-ttu-id="5e82d-158">Управление на модели</span><span class="sxs-lookup"><span data-stu-id="5e82d-158">Model management</span></span>
- <span data-ttu-id="5e82d-159">Присвоявания на роли</span><span class="sxs-lookup"><span data-stu-id="5e82d-159">Role assignments</span></span>

<span data-ttu-id="5e82d-160">Следните настройки *не* се копират:</span><span class="sxs-lookup"><span data-stu-id="5e82d-160">The following settings are *not* copied:</span></span>

- <span data-ttu-id="5e82d-161">Профили на клиенти.</span><span class="sxs-lookup"><span data-stu-id="5e82d-161">Customer profiles.</span></span>
- <span data-ttu-id="5e82d-162">Идентификационни данни на източник на данни.</span><span class="sxs-lookup"><span data-stu-id="5e82d-162">Data source credentials.</span></span> <span data-ttu-id="5e82d-163">Ще трябва да предоставите идентификационните данни за всеки източник на данни и да обновите източниците на данни ръчно.</span><span class="sxs-lookup"><span data-stu-id="5e82d-163">You'll have to provide the credentials for every data source and refresh the data sources manually.</span></span>
- <span data-ttu-id="5e82d-164">Източници на данни от папката Common Data Model и управлявано от Common Data Service хранилище.</span><span class="sxs-lookup"><span data-stu-id="5e82d-164">Data sources from Common Data Model folder and Common Data Service managed lake.</span></span> <span data-ttu-id="5e82d-165">Ще трябва да създадете тези източници на данни ръчно със същото име като в средата източник.</span><span class="sxs-lookup"><span data-stu-id="5e82d-165">You'll have to create those data sources manually with the same name as in the source environment.</span></span>

<span data-ttu-id="5e82d-166">Когато копирате среда, ще видите съобщение за потвърждение, че новата среда е създадена.</span><span class="sxs-lookup"><span data-stu-id="5e82d-166">When you copy an environment, you'll see a confirmation message that the new environment has been created.</span></span> <span data-ttu-id="5e82d-167">Изберете **Към източници на данни**, за да видите списъка с източници на данни.</span><span class="sxs-lookup"><span data-stu-id="5e82d-167">Select **Go to data sources** to see the list of data sources.</span></span>

<span data-ttu-id="5e82d-168">Всички източници на данни ще показват състояние **Изискват се идентификационни данни**.</span><span class="sxs-lookup"><span data-stu-id="5e82d-168">All the data sources will show a **Credentials Required** status.</span></span> <span data-ttu-id="5e82d-169">Редактирайте източниците на данни и въведете идентификационните данни, за да ги опресните.</span><span class="sxs-lookup"><span data-stu-id="5e82d-169">Edit the data sources and enter the credentials to refresh them.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="5e82d-170">![Копирани източници на данни](media/data-sources-copied.png)</span><span class="sxs-lookup"><span data-stu-id="5e82d-170">![Data sources copied](media/data-sources-copied.png)</span></span>

<span data-ttu-id="5e82d-171">След обновяване на източниците на данни отидете в **Данни** > **Обединяване**.</span><span class="sxs-lookup"><span data-stu-id="5e82d-171">After refreshing the data sources, go to **Data** > **Unify**.</span></span> <span data-ttu-id="5e82d-172">Тук ще намерите настройки от средата източник.</span><span class="sxs-lookup"><span data-stu-id="5e82d-172">Here you'll find settings from the source environment.</span></span> <span data-ttu-id="5e82d-173">Редактирайте ги според нуждите или изберете **Изпълнение** за стартиране на процеса на обединяване на данни и създаване на обекта на обединен клиент.</span><span class="sxs-lookup"><span data-stu-id="5e82d-173">Edit them as needed or select **Run** to start the data unification process and create the unified customer entity.</span></span>

<span data-ttu-id="5e82d-174">Когато обединението на данните приключи, отидете на **Мерки** и **Сегменти**, за да освежите и тях.</span><span class="sxs-lookup"><span data-stu-id="5e82d-174">When the data unification is complete, go to **Measures** and **Segments** to refresh them too.</span></span>

## <a name="edit-an-existing-environment"></a><span data-ttu-id="5e82d-175">Редактиране на съществуваща среда</span><span class="sxs-lookup"><span data-stu-id="5e82d-175">Edit an existing environment</span></span>

<span data-ttu-id="5e82d-176">Можете да редактирате някои подробности на съществуващите среди.</span><span class="sxs-lookup"><span data-stu-id="5e82d-176">You can edit some of the details of existing environments.</span></span>

1. <span data-ttu-id="5e82d-177">Отидете на **Администратор** > **Система** > **Относно**.</span><span class="sxs-lookup"><span data-stu-id="5e82d-177">Go to **Admin** > **System** > **About**.</span></span>

2. <span data-ttu-id="5e82d-178">Изберете **Редактиране**.</span><span class="sxs-lookup"><span data-stu-id="5e82d-178">Select **Edit**.</span></span>

3. <span data-ttu-id="5e82d-179">Можете да актуализирате **Показвано име** на средата, но не можете да промените **Регион** или **Тип**.</span><span class="sxs-lookup"><span data-stu-id="5e82d-179">You can update the environment's **Display name**, but you can't change the **Region** or **Type**.</span></span>

4. <span data-ttu-id="5e82d-180">Ако е конфигурирана среда за съхраняване на данни в Azure Data Lake Storage Gen2, можете да актуализирате **ключа за акаунта**.</span><span class="sxs-lookup"><span data-stu-id="5e82d-180">If an environment is configured to store data in Azure Data Lake Storage Gen2, you can update the **Account key**.</span></span> <span data-ttu-id="5e82d-181">Не можете обаче да промените **Име на акаунта** или име на **Контейнер**.</span><span class="sxs-lookup"><span data-stu-id="5e82d-181">However, you can't change the **Account name** or **Container** name.</span></span>

5. <span data-ttu-id="5e82d-182">По желание можете да актуализирате от базирана на връзка с ключ на акаунт към базирана на ресурси или базирана на абонамент връзка.</span><span class="sxs-lookup"><span data-stu-id="5e82d-182">Optionally, you can update from an account key based connection to a resource-based or subscription-based connection.</span></span> <span data-ttu-id="5e82d-183">След като бъдете надстроени, не можете да се върнете към ключа на акаунта след актуализацията.</span><span class="sxs-lookup"><span data-stu-id="5e82d-183">Once upgraded, you cannot revert to account key after the update.</span></span> <span data-ttu-id="5e82d-184">За повече информация вижте [Свързване на аналитични данни за аудитория с акаунт в Azure Data Lake Storage Gen2 с принципал на услуга Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="5e82d-184">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="5e82d-185">Не можете да се промените информацията **Контейнер** при актуализиране на връзката.</span><span class="sxs-lookup"><span data-stu-id="5e82d-185">You can't change **Container** information when updating the connection.</span></span>

## <a name="reset-an-existing-environment"></a><span data-ttu-id="5e82d-186">Нулиране на съществуваща среда</span><span class="sxs-lookup"><span data-stu-id="5e82d-186">Reset an existing environment</span></span>

<span data-ttu-id="5e82d-187">Можете да нулирате средата в празно състояние, ако искате да изтриете всички конфигурации и да премахнете погълнатите данни.</span><span class="sxs-lookup"><span data-stu-id="5e82d-187">You can reset an environment to an empty state if you want to delete all configurations and remove the ingested data.</span></span>

1.  <span data-ttu-id="5e82d-188">Отидете на **Администратор** > **Система** > **Относно**.</span><span class="sxs-lookup"><span data-stu-id="5e82d-188">Go to **Admin** > **System** > **About**.</span></span>

2.  <span data-ttu-id="5e82d-189">Избор на **нулиране**.</span><span class="sxs-lookup"><span data-stu-id="5e82d-189">Select **Reset**.</span></span> 

3.  <span data-ttu-id="5e82d-190">За да потвърдите изтриването, въведете името на средата и изберете **Нулиране**.</span><span class="sxs-lookup"><span data-stu-id="5e82d-190">To confirm the deletion, enter the environment name and select **Reset**.</span></span>


## <a name="delete-an-existing-environment"></a><span data-ttu-id="5e82d-191">Изтрийте съществуваща среда</span><span class="sxs-lookup"><span data-stu-id="5e82d-191">Delete an existing environment</span></span>

1. <span data-ttu-id="5e82d-192">Отидете на **Администратор** > **Система** > **Относно**.</span><span class="sxs-lookup"><span data-stu-id="5e82d-192">Go to **Admin** > **System** > **About**.</span></span>

1. <span data-ttu-id="5e82d-193">Изберете **Изтриване**.</span><span class="sxs-lookup"><span data-stu-id="5e82d-193">Select **Delete**.</span></span>

1. <span data-ttu-id="5e82d-194">За да потвърдите изтриването, въведете името на средата и изберете **Изтриване**.</span><span class="sxs-lookup"><span data-stu-id="5e82d-194">To confirm the deletion, enter the environment name and select **Delete**.</span></span>
