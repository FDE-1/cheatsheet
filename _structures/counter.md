---
title: Counter
layout: default
---

# Counter

> Counter is a class that is used to count the occurences of a given object.

## When to use
Frequencies

## Syntax
```python
from collections import Counter

obj = [1,2,3,4,5]
obj = "anagram"
obj = {
    "a": 1,
    "b": 2
}
Counter(obj)
```

## Example
```python
from collections import Counter

obj = [1,2,3,4,5]

ctr = Counter(obj)

items = list(ctr.elements()) -> donne un iterators

ctr.update([2,2,3,3,]) / subtract() -> ajoute ces valeurs / enleve les val

ctr.most_common(5) -> 5 most common

del ctr["key"]

```

## Pitfalls
    - Don't use iteration order use most_common
    - avoid storing 0
    - single value check iterable.count(value)

## Usual Pattern
    - One pass frequency map: Counter(iterable)
    - Top-N categories: Counter(data).most_common(n)
    - Incremental update: counter.update(batch) or counter.subtract(batch)
