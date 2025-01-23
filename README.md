# Выпускная квалификационная работа
Суть работы заключается в том, чтобы выбрать оптимальную форму магнита. Оптимальна она с точки зрения подавления побочных гармоник (6, 10, 14) разложения тангенсального магнитного поля на окружности радиуса 0.8 от апертуры с центром в точке (0, 0, 0), которая лежит в перпендикулярной пролетной оси плоскости.
У магнита имеются гиперпараметры формы такие как:
- ```Положение центра шима```;
- ```Точка обрыва гиперболы```;
- ```Высота гиперболы```;
- ```Радиус кривизны шима```;
- ```...```.

Рассматриваемый в этой работе пример более простой геометрии полюсного наконечника с двумя параметрами:

<img 
  src=https://github.com/Askash1234567890/Diplome/blob/main/pictures/рисунок_полюса.png
  alt="Геометрия полюса"
  width="500"
/>

Схема макроса для сбора данных и структура бд:

<img
  src=https://github.com/Askash1234567890/Diploma/blob/main/pictures/схема_алгоритма_сбора_данных.png
  alt='Сбор данных'
  width='900'
/>
## Этапы решения задачи:
- [x] Разобраться как строить геометрию в ```opera```;
- [x] Написать скрипт, который будет перебирать гиперпараметры задачи, получать значение *6, 10, 14* гармоник магнитного поля и записывать ее в бд - собираем *тренировочные* данные;
- [x] Накопить ```1024``` тренировочных примера;
- [x] Обучить мл модель на регрессию 6, 10, 14 гармоник магнитного поля по признакам (гиперпараметрам);
- [x] Использовать градиентный спуск, где в качестве варьируемых параметров выступают признаки, а веса модели неизменяемы (в качестве функции потерь использовать сумму 6, 10 и 14 гармоник магнитного поля = результат ```model.predict``` регрессионной модели для каждой из задачи);
- [x] Получить конечную форму.

## Дополнительно:
- [ ] Сделать единую сборку ```opera``` для создания полноценного API;
- [ ] Попробовать генетические алгоритмы;
- [ ] Попробовать обучение с подкреплением.

## Масштабирование решения
Если реализовать этот алгоритм на задаче с *двумя* степенями свободы формы, то он легко масштабируется на более сложную задачу с не столь очевидной формой. В рамках данного проекта произведена реализация для простого примера геометрии полюсных наконечников - параллелепипедов с фасками.
