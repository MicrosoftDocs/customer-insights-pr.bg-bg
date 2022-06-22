---
title: Работа с данни на Customer Insights в Microsoft Dataverse
description: Научете как да свържете "Аналитични данни за клиенти" и Microsoft Dataverse да разберете изходните обекти, които се експортират в Dataverse.
ms.date: 05/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 252723b8c174cb1ec488388c26fd2a1d398e9002
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: MT
ms.contentlocale: bg-BG
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011507"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Работа с данни на Customer Insights в Microsoft Dataverse

Customer Insights предоставя опцията обектите за изход да се предоставят като [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). Тази интеграция дава възможност за лесно споделяне на данни и персонализирано развитие чрез подход с нисък код/без код. Изходните [обекти](#output-entities) са налични като таблици в Dataverse среда. Можете да използвате данните за всяко друго приложение въз основа на Dataverse таблици. Тези таблици дават възможност за сценарии като автоматизирани работни потоци през Power Automate или изграждане на приложения с Power Apps.

Свързването с вашата Dataverse среда също ви дава възможност да [поглъщате данни от локален източници на данни с помощта на Power Platform потоци от данни и шлюзове](connect-power-query.md#add-data-from-on-premises-data-sources).

## <a name="prerequisites"></a>Предварителни изисквания

- Клиентските аналитични данни и Dataverse среди трябва да се хостват в един и същ регион.
- Трябва да имате роля на глобален администратор в Dataverse средата. Проверете дали тази [Dataverse среда е свързана с](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) определени групи за защита и се уверете, че сте добавени към тези групи за защита.
- Никоя друга среда на Customer Insights вече не е свързана със Dataverse средата, която искате да свържете. Научете как да [премахнете съществуваща връзка към Dataverse среда](#remove-an-existing-connection-to-a-dataverse-environment).
- Среда Microsoft Dataverse може да се свърже само с един акаунт за съхранение. Той се прилага само ако конфигурирате средата да [използва вашия Azure Data Lake Storage](own-data-lake-storage.md).

## <a name="connect-a-dataverse-environment-to-customer-insights"></a>Свързване на Dataverse среда към "Аналитични данни за клиенти"

Стъпката **Microsoft Dataverse** ви позволява да свържете Customer Insights с вашата Dataverse среда, докато [създавате среда](create-environment.md) на Customer Insights.

:::image type="content" source="media/dataverse-provisioning.png" alt-text="споделяне на данни с Microsoft Dataverse автоматично активирани за нетни нови среди.":::

Администраторите могат да конфигурират "Аналитични данни за клиенти" за свързване на съществуваща Dataverse среда. Предоставяйки URL адреса на околната Dataverse среда, той се прикачва към новата им среда "Аналитични данни за клиенти".

Ако не искате да използвате съществуваща Dataverse среда, системата създава нова среда за данните "Аналитични данни за клиенти" във вашия наемател. [Power Platform администраторите могат да контролират кой може да създава среди](/power-platform/admin/control-environment-creation). Когато настройвате нова среда на Customer Insights и администраторът е забранил създаването на среди за всички, с изключение на Dataverse администраторите, може да не сте в състояние да създадете нова среда.

**Активирайте споделянето** на данни с Dataverse, като поставите отметка в квадратчето за споделяне на данни.

Ако използвате собствен акаунт за съхранение на езерото за данни, трябва и **идентификаторът**"Разрешения". За повече информация как да получите идентификатора на разрешение прегледайте следния раздел.

## <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Разрешаване на споделянето на данни с Dataverse от вашите собствени Azure Data Lake Storage (Визуализация)

Разрешаването на споделянето на данни с Microsoft Dataverse, когато вашата среда [използва собствения Azure Data Lake Storage ви профил](own-data-lake-storage.md), се нуждае от някаква допълнителна конфигурация. Потребителят, настройващ средата "Аналитични данни за клиенти", трябва да има поне **разрешения за Съхранение на Blob Data Reader** в контейнера *CustomerInsights* в Azure Data Lake Storage акаунта.

1. Създайте две групи за защита на вашия абонамент за Azure - една **група за защита на Reader** и една **група за защита на contributor** и задайте Microsoft Dataverse услугата като собственик и за двете групи за защита.
2. Управлявайте списъка за контрол на достъпа (ACL) на контейнера CustomerInsights във вашия акаунт за съхранение чрез тези групи за защита. Добавете Microsoft Dataverse услугата и всякакви Dataverse базирани бизнес приложения като Dynamics 365 Marketing към групата за защита на **Reader** с **разрешения само** за четене. Добавете *само* приложението "Аналитични данни за клиенти" към групата за защита на **"Сътрудник** ", за да предоставите както разрешения за четене, така **и за запис**, за да пишете профили и аналитични данни.

### <a name="limitations"></a>Ограничения

Има две ограничения при използване Dataverse със собствен Azure Data Lake Storage профил:

- Има съпоставяне "едно към едно" между Dataverse организация и Azure Data Lake Storage профил. След като Dataverse дадена организация е свързана към акаунт за съхранение, тя не може да се свърже с друг акаунт за съхранение. Това ограничение предотвратява, че даден Dataverse не попълва няколко акаунта за съхранение.
- Споделянето на данни няма да работи, ако е необходима настройка на Azure private Link за достъп до профила Ви Azure Data Lake Storage, защото е зад защитна стена. Dataverse в момента не поддържа връзката с частни крайни точки чрез Private Link.

### <a name="set-up-powershell"></a>Настройване на PowerShell

За да изпълните скриптовете powerShell, първо трябва да настроите PowerShell съответно.

1. Инсталирайте най-новата версия на [Azure Active Directory PowerShell за графика](/powershell/azure/active-directory/install-adv2).
   1. На компютъра изберете клавиша Windows на клавиатурата, потърсете **Windows PowerShell** и изберете **Изпълняване като администратор**.
   1. В прозореца PowerShell, който се отваря, въведете `Install-Module AzureAD`.
2. Импортиране на три модула.
    1. В прозореца PowerShell въведете `Install-Module -Name Az.Accounts` и следвайте стъпките.
    1. Повторете за `Install-Module -Name Az.Resources` и `Install-Module -Name Az.Storage`.

### <a name="configuration-steps"></a>Стъпки за конфигуриране

1. Изтеглете двата скрипта powerShell, които трябва да изпълните от gitHub репото [на](https://github.com/trin-msft/byol) нашия инженер.
    1. `CreateSecurityGroups.ps1`
       - Имате нужда от *разрешения за администратор* на наемател, за да стартирате този скрипт powerShell.
       - Този скрипт powerShell създава две групи за защита на вашия абонамент за Azure. Един за групата Reader и друг за групата "Сътрудник" и ще направи Microsoft Dataverse обслужването като собственик както за тези групи за сигурност.
       - Изпълнение на този powerShell скрипт в Windows PowerShell, като предоставите ИД на абонамент за Azure, съдържащ вашия Azure Data Lake Storage. Отворете скрипта PowerShell в редактор, за да прегледате допълнителна информация и приложената логика.
       - Запишете и двете стойности на ИД на група за защита, генерирани от този скрипт, защото ще ги използваме в скрипта `ByolSetup.ps1`.

        > [!NOTE]
        > Създаването на група за защита може да бъде деактивирано на вашия наемател. В такъв случай би била необходима ръчна настройка и администраторът ви Azure AD ще трябва да даде възможност за [създаване на](/azure/active-directory/enterprise-users/groups-self-service-management) група за защита.

    2. `ByolSetup.ps1`
        - Трябва *съхранение Blob Data Owner* разрешения на ниво акаунт за съхранение / контейнер за изпълнение на този скрипт или този скрипт ще създаде един за вас. Задачата ви за роля може да бъде премахната ръчно след успешно изпълнение на скрипта.
        - Този powerShell скрипт добавя необходимия контрол на достъпа на базата на толе (RBAC) за Microsoft Dataverse услугата и всякакви Dataverse базирани бизнес приложения. Също така актуализира списъка за контрол на достъпа (ACL) на контейнера CustomerInsights за групите за защита, създадени със скрипта `CreateSecurityGroups.ps1`. Групата "Сътрудник" ще има *разрешение от RWX*, а групата "Читатели" ще има *разрешение само за R-X*.
        - Изпълнявайте този скрипт powerShell в Windows PowerShell, като предоставите ИД на абонамент за Azure, съдържащ вашето Azure Data Lake Storage, име на акаунт за съхранение, име на група ресурси и стойностите на ИД на групата за защита на четец и сътрудник. Отворете скрипта PowerShell в редактор, за да прегледате допълнителна информация и приложената логика.
        - Копирайте изходния низ след успешно изпълнение на скрипта. Изходният низ изглежда така: `https://DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`

2. Въведете изходния низ, копиран отгоре в **полето Идентификатор на разрешения** на стъпката за конфигуриране на средата за Microsoft Dataverse.

:::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Опции за конфигуриране, за да разрешите споделянето на данни от вашите собствени Azure Data Lake Storage с Microsoft Dataverse.":::

### <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>Премахване на съществуваща връзка към Dataverse среда

Когато се свързвате към Dataverse среда, съобщението **за грешка Тази CDS организация вече е прикрепена към друг екземпляр** на Customer Insights означава, че Dataverse средата вече се използва в среда на Customer Insights. Можете да премахнете съществуващата връзка като глобален администратор в Dataverse средата. Може да отнеме няколко часа, за да се населят промените.

1. Отидете на [Power Apps](https://make.powerapps.com).
1. Изберете средата от програмата за избор на среда.
1. Към **решения**
1. Деинсталирайте или изтрийте решението с име **Dynamics 365 Customer Insights Добавка за карта на клиент (Визуализация)**.

ИЛИ

1. Отворете средата си Dataverse.
1. Отидете на **Решения** > **за** разширени настройки.
1. Деинсталирайте **решението CustomerInsightsCustomerCard**.

Ако премахването на връзката е неуспешно поради зависимости, трябва да премахнете зависимостите също. За повече информация вижте [Премахване на зависимости](/power-platform/alm/removing-dependencies).

## <a name="output-entities"></a>Изходни обекти

Някои изходни обекти от "Аналитични данни за клиенти" се предлагат като таблици в Dataverse. Разделите по-долу описват очакваната схема на тези таблици.

- [CustomerProfile](#customerprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Обогатяване](#enrichment)
- [Прогноза](#prediction)
- [Членство в сегмент](#segment-membership)

### <a name="customerprofile"></a>CustomerProfile

Тази таблица съдържа единния потребителски профил от Customer Insights. Схемата за унифициран профил на клиент зависи от обектите и атрибутите, използвани в процеса на обединяване на данни. Схемата на потребителския профил обикновено съдържа подмножество на атрибутите от [Дефиниция на Common Data Model на CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile).

### <a name="alternatekey"></a>AlternateKey

Таблицата AlternateKey съдържа ключове на обектите, участвали в процеса на обединяване.

|Column  |Тип  |Описание  |
|---------|---------|---------|
|DataSourceName    |String         | Име на източник на данни. Например: `datasource5`        |
|EntityName        | String        | Име на обекта в "Аналитични данни за клиенти". Например: `contact1`        |
|AlternateValue    |String         |Алтернативен идентификатор, който се съпоставя с идентификатора на клиента. Пример: `cntid_1078`         |
|KeyRing           | Многоредов текст        | Стойност на JSON  </br> Пример: [{"dataSourceName":" datasource5 ",</br>"entityName":" contact1",</br>"preferredKey":" cntid_1078",</br>"keys":[" cntid_1078"]}]       |
|CustomerId         | String        | Идентификационен номер на унифицирания потребителски профил.         |
|AlternateKeyId     | GUID         |  Детерминиран GUID на AlternateKey, базиран на msdynci_identifier       |
|msdynci_identifier |   String      |   `DataSourceName|EntityName|AlternateValue`  </br> Пример: `testdatasource|contact1|cntid_1078`    |

### <a name="unifiedactivity"></a>UnifiedActivity

Тази таблица съдържа дейности от потребители, които са налични в Customer Insights.

| Column            | Тип        | Описание                                                                              |
|-------------------|-------------|------------------------------------------------------------------------------------------|
| CustomerId        | String      | ИД на профил на клиент                                                                      |
| ActivityId        | String      | Вътрешен идентификатор на активността на клиента (първичен ключ)                                       |
| SourceEntityName  | String      | Име на обекта-източник                                                                |
| SourceActivityId  | String      | Първичен ключ от изходния обект                                                       |
| ActivityType      | String      | Тип семантична дейност или име на персонализирана дейност                                        |
| ActivityTimeStamp | DATETIME    | Времево клеймо на дейността                                                                      |
| Заглавие             | String      | Заглавие или име на дейността                                                               |
| Описание       | String      | Описание на дейността                                                                     |
| URL адрес               | String      | Връзка към външен URL адрес, специфичен за дейността                                         |
| SemanticData      | Низ JSON | Включва списък на двойки ключови стойности за семантични полета за картографиране, специфични за вида дейност |
| RangeIndex        | String      | Отпечатъкът на Unix, използван за сортиране на времевата линия на дейността и ефективни заявки за диапазон |
| mydynci_unifiedactivityid   | GUID | Вътрешен идентификатор на активността на клиента (ActivityId) |

### <a name="customermeasure"></a>CustomerMeasure

Тази таблица съдържа изходни данни за базирани на атрибути на клиента мерки.

| Column             | Тип             | Описание                 |
|--------------------|------------------|-----------------------------|
| CustomerId         | String           | ИД на профил на клиент        |
| Мерки           | Низ JSON      | Включва списък с двойки ключови стойности за име на мярка и стойности за дадения клиент | 
| msdynci_identifier | String           | `Customer_Measure|CustomerId` |
| msdynci_customermeasureid | GUID      | ИД на профил на клиент |


### <a name="enrichment"></a>Обогатяване

Тази таблица съдържа резултатите от процеса на обогатяване.

| Column               | Тип             |  Описание                                          |
|----------------------|------------------|------------------------------------------------------|
| CustomerId           | String           | ИД на профил на клиент                                 |
| EnrichmentProvider   | String           | Имена доставчика за допълването                                  |
| EnrichmentType       | String           | Тип на обогатяване                                      |
| Стойности               | Низ JSON      | Списък на атрибутите, получени в процеса на обогатяване |
| msdynci_enrichmentid | GUID             | Детерминиран GUID, генериран от msdynci_identifier |
| msdynci_identifier   | String           | `EnrichmentProvider|EnrichmentType|CustomerId`         |

### <a name="prediction"></a>Прогноза

Тази таблица съдържа резултатите на предсказанията на модела.

| Column               | Тип        | Описание                                          |
|----------------------|-------------|------------------------------------------------------|
| CustomerId           | String      | ИД на профил на клиент                                  |
| ModelProvider        | String      | Имена доставчика на модела                                      |
| Модел                | String      | Име на модела                                                |
| Стойности               | Низ JSON | Списък на атрибутите, получени от модела |
| msdynci_predictionid | GUID        | Детерминиран GUID, генериран от msdynci_identifier | 
| msdynci_identifier   | String      |  `Model|ModelProvider|CustomerId`                      |

### <a name="segment-membership"></a>Членство в сегмент

Тази таблица съдържа информация за членство в сегмент на профилите на клиента.

| Column        | Вид | Описание                        |
|--------------------|--------------|-----------------------------|
| CustomerId        | String       | ИД на профил на клиент        |
| СегментПрочетир      | String       | Приложение, което публикува сегментите.      |
| СегментМембърствоТип | String       | Тип на клиента този запис на членство в сегмент. Поддържа няколко типа като "Клиент", "Контакт" или "Акаунт". По подразбиране: Клиент  |
| Сегменти       | Низ JSON  | Списък с уникални сегменти профилът на клиента е член на      |
| msdynci_identifier  | String   | Еднозначен идентификатор на записа за членство в сегмент. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | GUID      | Детерминистичен GUID, генериран от`msdynci_identifier`          |

<!--
## FAQ: Update existing environments to use Microsoft Dataverse

Between mid-May 2022 and June 13, 2022, administrators can update the environment settings with a Dataverse environment that Customer Insights can use. On June 13, 2022, your environment will be updated automatically and we'll create a Dataverse environment on your tenant for you.

1. My environment uses my own Azure Data Lake Storage account. Do I still need to update?

   If there's already a Dataverse environment configured in your environment, the update isn't required. If no Dataverse is environment configured, the **Update now** button will create a Dataverse environment and update from the Customer Insights database to a Dataverse database.

1. Will we get extra Dataverse capacity, or will the update use my existing Dataverse capacity?

   - If there's already a Dataverse environment configured in your Customer Insights environment, or connected with other Dynamics 365 or Power Apps applications, the capacity remains unchanged.
   - If the Dataverse environment is new, it will add new storage and database capacity. The capacity added varies per environment and entitlements. You'll get 3 GB for trial and sandbox environment. Production environments get 15 GB.

1. I proceeded with the update and it seems like nothing happened. Is the update complete?

   If the notification in Customer Insights doesn't show anymore, the update is complete. You can check the status of the update by reviewing your environment settings.

1. Why do I still see the banner after completing the update steps?

   It can happen due to an upgrade or refresh failure. Contact support.

1. I received a "Failed to provision Dataverse environment" error after starting the update. What happened?

   It can happen due to an upgrade or refresh failure. Contact support.
   Common causes:
    - Insufficient capacity. There's no more capacity to create more environments. For more information, see [Manage capacity action](/power-platform/admin/capacity-storage#actions-to-take-for-a-storage-capacity-deficit).
    - Region mismatch between tenant region and Customer Insights environment region in the Australia and India regions.
    - Insufficient privileges to provision Dataverse. The users starting the update needs a Dynamics 365 admin role.
    - -->
