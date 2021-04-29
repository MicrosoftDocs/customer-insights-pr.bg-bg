---
title: Обогатяване с SFTP персонализирано импортиране
description: Обща информация за обогатяването на SFTP персонализирано импортиране.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: a2d450635c19432bdd88db74b61c17febdeb568d
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896268"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="c3a04-103">Обогатете потребителските профили с персонализирани данни (преглед)</span><span class="sxs-lookup"><span data-stu-id="c3a04-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="c3a04-104">Персонализираното импортиране на защитения протокол за предаване на файлове (SFTP) ви позволява да импортирате данни, които не трябва да преминават през процеса на обединяване на данни.</span><span class="sxs-lookup"><span data-stu-id="c3a04-104">Secure File Transfer Protocol (SFTP) custom import enables you to import data that does not have to go through the process of data unification.</span></span> <span data-ttu-id="c3a04-105">Това е гъвкав, сигурен и лесен начин за въвеждане на вашите данни.</span><span class="sxs-lookup"><span data-stu-id="c3a04-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="c3a04-106">SFTP потребителски импорт може да се използва в комбинация с [SFTP експортиране](export-sftp.md), което ви позволява да експортирате данни за потребителския профил, необходими за обогатяване.</span><span class="sxs-lookup"><span data-stu-id="c3a04-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="c3a04-107">След това данните могат да бъдат обработени, обогатени и SFTP потребителски импорт може да се използва, за да върне обогатените данни обратно на способността за прозрение на аудиторията на Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="c3a04-107">The data can then be processed, enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c3a04-108">Предварителни изисквания</span><span class="sxs-lookup"><span data-stu-id="c3a04-108">Prerequisites</span></span>

<span data-ttu-id="c3a04-109">За да конфигурирате SFTP персонализирано импортиране, трябва да са изпълнени следните предпоставки:</span><span class="sxs-lookup"><span data-stu-id="c3a04-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="c3a04-110">Имате името на файла и местоположението (пътя) на файла, които ще се импортират на SFTP хоста.</span><span class="sxs-lookup"><span data-stu-id="c3a04-110">You have the filename and location (path) of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="c3a04-111">Има файл *model.json*, който указва [схемата на Common Data Model](/common-data-model/) за импортиране на данните.</span><span class="sxs-lookup"><span data-stu-id="c3a04-111">There is a *model.json* file that specifies [the Common Data Model schema](/common-data-model/) for the data to be imported.</span></span> <span data-ttu-id="c3a04-112">Този файл трябва да е в същата директория като файла за импортиране.</span><span class="sxs-lookup"><span data-stu-id="c3a04-112">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="c3a04-113">SFTP връзката вече е конфигурирана от администратор *или* вие имате разрешения на [администратор](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="c3a04-113">An SFTP connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="c3a04-114">Ще ви трябват потребителски идентификационни данни, URL адрес и номер на порт за SFTP местоположението, от което искате да импортирате данни.</span><span class="sxs-lookup"><span data-stu-id="c3a04-114">You'll need the user credentials, URL, and port number for the SFTP location where you want to import data from.</span></span>


## <a name="configure-the-import"></a><span data-ttu-id="c3a04-115">Конфигуриране на импортиране</span><span class="sxs-lookup"><span data-stu-id="c3a04-115">Configure the import</span></span>

1. <span data-ttu-id="c3a04-116">Отидете в раздела **Данни** > **Допълване** и изберете раздела **Откриване**.</span><span class="sxs-lookup"><span data-stu-id="c3a04-116">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="c3a04-117">На **плочка за персонализирано импортиране чрез SFTP** изберете **Допълване на моите данни** и след това изберете **Начало**.</span><span class="sxs-lookup"><span data-stu-id="c3a04-117">On the **SFTP custom import tile**, select **Enrich my data** and then select **Get started**.</span></span>

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="Плочка за персонализирано импортиране чрез SFTP.":::

1. <span data-ttu-id="c3a04-119">Изберете [връзка](connections.md) от падащия списък.</span><span class="sxs-lookup"><span data-stu-id="c3a04-119">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="c3a04-120">Свържете се с администратор, ако няма налична връзка.</span><span class="sxs-lookup"><span data-stu-id="c3a04-120">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="c3a04-121">Ако сте администратор, може да създадете връзка, като изберете **Добавяне на връзка** и изберете **Персонализирано импортиране чрез SFTP** от падащото меню.</span><span class="sxs-lookup"><span data-stu-id="c3a04-121">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **SFTP Custom Import** from the drop-down.</span></span>

1. <span data-ttu-id="c3a04-122">Изберете **Свързване с персонализирано импортиране**, за да потвърдите избраната връзка.</span><span class="sxs-lookup"><span data-stu-id="c3a04-122">Select **Connect to Custom Import** to confirm the selected connection.</span></span>

1.  <span data-ttu-id="c3a04-123">Изберете **Напред** и въведете **името на файла** и **пътя** на файла с данни, който искате да импортирате.</span><span class="sxs-lookup"><span data-stu-id="c3a04-123">Select **Next** and enter the **Filename** and **Path** of the data file that you want to import.</span></span>

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="Екранна снимка при въвеждане на местоположение на данни.":::

1. <span data-ttu-id="c3a04-125">Изберете **Напред** и предоставете име за допълването и име за изходния обект.</span><span class="sxs-lookup"><span data-stu-id="c3a04-125">Select **Next** and provide a name for the enrichment and a name for the output entity.</span></span> 

1. <span data-ttu-id="c3a04-126">Изберете **Записване на допълването**, след като прегледате избора си.</span><span class="sxs-lookup"><span data-stu-id="c3a04-126">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-sftp-custom-import"></a><span data-ttu-id="c3a04-127">Конфигуриране на връзката за персонализирано импортиране чрез SFTP</span><span class="sxs-lookup"><span data-stu-id="c3a04-127">Configure the connection for SFTP Custom Import</span></span> 

<span data-ttu-id="c3a04-128">Трябва да сте администратор, за да конфигурирате връзки.</span><span class="sxs-lookup"><span data-stu-id="c3a04-128">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="c3a04-129">Изберете **Добавяне на връзка**, когато конфигурирате допълването, *или* отидете на **Администратор** > **Връзки** и изберете **Настройка** в плочката за персонализирано импортиране.</span><span class="sxs-lookup"><span data-stu-id="c3a04-129">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Custom Import tile.</span></span>

1. <span data-ttu-id="c3a04-130">Въведете име за връзката в полето **Показвано име**.</span><span class="sxs-lookup"><span data-stu-id="c3a04-130">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="c3a04-131">Въведете валидно потребителско име, парола и URL адрес на хоста за STFP сървъра, на който се намират данните, които ще се импортират.</span><span class="sxs-lookup"><span data-stu-id="c3a04-131">Enter valid user name, password, and host URL for the STFP server the data to be imported resides on.</span></span>

1. <span data-ttu-id="c3a04-132">Прегледайте и дайте своето съгласие за **Поверителност и съответствие на данните**, като изберете отметката **Приемам**.</span><span class="sxs-lookup"><span data-stu-id="c3a04-132">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="c3a04-133">Изберете **Проверка**, за да проверите конфигурацията.</span><span class="sxs-lookup"><span data-stu-id="c3a04-133">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="c3a04-134">След като проверката приключи, връзката може да се запише чрез щракване върху **Записване**.</span><span class="sxs-lookup"><span data-stu-id="c3a04-134">Once the verification has completed, the connection can be saved by clicking **Save**.</span></span>

> [!div class="mx-imgBorder"]
   > <span data-ttu-id="c3a04-135">![Страница за конфигуриране на връзка на Experian](media/enrichment-SFTP-connection.png "Страница за конфигуриране на връзка на Experian")</span><span class="sxs-lookup"><span data-stu-id="c3a04-135">![Experian connection configuration page](media/enrichment-SFTP-connection.png "Experian connection configuration page")</span></span>


## <a name="defining-field-mappings"></a><span data-ttu-id="c3a04-136">Определяне на нанасяния на полета</span><span class="sxs-lookup"><span data-stu-id="c3a04-136">Defining field mappings</span></span> 

<span data-ttu-id="c3a04-137">Директорията, която съдържа файла, който ще се импортира на SFTP сървъра, също трябва да съдържа *model.json* файл.</span><span class="sxs-lookup"><span data-stu-id="c3a04-137">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="c3a04-138">Този файл дефинира схемата, която да се използва за импортиране на данните.</span><span class="sxs-lookup"><span data-stu-id="c3a04-138">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="c3a04-139">Схемата трябва да използва [Common Data Model](/common-data-model/), за да зададете нанасяне на полето.</span><span class="sxs-lookup"><span data-stu-id="c3a04-139">The schema has to use [the Common Data Model](/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="c3a04-140">Един прост пример за файл model.json изглежда така:</span><span class="sxs-lookup"><span data-stu-id="c3a04-140">A simple example of a model.json file looks like this:</span></span>

```
{
    "name": "EnrichmentFromMicrosoft",
    "description": "Model containing data enrichment",
    "entities": [
        {
            "name": "CustomImport",
            "attributes": [
                {
                    "name": "CustomerId",
                    "friendlyName": "Client id",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred City for vacation",
                    "dataType": "string"
                },
                {
                    "name": "PreferredTransportation",
                    "friendlyName": "Preferred transportation",
                    "dataType": "string"
                }
            ],
            "annotations": [
                {
                    "name": "c360:PrimaryKey",
                    "value": "CustomerId"
                }
            ]
        }
    ],
    "modifiedTime": "2020-01-02T12:00:00+08:00",
    "annotations": [
        {
            "name": "testAnnotation",
            "value": "testValue"
        }
    ]
}
```

## <a name="enrichment-results"></a><span data-ttu-id="c3a04-141">Резултати от допълването</span><span class="sxs-lookup"><span data-stu-id="c3a04-141">Enrichment results</span></span>

<span data-ttu-id="c3a04-142">За да започнете процеса на допълване, изберете **Стартиране** от командната лента.</span><span class="sxs-lookup"><span data-stu-id="c3a04-142">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="c3a04-143">Можете също така да оставите системата да стартира допълването автоматично като част от [планирано обновяване](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="c3a04-143">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="c3a04-144">Времето за обработка ще зависи от размера на данните, които ще се импортират, и връзката със SFTP сървъра.</span><span class="sxs-lookup"><span data-stu-id="c3a04-144">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="c3a04-145">След като процесът на обогатяване завърши, можете да прегледате новоимпортираните си данни за обогатяване по-долу **Моите обогатявания**.</span><span class="sxs-lookup"><span data-stu-id="c3a04-145">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="c3a04-146">Освен това ще намерите часа на последната актуализация и броя на допълнените профили.</span><span class="sxs-lookup"><span data-stu-id="c3a04-146">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="c3a04-147">Можете да получите достъп до подробен изглед на всеки допълнен профил, като изберете **Преглед на допълнените данни**.</span><span class="sxs-lookup"><span data-stu-id="c3a04-147">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="c3a04-148">Следващи стъпки</span><span class="sxs-lookup"><span data-stu-id="c3a04-148">Next steps</span></span>

<span data-ttu-id="c3a04-149">Надградете допълнените клиентски данни.</span><span class="sxs-lookup"><span data-stu-id="c3a04-149">Build on top of your enriched customer data.</span></span> <span data-ttu-id="c3a04-150">Създайте [сегменти](segments.md), [мерки](measures.md) и [експортирайте данните](export-destinations.md), за да доставите персонализирано изживяване на вашите клиенти.</span><span class="sxs-lookup"><span data-stu-id="c3a04-150">Create [segments](segments.md), [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
