---
title: Заявки по правата на субекта на данни (DSR) съгласно GDPR | Microsoft Docs
description: Отговорете на заявки за субект на данни за способността за аналитични данни за аудитория на Dynamics 365 Customer Insights.
ms.date: 08/11/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: e095eb4f8e194f314d7d6baf6fa6a7a319319d2a
ms.sourcegitcommit: 1946d7af0bd2ca216885bec3c5c95009996d9a28
ms.translationtype: MT
ms.contentlocale: bg-BG
ms.lasthandoff: 02/25/2022
ms.locfileid: "8350256"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Правата на субекта на данни (DSR) съгласно GDPR

Общ регламент относно защитата на данните (GDPR) на Европейския съюз е в сила от 25 май 2018 г. Той дава значителни права на физическите лица по отношение на техните данни. GDPR е свързан със защитата и осигуряването на неприкосновеността на личния живот на хората. Можете да прочетете повече за ангажимента на Microsoft за сигурност и съответствие в [Център за сигурност на Microsoft](https://www.microsoft.com/trust-center).

Ние се ангажираме да помагаме на нашите клиенти да отговарят на изискванията на GDPR. Той включва правото да изтривате и експортирате данни, които включват лична информация като потребителски идентификатори, телефонни номера и имейл адреси. Администраторите могат да изпълняват потребителски заявки за изтриване или експортиране на лични данни.

## <a name="audience-insights"></a>Аналитични данни за аудиторията

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a>Отговор на заявки за изтриване на субект на данни според GDPR за способността за аналитични данни за аудитория на Dynamics 365 Customer Insights

„Правото на изтриване” чрез премахване на лични данни от клиентските данни на организацията е ключова защита в Общия регламент относно защитата на данните (GDPR). Премахването на лични данни включва премахване на всички лични данни и системно генерирани регистрационни файлове, с изключение на информацията от регистрационни файлове за одит.

#### <a name="manage-data-subject-delete-requests"></a>Управление на заявки за изтриване на субект на данни

Аналитични данни за аудитория предлага следните функционалности на продуктите за изтриване на лични данни за конкретен клиент или потребител:

- **Управление на заявки за изтриване на клиентски данни**: Клиентските данни в Customer Insights се приемат от първоначални източници на данни, външни за Customer Insights. Всички заявки за изтриване съгласно GDPR трябва да се изпълнят в първоначалния източник на данни.
- **Управлявайте заявки за изтриване на потребителски данни на Customer Insights**: Данните за потребителите се създават от Customer Insights. Всички заявки за изтриване по GDPR трябва да се изпълнят в Customer Insights.

##### <a name="manage-requests-to-delete-customer-data"></a>Управление на заявки за изтриване на клиентски данни

Администратор на Customer Insights може да следва тези стъпки, за да премахне клиентските данни, които са били изтрити в източника на данни:

1. Влезте в Dynamics 365 Customer Insights.
2. В статията за аудиторията отидете на **Данни** > **Източници на данни**
3. За всеки източник на данни в списъка, който съдържа изтрити клиентски данни:
   1. Изберете (...) и след това изберете **Обновяване**.
   2. Проверете състоянието на източника на данни под **Състояние**. Отметката означава, че обновяването е успешно. Предупредителният триъгълник означава, че нещо се е объркало. Ако се покаже предупредителен триъгълник, свържете се с D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![Обработка на заявки за изтриване съгласно GDPR за клиентски данни.](audience-insights/media/gdpr-data-sources.png "Обработка на заявки за изтриване съгласно GDPR за клиентски данни")

##### <a name="manage-delete-requests-for-user-data"></a>Управление на заявки за изтриване на потребителски данни

Администраторът на Customer Insights може да следва тези стъпки, за да изтрие потребителските данни в Customer Insights:

1. Влезте в Dynamics 365 Customer Insights.
2. В статията за аудиторията отидете на **Администратор** > **Разрешения**.
3. Поставете отметка в квадратчето за потребителя, който искате да изтриете.
4. Изберете **Премахване**.

### <a name="responding-to-gdpr-data-subject-export-requests"></a>Отговор на заявки за експортиране на субект на данни съгласно GDPR

Като част от ангажимента ни да си партнираме с вас по пътя към Общия регламент относно защитата на данните (GDPR), разработихме документация, която да ви помогне да се подготвите. Тази документация описва стъпки, които можете да предприемете днес, за да подкрепите спазването на GDPR, когато използвате статистика за аудиторията.

#### <a name="manage-export-and-view-requests"></a>Управление на заявки за експортиране и преглед

Правото на преносимост на данните позволява на субектите на данни да изискат копие от своите лични данни в електронен формат (определен като „структуриран, често използван, машинно четим и оперативно съвместим формат”), който може да бъде предаден на друг администратор на данни.

##### <a name="export-customer-data-tenant-admin"></a>Експортиране на клиентски данни (администратор на клиент)

Администраторът на клиент може да следва тези стъпки за експортиране на данни:

1. Изпратете имейл до D365CI@microsoft.com, за да укажете имейл адреса на клиента в заявката. Екипът на Customer Insights ще изпрати имейл на регистрирания имейл адрес на администратора на клиента, който изисква потвърждение за експортирането на данни.
2. Приемане на потвърждението за експортиране на данните за заявения клиент.
3. Получаване на експортираните данни чрез имейл адреса на администратора на клиента.

##### <a name="export-user-data-tenant-admin"></a>Експортиране на потребителски данни (администратор на клиент)

1. Изпратете имейл до D365CI@microsoft.com, за да укажете имейл адреса на потребителя в заявката. Екипът на Customer Insights ще изпрати имейл на регистрирания имейл адрес на администратора на клиента, който изисква потвърждение за експортирането на данни.
2. Приемане на потвърждението за експортиране на данните за заявения потребител.
3. Получаване на експортираните данни чрез имейл адреса на администратора на клиента.

## <a name="consent-management-preview"></a>Управление на съгласието (предварителен преглед)

Възможността за управление на съгласието не събира потребителски данни директно. Той внася и обработва само данни за съгласие, които се предоставят от потребителите в други приложения.

За да премахнете данните за съгласие за конкретни потребители, премахнете го в източниците на данни, погълнат към възможността за управление на съгласието. След обновяване на източник на данни премахнатите данни ще бъдат изтрити и в Центъра за съгласие. Приложенията, които използват обекта на съгласието, също ще изтриват данни, които са премахнати на източника след [обновяване](audience-insights/system.md#refresh-processes). Препоръчваме освежаващи източници на данни бързо след отговор на заявка за субект на данни за премахване на данните на потребителя от всички други процеси и приложения.


<!-- ## Engagement insights (preview)

### Deleting and exporting event data containing end user identifiable information

The following sections describe how to delete and export event data that might contain personal data.

To delete or export data:

1. Tag event properties that contain data with personal information.
2. Delete or export data associated with specific values (for example: a specified user ID).

#### Tag and update event properties

Personal data is tagged on an event property level. First, tag the properties being considered for deletion or export.

To tag an event property as containing personal information, follow these steps:

1. Open the workspace containing the event.

1. Go to **Data** > **Events** to see the list of events in the selected workspace.
  
1. Select the event you want to tag.

1. Select **Edit properties** to open the pane listing all properties of the selected event.
     
1. Select **...** and then choose **Edit** to reach the **Update property** dialog.

   ![Edit event.](engagement-insights/media/edit-event.png "Edit event")

1. In the **Update Property** window, choose **...** in the upper right corner, and then choose the **Contains EUII** box. Choose **Update** to save your changes.

   ![Save your changes.](engagement-insights/media/update-property.png "Save your changes")

   > [!NOTE]
   > Every time the event schema changes or you create a new event, it's recommended that you evaluate the associated event properties and tag or untag them as containing personal data, if necessary.

#### Delete or export tagged event data

If all event properties have been tagged appropriately as described in the previous step, an environment admin can issue a deletion request against the tagged event data.

To manage EUII deletion or export requests

1. Go to **Admin** > **Environment** > **Settings**.

1. In the **Manage end user identifiable information (EUII)** section, select **Manage EUII**.

##### Deletion

For deletion, you can enter a list of comma-separated user IDs in the **Delete end user identifiable information (EUII)** section. These IDs will then be compared with all tagged event properties of all projects in the current environment via exact string matching. 

If a property value matches one of the provided IDs, the associated event will be permanently deleted. Due to the irreversibility of this action, you must confirm the deletion after selecting **Delete**.

##### Export

The export process is identical to the deletion process when it comes to defining event property values in the **Export end user identifiable information (EUII)** section. Additionally, you'll need to provide an **Azure blob storage URL** to specify the export destination. The Azure Blob URL must include a [Shared Access Signature (SAS)](/azure/storage/common/storage-sas-overview).

After selecting **Export**, all events of the current team that contain matching tagged properties will be exported in CSV format to the export destination.

### Good practices

* Try to avoid sending any events that contain personal data.
* If you need to send events containing EUII data, limit the number of events and event properties that contain EUII data. Ideally, limit yourself to one such event.
* Make sure that as few people as possible have access to the sent personal data.
* For events containing personal data, make sure that you set one property to emit a unique identifier that can easily be linked to a specific user (for example, a user ID). This makes it easier to segregate data and to export or delete the right data.
* Only tag one property per event as containing personal data. Ideally one that only contains a unique identifier.
* Do not tag properties containing verbose values (for example, an entire request body). Engagement insights capability uses exact string matching when deciding which events to delete or export. -->

[!INCLUDE[footer-include](includes/footer-banner.md)]