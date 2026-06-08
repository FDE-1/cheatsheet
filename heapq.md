---
title: heapq
layout: default
---
# heapq

> heapq is module that create a heap priority queue(smallest at the first)

## When to use
Priorities, Top-K element, Botton-K element

## Syntax
```python
import heapq

heap = []

obj = [5, 2, 8, 1]
heapq.heapify(obj)
```

## Example
```python
import heapq

heap = []

obj = [5, 2, 8, 1]

heapq.heapify(obj) -> O(n)

heapq.heappush(heap, 3) ->  add 3

smallest = heapq.heappop(heap) -> return smallest i.e. 1

heapq.heappushpop(heap, 4) -> push 4 and then return smallest i.e. 2 

heapq.heapreplace(heap, 10)-> return smallest i.e. 3 and add 10

heapq.nlargest(2, heap) -> return list of 2 largest

heapq.nsmallest(2, heap) -> return list of 2 smallest

```

## Pitfalls
    - MinHeap -> Maxheap = multiply by -1
    - Only heap[0] is ordered, i.e. smallest rest not sorted
    - Tuple it use the (priority, obj) -> if tie compare of obj == crash if no comparaison method


## Usual Pattern
    - Top-K or Bottom-K elements: heapq.nlargest(k, iterable) / heapq.nsmallest(k, iterable)
    - Priority Queue: heapq.heappush(heap, (priority, task_id, task)) (using a unique task_id prevents the object comparison crash mentioned above)
    - Merging sorted streams: heapq.merge(*iterables) to combine multiple sorted lists into one sorted iterator