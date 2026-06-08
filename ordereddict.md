---
title: OrderedDict
layout: default
---
# OrderedDict

> OrderedDict is a dictionnary that remember the order of the keys inserted.

## When to use

LRU(Last recently used), FIFO, need to consider order of items

## Syntax
```python
from collections import OrderedDict

od= OrderedDict()
# or
od = OrderedDict([('a', 1), ('b', 2), ('c', 3)])
```

## Example

```python
from collections import OrderedDict
od = OrderedDict()
od['apple'] = 3
od['banana'] = 5
od['orange'] = 2

od.move_to_end('apple') -> move to end

od.move_to_end('apple', last=False) -> move to the begining

last_item = od.popitem() -> last item pop (LIFO)

first_item = od.popitem(last=False) -> first item (FIFO)
```

## Pitfalls
    - Since python 3.7 dict also guarantees insertion order 
    - Memory: Ordered dict takte more space than dict
    - Equality: check same order but dict check same value / keys

# Usual Pattern
    - LRU Cache: Combine my_dict[key] = value with my_dict.move_to_end(key) when an item is accessed, and my_dict.popitem(last=False) when the cache gets full.
    - Order-Sensitive State: od1 == od2 (To explicitly enforce that two data structures must be built in the exact same sequence to be valid).
    - FIFO Mapping: od.popitem(last=False) allows you to process and remove the oldest dictionary entries efficiently.