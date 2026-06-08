---
title: defaultdict
layout: default
---

# defaultdict
> defaultdict in Pyhon

> defaultdict is a class in python that create a dict that assign default value to keys that do not exist.

## When to use
Grouping of element.

## Syntax:
```python
from collections import defaultdict

d= defaultdict(default_factory) -> i.e. list, int, set
d.values()
d.keys()
del d["key"]
d.clear()
```

## Example:
```python
from collections import defaultdict
words = ["apple", "ant", "banana"]
d = defaultdict(list)

for word in words:
    d[word[0]].append(word) -> group by first letter

d = defaultdict(list)
for i in range(5):
    d[i].append(i) -> {0: [0], 1: [1], 2: [2], 3: [3], 4: [4]}


```

## Pitfalls
    - access with get() to avoid exceptions
    - update with update(key=value) to avoid exceptions
    - copy with copy()
    - num and diff type (bool, float) can be the same key (1 == 1.0 == True) 

## Usual Pattern
    - Grouping / Graph Adjacency Lists: d = defaultdict(list) then d[key].append(value)
    - Counting / Frequency Tracking: d = defaultdict(int) then d[key] += 1
    - Categorizing Unique Items: d = defaultdict(set) then d[key].add(value)
    - 2D Grids / Nested Maps: d = defaultdict(lambda: defaultdict(int)) then d[x][y] += 1