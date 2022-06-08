---
title: Премахване на дубликати преди обединение на данни
description: Втората стъпка в процеса на обединяване е избирането кой запис да се запази, когато се намерят дубликати.
recommendations: false
ms.date: 04/22/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-map
- ci-match
- customerInsights
ms.openlocfilehash: 27dff3551ab411a12c273536d7431d651c48573e
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: MT
ms.contentlocale: bg-BG
ms.lasthandoff: 05/11/2022
ms.locfileid: "8742919"
---
# <a name="remove-duplicates-before-unifying-data"></a>Премахване на дубликати преди обединение на данни

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Тази стъпка в обединяването по избор ви дава възможност да настроите правила за работа с дублиращи се записи в рамките на обект. *Дедупликацията* идентифицира дублираните записи и ги обединява в един запис. Изходните записи се свързват към обединения запис с алтернативни идентификатори. Ако правилата не са конфигурирани, се прилагат дефинирани от системата правила.

## <a name="include-enriched-entities-preview"></a>Включване на обогатени обекти (визуализация)

Ако сте обогатявали обекти на ниво източник на данни, за да помогнете за подобряване на резултатите от обединяването ви, изберете ги. За повече информация вижте [Обогатяване за източници на данни](data-sources-enrichment.md).

1. На **страницата Дублирани** записи изберете **Използване на обогатени обекти** в горната част на страницата.

1. От екрана Използване на **обогатени обекти** изберете един или повече обогатени обекти.

1. Изберете **Готово**.

## <a name="define-deduplication-rules"></a>Дефиниране на правилата за дедупликация

1. На **страницата Дублирани** записи изберете обект и изберете **Добавяне на правило**, за да определите правилата за дедупликация.

   :::image type="content" source="media/m3_duplicates_showmore.png" alt-text="Екранна снимка на дублирани записи страници с Показване на по-осветени":::

   1. В прозореца Добавяне на **правило** въведете следната информация:
      - **Изберете поле**: Изберете от списъка на наличните полета от обекта, който искате да проверите за дубликати. Изберете полета, които вероятно са уникални за всеки отделен клиент. Например имейл адрес или комбинацията от име, град и телефонен номер.
      - **Нормализирайте**: Изберете от следните опции за нормализиране на избраните атрибути.
        - **Цифри**: Преобразува други цифрови системи, като римски цифри, в арабски цифри. *VIII* става *8*.
        - **Символи**: Премахва всички символи и специални знаци. *Head&Shoulder* става *HeadShoulder*.
        - **Текст в долен случай: Преобразува целия знак в по-нисък случай**. *САМО ГЛАВНИ и Заглавни Букви* става *само главни и заглавни букви*.
        - **Тип (Телефон, Име, Адрес, Организация)**: Стандартизиране на имена, заглавия, телефонни номера, адреси и др.
        - **Unicode в ASCII**: Преобразува unicode нотация в ASCII знаци. */u00B2* става *2*.
        - **Whitespace**: Премахва всички пространства. *Здравей свят* става *ЗдравейСвят*.
      - **Прецизност**: Задайте нивото на точност, за да кандидатствате за това състояние.
        - **Основно**: Изберете от *Ниско (30%)*, *Средно (60%)*, *Високо (80%)*, и *Точно (100%)*. Изберете **Точно**, за да съответствате само на записи, които съответстват на 100 процента.
        - **Персонализиран**: Задайте процент, на който записите трябва да съвпадат. Системата ще съвпада само със записи, преминали този праг.
      - **Име**: Име на правилото.

      :::image type="content" source="media/m3_duplicates_add.png" alt-text="Екранна снимка на Добавяне на прозорец с правила за премахване на дубликати.":::

   1. По желание изберете **Добавяне** > **на условие**, за да добавите още условия към правилото. Условията са свързани с логически оператор И и по този начин се изпълняват само ако са изпълнени всички условия.

   1. По желание **Добавете добавяне на изключение** > **, за да** добавите изключения към [правилото](match-entities.md#add-exceptions-to-a-rule). Изключенията се използват за справяне с редки случаи на фалшиви положителни резултати и фалшиви негативи.

   1. Изберете **Готово**, за да създадете правилото.

1. По желание, [добавете още правила](#define-deduplication-rules).

1. Изберете обект и след това **Редактирайте предпочитанията за** обединяване.

1. В **екрана с предпочитания за обединяване**:
   1. Изберете една от трите опции, за да определите кой запис да запазите, ако се намери дубликат:
      - **Най-попълвани**: Идентифицира записа с най-попълнени полета на атрибути като записа победител. Това е опцията за сливане по подразбиране.
      - **Най-скорошни**: Идентифицира записа на победителя въз основа на най-скорошни. Изисква дата или числово поле за определяне на скоростта.
      - **Най-нескорошни**: Идентифицира записа на победителя въз основа на най-нескорошни. Изисква дата или числово поле за определяне на скоростта.
      
      В случай на вратовръзка, записът на победителя е този с MAX(PK) или по-голямата стойност на първичния ключ.
      
   1. По желание, за да определите предпочитанията за обединяване на отделни атрибути на обект, изберете **Разширени** в долната част на екрана. Можете например да изберете да запазите най-скорошния имейл И най-пълния адрес от различни записи. Разгънете обекта, за да видите всички негови атрибути и да определите коя опция да използвате за отделни атрибути. Ако изберете опция, базирана на рекреция, трябва също така да зададете поле за дата/час, което определя възможността за възстановяване.

      :::image type="content" source="media/m3_adv_merge.png" alt-text="Разширен екран с предпочитания за обединяване, показващ скорошния имейл и пълен адрес":::

   1. Изберете **Готово**, за да приложите предпочитанията си за обединяване.

1. След като дефинирате правилата за дедупликация и обедините предпочитанията, изберете **Напред**.
  
> [!div class="nextstepaction"]
> [Следваща стъпка за един-единствен обект: Обединение на полета](merge-entities.md)

> [!div class="nextstepaction"]
> [Следваща стъпка за няколко обекта: Съвпадение на условията](match-entities.md)

## <a name="deduplication-output-as-an-entity"></a>Дедупликация изход като обект

Процесът на дедупликация създава нов дедъпликиран обект за всеки от обектите източник. Тези обекти могат да бъдат намерени заедно с **ConflationMatchPairs:CustomerInsights** в секцията **Система** на страницата **Обекти** с името **Deduplication_DataSource_Entity**.

Изходният обект за дедупликация съдържа следната информация:

- ИД/ключове
  - Полета за първичен ключ и Алтернативен ИД. Алтернативно ид поле се състои от всички алтернативни Идентификатори, идентифицирани за запис.
  - Полето Deduplication_GroupId показва групата или клъстера, идентифицирани в обект, който групира всички подобни записи въз основа на посочените полета за дедупликация. Това се използва за целите на системната обработка. Ако не са посочени ръчни правила за дедупликация и се прилагат дефинирани от системата правила за дедупликация, може да не намерите това поле в изходния обект на дедупликация.
  - Deduplication_WinnerId: Това поле съдържа идентификатора на победителя от идентифицираните групи или клъстери. Ако Deduplication_WinnerId е същото като стойността на основния ключ за запис, това означава, че записът е победител.
- Полета, използвани за определяне на правилата за дедупликация.
- Полета „Правило” и „Оценка”, за да се посочи кое от правилата за дедупликация е приложено и резултатът, върнат от алгоритъма за съвпадение.

[!INCLUDE[footer-include](includes/footer-banner.md)]