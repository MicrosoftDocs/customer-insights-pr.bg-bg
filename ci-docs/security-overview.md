---
title: Конфигуриране на настройките за защита
description: Научете за настройките за защита в Dynamics 365 Customer Insights.
ms.date: 08/02/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: ea21163d7dd05370de28ca8340ae9583846adb26
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: bg-BG
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246049"
---
# <a name="configure-security-settings"></a>Конфигуриране на настройките за защита

Управление на API ключове, достъп до клиентски данни и настройване на Azure частна връзка.

## <a name="manage-api-keys"></a>Управление на API ключове

Преглеждайте и управлявайте ключовете, за да използвате API [на](apis.md) Customer Insights с данните във вашата среда.

1. Отидете на **Системна** > **защита** и изберете раздела **API**.

1. Ако API достъпът до средата не е настроен, изберете **Разрешаване**. Или, за да блокирате API достъпа до околната среда, изберете **Забрани** и потвърдете.

1. Управление на първичните и вторичните API ключове:

   1. За да покажете основния или вторичния API ключ, изберете символа **Показване**.

   1. За да копирате основния или вторичния API ключ, изберете символа **Копиране**.

   1. За да създадете нови първични или вторични API ключове, изберете **Регенериране на** първични или **Регенериране на вторични**.

## <a name="securely-access-customer-data-with-customer-lockbox-preview"></a>Защитен достъп до клиентски данни с Клиент Lockbox (Предварителен преглед)

"Аналитични данни за клиенти" използва възможността за блокиране на Power Platform клиенти. Customer Lockbox предоставя интерфейс за преглед и одобряване (или отхвърляне) на заявки за достъп до данни. Тези заявки възникват, когато е необходим достъп на данни до клиентски данни за разрешаване на случай на поддръжка. За да използвате тази функция, Customer Insights трябва да има съществуваща връзка към Microsoft Dataverse среда във вашия наемател.

За повече информация относно Lockbox на клиента вижте обобщението [на](/power-platform/admin/about-lockbox#summary) Lockbox на Power Platform клиента. Статията описва [също работния поток](/power-platform/admin/about-lockbox#workflow) и необходимата [настройка](/power-platform/admin/about-lockbox#enable-the-lockbox-policy), за да разрешите Lockbox на клиента.

> [!IMPORTANT]
> Глобалните администратори за Power Platform или Power Platform администраторите могат да одобрят заявките на Customer Lockbox, издадени за "Аналитични данни за клиенти".

## <a name="set-up-an-azure-private-link"></a>Настройване на частна връзка на Azure

[Azure Private Link](/azure/private-link/private-link-overview) нека клиентските аналитични данни се свържат с профила ви Azure Data Lake Storage по частна крайна точка във вашата виртуална мрежа. За данни в акаунт за съхранение, който не е изложен на публичния интернет, Private Link позволява връзката с тази ограничена мрежа.

> [!IMPORTANT]
> Изискване за минимална роля за настройване на връзка с частна връзка:
>
> - Аналитични данни за клиенти: администратор
> - Вградена роля на Azure: [Сътрудник на акаунт за съхранение](/azure/role-based-access-control/built-in-roles#storage-account-contributor)
> - Разрешения за персонализирана роля в Azure: [Microsoft.Storage/съхранениеБроя/четене и Microsoft.Storage/storageAccounts/PrivateEndpointConnectionsОдобрение/действие](/azure/role-based-access-control/resource-provider-operations#microsoftstorage)

1. В "Аналитични данни за клиенти" отидете **в Защита на администратора** > **и** изберете **раздела Лични връзки**.

1. Изберете **Добавяне на частна връзка**.

   Прозорецът "Добавяне на **частна връзка"** изброява акаунти за съхранение от вашия наемател, които имате разрешения да виждате.

1. Изберете абонамента, групата ресурси и акаунта за съхранение.

1. Прегледайте поверителността на [данните и съответствието](connections.md#data-privacy-and-compliance) и изберете **Съгласен** съм.

1. Изберете **Записване**.

1. Отидете в профила си в Data Lake Storage и отворете връзката, представена на екрана.

1. Одобрят Частната връзка.


[!INCLUDE [footer-include](includes/footer-banner.md)]
