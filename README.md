# algoMain

Это модуль созданный в целях научиться экспортировать свой код на Python

## Инструкция 

### Установка пакета

```python
>>> pip install algomain
```

### Импорт проекта

```python
import algoMain
```

### Встроенные функции

**Простой поиск для любого списка**

Функция `l_search` выполняет поиск элемента в списке по его индексу.

**Бинарный поиск для сортированного (по возрастанию) списка**

Функция `b_search` выполняет бинарный поиск элемента в отсортированном по возрастанию списке.

```python
arr = [15, 14, 37, 62, 87]

l_search(arr, 62) # 3
b_search(arr, 14) # 1
```

**Поиск в ширину для графов**

Функция `search_in_width` выполняет поиск в ширину для графов и возвращает словарь, в котором показано количество расстояний от стартового узла.

```python
graph = {  
    'A': ['B', 'C', 'D'],  
    'B': ['A', 'C', 'E'],  
    'C': ['A', 'B', 'D', 'F'],  
    'D': ['A', 'C', 'G'],  
    'E': ['B', 'H'],  
    'F': ['C', 'I'],  
    'G': ['D', 'J'],  
    'H': ['E', 'I'],  
    'I': ['F', 'H'],  
    'J': ['G']  
}

search_in_width(graph, "J")
# {0: ['J'], 1: ['G'], 2: ['D'], 3: ['A', 'C'], 4: ['B', 'F'], 5: ['E', 'I'], 6: ['H']}
```

**Алгоритм Дейкстры для взвешенных графов**

Функция `dijkstra` выполняет алгоритм Дейкстры для взвешенных графов.

```python
graph = {  
    'A': {'B': 1, 'C': 2, 'D': 3},  
    'B': {'A': 1, 'C': 4, 'E': 5},  
    'C': {'A': 2, 'B': 4, 'D': 6, 'F': 7},  
    'D': {'A': 3, 'C': 6, 'G': 8},  
    'E': {'B': 5, 'H': 9},  
    'F': {'C': 7, 'I': 10},  
    'G': {'D': 8, 'J': 11},  
    'H': {'E': 9, 'I': 12},  
    'I': {'F': 10, 'H': 12},  
    'J': {'G': 11}  
}

dijkstra(graph, "J")
# {'A': 22, 'B': 23, 'C': 24, 'D': 19, 'E': 28, 'F': 31, 'G': 11, 'H': 37, 'I': 41, 'J': 0}
```

**Динамическое программирование**

Функция `knapsack` выполняет динамическое программирование для задачи о рюкзаке. Она принимает вместимость рюкзака и список предметов, каждый из которых представлен в виде кортежа с весом и стоимостью.

```python
capacity = 10  
items = [(5, 10), (4, 40), (6, 30), (3, 50)]

knapsack(capacity, items) # (90, [(3, 50), (4, 40)])
```

**Алгоритм k-ближайших соседей**

Функция `knn` выполняет поиск k ближайших соседей для тестируемого элемента с использованием евклидова расстояния. Она принимает список кортежей с предметами, тестируемый элемент и количество похожих элементов (k).

```python
items = [  
    [1.0, 2.0, 3.0],  
    [2.0, 3.0, 4.0],  
    [3.0, 4.0, 5.0],  
    [5.0, 5.0, 5.0]  
]  
test = [3.5, 3.5, 3.5]

knn(items, test, k=2)  #[[2.0, 3.0, 4.0], [3.0, 4.0, 5.0]]
