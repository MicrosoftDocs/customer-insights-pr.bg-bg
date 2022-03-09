---
title: Създаване на връзка между аналитични данни за аудитория и аналитични данни за ангажираност
description: Създайте активна връзка между аналитичните данни за аудитория и аналитичните данни за ангажираност, за да активирате двупосочно споделяне на данни.
ms.date: 09/08/2021
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 56adc206d83bc6e34a55f11383393b5ac66da531
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: bg-BG
ms.lasthandoff: 02/16/2022
ms.locfileid: "8229859"
---
# <a name="create-a-link-between-audience-insights-and-engagement-insights"></a>Създаване на връзка между аналитични данни за аудитория и аналитични данни за ангажираност

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Интеграцията между аналитични данни за ангажираност и аналитични данни за аудитория свързва среди от двете възможности и позволява да се споделят данни двупосочно между тях.

Използвайте унифицирани профили и сегменти от аналитичните данни за аудитория за повече опции за анализ в аналитичните данни за ангажираност. Експортирайте събития, които имат висока бизнес стойност на аналитичните данни за ангажираност. Използвайте тези събития, за да добавите данни към унифицирани профили в аналитичните данни за аудитория.

## <a name="prerequisites"></a>Предварителни изисквания

- Профилите за аналитични данни за аудитория трябва да се съхраняват в акаунт на Azure Data Lake Storage, който притежавате, или в управлявано [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro)&ndash;data lake. 
- Средата на аналитичните данни за аудитория трябва да има свързана среда на Dataverse. И ако тази среда също се използва Dataverse за съхранение на данни, проверете **Активиране на споделянето на данни** опция в анализите на аудиторията. За повече информация вижте [Създайте и конфигурирайте среда в анализите на аудиторията](../audience-insights/create-environment.md).
- Имате нужда от разрешения на администратор за средите на аналитичните данни за ангажираност и на аналитичните данни за аудитория.
- Свързаните среди трябва да са в един и същ географски регион.

> [!NOTE]
> - Ако абонаментът за аналитичните данни за аудитория е пробен, който използва вътрешно управлявано data lake за аналитични данни за аудитория, свържете се с [pirequest@microsoft.com](mailto:pirequest@microsoft.com) за помощ. 
> - Ако средата на аналитичните данни за аудитория използва ваше Azure Data Lake Storage за съхраняване на данни, трябва да добавите субект на услугата Azure към акаунта за съхранение. За подробности отидете на [Свързване с акаунт на Azure Data Lake Storage със субект на услуга на Azure за аналитични данни за аудитория](../audience-insights/connect-service-principal.md). 


## <a name="create-an-environment-link"></a>Създаване на връзка към среда

Можете да създадете връзка към среда, като актуализирате настройките **Администратор** > **Среда** в аналитичните данни за ангажираност.

**За да установите активна връзка между аналитичните данни за аудитория и аналитичните данни за ангажираност**

1. На страницата **Администратор на среда** изберете раздела **Свързване на среди**.

    :::image type="content" source="media/integrate1.png" alt-text="Настройване на среда.":::

1. Изберете **Настройване на среди** в горния ляв ъгъл или в долната част на екрана.

     :::image type="content" source="media/integrate2.png" alt-text="Избор на среда за аналитични данни за аудитория.":::

1. Изберете среда за аналитични данни за аудитория и след това изберете ***Напред**, за да приключите. Сега можете да изберете допълнителни функции за свързаните среди.
 
## <a name="enable-audience-insights-unified-profiles-attributes-and-segments"></a>Активиране на атрибути и сегменти на унифицирани профили на аналитични данни за аудитория

След свързването на средите можете да изберете допълнителни функции за свързаните среди. Тези функции разрешават унифицирани атрибути и сегменти на профил от аналитичните данни за аудитория за интерактивен анализ на клиентските данни.

> [!IMPORTANT]
> За да се покажат сегменти с аналитични данни за аудитория в аналитичните данни за ангажираност, първо трябва [да изпълните сливане и процесите надолу по веригата](../audience-insights/merge-entities.md). Процесите надолу по веригата са важни, тъй като генерират уникална таблица, която подготвя сегменти на аналитичните данни за аудитория, които да се споделят с аналитичните данни за ангажираност. (Ако е планирано обновяване на системата, то автоматично ще включва процеси надолу по веригата.)

**За анализиране на уеб данни в аналитични данни за ангажираност**

1. На страницата **Администратор на среда** включете превключвателя **Споделяне на данни от аналитични данни за аудитория с аналитични данни за ангажираност** и след това изберете **Напред**.

    :::image type="content" source="media/integrate4.png" alt-text="Изберете функции.":::

1. Изберете атрибутите на унифицираните профили, които ще станат измерения в аналитичните данни за ангажираност. (Не всички атрибути са полезни измерения. Например, няма вероятност да имате нужда от **Собствено име** или **Фамилно име** като атрибут за анализ на събитията на уебсайта.)

    :::image type="content" source="media/integrate5.png" alt-text="Управление на измерения.":::

   >[!NOTE]
   > Всички атрибути на профила на аналитичните данни за аудитория, които представляват идентификатори (като **ИД** и **алтернативен ИД**) се филтрират от наличните атрибути и стават измерения в аналитичните данни за ангажираност.

1. Когато приключите с избора на атрибути, изберете **Напред**.
1. Добавете потребители, които могат да преглеждат измеренията на профила в аналитичните данни за аудитория и сегментите в аналитичните данни за ангажираност.

    :::image type="content" source="media/integrate6.png" alt-text="Управление на достъпа до данните на клиентите.":::

   > [!IMPORTANT]
   > Ако не добавите изрично потребители в тази стъпка, данните ще бъдат скрити от потребителите в аналитичните данни за ангажираност.
   > За да се покажат сегменти с аналитични данни за аудитория в аналитичните данни за ангажираност, първо трябва [да изпълните сливане и процесите надолу по веригата](../audience-insights/merge-entities.md). Процесите надолу по веригата са важни, тъй като генерират уникална таблица, която подготвя сегменти на аналитичните данни за аудитория, които да се споделят с аналитичните данни за ангажираност. (Ако е планирано обновяване на системата, то автоматично ще включва процеси надолу по веригата.)

1. Прегледайте избора си и след това изберете **Готово**.

    :::image type="content" source="media/integrate7.png" alt-text="Прегледайте настройките за клиентски данни.":::

## <a name="export-refined-events-to-audience-insights"></a>Експортиране на прецизирани събития с аналитичните данни за аудитория

След като създадете връзка между среди, можете да експортирате прецизирани събития от аналитичните данни за ангажираност в аналитичните данни за аудитория и да ги приемете като нов източник на данни. 

За повече информация отидете на [Интегриране на уеб данни от аналитични данни за ангажираност с аналитични данни за аудитория](../audience-insights/integrate-engagement-insights.md).

<!--
## Share engagement insights refined events with audience insights

After you create a link between environments, a new option becomes available for you to share [refined events](refined-events.md) with audience insights.

Consider the following when creating refined events for audience insights: 

- Provide a meaningful name for the refined event. It will be used as an activity name in audience insights.
- Select at least the following properties to create an activity in audience insights: 
    - Signal.Action.Name indicates the activity details.
    - Signal.User.Id maps with the customer ID.
    - Signal.View.Uri is a web address as a basis for segments or measures.
    - Signal.Export.Id is a primary key for events.
    - Signal.Timestamp determines the date and time for the activity.

To share refined events:

1. From the engagement insights menu, select **Data** and then select the **Events** tab.
2. On the **Action** menu, select **Share as activity**.

    :::image type="content" source="media/integrate8.png" alt-text="Data shared events settings.":::

3. You can view and stop actively shared events on the **Export and Sharing** tab.
4. -- per Michael K, we need a mock here (Mukesh needs to update to reflect what happens in AUI once a user shares a refined event (i.e. no longer AUI, data wrangler needs to go discover data in the storage, the shared event is available as a DS and entity, correct?)

### Attach refined events shared as activities to unified profiles in audience insights

You can bring customer web activity data from engagement insights into audience insights. In addition to transactional, demographic, or behavioral data, you can view activities on the web in unified customer profiles. You can then use these profiles to get insights such as segments, measures, and predictions for audience activation.

Follow the steps in [data unification](../audience-insights/data-unification.md) to map, match, and merge website authentication information to unified profiles in audience insights.

You can also share refined events that are now available in audience insights, identified as data sources and entities. 

Next, you can relate event data from engagement insights as unified activities in customer profiles.

### Relate refined event data as an activity of a customer profile

After unifying the data, you can configure the activity for the customer profile. For more information, go to [Customer activities](../audience-insights/activities.md).

:::image type="content" source="media/web-event-activity.png" alt-text="Activities page with expanded Edit activity pane.":::

Next, configure the new activity by using mapping elements: 

- **Primary Key**: Signal.Export.Id, a unique ID that is available for every event record in engagement insights. This property is automatically generated.

- **Timestamp**: Signal.Timestamp in the event property.

- **Event**: Signal.Name, the event name that you want to track.

- **Web address**: Signal.View.Uri that refers to the URI of the page that created the event.

- **Details**: Signal.Action.Name to represent the information to associate with the event. The selected property in this case indicates that the event is for email promotion.

- **Activity type**: In this example, we choose the existing activity type WebLog. This selection is a useful filter option to run prediction models or create segments based on this activity type.

- **Set up relationship**: This important setting ties the activity to existing customer profiles. **Signal.User.Id** is the identifier configured in the SDK to be collected. It relates to the user ID in other data sources that are configured in audience insights. 

This example configures the relationship between Signal.User.Id and RetailCustomers:CustomerRetailId, which is the primary key that was identified in the map step of the data unification process.

After processing the activities, you can review customer records and open a customer card to see activities from engagement insights in the timeline. 

> [!TIP]
> To find a customer ID that has an engagement insights activity, go to **Entities** and preview the data for the UnifiedActivity entity. **ActivityTypeDisplay = WebLog** contains the engagement insights activity configured in the preceding example. Copy the customer ID for one of those records and search<!--note from editor: Edit okay? I couldn't quite follow this.-- > for that ID on the **Customers** page.

--> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
