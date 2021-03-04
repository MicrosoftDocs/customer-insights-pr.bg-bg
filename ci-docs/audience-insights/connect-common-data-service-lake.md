---
title: Свържете се с обекти в управлявано хранилище на Common Data Service
description: Импортиране на данни от управлявано хранилище Data Lake в Common Data Service.
ms.date: 09/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.reviewer: adkuppa
ms.openlocfilehash: 18b6cd3fdaf5b738877a73b520b91dbc6ded40de
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: bg-BG
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267784"
---
# <a name="connect-to-data-in-a-common-data-service-managed-data-lake"></a>Свързване с данни в управлявано от Common Data Service хранилище за необработени данни

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Тази статия предоставя информация за това как съществуващите клиенти на Dynamics 365 могат бързо да се свържат със своите аналитични обекти в управляваното хранилище в Common Data Service. Трябва да сте администратор на организация в Common Data Service, за да продължите и да видите списъка с обекти, налични в управляваното хранилище.

## <a name="important-considerations"></a>Важни съображения

Данните, съхранявани в онлайн услуги като Azure Data Lake Storage може да се съхраняват на различно място от това, на което се обработват или съхраняват данни в Dynamics 365 Customer Insights. Чрез импортиране или свързване към данни, съхранявани в онлайн услуги, вие се съгласявате, че данните могат да се прехвърлят и съхраняват в Dynamics 365 Customer Insights. [Научете повече в центъра за сигурност на Microsoft.](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-common-data-service-managed-lake"></a>Свържете се с управлявано от Common Data Service хранилище

1. В статията за аудиторията отидете на **Данни** > **Източници на данни**.

2. Изберете **Добавяне на източник на данни**.

3. Изберете **Свържете се с Common Data Service** и изберете **Напред**.

4. Въведете **Име** за източника на данни и изберете **Напред**. Насоки за име: 
   - Започнете с буква.
   - Използвайте само букви и цифри. Не е разрешено въвеждането на специални знаци и интервали.
   - Използвайте между 3 и 64 знака.

5. Предоставете **Адрес на сървър** за организацията ви на Common Data Service и изберете **Вход**.

   > [!div class="mx-imgBorder"]
   > ![Диалогов прозорец за влизане на адрес на сървър на Common Data Service](media/enter-CDS-org-details.png)

6. Изберете обектите, които искате да поемете от наличния списък.    

   > [!NOTE]
   > Ако някои обекти вече са избрани, те могат да бъдат използвани от други приложения на Dynamics 365 (като например Dynamics 365 Sales Insights или Customer Service Insights). Не можете да променяте този избор. Тези обекти ще бъдат достъпни след създаването на източника на данни.

   > [!div class="mx-imgBorder"]
   > ![Диалогов прозорец, показващ списък с обекти в организация на Common Data Service](media/select-analytical-entities.png)

7. Запазете своя избор, за да започнете да синхронизирате избраните обекти с управлявано от Common Data Service хранилище. Ще намерите ново добавената връзка на страницата **Източници на данни**. Тя ще бъде поставена на опашка за опресняване и ще показва, че единиците се броят като 0, докато всички обекти не се синхронизират.

Само един източник на данни от среда може едновременно да използва същото управлявано хранилище на Common Data Service.

## <a name="edit-a-common-data-service-managed-lake-data-source"></a>Редактиране на управляван от Common Data Service източник на данни на хранилище

Вие редактирате избора на обекти само след като създадете източник на данни. Например, ако в Common Data Service са добавени допълнителни обекти и вие също искате да ги импортирате.    
За да свържете към различен Common Data Service, [създайте нов източник на данни](#connect-to-a-common-data-service-managed-lake).

1. В статията за аудиторията отидете на **Данни** > **Източници на данни**.

2. До източника на данни, който искате да актуализирате, изберете многоточието.

3. Изберете опцията **Редактиране** от списъка.

4. Изберете допълнителни обекти от наличния списък и изберете **Записване**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]