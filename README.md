# Примеры алгоритмов оптимизации

В данном репозитории представлены примеры несложных алгоритмов для задач оптимизации или комбинаторики. Все реализовано на языке F#. 
Для каждого примера написан небольшой набор тестовых случаев.

## Жадные алгоритмы

### Размен валюты

#### Проект
Проект `OptimizationProblems.Greedy.MoneyExchange`.  

#### Задача
Простая задача: необходимо разменять некоторую сумму с помощью монет предложенных номиналов таким образом, чтобы общее количество купюр было минимальным.

#### Входные значения
На входе функция два параметра: `nominals` - массив номиналов монет, `sum` - сумма для размена.  

#### Результат
На выходе список пар `(номинал, количество)`, отсортированный по убыванию номинала.

#### Пример
Вход:
```
[1; 5; 10, 100]
207
```
Результат:
```
[(100, 2); (5, 1); (1, 2)]
```

### Задача о рюкзаке

#### Проект
Проект `OptimizationProblems.Greedy.Bagpack`.  

#### Задача
Дан набор *неделимых на куски* предметов с известной стоимостью и массой, а также вместимость некоторого контейнера (рюкзака). 
Необходимо поместить в рюкзак предметы таким образом, чтобы стоимость была минимальной.  

#### Входные значения
На входе три параметра: массив масс `weights`, массив стоимостей `prices` и емкость рюкзака `capacity`.  

#### Результат
На выходе возвращается список пар `(цена, масса)`, соответствующий предметам, которые необходимо взять.  

#### Примечание
Жадный алгоритм для данной задачи часто дает неточное решение.

#### Пример
Вход
```
[100; 240; 300; 400; 420;]
[5; 3; 2; 4; 6;]
```
Результат:
```
[(240, 3); (300, 2); (400, 4);  (420, 6)]
```

### Оптимальное слияние массивов

#### Проект
Проект `OptimizationProblems.Greedy.OptimalMerge`.  

#### Задача
Предположим, что для слияния массивов длинами `M` и `N` требуется строго `M` + `N` операций. Дан список длин массивов. 
Необходимо найти минимальное количество операций, которое потребуется при попарном слиянии всех массивов в один.  

#### Входные данные
На входе дается список из длин массивов.  

#### Результат
Возвращается целое число - минимально возможное количество операций.

#### Пример
Например, пусть мы имеем массив длин `1 1 1 1`. Минимальным количеством операций тогда будет `8`: `1 1 1 1` --> `2(1+1) 1 1` --> `2 2(1+1)` --> `4(2+2)`

Вход
```
[1; 1; 1; 1]
```
Результат:
```
8
```  

### Активности с дедлайнами

#### Проект
Проект `OptimizationProblems.Greedy.ActivitiesWithDeadlines`.  

#### Задача
Пусть за каждую активность полагается некоторая награда. 
Пусть также у каждой активности имеется некоторый дедлайн - время, после которого активность становится недоступной. 
Предположим, что на каждую активность требуется ровно одна едициница времени на выполнение. 
Требуется выбрать такие активности, чтобы общая прибыль от их выполнения была максимальной. Считаем, что на начало работы текущее время равно `0`.

#### Входные данные
На вход подается список пар `(стоимость, дедлайн)`. Каждая пара представлена в виде записи.

#### Результат
Функция возвращает список активностей, которые необходимо "взять", чтобы получить наибольшую прибыль.

#### Пример
Вход:
```
[ 
  { Price = 5; Deadline = 1 }
  { Price = 10; Deadline = 1 }
  { Price = 1; Deadline = 2 }
]
```
Результат:
```
[
  { Price = 10; Deadline = 1 }
  { Price = 1; Deadline = 2 }
]
```

### Выбор максимального числа активностей

#### Проект
Проект `OptimizationProblems.Greedy.SelectActivities`.

#### Задача
Дан список некоторых мероприятий. Про каждое мероприятие известно время начала и время окончания. 
Необходимо выбрать максимальное число мероприятий, при условии, что каждое из мероприятий будет посещено от начала до конца.

#### Входные данные
На входе дается список пар целочисленных значений: время начала и время конца мероприятия. Каждая пара значений представлена в виде записи.

#### Результат
Функция возвращает список мероприятий, которые необходимо выбрать. Мероприятия не должны "пересекаться" по времени: каждое мероприятие необходимо посетить полностью.

#### Пример
Вход:
```
[
  {Start = 0; End = 3} 
  {Start = 2; End = 3} 
  {Start = 4; End = 6} 
  {Start = 5; End = 7} 
]
```

Результат (возможный):
```
[
  {Start = 0; End = 3}
  {Start = 4; End = 6}
]
```

## Динамическое программирование
### Задача о рюкзаке
...

## Поиск с возвратом
### Поиск подмножества с определенной суммой
...
### Задача N ферзей
...
