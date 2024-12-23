# Исследование гипотез для увеличения выручки интернет-магазина

Цель проекта — приоритизировать гипотезы маркетологов интернет-магазина, проанализировать результаты A/B-теста.

## Данные

Для исследования были предоставлены два датафрейма. Первый — с описанием гипотез. Второй — с транзакциями интернет-магазина.

Датафрейм №1: 
- Hypothesis — краткое описание гипотезы;
- Reach — охват пользователей по 10-балльной шкале;
- Impact — влияние на пользователей по 10-балльной шкале;
- Confidence — уверенность в гипотезе по 10-балльной шкале;
- Efforts — затраты ресурсов на проверку гипотезы по 10-балльной шкале. Чем больше значение Efforts, тем дороже проверка гипотезы.
- Данные для второй части:

Датафрейм №2:
- transactionId — идентификатор заказа;
- visitorId — идентификатор пользователя, совершившего заказ;
- date — дата, когда был совершён заказ;
- revenue — выручка заказа;
- group — группа A/B-теста, в которую попал заказ.
- date — дата;
- group — группа A/B-теста;
- visitors — количество пользователей в указанную дату в указанной группе A/B-теста

## Задачи решавшиеся в проекте:

- предобработка данных,
- исследовательский и статистический анализ данных,
- приоритезация гипотез по фреймвормам ICE и RICE,
- проверка стат.значимой разницы среднего чека и количества заказов в группах А и В. 

## Используемые библиотеки
*pandas*, *numpy*, *math*, *matplotlib*, *scipy*, *seaborn*

## Выводы по проекту
- Нет статистически значимого различия по среднему количеству заказов между группами ни по «сырым», ни по данным после фильтрации аномалий;
- Есть статистически значимое различия по среднему чеку между группами как по «сырым», так и по данным очищенных от аномальных пользователей. При этом сырые данные демонстрируют прирост среднего чека на заказ в группе В на 28,7% по сравнению с группой А. В то время как очищенные данные говорят: средний чек на заказ в группе В на 3% меньше, чем в группе А.
- График изменения кумалятивного среднего чека группы В относительно группы А нестабилен. Имеют место несколько всплесков. Резкий рост примерно на 2,6 и 18 день, а затем стабильное и снижение. На всплески вероятно оказывали влияние аномальные дорогие заказы, которые мы отфильтровали из сырых данных. Сейчас с одной стороны мы видим прирост группы В по сравнению с А. Возможно с продолжением теста тенденция на снижение среднего чека будет продолжена и станет более очевидно имеется ли прирост в группе В.
- График кумулятивного среднего количества заказов на посетителя показыввает, что до шестого дня группа В по среднему количеству заказов показывала себя хуже, чем группа А. после начала теста группа B лидирует по метрике. С 6 по 10 день группа В выдала достаточно резкий рост, на 15 - 17 день теста группа В достигала 20% прироста относительно группы А. Но далее начало снижение среднего количества заказов. Возможно прирост группы В связан с аномально частыми заказами. Можно предположить, что если тест будет продолжен, то тенденция к снижению прироста группы В над группой А будет продолжен.
- Основываясь на вышесказанном кажется правильным продолжить тест, чтобы более четко зафиксировать тенденции на снижение среднего чека на заказ и среднего количество заказов на пользователя. Пока мы больше склоняемся к тому, что тест неудачен и группа В не показывает значимого экономического эффекта (на очищенных данных среднее кол-во заказов на пользователя не увеличилось, а средний чек на заказ и вовсе стал меньше).
