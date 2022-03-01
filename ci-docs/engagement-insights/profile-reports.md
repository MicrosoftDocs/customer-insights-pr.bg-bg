---
title: Активиране на отчети за потребителски профили
description: Как да създадете отчети за потребителски профили, групирани по пол, възраст и окръг или регион на произход.
author: darrinw-docs
ms.reviewer: mhart
ms.author: darrinw
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: bf2ec67c9fb99918b87841d3c0b131934e31b58b
ms.sourcegitcommit: 0ceb46c4f57ab49d3a2ebb1c8a816bbafe979e3d
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 09/09/2021
ms.locfileid: "7486107"
---
# <a name="out-of-box-profile-reports"></a>Предварително подготвени отчети на профил

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Отчетът е колекция от визуализиране на данни, която да ви помага да разбирате поведението на потребителите. Чрез свързване с аналитични данни за аудитория на Customer Insights, статистика за ангажираността може да покаже отчет с информация за единни клиентски профили. Този отчет включва броя на потребителските профили, групирани по пол, възраст и географско местоположение.

## <a name="prerequisites"></a>Предварителни изисквания

Средата за аналитични данни за аудитория трябва да съхранява данни в управляван от клиента акаунт на Azure Data Lake Storage.

Ако използвате пробна версия на способността за аналитични данни за аудитория или среда в езерото с данни на Customer Insights, [свържете се с нас](https://go.microsoft.com/fwlink/?linkid=2145734) за помощ.  


## <a name="enable-the-customer-profile-report"></a>Активирайте отчета за потребителския профил

Администратор на среда трябва да [свържете прозрения за ангажираност и прозрения за аудиторията](integrate-audience-insights-engagement-insights.md).

След като посочи подробности за връзката, администраторът може да предостави достъп на други хора в организацията, за да види отчета. Администраторът на средата, който настройва връзката, автоматично има достъп до отчета. 

След завършване на връзката, функцията **Профили** ще бъде налична в левия навигационен прозорец. 

- Отидете на **Откриване** > **Профили**, за да видите отчета.

Отчетът **Профили** съдържа визуализации за пола, възрастта и географското местоположение на свързаните клиентски профили.

:::image type="content" source="media/customer-profiles.png" alt-text="Отчет за клиентски профил.":::

[!INCLUDE[footer-include](../includes/footer-banner.md)]