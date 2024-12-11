# Дипломная работа
Суть работы заключается в том, чтобы выбрать оптимальную форму магнита. Оптимальна она с точки зрения подавления побочных гармоник (6, 10, 14) разложения тангенсального магнитного поля на окружности 0.8 от апертуры.
У магнита имеются гиперпараметры формы такие как:
- ```Положение центра шима```;
- ```Точка обрыва гиперболы```;
- ```Высота гиперболы```;
- ```Радиус кривизны шима```;
- ```...```.

## Этапы реализации конечной задачи:
- [ ] Разобраться как строить геометрию в ```opera```;
- [ ] Написать скрипт, который будет перебирать гиперпараметры задачи, получать значение *6, 10, 14* гармоник градиента и записывать ее в бд - собираем *тренировочные* данные;
- [ ] Накопить около ```1_000``` тренировочных примеров;
- [ ] Обучить мл модель на регрессию 6, 10, 14 гармоник градиента по признакам (гиперпараметрам);
- [ ] Использовать градиентный спуск, где в качестве варьируемых параметров выступают признаки, а веса модели неизменяемы (в качестве функции потерь использовать сумму 6, 10 и 14 гармоник градиента = результат ```model.predict``` регрессионной модели для каждой из задачи);
- [ ] Попробовать генетический алгоритм вместо мльного.

## Промежуточная задача
Если реализовать этот алгоритм на более простой задаче, которая обладает всего *двумя* степенями свободы формы, то алгоритм легко масштабируется на более сложную исходную задачу. Попробуем реализовать на простом примере, после чего можно приступать к сложному.
