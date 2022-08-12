---
title: Използване на съгласието на клиента
description: Почитайте предпочитанията за съгласие на клиентите в "Аналитични данни за клиенти", като импортирате данни за съгласие.
ms.date: 06/07/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 99fe24cb47a8c20f629182d9a1c6adfd36a1eaf7
ms.sourcegitcommit: c45c3e044034bf866b0662f80a59166cee4ababe
ms.translationtype: MT
ms.contentlocale: bg-BG
ms.lasthandoff: 07/22/2022
ms.locfileid: "9188034"
---
# <a name="use-customer-consent"></a>Използване на съгласието на клиента

Регламентите за защита на данните и неприкосновеността на личния живот предоставят на физическите лица правото да управляват как дадена организация използва личните си данни. Примери за такива регламенти са Общият регламент относно защитата на данните в Европейския съюз или Калифорнийският закон за неприкосновеността на личния живот на потребителите в САЩ. Тези разпоредби позволяват на хората да се откажат от това личните им данни да се събират, обработват от или споделят с трети лица.  

Клиентите могат да изберат да оттеглят или удържат съгласието си за конкретни форми на контакт. Те могат също така да поискат да ги откажете от събирането, съхранението, използването или продажбата на личните им данни. Важно е вашата организация да почита всички предпочитания за съгласие и поверителност на клиентите.  

Dynamics 365 Customer Insights ви помага да почитате исканията на клиентите си, като импортирате и запазвате предпочитанията им като част от унифицираните профили на клиенти.

Ако данните за съгласието се съхраняват отделно от профилите ви на клиенти, [добавете данните за съгласието си като нов източник на данни](#import-and-unify-consent-data). Към процеса на обединяване на данни се добавя източник на данни, който съдържа данните за съгласието. Успешното обединение на данните за съгласие и профилите на клиентите след това води до единни клиентски профили, които съдържат информацията за съгласието. За профили на клиенти, които вече съдържат информация за съгласие, преминете директно към раздела за данни [за съгласие за](#use-consent-data) използване.

## <a name="prerequisites"></a>Предварителни изисквания

Следната информация трябва да бъде налична във вашите изходни данни, за да се унифицират данните за съгласие с други профили на клиенти:

- алтернативен ключ да нанесете информацията за съгласието към потребителски профили в "Аналитични данни за клиенти". Например имейл адрес или телефонен номер.
- Стойност на съгласието за определяне на състоянието на съгласието на клиента.

Обмислете да добавите следната *незадължителна* информация:

- Основен ключ за актуализиране на състоянието на съгласието, ако клиент поиска промяна.
- Тип съгласие, ако има повече от един начин за обработка на информация за клиента.
- Дата на съгласие или друг вид данни, имащи отношение към вашите сценарии за съгласие.

Примерна таблица на проста база данни за съгласие с множество опции за съгласие:

|ИД на съгласие (първичен ключ)   |Имейл (алтернативен ключ)  |Опция за съгласие  |Стойност на съгласието  |
|---------|---------|---------|---------|
|1    |  holly@contoso.com       |  Бюлетин       |  False       |
|2    |  holly@contoso.com       |  Актуализации на продукта       |  True       |
|3    |  frank@contoso.com       |  Бюлетин       | True        |
|4    |  frank@contoso.com       |  Актуализации на продукта       |  False       |

## <a name="import-and-unify-consent-data"></a>Импортиране и обединение на данни за съгласие

Импортиране на данни за съгласие по същия начин, по който сте погълнали други източници на данни в "Аналитични данни за клиенти". За повече информация относно поддържаните източници на данни и как да ги импортирате вижте [Преглед на източниците на данни](data-sources.md).

За повече информация относно обединяването на източниците ви на данни вижте [Преглед](data-unification.md) на обединяването на данни.

## <a name="use-consent-data"></a>Използване на данни за съгласие

След като данните ви за съгласие са част от вашите единни профили на клиенти, можете да ги използвате в "Аналитични данни за клиенти". Например създайте сегмент с правило, за да сте сигурни, че почитате предпочитанията на клиентите си за поверителност и защита на данните. Правила, поддържащи предпочитания за съгласие, се използват за изключване на потребителите от сегмент, базиран на атрибути на профила. Добавете правило към сегмент, който изключва профили на клиенти, които не са предоставили съгласие за контакт.

Позовавайки се на примерната таблица по-горе, даден сегмент би могъл да съдържа това правило:`Consent option=Newsletter & Consent value=True`. Тази конфигурация води до сегмент, който почита предпочитанията за контакт за изпращане на бюлетин.

За повече информация относно градивните сегменти вижте [Създаване на сегменти](segment-builder.md).

След като сегментът бъде създаден, можете да използвате една от многото [опции](export-destinations.md) за експортиране, за да използвате сегмента в други приложения.

## <a name="ensure-updated-consent-status"></a>Осигуряване на актуализирано състояние на съгласието

Важно е да запазите състоянието на съгласието за клиентите си актуализирано. Планираното обновяване в Customer Insights винаги импортира най-новото състояние на вашите източници на данни. След това тази информация се обработва чрез обединяване на данни и води до актуализирани профили на клиенти. След това тези актуализирани профили се използват за обновяване на сегменти, за да се уверите, че работите с най-актуалната информация.

С други думи, уверете се, че изходните данни, които се импортират в Customer Insights, винаги имат най-новата информация.

За повече информация вижте [Обновете сегментите ръчно](segments.md#refresh-segments) или [конфигурирайте планирано обновяване](system.md#schedule-tab).

[!INCLUDE [footer-include](includes/footer-banner.md)]