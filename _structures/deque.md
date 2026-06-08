---
title: deque
layout: default
---
# deque

> deque is a class that is used as both a queue(FIFO) and a stack(LIFO)

## When to use
queues / BFS

## Syntax
```python
from collections import deque

d = deque([1, 2, 3, 4])
d[0] -> 1
d[-1] -> 4
d.pop() -> remove 4
d.popleft() -> remove 1
d.append(4) -> add 4 at the end 
d.extend([5,6,7]) -> add 5 6 7 at the end
d.appendleft(1) -> add 1 at the begining
d.extendleft([-2, -1, 0]) -> add -2 -1 0 at the begining
d.remove(value) -> remove first occurence of the value
d.rotate(value) -> rotate value to the right work with - value for left 
```

## Example
```python
from collections import deque

task_queue = deque()
task_queue.append("Look at Email")
task_queue.append("Process Refund")
task_queue.append("Update Database")

while task_queue:
    current = task_queue.popleft()
    print(f"Working on: {current}") 



recent_actions = deque(maxlen=3)
actions = ["Opened app", "Clicked settings", "Changed theme", "Saved profile", "Logged out"]

for action in actions:
    recent_actions.append(action)
    print(list(recent_actions)) -> ['Changed theme', 'Saved profile', 'Logged out']



players = deque(["Alice", "Bob", "Charlie", "Diana"])

for turn in range(1, 4):
    current_player = players[0]    
    print(f"player turn: {current_player}")
    players.rotate(-1)
```

## Pitfalls
    - Not a list -> acces to left / right is O(1) but other is O(n)
    - Slicing -> Error
    - Forgetting maxlen
    - Memory Overhead -> doubled link = higher memory 

## Usual Pattern 
    - FIFO Queue / BFS Traversal: queue.append(item) then queue.popleft()
    - Fixed-size history (Sliding window): deque(maxlen=N)
    - Round-robin rotation: queue.rotate(steps)
    - Bidirectional building: queue.appendleft(item) or queue.extendleft(iterable)