---
title: Обогатяване с SFTP персонализирано импортиране
description: Обща информация за обогатяването на SFTP персонализирано импортиране.
ms.date: 11/18/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jdahl
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f25dcc08d96d36507e47af0d7b184003ae095819
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269593"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="fdbfe-103">Обогатете потребителските профили с персонализирани данни (преглед)</span><span class="sxs-lookup"><span data-stu-id="fdbfe-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="fdbfe-104">Потребителското импортиране Secure File Transfer Protocol(SFTP) ви позволява да импортирате обогатяващи данни, които не трябва да преминават през процеса на обединяване на данните.</span><span class="sxs-lookup"><span data-stu-id="fdbfe-104">Secure File Transfer Protocol(SFTP) custom import enables you to import data that doesn't have to go through the process of data unification.</span></span> <span data-ttu-id="fdbfe-105">Това е гъвкав, сигурен и лесен начин за въвеждане на вашите данни.</span><span class="sxs-lookup"><span data-stu-id="fdbfe-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="fdbfe-106">SFTP потребителски импорт може да се използва в комбинация с [SFTP експортиране](export-sftp.md), което ви позволява да експортирате данни за потребителския профил, необходими за обогатяване.</span><span class="sxs-lookup"><span data-stu-id="fdbfe-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="fdbfe-107">След това данните могат да бъдат обработени, обогатени и SFTP потребителски импорт може да се използва, за да върне обогатените данни обратно на способността за прозрение на аудиторията на Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="fdbfe-107">The data can then be processed, enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="fdbfe-108">Предварителни изисквания</span><span class="sxs-lookup"><span data-stu-id="fdbfe-108">Prerequisites</span></span>

<span data-ttu-id="fdbfe-109">За да конфигурирате SFTP персонализирано импортиране, трябва да са изпълнени следните предпоставки:</span><span class="sxs-lookup"><span data-stu-id="fdbfe-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="fdbfe-110">Имате потребителски идентификационни данни (потребителско име и парола) за SFTP местоположението, откъдето ще бъдат импортирани данните.</span><span class="sxs-lookup"><span data-stu-id="fdbfe-110">You have user credentials (user name and password) for the SFTP location where the data that is going to be imported from.</span></span>
- <span data-ttu-id="fdbfe-111">Имате URL и номер на порт (обикновено 22) за STFP хоста.</span><span class="sxs-lookup"><span data-stu-id="fdbfe-111">You have the URL and port number (usually 22) for the STFP host.</span></span>
- <span data-ttu-id="fdbfe-112">Имате името на файла и местоположението на файла, който ще се импортира на SFTP хоста.</span><span class="sxs-lookup"><span data-stu-id="fdbfe-112">You have the filename and location of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="fdbfe-113">Има *model.json* файл, който указва схемата за данните, които трябва да бъдат импортирани.</span><span class="sxs-lookup"><span data-stu-id="fdbfe-113">There's a *model.json* file that specifies the schema for the data that are to be imported.</span></span> <span data-ttu-id="fdbfe-114">Този файл трябва да е в същата директория като файла за импортиране.</span><span class="sxs-lookup"><span data-stu-id="fdbfe-114">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="fdbfe-115">Имате разрешение за [Администратор](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="fdbfe-115">You have [Administrator](permissions.md#administrator) permission.</span></span>

## <a name="configuration"></a><span data-ttu-id="fdbfe-116">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="fdbfe-116">Configuration</span></span>

1. <span data-ttu-id="fdbfe-117">Отидете в раздела **Данни** > **Допълване** и изберете раздела **Откриване**.</span><span class="sxs-lookup"><span data-stu-id="fdbfe-117">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="fdbfe-118">На **Плочка за SFTP персонализирано импортиране**, изберете **Обогати данните ми**.</span><span class="sxs-lookup"><span data-stu-id="fdbfe-118">On the **SFTP custom import tile**, select **Enrich my data**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="fdbfe-119">![Плочка за SFTP персонализирано импортиране](media/SFTP_Custom_Import_tile.png "Плочка за SFTP персонализирано импортиране")</span><span class="sxs-lookup"><span data-stu-id="fdbfe-119">![SFTP Custom Import tile](media/SFTP_Custom_Import_tile.png "SFTP Custom Import tile")</span></span>

1. <span data-ttu-id="fdbfe-120">Изберете **Първи стъпки** и предоставете идентификационните данни и адреса на SFTP сървъра.</span><span class="sxs-lookup"><span data-stu-id="fdbfe-120">Select **Get started** and provide the credentials and the address for the SFTP server.</span></span> <span data-ttu-id="fdbfe-121">Например sftp://mysftpserver.com:22.</span><span class="sxs-lookup"><span data-stu-id="fdbfe-121">For example, sftp://mysftpserver.com:22.</span></span>

1. <span data-ttu-id="fdbfe-122">Въведете името на файла, който съдържа данните и пътя до файла на SFTP сървъра, ако не е в основната папка.</span><span class="sxs-lookup"><span data-stu-id="fdbfe-122">Enter the name of the file that contains the data and path to the file on the SFTP server if it's not in the root folder.</span></span>

1. <span data-ttu-id="fdbfe-123">Потвърдете всички входове, като изберете **Свържете се с персонализирано импортиране**.</span><span class="sxs-lookup"><span data-stu-id="fdbfe-123">Confirm all inputs by selecting **Connect to Custom Import**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="fdbfe-124">![Оформление на конфигурация на SFTP персонализирано импортиране](media/SFTP_Custom_Import_Configuration_flyout.png "Оформление на конфигурация на SFTP персонализирано импортиране")</span><span class="sxs-lookup"><span data-stu-id="fdbfe-124">![SFTP Custom Import Configuration flyout](media/SFTP_Custom_Import_Configuration_flyout.png "SFTP Custom Import Configuration flyout")</span></span>

## <a name="defining-field-mappings"></a><span data-ttu-id="fdbfe-125">Определяне на нанасяния на полета</span><span class="sxs-lookup"><span data-stu-id="fdbfe-125">Defining field mappings</span></span> 

<span data-ttu-id="fdbfe-126">Директорията, която съдържа файла, който ще се импортира на SFTP сървъра, също трябва да съдържа *model.json* файл.</span><span class="sxs-lookup"><span data-stu-id="fdbfe-126">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="fdbfe-127">Този файл дефинира схемата, която да се използва за импортиране на данните.</span><span class="sxs-lookup"><span data-stu-id="fdbfe-127">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="fdbfe-128">Схемата трябва да използва [Common Data Model](https://docs.microsoft.com/common-data-model/), за да зададете нанасяне на полето.</span><span class="sxs-lookup"><span data-stu-id="fdbfe-128">The schema has to use [the Common Data Model](https://docs.microsoft.com/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="fdbfe-129">Един прост пример за файл model.json изглежда така:</span><span class="sxs-lookup"><span data-stu-id="fdbfe-129">A simple example of a model.json file looks like this:</span></span>

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

## <a name="enrichment-results"></a><span data-ttu-id="fdbfe-130">Резултати от допълването</span><span class="sxs-lookup"><span data-stu-id="fdbfe-130">Enrichment results</span></span>

<span data-ttu-id="fdbfe-131">За да започнете процеса на допълване, изберете **Стартиране** от командната лента.</span><span class="sxs-lookup"><span data-stu-id="fdbfe-131">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="fdbfe-132">Можете също така да оставите системата да стартира допълването автоматично като част от [планирано обновяване](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="fdbfe-132">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="fdbfe-133">Времето за обработка ще зависи от размера на данните, които ще се импортират, и връзката със SFTP сървъра.</span><span class="sxs-lookup"><span data-stu-id="fdbfe-133">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="fdbfe-134">След като процесът на обогатяване завърши, можете да прегледате новоимпортираните си данни за обогатяване по-долу **Моите обогатявания**.</span><span class="sxs-lookup"><span data-stu-id="fdbfe-134">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="fdbfe-135">Освен това ще намерите часа на последната актуализация и броя на допълнените профили.</span><span class="sxs-lookup"><span data-stu-id="fdbfe-135">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="fdbfe-136">Можете да получите достъп до подробен изглед на всеки допълнен профил, като изберете **Преглед на допълнените данни**.</span><span class="sxs-lookup"><span data-stu-id="fdbfe-136">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="fdbfe-137">Следващи стъпки</span><span class="sxs-lookup"><span data-stu-id="fdbfe-137">Next steps</span></span>

<span data-ttu-id="fdbfe-138">Надградете допълнените клиентски данни.</span><span class="sxs-lookup"><span data-stu-id="fdbfe-138">Build on top of your enriched customer data.</span></span> <span data-ttu-id="fdbfe-139">Създайте [сегменти](segments.md), [мерки](measures.md) и [експортирайте данните](export-destinations.md), за да доставите персонализирано изживяване на вашите клиенти.</span><span class="sxs-lookup"><span data-stu-id="fdbfe-139">Create [segments](segments.md), [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>




[!INCLUDE[footer-include](../includes/footer-banner.md)]