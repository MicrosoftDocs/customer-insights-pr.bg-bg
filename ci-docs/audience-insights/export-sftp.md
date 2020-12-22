---
title: Експортирайте данните от Customer Insights в SFTP хостове
description: Научете как да конфигурирате връзката към хост SFTP.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c2529744d7a26a06324b79cad6a8001d75903545
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643490"
---
# <a name="connector-for-sftp-preview"></a><span data-ttu-id="8ca8d-103">Конектор за SFTP (преглед)</span><span class="sxs-lookup"><span data-stu-id="8ca8d-103">Connector for SFTP (preview)</span></span>

<span data-ttu-id="8ca8d-104">Използвайте клиентските данни в приложения на трети страни, като ги експортирате в хост със Secure File Transfer Protocol (SFTP).</span><span class="sxs-lookup"><span data-stu-id="8ca8d-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol(SFTP) host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8ca8d-105">Предварителни изисквания</span><span class="sxs-lookup"><span data-stu-id="8ca8d-105">Prerequisites</span></span>

- <span data-ttu-id="8ca8d-106">Наличие на хост SFTP и съответните идентификационни данни.</span><span class="sxs-lookup"><span data-stu-id="8ca8d-106">Availability of a SFTP host and corresponding credentials.</span></span>

## <a name="connect-to-sftp"></a><span data-ttu-id="8ca8d-107">Свързване с SFTP</span><span class="sxs-lookup"><span data-stu-id="8ca8d-107">Connect to SFTP</span></span>

1. <span data-ttu-id="8ca8d-108">Отидете на **Администратор** > **Експортиране на дестинации**.</span><span class="sxs-lookup"><span data-stu-id="8ca8d-108">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="8ca8d-109">Под **SFTP** изберете **Настройване**.</span><span class="sxs-lookup"><span data-stu-id="8ca8d-109">Under **SFTP**, select **Set up**.</span></span>

1. <span data-ttu-id="8ca8d-110">Въведете разпознаваемо име за местоназначението в полето **Показвано име**.</span><span class="sxs-lookup"><span data-stu-id="8ca8d-110">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="8ca8d-111">Предоставете **Потребителско име**, **Парола** и **Име на хост** за вашия SFTP акаунт.</span><span class="sxs-lookup"><span data-stu-id="8ca8d-111">Provide a **Username**, **Password** and **Hostname** for your SFTP account.</span></span> <span data-ttu-id="8ca8d-112">Пример: Ако коренната папка на вашия SFTP сървър е /root/папка и искате данните да бъдат експортирани в /root/folder/ci_export_destination_folder, хостът трябва да бъде sftp://<адрес на_сървър>/ci_export_destination_folder.</span><span class="sxs-lookup"><span data-stu-id="8ca8d-112">Example: If your SFTP server's root folder is /root/folder, and you would like the data to be exported to /root/folder/ci_export_destination_folder, the the host should be sftp://<server_address>/ci_export_destination_folder".</span></span>

1. <span data-ttu-id="8ca8d-113">Изберете **Проверка**, за да тествате връзката.</span><span class="sxs-lookup"><span data-stu-id="8ca8d-113">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="8ca8d-114">След успешна проверка изберете дали искате да експортирате данните **Архивирани в zip файл** или **Разархивирани** и изберете **разделител на полето** за експортираните файлове.</span><span class="sxs-lookup"><span data-stu-id="8ca8d-114">After successful verification, choose if you want to export your data **Zipped** or **Unzipped**, and select the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="8ca8d-115">Изберете **Приемам**, за да потвърдите **Поверителност на данните и съответствие**.</span><span class="sxs-lookup"><span data-stu-id="8ca8d-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="8ca8d-116">Изберете **Напред**, за да започнете да конфигурирате експортирането.</span><span class="sxs-lookup"><span data-stu-id="8ca8d-116">Select **Next** to start configuring the export.</span></span>

## <a name="configure-the-connection"></a><span data-ttu-id="8ca8d-117">Конфигуриране на връзката</span><span class="sxs-lookup"><span data-stu-id="8ca8d-117">Configure the connection</span></span>

1. <span data-ttu-id="8ca8d-118">Изберете **атрибутите на клиенти**, които искате да експортирате.</span><span class="sxs-lookup"><span data-stu-id="8ca8d-118">Select the **customer attributes** you want to export.</span></span> <span data-ttu-id="8ca8d-119">Можете да експортирате един или няколко атрибута.</span><span class="sxs-lookup"><span data-stu-id="8ca8d-119">You can export one or multiple attributes.</span></span>

1. <span data-ttu-id="8ca8d-120">Изберете **Напред**.</span><span class="sxs-lookup"><span data-stu-id="8ca8d-120">Select **Next**.</span></span>

1. <span data-ttu-id="8ca8d-121">Изберете сегментите, които искате да експортирате.</span><span class="sxs-lookup"><span data-stu-id="8ca8d-121">Select the segments you want to export.</span></span>

1. <span data-ttu-id="8ca8d-122">Изберете **Записване**.</span><span class="sxs-lookup"><span data-stu-id="8ca8d-122">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="8ca8d-123">Експортиране на данните</span><span class="sxs-lookup"><span data-stu-id="8ca8d-123">Export the data</span></span>

<span data-ttu-id="8ca8d-124">Можете да [експортирате данни при поискване](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="8ca8d-124">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="8ca8d-125">Експортирането също ще се изпълнява с всяко [планирано обновяване](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="8ca8d-125">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="8ca8d-126">Поверителност и съответствие на данните</span><span class="sxs-lookup"><span data-stu-id="8ca8d-126">Data privacy and compliance</span></span>

<span data-ttu-id="8ca8d-127">Когато активирате Dynamics 365 Customer Insights, за да предавате данни чрез SFTP, разрешавате прехвърляне на данни извън границата за съответствие за Dynamics 365 Customer Insights, включително потенциално чувствителни данни като Лични данни.</span><span class="sxs-lookup"><span data-stu-id="8ca8d-127">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="8ca8d-128">Microsoft ще прехвърли такива данни по ваше указание, но вие носите отговорност да гарантирате, че местоположението за експортиране отговаря на всички задължения за поверителност или сигурност, които може да имате.</span><span class="sxs-lookup"><span data-stu-id="8ca8d-128">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="8ca8d-129">За информация посетете [Декларация за поверителност Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="8ca8d-129">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="8ca8d-130">Вашият администратор на Dynamics 365 Customer Insights да премахнете това местоназначение за експортиране по всяко време, за да прекратите използването на тази функционалност.</span><span class="sxs-lookup"><span data-stu-id="8ca8d-130">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
