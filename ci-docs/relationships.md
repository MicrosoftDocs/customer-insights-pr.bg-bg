---
title: Релации между обекти и пътища на обект
description: Създавайте и управлявайте връзки между обекти от множество източници на данни.
ms.date: 09/27/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-semantic-mapping
- ci-entities
- ci-relationships
- ci-activities
- ci-activities-wizard
- ci-measures
- ci-segments
- ci-segment-builder
- ci-measure-builder
- ci-measure-template
- ci-permissions
- customerInsights
ms.openlocfilehash: a7b10d985d5cba64b25595a3d7c101d6cb5c62a5
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: bg-BG
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642409"
---
# <a name="relationships-between-entities"></a>Релации между обекти

Връзките свързват обекти и дефинират графика на вашите данни, когато обектите споделят общ идентификатор, външен ключ. Този външен ключ може да се препраща от един обект към друг. Свързаните обекти ви позволяват дефинирането на сегменти и мерки въз основа на няколко източника на данни.

Има три типа взаимоотношения: 
- Нередактируеми системни взаимоотношения, създадени от системата като част от процеса на обединяване на данните
- Нередактируеми наследени връзки, които се създават автоматично от поглъщането на източници на данни 
- Редактируеми персонализирани взаимоотношения, създадени и конфигурирани от потребители

## <a name="non-editable-system-relationships"></a>Нередактируеми системни взаимоотношения

По време на обединяването на данните системните взаимоотношения се създават автоматично въз основа на интелигентно съвпадение. Тези релации помагат да се свържат записите на клиентски профил с други съответстващи записи. Следващата диаграма илюстрира създаването на три базирани на системата взаимоотношения. Клиентският обект се съпоставя с други обекти, за да се получи унифицираният обект *Клиент*.

:::image type="content" source="media/relationships-entities-merge.png" alt-text="Диаграма с пътища на взаимоотношения за обекта на клиента с три 1-n връзки.":::

- **Релацията *CustomerToContact*** е създадена между обекта на *клиент* и обекта на *контакт*. Обектът на *клиент* получава полето за ключ **Contact_contactID** за свързване с полето за ключ на *контакт* **contactID**.
- **Релацията *CustomerToAccount*** е създадена между обекта на *клиент* и обекта на *акаунт*. Обектът на *клиент* получава полето за ключ **Account_accountID** за свързване с полето за ключ на *акаунт* **accountID**.
- **Релацията *CustomerToWebAccount*** е създадена между обекта на *клиент* и обекта на *WebAccount*. Обектът на *клиент* получава полето за ключ **WebAccount_webaccountID** за свързване с полето за ключ на обект *WebAccount* **webaccountID**.

## <a name="non-editable-inherited-relationships"></a>Нередактируеми наследени релации

По време на процеса на поглъщане на данни системата проверява източниците на данни за съществуващи връзки. Ако не съществува връзка, системата автоматично ги създава. Тези взаимоотношения се използват и в процесите надолу по веригата.

## <a name="create-a-custom-relationship"></a>Създаване на персонализирана релация

Връзката се състои от *субект източник* съдържащ външния ключ и *целеви обект* към който сочи външният ключ на субекта източник. 

1. Отидете на **Данни** > **Релации**.

2. Изберете **Нова релация**.

3. В екрана **Нова релация** посочете следната информация:

   :::image type="content" source="media/relationship-add.png" alt-text="Нов страничен прозорец на връзката с празни полета за въвеждане.":::

   - **Име на връзката**: Име, което отразява целта на връзката. Пример: CustomerToSupportCase.
   - **Описание**: Описание на релацията.
   - **Обект източник**: Обект, който се използва като източник във връзката. Пример: SupportCase.
   - **Целеви обект**: Обект, който се използва като цел във връзката. Пример: Клиент.
   - **Изходна кардиналност**: Посочете кардиналността на обекта източник. Кардиналността описва броя на възможните елементи в даден набор. Винаги се отнася до целевата кардиналност. Можете да избирате между **Едно** и **Много**. Поддържат се само релации „много към един” и „един към един”.  
     - Много към едно: множество записи на източника могат да се отнасят до един целеви запис. Пример: Множество случаи за поддръжка от един клиент.
     - Един към един: Записът от един източник се отнася до запис от една цел. Пример: Един идентификатор за лоялност за един клиент.

     > [!NOTE]
     > Връзките много към много могат да бъдат създадени с помощта на две връзки много към едно и свързващ обект, който свързва изходния обект и целевия обект.

   - **Целева важност** : Изберете важността на записите на целеви обект. 
   - **Ключово поле на източника**: Полето за външния ключ в обекта източник. Пример: SupportCase може да използва CaseID като поле за външен ключ.
   - **Целево поле за ключ**: Ключовото поле на целевия обект. Пример Клиентът може да използва **CustomerID** ключово поле.

4. За да създадете персонализирана връзка, изберете **Записване**.

## <a name="set-up-account-hierarchies"></a>Настройване на йерархиите на акаунт

Среди, които са конфигурирани да използват бизнес акаунти като основна целева аудитория, могат да конфигурират йерархии на сметки за свързани бизнес акаунти. Например компания, която има отделни бизнес единици. 

Организациите създават йерархии на акаунти, за да управляват по -добре акаунтите и техните взаимоотношения помежду си. Customer Insights поддържа йерархии на акаунт родител-дете, които вече съществуват в estested клиентски данни. Например сметки от Dynamics 365 Sales. Тези йерархии могат да бъдат конфигурирани на **страницата Релации**.

1. Отидете на **Данни** > **Релации**.
1. Изберете раздела **йерархия на акаунтите**.
1. Изберете **йерархия на нов акаунт**. 
1. В екрана **Йерархия на акаунта**, предоставете име за йерархията. Системата създава име за изходния обект. Можете да промените името на обекта на изходното име.
1. Изберете обекта, който съдържа йерархията на вашия акаунт. Обикновено се намира в същия обект, който съдържа сметките.
1. Изберете **ИД на акаунт** и **ИД на родител на акаунт** от избрания обект 
1. Изберете **Записване**, за да приложите настройките и да финализирате йерархията на акаунта.

## <a name="view-relationships"></a>Преглед на релациите

Страницата Връзки изброява всички създадени връзки. Всеки ред представлява връзка, която също включва подробности за обекта източник, целевия обект и мощността. 

:::image type="content" source="media/relationships-list.png" alt-text="Списък на връзките и опциите в лентата за действие на страницата „Връзки“.":::

Тази страница предлага набор от опции за съществуващи и нови взаимоотношения: 
- **Нова релация:** Изберете [Създаване на персонализирана релация](#create-a-custom-relationship).
- **Визуализатор**: [Разгледайте визуализатора на връзката](#explore-the-relationship-visualizer) за да видите мрежова диаграма на съществуващите взаимоотношения и тяхната същественост.
- **Филтрирайте по**: Изберете типа връзки, които да се показват в списъка.
- **Търсене на релации**: Използвайте текстово търсене на свойствата на връзките.

### <a name="explore-the-relationship-visualizer"></a>Разгледайте визуализатора на връзката

Визуализаторът на релации показва мрежова диаграма на съществуващите взаимоотношения между свързаните обекти и тяхната кардиналност. Той също така визуализира пътя на релацията.

За да персонализирате изгледа, можете да промените позицията на полетата, като ги плъзнете върху платното.

:::image type="content" source="media/relationship-visualizer.png" alt-text="Екранна снимка на мрежовата диаграма на визуализатора на връзки с връзки между свързани обекти.":::

Налични опции: 
- **Експортиране като изображение**: Запазване на текущия изглед като файл с изображение.
- **Промяна на хоризонтално/вертикално оформление**: Променете подравняването на обектите и връзките.
- **Редактиране**: Актуализирайте свойствата на персонализираните връзки в екрана за редактиране и запазете промените.

## <a name="relationship-paths"></a>Пътеки на релацията

Пътят на отношенията описва обектите, които са свързани с връзки между обект източник и целеви обект. Използва се при създаване на сегмент или мярка, която включва други обекти, освен обекта на унифицирания профил, и има множество опции за достигане до обекта на унифицирания профил. 

Пътят на връзката информира системата за това кои взаимоотношения за достъп до обекта на унифициран профил. Различните пътища на релациите могат да дадат различни резултати.

Например обектът *eCommerce_eCommercePurchases* има следните релации с обекта *Клиент* на унифицирания профил:

- eCommerce_eCommercePurchases > Клиент
- eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > Клиент
- eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > loyaltyScheme_loyCustomers > Клиент 

Пътят на връзката определя кои обекти можете да използвате, когато създавате правила за мерки или сегменти. Избирането на опцията с най-дългия път на релация вероятно ще даде по-малко резултати, тъй като съответстващите записи трябва да са част от всички обекти. В този пример клиентът трябва да е закупил стоки чрез електронна търговия (eCommerce_eCommercePurchases), на място за продажба (POS_posPurchases) и да участва в нашата програма за лоялност (loyaltyScheme_loyCustomers). Когато избирате първата опция, вероятно ще получите повече резултати, тъй като е достатъчно клиентите да съществуват само в един допълнителен обект.

### <a name="direct-relationship"></a>Директна релация

Връзката се класифицира като **директна релация**, когато субект източник се свързва с целеви обект само с една връзка.

Например, ако обект на дейност извика *eCommerce_eCommercePurchases* се свързва с целеви обект *eCommerce_eCommerceContacts* обект чрез *ContactId* само че това е пряка връзка.

:::image type="content" source="media/direct_Relationship.png" alt-text="Източникът се свързва директно с целевия обект.":::

#### <a name="multi-path-relationship"></a>Релация с множество пътеки

**Релация с множество пътеки** е специален вид директна връзка, която свързва източник на източник с повече от един целеви обект.

Например, ако обект на дейност извика *eCommerce_eCommercePurchases* се отнася до два целеви обекта, и двата *eCommerce_eCommerceContacts* и *loyaltyScheme_loyCustomers*, това е многопътна връзка.

:::image type="content" source="media/multi-path_relationship.png" alt-text="Изходният обект се свързва директно с повече от един целеви обект чрез мулти-хоп връзка.":::

### <a name="indirect-relationship"></a>Косвена релация

Връзката се класифицира като **косвена релация**, когато субект източник се свързва с един или повече допълнителни обекти преди свързването с целеви обект.

#### <a name="multi-hop-relationship"></a>Релация с множество прескачания

*Релация с множество прескачания* е *косвена релация*, която ви позволява да свържете източник на източник към целево обект чрез един или повече други посреднически обекти.

Например, ако обект на дейност извика *eCommerce_eCommercePurchasesWest* се свързва с междинно образувание, наречено *eCommerce_eCommercePurchasesEast* и след това се свързва с целеви обект, наречен *eCommerce_eCommerceContacts*, това е релация с множество прескачания.

:::image type="content" source="media/multi-hop_relationship.png" alt-text="Източникът се свързва директно към целевия обект с междинен обект.":::

### <a name="multi-hop-multi-path-relationship"></a>Релацията с множествено прескачане и множество пътеки

Релациите с много прескачания и много пътища могат да се използват заедно за създаване **релации с множествено прескачане и множество пътеки**. Този специален тип съчетава функциите на **мулти-хоп** и **многопътни релации**. Тя ви позволява да се свързвате с повече от един целеви обект, докато използвате междинни обекти.

Например, ако обект на дейност извика *eCommerce_eCommercePurchasesWest* се свързва с междинно образувание, наречено *eCommerce_eCommercePurchasesEast* и след това се свързва два целеви обекта, едновременно *eCommerce_eCommerceContacts* и *loyaltyScheme_loyCustomers*, това е релация с множество прескачания и множество пътеки.

:::image type="content" source="media/multi-hop_multi-path_relationship.png" alt-text="Източникът се свързва директно с един целеви обект и се свързва с друг целеви обект чрез междинен обект.":::

## <a name="manage-existing-relationships"></a>Управление на съществуващи релации 

На страницата „Връзки“ всяка връзка е представена с ред. 

Изберете връзка и изберете една от следните опции: 
 
- **Редактиране**: Актуализирайте свойствата на персонализираните връзки в екрана за редактиране и запазете промените.
- **Изтриване**: Изтриване на персонализирани връзки.
- **Изглед**: Преглед на създадени от системата и наследени връзки. 

## <a name="next-step"></a>Следваща стъпка

Системните и персонализираните релации често [създават сегменти](segments.md) и [мерки](measures.md) въз основа на множество източници на данни, които вече не се измерват.

[!INCLUDE [footer-include](includes/footer-banner.md)]