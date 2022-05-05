---
title: Донесете свой собствен хранилище за ключове на Azure, за да управлявате тайни
description: Научете как да конфигурирате Customer Insights да използва вашия собствен хранилище за ключове на Azure.
ms.date: 10/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: 9eb06a1190fe4e8012ecd3d6742b8b3f5f4d6349
ms.sourcegitcommit: cf74b8c20d88eb96e1ac86e18cd44fe27aad5ab9
ms.translationtype: MT
ms.contentlocale: bg-BG
ms.lasthandoff: 04/28/2022
ms.locfileid: "8653464"
---
# <a name="bring-your-own-azure-key-vault-preview"></a>Донесете свой собствен ключ за хранилище на Azure (предварителен преглед)

Свързването на специализиран [трезор](/azure/key-vault/general/basic-concepts) за ключове на Azure с среда на Customer Insights помага на организациите да отговорят на изискванията за съответствие.
Специалното хранилище за ключове може да се използва за поставяне и използване на тайни в границите за съответствие на организацията. Клиентските аналитични данни могат да използват тайните в хранилището за ключове на Azure, за да [настроите връзки към](connections.md) системи на трети страни.

## <a name="link-the-key-vault-to-the-customer-insights-environment"></a>Свързване на ключовия трезор към средата "Аналитични данни за клиенти"

### <a name="prerequisites"></a>Предварителни изисквания

За да конфигурирате хранилището за ключове в "Аналитични данни за клиенти", трябва да бъдат изпълнени следните предпоставки:

- Трябва да имате активен абонамент за Azure.

- Имате [роля на администратор](permissions.md#admin) в "Аналитични данни за клиенти". Научете повече за [потребителските разрешения в "Аналитични данни за](permissions.md#assign-roles-and-permissions) клиенти".

- Вие имате роли [Сътрудник](/azure/role-based-access-control/built-in-roles#contributor) и [Администратор за потребителски достъп](/azure/role-based-access-control/built-in-roles#user-access-administrator) в хранилището с ключове или групата ресурси, към която принадлежи хранилището с ключове. За повече информация отидете на [Добавяне или премахване на присвояване на роли на Azure чрез портала на Azure](/azure/role-based-access-control/role-assignments-portal). Ако нямате ролята на администратор на достъп за потребители в хранилището с ключове, трябва да настроите ролевите разрешения за контрол на достъпа за главен за услугата Azure за Dynamics 365 Customer Insights отделно. Следвайте стъпките, за да [използвате главен служител на Azure](connect-service-principal.md) за хранилището с ключове, което трябва да бъде свързано.

- Трезорът с ключове трябва да има **забранена** защитна стена на хранилището за ключове.

- Ключовият трезор е в същото [местоположение](https://azure.microsoft.com/global-infrastructure/geographies/#overview) на Azure като средата на "Аналитични данни за клиенти". Регионът на околната среда в Клиентските аналитични данни е посочен в **AdminSystemAboutRegion** > **·** > **·** > **·**.

### <a name="link-a-key-vault-to-the-environment"></a>Свържете ключов трезор със средата

1. Отидете **на AdminSecurity** > **и** след това изберете раздела **Ключ хранилище**.
1. На плочката **Хранилище за ключове** изберете **Настройка**.
1. Изберете **Абонамент**.
1. Изберете хранилище за ключове от **Хранилището за ключове** падащ списък. Ако се показват твърде много ключови трезори, изберете група ресурси, за да ограничите резултатите от търсенето.
1. Приемете декларацията за **Поверителност и съответствие на данните**.
1. Изберете **Записване**.

:::image type="content" source="media/set-up-azure-key-vault.png" alt-text="Стъпки за настройване на свързан ключ хранилище в Customer Insights.":::

Плочката **Трезор за ключове** сега показва свързаното име на хранилището с ключове, групата ресурси и абонамента. Той е готов за използване при настройката на връзката.
За подробности за това кои разрешения на ключовия трезор се предоставят на Customer Insights отидете [на Разрешения, предоставени на трезора](#permissions-granted-on-the-key-vault) за ключове, по-късно в тази статия.

## <a name="use-the-key-vault-in-the-connection-setup"></a>Използвайте хранилището за ключове в настройките за връзка

Когато [създавате връзки](connections.md) към системи на трети страни, тайните от свързания Key Vault могат да се използват за конфигуриране на връзките.

1. Отидете на **Администратор** > **Връзки**.
1. Изберете **Добавяне на връзка**.
1. За поддържаните типове връзки, **Използвайте хранилище за ключове** превключвателят е наличен, ако сте свързали хранилище за ключове.
1. Вместо да въвеждате тайната ръчно, можете да изберете тайното име, което сочи към тайната стойност в хранилището за ключове.

:::image type="content" source="media/use-key-vault-secret.png" alt-text="Панел за връзка с SFTP връзка, която използва секрет на Key Vault.":::

## <a name="supported-connection-types"></a>Поддържани типове връзки

Следните връзки за [експортиране](export-destinations.md) се поддържат:

* [ActiveCampaign](export-active-campaign.md)
* [Autopilot](export-autopilot.md)
* [DotDigital](export-dotdigital.md)
* [Google Ads](export-google-ads.md)
* [Klaviyo](export-klaviyo.md)
* [LiveRamp](export-liveramp.md)
* [Marketo](export-marketo.md)
* [Omnisend](export-omnisend.md)
* [Salesforce Marketing Cloud](export-salesforce.md)
* [Sendgrid](export-sendgrid.md)
* [Sendinblue](export-sendinblue.md)
* [SFTP](export-sftp.md)

## <a name="permissions-granted-on-the-key-vault"></a>Разрешения, предоставени на ключовия трезор

Следните разрешения се предоставят на Customer Insights на свързан ключ хранилище, ако е разрешена или [правилата](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) за достъп до Key Vault, или [контрола](/azure/key-vault/general/rbac-guide?tabs=azure-cli) за достъп въз основа на роля на Azure.

### <a name="key-vault-access-policy"></a>Политика за достъп до хранилище за ключове

| Тип        | Разрешения          |
| ----------- | -------------------- |
| Клавиш         | [Вземете ключове](/rest/api/keyvault/get-keys), [Вземете ключ](/rest/api/keyvault/get-key)                                 |
| Секрет      | [Вземете тайни](/rest/api/keyvault/get-secrets), [Вземете тайна](/rest/api/keyvault/get-secret)                     |
| Сертификат | [Вземете сертификати](/rest/api/keyvault/get-certificates), [Вземете сертификат](/rest/api/keyvault/get-certificate) |

Предходните стойности са минималните за изброяване и четене по време на изпълнение.

### <a name="azure-role-based-access-control"></a>Azure контрол на достъпа, базиран на роли

Ключовите хранилище четец и ключови хранилище тайни потребителски роли ще бъдат добавени за Клиентски прозрения. За подробности относно тези роли отидете на [Вградени роли в Azure за операции с равнище на данни в хранилище за ключове](/azure/key-vault/general/rbac-guide?tabs=azure-cli).

## <a name="recommendations"></a>Препоръки

- Използвайте отделен или специализиран ключ хранилище, което съдържа само тайните, необходими за Customer Insights. Прочетете повече за това защо [се препоръчват отделни хранилища с ключове](/azure/key-vault/general/best-practices#why-we-recommend-separate-key-vaults).

- Следвайте [най-добрите практики за използване на хранилище за ключове](/azure/key-vault/general/best-practices#turn-on-logging) за опции за контрол на достъпа, архивиране, одит и възстановяване.

## <a name="frequently-asked-questions"></a>Често задавани въпроси

### <a name="can-customer-insights-write-secrets-or-overwrite-secrets-into-the-key-vault"></a>Може ли Customer Insights да напише тайни или да презапише тайни в ключовия трезор?

Не. Само разрешенията за четене и списък, очертани в [раздела с предоставени разрешения](#permissions-granted-on-the-key-vault) по-рано в тази статия, се предоставят на "Аналитични данни за клиенти". Системата не може да добавя, изтрива или презаписва тайни в хранилището за ключове. Това е и причината, поради която не можете да въведете идентификационни данни, когато дадена връзка използва хранилище за ключове.

### <a name="can-i-change-a-connection-from-using-key-vault-secrets-to-default-authentication"></a>Мога ли да променя връзка от използване на тайни на хранилище за ключове към удостоверяване по подразбиране?

Не. Не можете да се върнете към връзка по подразбиране, след като сте я конфигурирали, като използвате тайна от свързано хранилище за ключове. Създайте отделна връзка и изтрийте старата, ако вече не се нуждаете от нея.

### <a name="how-can-i-revoke-access-to-a-key-vault-for-customer-insights"></a>Как мога да отменя достъпа до ключов трезор за Customer Insights?

В зависимост от това дали [Политика за достъп до хранилище за ключове](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) или [Azure контрол на достъпа, базиран на роли](/azure/key-vault/general/rbac-guide?tabs=azure-cli) е разрешено, трябва да премахнете разрешенията за принципала на услугата `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` с името `Dynamics 365 AI for Customer Insights`. Всички връзки, които използват хранилището за ключове, ще спрат да работят.

### <a name="a-secret-thats-used-in-a-connection-got-removed-from-the-key-vault-what-can-i-do"></a>От хранилището за ключове е премахната тайна, използвана във връзка. Какво мога да направя?

В "Аналитични данни за клиенти" се появява известие, когато конфигурирана тайна от хранилището за ключове вече не е достъпна. Активиране [неокончателно изтриване](/azure/key-vault/general/soft-delete-overview) върху хранилището за ключове за възстановяване на тайни, ако те са случайно премахнати.

### <a name="a-connection-doesnt-work-but-my-secret-is-in-the-key-vault-what-might-be-the-cause"></a>Връзката не работи, но тайната ми е в хранилището за ключове. Каква може да е причината?

В "Аналитични данни за клиенти" се появява известие, когато няма достъп до хранилището за ключове. Причината може да е:

- Разрешенията за директора на услугата "Аналитични данни за клиенти" са премахнати. Те трябва да бъдат възстановени ръчно.

- Защитната стена в хранилището за ключове е активирана. Защитната стена трябва да бъде деактивирана, за да направи ключа трезор достъпен за Customer Insights отново.
