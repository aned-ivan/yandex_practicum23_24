# Исследование рынка общественного питания в Москве

Инвесторы частного фонда решили попробовать себя в новой области и открыть заведение общественного питания в Москве. Заказчики ещё не знают, что это будет за место: кафе, ресторан, пиццерия, паб или бар, — и какими будут расположение, меню и цены.

Задача проекта — подготовить исследование рынка Москвы, найти интересные особенности и презентовать полученные результаты, которые в будущем помогут в выборе подходящего инвесторам места.

## Данные

Был доступен датасет с заведениями общественного питания Москвы, составленный на основе данных сервисов Яндекс Карты и Яндекс Бизнес на лето 2022 года. Информация, размещённая в сервисе Яндекс Бизнес, могла быть добавлена пользователями или найдена в общедоступных источниках. Она носит исключительно справочный характер.

Датасет содержал следующую информацию:
- название заведения;
- адрес заведения;
- категория заведения, например «кафе», «пиццерия» или «кофейня»;
- информация о днях и часах работы;
- широта географической точки, в которой находится заведение;
- долгота географической точки, в которой находится заведение;
- рейтинг заведения по оценкам пользователей в Яндекс Картах (высшая оценка — 5.0);
- категория цен в заведении, например «средние», «ниже среднего», «выше среднего» и так далее;
- строка, которая хранит среднюю стоимость заказа в виде диапазона, например:
  - «Средний счёт: 1000–1500 ₽»;
  - «Цена чашки капучино: 130–220 ₽»;
  - «Цена бокала пива: 400–600 ₽».
- число с оценкой среднего чека, которое указано только для значений из столбца avg_bill, начинающихся с подстроки «Средний счёт»:
  - Если в строке указан ценовой диапазон из двух значений, в столбец войдёт медиана этих двух значений.
  - Если в строке указано одно число — цена без диапазона, то в столбец войдёт это число.
  - Если значения нет или оно не начинается с подстроки «Средний счёт», то в столбец ничего не войдёт.
- число с оценкой одной чашки капучино, которое указано только для значений из столбца avg_bill, начинающихся с подстроки «Цена одной чашки капучино»:
  - Если в строке указан ценовой диапазон из двух значений, в столбец войдёт медиана этих двух значений.
  - Если в строке указано одно число — цена без диапазона, то в столбец войдёт это число.
  - Если значения нет или оно не начинается с подстроки «Цена одной чашки капучино», то в столбец ничего не войдёт.
- число, выраженное 0 или 1, которое показывает, является ли заведение сетевым (для маленьких сетей могут встречаться ошибки);
- административный район, в котором находится заведение, например Центральный административный округ;
- количество посадочных мест.

## Задачи решавшиеся в проекте:

- изучение категорий пунктов общественного питания по количеству посадочных места, среднему чеку и рейтингу,
- сравнение сетевых и несетевых заведений,
- определение округов и улиц с максимальным и минимальным количеством заведений,
- подсчет количества кофеен в Москве, выявление особенностей их расположения,
- сегментация районов города по среднему чеку и рейтингу кофеен. 

## Используемые библиотеки
*pandas*, *numpy*, *math*, *matplotlib*, *scipy*, *seaborn*, *folium*, *plotly*  

## Выводы по проекту
- Была исследована инфорнация о 5589 заведениях общественного питания. Среди них преобладают "Кафе" (2377шт, 28.3%), "Ресторан" (2041шт, 24.3%) и "Кофейня" (1413, 16.8%). Меньше всего заведений относятся к категории булочных (256, 3.05%) и столовых (315, 3.75%).
- Наибольшее медианное кол-во мест у баров/пабов - 202 места. Далее идут кофейни - 170 мест, пиццерии - 150 мест, быстрое питание - 140, кафе - 111.
- Более 61% заведений общественного питания относятся к несетевым. Сетевыми являются окло 39% заведений.
- Сетевыми чаще всего бывают булочные (61,33%), пиццерии (52,45%) и кофейни (51,38%). Реже всего сетевыми являются бары/пабы (22,2%).
- Самая популярная сеть в Москве со значительным отрывом - кофейня "Шоколадница" (119 филиалов, 3.66% от всех сетей). Далее идут пиццерии Домино'с пицца (77 филиалов, 2,37%) и Додо пицца (74 филиала, 2.27%).
- Средние оценки по категориям отличаются не сильно - все категории в пределах полупроцента. Лидируют с самым высоким средним рейтингом бары/пабы - 4,39. Самые низкие средние рейтинги у заведений быстрого питания и кафе.
- Среди округов самый высокий средний рейтинг всех заведений общественного питания у Центрального (4,37), самый низкий - у Юго-Восточного (4,10).
- Больше всего заведений на Проспекте Мира - 183 объектов. 29% из них - кафе, 24% - рестораны, 19,7% - кофейни. Доля столовых на Проспекте Мира всего 1,1%. Меньше всего заведений на Пятницкой улице - 48 объектов, из которых 37,5% - рестораны, 18,8% - бары, 14,6% - кафе. Столовых на Пятницкой улице нет совсем.

**Рекомендации по открытию кофейни**
- Приоритетным для открытия кофейни можно считать Юго-Западный округ Москвы. В нем самая высокая медианная цена чашки капучино (198 руб), то есть клиенты готовы платить такую цену. Кроме того в этом округе относительно небольшая насыщеность кофейнями - всего 13.54% точек общественного питания относятся к кофейням. 68,42% улиц имеют не более 1 кофейни, то есть конкуренция в категории кофеен ниже чем в других округах.
- В этом округе 7.29% круглосуточных кофеен (7 шт) - самая высокая доля среди всех округов. Кофейни такого формата в округе будут востребованы.
- Средний рейтинг кофеен на юго-западе (4.28) сопоставим с другими округами, при этом минимальный рейтинг кофейти в Юго-Западном округе самый высокий (3,3). Это может говорить о том, что здесь хорошие кофейни-конкуренты выбирают Юго-Западный округ.
