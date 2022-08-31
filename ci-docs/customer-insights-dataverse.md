---
title: Работа с данни на Customer Insights в Microsoft Dataverse
description: Научете как да свържете "Аналитични данни за клиенти" и Microsoft Dataverse да разберете изходните обекти, които се експортират в Dataverse.
ms.date: 08/15/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 0d536259f310b41fe12922baeebdc4569937db08
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: bg-BG
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303816"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Работа с данни на Customer Insights в Microsoft Dataverse

Customer Insights предоставя опция за предоставяне на изходни обекти в [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). Тази интеграция дава възможност за лесно споделяне на данни и персонализирано развитие чрез подход с нисък код/без код. Изходните [обекти](#output-entities) са налични като таблици в Dataverse среда. Можете да използвате данните за всяко друго приложение въз основа на Dataverse таблици. Тези таблици дават възможност за сценарии като автоматизирани работни потоци през Power Automate или изграждане на приложения с Power Apps.

Свързването с вашата Dataverse среда също ви дава възможност да [поглъщате данни от локален източници на данни с помощта на Power Platform потоци от данни и шлюзове](connect-power-query.md#add-data-from-on-premises-data-sources).

## <a name="prerequisites"></a>Предварителни изисквания

- Клиентските аналитични данни и Dataverse среди трябва да се хостват в един и същ регион.
- Глобална роля на администратор, настроена в околната Dataverse среда. Проверете дали тази [Dataverse среда е свързана с](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) определени групи за защита и се уверете, че сте добавени към тези групи за защита.
- Никоя друга среда на Customer Insights, която вече е свързана със Dataverse средата, която искате да свържете. Научете как да [премахнете съществуваща връзка към Dataverse среда](#remove-an-existing-connection-to-a-dataverse-environment).
- Microsoft Dataverse Среда, свързана към един акаунт за съхранение, ако конфигурирате средата да [използва вашия Azure Data Lake Storage](own-data-lake-storage.md).

## <a name="dataverse-storage-capacity-entitlement"></a>Dataverse право на капацитет за съхранение

Абонамент за Customer Insights ви дава право на допълнителен капацитет за съществуващия [Dataverse капацитет](/power-platform/admin/capacity-storage) за съхранение на вашата организация. Добавеният капацитет зависи от броя на профилите, които абонаментът Ви използва.

**Пример:**

Ако приемем, че получавате 15 GB място за съхранение на база данни и 20 GB място за съхранение на файлове на 100 000 клиентски профила. Ако абонаментът ви включва 300 000 клиентски профила, общият ви капацитет за съхранение е 45 GB (3 x 15 GB) място за съхранение на база данни и място за съхранение на файлове 60 GB (3 x 20 GB). По същия начин, ако имате b-to-B абонамент с 30K акаунти, общият ви капацитет за съхранение е 45 GB (3 x 15 GB) място за съхранение на база данни и 60 GB място за съхранение на файлове (3 x 20 GB).

Капацитетът на регистрационния файл не е постъпково и фиксиран за вашата организация.

За повече информация относно подробните права на капацитет вижте [Ръководство](https://go.microsoft.com/fwlink/?LinkId=866544) за лицензиране на Dynamics 365.

## <a name="connect-a-dataverse-environment-to-customer-insights"></a>Свързване на Dataverse среда към "Аналитични данни за клиенти"

Стъпката **Microsoft Dataverse** ви позволява да свържете Customer Insights с вашата Dataverse среда, докато [създавате среда](create-environment.md) на Customer Insights.

:::image type="content" source="media/dataverse-provisioning.png" alt-text="споделяне на данни с Microsoft Dataverse автоматично активирани за нови среди.":::

1. Предоставете URL адреса на средата си Dataverse или оставете празен, за да имате създаден за вас такъв.

   > [!NOTE]
   > След установяване на връзката между Customer Insights и Dataverse, не променяйте името на организацията за Dataverse средата. Името на организацията се използва в Dataverse URL адреса и променено име прекъсва връзката с Customer Insights.

   [Power Platform администраторите могат да контролират кой може да създаде нови Dataverse среди](/power-platform/admin/control-environment-creation). Ако се опитвате да настроите нова среда на Customer Insights и не можете, администраторът може да е забранил създаването на Dataverse среди за всички, с изключение на администраторите.

1. Ако използвате собствен акаунт за съхранение на data lake:
   1. Изберете **Разрешаване на споделянето на** данни с Dataverse.
   1. Въведете идентификатора **"Разрешения"**. За да получите идентификатора на разрешението, [разрешете споделянето на данни с Dataverse от вашите собствени Azure Data Lake Storage](#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview).

## <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Разрешаване на споделянето на данни с Dataverse от вашите собствени Azure Data Lake Storage (визуализация)

В [собствения си профил Azure Data Lake Storage проверете потребителя настройка на средата на Customer Insights има поне](own-data-lake-storage.md) Съхранение Blob Данни Reader **разрешения на** контейнера в `customerinsights` акаунта за съхранение.

### <a name="limitations"></a>Ограничения

- Само съпоставяне "едно към едно" между Dataverse организация и Azure Data Lake Storage акаунт. След като Dataverse дадена организация е свързана към акаунт за съхранение, тя не може да се свърже с друг акаунт за съхранение. Това ограничение предотвратява Dataverse попълването на няколко акаунта за съхранение.
- Споделянето на данни няма да работи, ако е необходима настройка на Azure private Link за достъп до профила Ви Azure Data Lake Storage, защото е зад защитна стена. Dataverse в момента не поддържа връзката с частни крайни точки чрез Private Link.

### <a name="set-up-security-groups-on-your-own-azure-data-lake-storage"></a>Настройване на групи за защита сами Azure Data Lake Storage

1. Създайте две групи за защита на вашия абонамент за Azure - една **група за защита на Reader** и една **група за защита на contributor** и задайте Microsoft Dataverse услугата като собственик и за двете групи за защита.

1. Управление на списъка за контрол на достъпа (ACL) на контейнера `customerinsights` във вашия акаунт за съхранение чрез тези групи за защита.
   1. Добавете Microsoft Dataverse услугата и всякакви Dataverse базирани бизнес приложения като Dynamics 365 Marketing към групата за защита на **Reader** с **разрешения само** за четене.
   1. Добавете *само* приложението "Аналитични данни за клиенти" към групата за защита на **"Сътрудник** ", за да предоставите както разрешения за четене, така **и за запис**, за да пишете профили и аналитични данни.

### <a name="set-up-powershell"></a>Настройване на PowerShell

Настройване на PowerShell за изпълнение на powerShell скриптове.

1. Инсталирайте най-новата версия на [Azure Active Directory PowerShell за графика](/powershell/azure/active-directory/install-adv2).
   1. На компютъра изберете клавиша Windows на клавиатурата, потърсете **Windows PowerShell** и изберете **Изпълняване като администратор**.
   1. В прозореца PowerShell, който се отваря, въведете `Install-Module AzureAD`.

1. Импортиране на три модула.
   1. В прозореца PowerShell въведете `Install-Module -Name Az.Accounts` и следвайте стъпките.
   1. Повторете за `Install-Module -Name Az.Resources` и `Install-Module -Name Az.Storage`.

### <a name="execute-powershell-scripts-and-obtain-the-permission-identifier"></a>Изпълнение на powerShell скриптове и получаване на идентификатор на разрешение

1. Изтеглете двата скрипта powerShell, които трябва да изпълните от gitHub репото [на](https://github.com/trin-msft/byol) нашия инженер.
   - `CreateSecurityGroups.ps1`: Изисква разрешения за администратор на наемателя.
   - `ByolSetup.ps1`: Изисква Съхранение Blob Data Owner разрешения на ниво акаунт за съхранение/контейнер. Този скрипт ще създаде разрешението за вас. Задачата ви за роля може да бъде премахната ръчно след успешно изпълнение на скрипта.

1. Изпълни `CreateSecurityGroups.ps1` в Windows PowerShell, като предоставиш ИД на абонамент за Azure, съдържащ твоя Azure Data Lake Storage. Отворете скрипта PowerShell в редактор, за да прегледате допълнителна информация и внедрената логика.

   Този скрипт създава две групи за защита на вашия абонамент за Azure: една за групата читатели и друга за групата "Сътрудник". Microsoft Dataverse услуга е собственик както за тези групи за сигурност.

1. Запишете и двете стойности на ИД на група за защита, генерирани от този скрипт, да се използват в скрипта `ByolSetup.ps1`.

   > [!NOTE]
   > Създаването на група за защита може да бъде деактивирано на вашия наемател. В такъв случай би била необходима ръчна настройка и администраторът ви Azure AD ще трябва да даде възможност за [създаване на](/azure/active-directory/enterprise-users/groups-self-service-management) група за защита.

1. Изпълнявайте `ByolSetup.ps1` в Windows PowerShell, като предоставите ИД на абонамент за Azure, съдържащ вашето Azure Data Lake Storage, име на акаунт за съхранение, име на група ресурси и стойностите на ИД на групата за защита на четец и сътрудник. Отворете скрипта PowerShell в редактор, за да прегледате допълнителна информация и внедрената логика.

   Този скрипт добавя необходимия ролево базиран контрол на достъпа за Microsoft Dataverse услугата и всякакви Dataverse базирани бизнес приложения. Той също така актуализира списъка за контрол на достъпа (ACL) на `customerinsights` контейнера за групите за защита, създадени със скрипта `CreateSecurityGroups.ps1`. На групата "Сътрудник" се дава *разрешение от RWX* и на Readers group се дава *разрешение само r-x*.

1. Копирайте изходния низ, който изглежда като: `https://DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`

1. Въведете копирания изходен низ в **полето Идентификатор на разрешения** на стъпката за конфигуриране на средата за Microsoft Dataverse.

   :::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Опции за конфигуриране, за да разрешите споделянето на данни от вашите собствени Azure Data Lake Storage с Microsoft Dataverse.":::

## <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>Премахване на съществуваща връзка към Dataverse среда

Когато се свързвате към Dataverse среда, съобщението **за грешка Тази CDS организация вече е прикрепена към друг екземпляр** на Customer Insights означава, че Dataverse средата вече се използва в среда на Customer Insights. Можете да премахнете съществуващата връзка като глобален администратор в Dataverse средата. Може да отнеме няколко часа, за да се населят промените.

1. Отидете на [Power Apps](https://make.powerapps.com).
1. Изберете средата от програмата за избор на среда.
1. Отидете на **Решения**.
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
| ActivityTimeStamp | DATETIME    | Печат за време за активност                                                                      |
| Обръщение             | String      | Заглавие или име на дейността                                                               |
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

| Column        | Тип | Описание                        |
|--------------------|--------------|-----------------------------|
| CustomerId        | String       | ИД на профил на клиент        |
| СегментПрочетир      | String       | Приложение, което публикува сегментите.      |
| СегментМембърствоТип | String       | Тип клиент за този запис на членство в сегмент. Поддържа няколко типа като "Клиент", "Контакт" или "Акаунт". По подразбиране: Клиент  |
| Сегменти       | Низ JSON  | Списък с уникални сегменти профилът на клиента е член на      |
| msdynci_identifier  | String   | Еднозначен идентификатор на записа за членство в сегмент. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | GUID      | Детерминистичен GUID, генериран от`msdynci_identifier`          |


[!INCLUDE [footer-include](includes/footer-banner.md)]
