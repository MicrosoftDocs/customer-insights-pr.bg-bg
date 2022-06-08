---
title: Как да - Управление на среди
description: Научете как да управлявате съществуващите среди на Customer Insights като администратор."
ms.date: 05/31/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: 62a5856edac5e66e5e42c93313d78fa6826469b3
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: MT
ms.contentlocale: bg-BG
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833479"
---
# <a name="how-to-manage-environments"></a>Как да: Управление на среди

Администраторите [създават](create-environment.md) и управляват среди. Те могат да променят някои настройки в съществуващи среди. Бизнес, тип, регион, опция за съхранение и Dataverse настройки се фиксират след създаването на средата. Ако искате да промените тези настройки, нулирайте средата или създайте нова среда.

## <a name="edit-an-existing-environment"></a>Редактиране на съществуваща среда

Можете да редактирате някои подробности на съществуващите среди.

1. Изберете инструмент за избор **Среда** в заглавката на приложението.

1. Изберете иконата за **редактиране**.

   :::image type="content" source="media/edit-environment.png" alt-text="Икона за редактиране на настройките на средата.":::

1. В **Редактиране на среда** можете да актуализирате настройките на средата.

За да започнете със свежа среда, вижте [Създаване на нова среда](create-environment.md).

## <a name="change-the-owner-of-an-environment"></a>Промяна на собственика на среда

Няколко потребители могат да имат администраторски разрешения, но само един потребител е собственик на среда. По подразбиране администраторът е този, който първоначално създава среда. Като администратор на среда можете да присвоите собственост на друг потребител с администраторски разрешения.

1. Изберете инструмент за избор **Среда** в заглавката на приложението.

1. Изберете иконата за **редактиране**.

1. В полето Редактиране на **средата** преминете към стъпката **Основна информация**.

1. В полето **Промяна на собственика на средата** изберете новия собственик на средата.  

1. Изберете **Преглед и завършване**, след което **Актуализирайте**, за да приложите промените.

## <a name="claim-ownership-of-an-environment"></a>Претендиране на собственост върху среда

Ако потребителският акаунт на собственика е изтрит или спрян, средата няма да има собственик. Всеки администратор потребител може да претендира за собствеността и да стане новият собственик. Те могат да продължат да притежават околната среда или [да променят собствеността на друг администратор](#change-the-owner-of-an-environment).

За да заявите собственост, **изберете бутона "Вземи собствеността** ", който се показва в горната част на всяка страница в "Статистика за клиенти", когато първоначалният собственик е напуснал организацията.

## <a name="reset-an-existing-environment-preview"></a>Нулиране на съществуваща среда (Визуализация)

Като собственик на среда можете да нулирате среда в празно състояние, ако искате да изтриете всички конфигурации и да премахнете поглъщането на данните.

1. Изберете инструмент за избор **Среда** в заглавката на приложението.

1. Изберете средата, която искате да нулирате, и изберете вертикалното елипсис (&vellip;).

1. Изберете опцията **Нулиране**.

   :::image type="content" source="media/reset-environment.png" alt-text="Контрола за нулиране на среда.":::

1. Изберете дали искате да нулирате цялата среда, всичко, с изключение на източниците на данни, или нещо, което е конфигурирано в горната част на потребителския профил на унифициран клиент.

1. За да потвърдите, въведете името на средата и изберете **Нулиране**.

## <a name="delete-an-existing-environment"></a>Изтрийте съществуваща среда

Като собственик на среда можете да изтриете среда, която администрирате.

1. Изберете инструмент за избор **Среда** в заглавката на приложението.

1. Изберете средата, която искате да нулирате, и изберете вертикалното елипсис (&vellip;). 

1. Изберете опцията **Изтриване**.

   :::image type="content" source="media/delete-environment.png" alt-text="Контрола за изтриване на средата.":::

1. За да потвърдите изтриването, въведете името на средата и изберете **Изтриване**.

> [!IMPORTANT]
> Изтриването на среда не премахва връзката към Dataverse среда. Ако планирате да свържете същата Dataverse среда с нова среда на Customer Insights в бъдеще, трябва да премахнете тази връзка Научете как да [премахнете съществуваща връзка към Dataverse среда](customer-insights-dataverse.md#remove-an-existing-connection-to-a-dataverse-environment).

[!INCLUDE [footer-include](includes/footer-banner.md)]