---
title: Прогноза за препоръки за продукти
description: Предскажете продуктите, които клиентът вероятно ще закупи или взаимодейства с тях.
ms.date: 05/09/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: 9b3e60c49d294d031f43ef0594cb69707bb64019
ms.sourcegitcommit: 82f417cfb0a16600e9f552d7a21d598cc8f5a267
ms.translationtype: MT
ms.contentlocale: bg-BG
ms.lasthandoff: 05/16/2022
ms.locfileid: "8762719"
---
# <a name="product-recommendation-prediction"></a>Прогноза за препоръки за продукти

Моделът за препоръчване на продукти създава набори от прогнозни препоръки за продукти. Препоръките се основават на предишно поведение при покупки и клиенти с подобни модели на покупка. Можете да създадете нови прогнози за препоръки за продукти на страница **Интелигентност** > **Прогнози**. Изберете **Моите прогнози**, за да видите други прогнози, които сте създали.

Препоръките за продукт може да са предмет на местните закони и разпоредби и очакванията на клиентите, а моделът не е създаден специално да ги взема предвид.  Като потребител на тази възможност за прогнозиране, **трябва да прегледате препоръките, преди да ги доставите на клиентите**, за да сте сигурни, че спазвате всички приложими закони или разпоредби и очакванията на клиентите за това, което можете да препоръчате.

Освен това изходът на този модел ще ви даде препоръки въз основа на идентификатора на продукта. Механизмът за доставка ще трябва да съпостави прогнозните идентификатори на продукти с подходящо съдържание, за да могат клиентите да вземат под внимание локализацията, съдържанието на изображенията и друго специфично за бизнеса съдържание или поведение.

## <a name="sample-guide"></a>Примерно ръководство

Ако се интересувате да изпробвате тази функция, но нямате данни, за да изпълните изискванията по-долу, можете [създайте примерна реализация](sample-guide-predict-product-recommendation.md).

## <a name="prerequisites"></a>Предварителни изисквания

- Поне [Разрешения на сътрудник](permissions.md) в Customer Insights.

- Бизнес знания, за да разберете различни видове продукти за вашия бизнес и как вашите клиенти взаимодействат с тях. Поддържаме препоръчване на продукти, закупени преди това от вашите клиенти, или препоръки за нови продукти.

- Вие среда трябва да бъде конфигуриран за отделните **потребители** основна целева аудитория.

- Данни за транзакции, покупки и тяхната история:
  - Идентификатори на транзакции за разграничаване на покупки или транзакции.
  - Клиентски идентификатори, за да съпоставите транзакциите с вашите клиенти.
  - Дати на транзакционните събития, които определят датите, на които е настъпила транзакцията.
  - Информация за идентификатор на продукт за трансакцията.
  - (По избор) Обект на данни на продуктов каталог за използване на продуктов филтър.
  - (По избор) Ако дадена транзакция е връщане или не.
  - Схемата на семантичните данни изисква следната информация:
    - **Номер на транзакцията:** Уникален идентификатор на покупка или транзакция.
    - **Дата на трансакцията:** Датата на покупката или трансакцията.
    - **Стойност на транзакцията:** Числовата стойност на покупката или транзакцията.
    - **Уникален идентификатор на продукта:** Идентификационният номер на закупения продукт или услуга, ако данните ви са на ниво договорена покупка.
    - (По избор) **Закупуване или връщане:** Булево поле, където стойността *вярно* определя, че трансакцията е връщане. Ако данните за закупуване или връщане не са предоставени, моделът и **стойността на сделката** са отрицателни, ще използваме и тази информация, за да подскажем връщане.
- Характеристики на предложени данни:
  - Достатъчни хронологични данни: данни от трансакции за поне една година, за предпочитане за две до три години, за да се включи известна повторяемост.
  - Няколко покупки на клиент: три или повече трансакции на ИД на клиент
  - Брой клиенти: най-малко 100 клиенти, за предпочитане повече от 10 000 клиенти. Моделът ще е неуспешен с по-малко от 100 клиенти.

> [!NOTE]
>
> - Моделът изисква хронология на трансакциите на клиентите. Определението за трансакция е доста гъвкаво. Всички данни, които описват взаимодействие между потребител и продукт, могат да действат като входни. Например закупуване на продукт, участие в обучение или присъствие на събитие.
> - В момента може да се конфигурира само един обект в хронологията на трансакциите. Ако има няколко обекта за покупка, ги профсъюзите преди Power Query поглъщането на данни.
> - Ако поръчката и подробностите за поръчката са различни обекти, присъединете се към тях, преди да ги използвате в модела. Моделът не работи само с идентификатор на поръчка или ИД на разписка в обект.

## <a name="create-a-product-recommendation-prediction"></a>Създаване на прогноза за препоръки за продукти

1. В Customer Insights отидете на **Анализ** > **Прогнози**.

1. Изберете плочката модел **препоръки за продукти и изберете** Използване на **този модел**.
   > [!div class="mx-imgBorder"]
   > ![Плочка на модел за препоръка за продукт с бутон „Използване на този модел”.](media/product-recommendation-usethismodel.PNG "Препоръка за продукт модел плочка с бутон „Използвайте този модел”")

1. Прегледайте информацията за изискванията на модела. Ако имате необходимите данни, изберете **Първи стъпки**.

### <a name="name-model"></a>Задаване на име на модел

1. Задайте име на модела, за да го различавате от другите модели.

1. Въведете име за изходния обект, като използвате само букви и цифри, без интервали. Това е името, което ще използва обектът на модела. След това изберете **Напред**.

### <a name="define-product-recommendation-configuration"></a>Определете конфигурацията на препоръките за продукти

1. Задайте **Брой продукти**, който искате да препоръчате на клиент. Тази стойност зависи от начина, по който методът ви за доставка попълва данни. Ако можете да препоръчате три продукта, задайте съответно тази стойност.

   >[!TIP]
   > Можете да изберете **Запазване на черновата** по всяко време, за да запишете прогноза като чернова. Ще намерите черновата прогноза в раздела **Моите прогнози**.

1. Изберете, ако искате да включите продукти, които клиентите са закупили наскоро в **полето Повтаряне на очакваните** покупки.

1. Задайте **прозореца** Поглед назад. Тази настройка определя времевата рамка, която моделът взема предвид, преди да препоръча продукта отново на потребителя. Например посочете, че клиент купува лаптоп на всеки две години. Този прозорец ще разгледа хронологията на покупките за последните две години и ако намери елемент, елементът ще се филтрира от препоръките.

1. Избор на **Напред**

### <a name="add-required-data"></a>Добавяне на задължителни данни

1. Изберете **Добавете данни** и изберете типа дейност страничния панел, който съдържа необходимата информация за транзакциите или историята на покупките.

1. Под **Изберете дейности**, изберете конкретните дейности от избраната дейност, върху която искате да се фокусира изчислението.

   :::image type="content" source="media/product-recommendation-select-semantic-activity.PNG" alt-text="Страничен прозорец, показващ избора на конкретни дейности под семантичния тип.":::

1. Ако все още не сте свързали дейността със семантичен тип, изберете **редактиране**, за да го направите. Отваря се ръководеният опит за картографиране на семантични дейности. Нанесете данните си към съответните полета в избрания тип дейност.

   :::image type="content" source="media/product-recommendation-set-activity-type.PNG" alt-text="Тип дейност за настройка на страница.":::

1. След съпоставяне на дейността със съответния семантичен тип изберете **Напред**, за да продължите.

1. Съпоставете семантичните атрибути с полетата, които са необходими за стартиране на модела.

1. Изберете **Записване**.

1. Изберете **Напред**.

### <a name="configure-product-filters"></a>Конфигуриране на филтри за продукти

Понякога само определени продукти са полезни или подходящи за типа прогноза, който създавате. Филтрите за продукти ви позволяват да идентифицирате поднабор от продукти със специфични характеристики, които да препоръчате на клиентите. Моделът ще използва всички налични продукти, за да научи примерни модели, но използва само продуктите, които съответстват на филтъра за продукти в изходните данни.

1. В стъпката **Добавяне на информация за продукт** добавете продуктовия каталог с информация за всеки продукт. Нанесете необходимата информацията и изберете **Напред**.

1. В стъпката **Филтри за продукт** изберете между следните опции.

   - **Няма филтри**: Използвайте всички продукти в прогнозата за препоръка на продукт.

   - **Определяне на конкретни филтри за продукт**: Използвайте конкретни продукти в прогнозата за препоръка на продукт.

1. Изберете **Напред**.

1. Ако решите да дефинирате филтър за продукт, трябва да го дефинирате сега. В прозореца **Атрибути на продуктов каталог** изберете атрибутите от *обекта на продуктов каталог*, които искате да включите във филтъра.

   :::image type="content" source="media/product-filters-sidepane.png" alt-text="Страничен прозорец, който показва атрибути в обекта на продуктов каталог, които да изберете за филтри за продукт.":::

1. Изберете дали искате филтъра за продукт да използва конекторите **и** или **или**, за да комбинирате логически селекцията на атрибути от продуктовия каталог.

   :::image type="content" source="media/product-filters-sample.png" alt-text="Примерна конфигурация на филтри за продукт, комбинирани с логически конектори И.":::

1. Изберете **Напред**.

### <a name="set-update-schedule-and-review-configuration"></a>Задаване на график за актуализиране и преглед на конфигурацията

1. Задайте честота, за да преобучите модела си. Тази настройка е важна за актуализиране на точността на прогнозите, тъй като новите данни се импортират в Customer Insights. Повечето фирми могат да преобучават веднъж месечно и да получат добра точност за прогнозите си.

1. Изберете **Напред**.

1. Прегледайте конфигурацията. Можете да се върнете към която и да е част от конфигурацията за прогнозиране, като изберете **Редактиране** под показаната стойност. Или можете да изберете конфигурационна стъпка от индикатора за напредък.

1. Ако всички стойности са конфигурирани правилно, изберете **Запазване и изпълнение**, за да започне процесът на прогнозиране. В раздела **Моите прогнози** можете да видите състоянието на своите прогнози. Процесът може да отнеме няколко часа в зависимост от количеството данни, използвани в прогнозата.

## <a name="review-a-prediction-status-and-results"></a>Преглед на състоянието на прогнозата и резултатите

1. Отидете в раздела **Моите прогнози** в **Разузнаване** > **Прогнози**.
   > [!div class="mx-imgBorder"]
   > ![Изглед на страницата „Моите прогнози“.](media/product-recommendation-mypredictions.PNG "Изглед на страницата „Моите прогнози“")

1. Изберете прогнозата, която искате да прегледате.
   - **Име на прогнозата:** Името на прогнозата, зададено при създаването й.
   - **Тип на прогнозата:** Типът на модела, използван за прогнозата
   - **Изходен обект:** Името на обекта, който да съхранява резултата от прогнозата. Можете да намерите обект с това име в **Данни** > **Обекти**.
      *Резултат* в изходния обект е количествена мярка на препоръката. Моделът препоръчва продукти с по-висок резултат спрямо продукти с по-нисък резултат.
   - **Прогнозно поле:** Това поле се попълва само за някои видове прогнози и не се използва в прогноза за препоръка на продукт.
   - **Състояние:** Текущото състояние на изпълнението на прогнозата.
        - **На опашката:** В момента прогнозата чака да бъдат изпълнени други процеси.
        - **Обновява се:** В момента прогнозата преминава етапа на „оценка“ на обработката, за да се получат резултати, които ще се влеят в изходния обект.
        - **Неуспешна:** Прогнозата е неуспешна. Изберете **Регистрационни файлове** за повече подробности.
        - **Успешна:** Прогнозата е успешна. Изберете **Преглед** под вертикалното многоточие за преглед на прогнозата
   - **Редактирана:** Датата, на която е променена конфигурацията за прогнозата.
   - **Последно обновена:** Датата на обновяване на прогнозата за получаване на изходния обект.

1. Изберете вертикалното многоточие до прогнозата, за която искате да прегледате резултатите, и изберете **Преглед**.
   > [!div class="mx-imgBorder"]
   > ![Преглед на опциите в менюто на вертикалното многоточие за прогноза, включително редактиране, обновяване, преглед, регистрационни файлове и изтриване.](media/product-recommendation-verticalellipses.PNG "Преглед на опциите в менюто на вертикалното многоточие за прогноза, включително редактиране, обновяване, преглед, регистрационни файлове и изтриване")

1. В страницата с резултати има пет основни секции с данни:
    1. **Ефективност на модела за обучение:** Възможните резултати са A, B или C. Този резултат показва ефективността на прогнозата и може да ви помогне да вземете решение дали да използвате резултатите, съхранени в изходния обект.
        - Резултатите се определят въз основа на следните правила:
            - **A** Моделът ще бъде разгледан **A** качество, ако показателят "Успех @ K" е поне 10% повече от базовото ниво. 
            - **Б** Моделът ще бъде разгледан **Б** качество, ако показателят „Успех @ K” е с 0% до 10% повече от базовото ниво.
            - **В** Моделът ще бъде разгледан **В** качество, ако показателят „Успех @ K” е по-нисък от базовото ниво.

               > [!div class="mx-imgBorder"]
               > ![Преглед на резултата от ефективността на модела.](media/product-recommendation-modelperformance.PNG "Преглед на резултата от ефективността на модела")
            - **Базова линия**: Моделът взема най-добре препоръчваните продукти по брой покупки за всички клиенти и използва научени правила, идентифицирани от модела, за да създаде набор от препоръки за клиентите. След това прогнозите се сравняват с най-добрите продукти, изчислени от броя на клиентите, закупили продукта. Ако клиентът има поне един продукт в препоръчаните си продукти, който се вижда и в най-закупените продукти, той се счита за част от базовото ниво. Ако имаше 10 от тези клиенти, които са закупили препоръчан продукт от общо 100 клиенти, изходното ниво би било 10%.
            - **Успех @ K**: Използвайки валидационен набор от времеви период на транзакциите, се създават препоръки за всички клиенти и се сравняват с валидиращия набор от транзакции. Например, в период от 12 месеца, месец 12 може да бъде отделен като валидиращ набор от данни. Ако моделът прогнозира поне едно нещо, което бихте закупили през месец 12 въз основа на наученото от предходните 11 месеца, клиентът би увеличил показателя „Успех @ К“.

    1. **Най-предлагани продукти (със съвпадение):** Петте най-добри продукта, които са прогнозирани за клиентите.
       > [!div class="mx-imgBorder"]
       > ![Графика, показваща 5-те най-препоръчани продукта.](media/product-recommendation-topproducts.PNG "Графика, показваща 5-те най-препоръчани продукта")

    1. **Основни фактори за препоръка:** Моделът използва хронологията на трансакциите на клиентите, за да дава препоръки за продукти. Той научава модели, основани на минали покупки и открива прилики между клиентите и продуктите. След това тези прилики се използват за генериране на препоръки за продукт.
    Следват факторите, които биха могли да повлияят на препоръка за продукт, генерирана от модела.
        - **Минали трансакции**: Моделите на покупки в миналото се използват от модела за генериране на препоръки за продукти. Например моделът може да препоръча *мишка Surface Arc*, ако наскоро някой е закупил *Surface Book 3* и *писалка Surface*. Моделът е научил, че във времето много клиенти са закупили *мишка Surface Arc* след закупуване на *Surface Book 3* и *писалка Surface*.
        - **Сходство на клиенти**: Препоръчаният продукт е закупен във времето от други клиенти, които показват подобни модели на покупка. Например Джон получава препоръка за *слушалки Surface 2*, защото Дженифър и Брад наскоро са закупили *слушалки Surface 2*. Моделът вярва, че Джон е подобен на Дженифър и Брад, тъй като във времето са имали сходни модели на покупки.
        - **Сходство на продукти**: Препоръчаният продукт е подобен на други продукти, които клиентът е закупил по-рано. Моделът счита два продукта за сходни, ако са закупени заедно или от подобни клиенти. Например клиент получава препоръка за *USB устройство за съхранение*, защото по-рано е закупил *адаптер USB-C to USB* и моделът смята, че *USB устройството за съхранение* е подобно на *адаптера USB-C to USB* въз основа на хронологични модели на покупка.

        Всяка препоръка за продукт се влияе от един или повече от тези фактори. Процентът на препоръките, при които всеки влияещ фактор играе роля, се визуализира в диаграма. В следващия пример 100% от препоръките са повлияни от минали трансакции, 60% от сходство на клиенти и 22% от сходство на продукти. Задръжте курсора на мишката върху лентите в диаграмата, за да видите точния процент на приноса на влияещите фактори.

        > [!div class="mx-imgBorder"]
        > ![Ключови фактори за препоръките.](media/product-recommendation-keyrecommendationfactors.png "Основни фактори за препоръка, научени от модела за генериране на препоръки за продукт")

   1. **Статистика на данните**: Предоставя преглед на броя на трансакциите, клиентите и продуктите, които разглежда моделът. Тя се основава на входните данни, използвани за изучаване на модели и генериране на препоръки за продукт.

      > [!div class="mx-imgBorder"]
      > ![Статистика на данните.](media/product-recommendation-datastatistics.png "Статистика на данните за изходящите данни, използвани от модела за изучаване на примерни модели")

      Тази секция показва статистика по точките от данни, които се използват от модела за изучаване на модели и генериране на препоръки за продукт. Филтрирането, както е конфигурирано в конфигурацията на модела, ще се прилага за изходните данни, генерирани от модела. Моделът обаче използва всички налични данни, за да научи примерни модели. Следователно, ако използвате филтриране на продукти в конфигурацията на модела, тази секция ще покаже общия брой продукти, които моделът е анализирал, за да научи модели, които може да се различават от броя на продуктите, които отговарят на определените критерии за филтриране.

   1. **Високо уверени препоръки за продукти:** Извадка от препоръки, предоставени на вашите клиенти, които моделът смята, че е вероятно да бъдат закупени от клиента.    
      Ако се добави продуктов каталог, идентификаторите на продуктите се заменят с имена на продукти. Имената на продуктите предоставят по-приложима и интуитивна информация за прогнозите.
       > [!div class="mx-imgBorder"]
       > ![Списък, показващ предложения за висока достоверност за избран набор от индивидуални клиенти.](media/product-recommendation-highconfidence.PNG "Списък, показващ предложения за висока увереност за избран набор от индивидуални клиенти")

## <a name="manage-predictions"></a>Управление на прогнозите

Възможно е да се оптимизират, отстраняват неизправности, опресняват или изтриват прогнози. Прегледайте отчет за използваемостта на входящите данни, за да разберете как да направите прогноза по-бърз и по-надежден. За повече информация вижте [Управление на прогнози](manage-predictions.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]