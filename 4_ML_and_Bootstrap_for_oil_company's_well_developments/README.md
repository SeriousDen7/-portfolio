# Выбор локации для скважины
Допустим, мы работаетм в добывающей компании «ГлавРосГосНефть». Необходимо выяснить, где бурить новую скважину.

Нам предоставлены пробы нефти в трёх регионах: в каждом 10 000 месторождений, где измерили качество нефти и объём её запасов. Необходимо построить модель машинного обучения, которая поможет определить регион, где добыча принесёт наибольшую прибыль. Так же проанализируем возможную прибыль и риски техникой *Bootstrap.*

Шаги для выбора локации:

- В избранном регионе ищут месторождения, для каждого определяют значения признаков;
- Строят модель и оценивают объём запасов;
- Выбирают месторождения с самым высокими оценками значений. Количество месторождений зависит от бюджета компании и стоимости разработки одной скважины;
- Прибыль равна суммарной прибыли отобранных месторождений.

**Цель исследования:** 
1. Создание модели и комплекса инструментов для предсказани оптимального выбора региона и конкретых месторождений нефти с помощью машинного обучения.

**Задачи исследования:**
1. Подготовить и выделить данные на 2 выборки: обучающую и валидационную;
2. Обучить и проверить модели для каждого региона; 
3. Расчитать ожидаемую прибыль и выбрать безрисковые месторождения в регионах и регион для дальнейшей разработки.

**Объектом исследования** является информация о замерах показателей месторождений в трех регионах.

**Предметом исследования** является комплекс методик машинного обучения и инструментов связанных с МО.

**Ход выполнения**
1. Импортировать все необходимые библиотеки
2. Загрузить данные из трех файлов
3. Проанализировать общую информацию о качестве и структуре данных, предобработать данные
4. Разбить каждый из 3х датасетов на обучающую и валидационную выборки
5. Обучить и проверить модели (подойдет только линейная регрессия)
6. Рассчитать ожидаемую прибыль по месторождениям
7. Рассчитать вероятность рисков и прибыль в целом по регионам
8. Сделать выводы и рекомендации для дальнейшего исследования

**Описание данных**
Есть 3 набора данных, по каждому региону. Каждая строчка это характеристика месторождения 

Известно:
- `id` — уникальный идентификатор скважины;
- `f0`, `f1`, `f2` — три признака точек (неважно, что они означают, но сами признаки значимы);

Целевой признак
- `product` — объём запасов в скважине (тыс. баррелей).