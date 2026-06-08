from collections import Counter, defaultdict, deque, OrderedDict

# ==========================================
# 1. Standard Dictionary (dict)
# ==========================================
d = {}

d["key"] = "value"       # -> O(1) average, O(N) worst case (Insertion)
val = d["key"]           # -> O(1) average (Lookup)
val = d.get("key", 0)    # -> O(1) average (Safe lookup with default)
"key" in d               # -> O(1) average (Existence check)
del d["key"]             # -> O(1) average (Deletion)
val = d.pop("key")       # -> O(1) average (Pop and return)

# Iteration
# -> O(N) to iterate through all items
for k, v in d.items(): 
    pass


# ==========================================
# 2. Default Dictionary (defaultdict)
# ==========================================
# Automatically initializes missing keys with the factory function (e.g., int -> 0, list -> [])
dd = defaultdict(int)

dd["new_key"] += 1       # -> O(1) average (Auto-initializes to 0, then adds 1)
dd["missing_key"]        # -> O(1) average (Auto-initializes to 0 and returns it)
dd.get("missing_key")    # -> O(1) average (Safe lookup, DOES NOT auto-initialize)


# ==========================================
# 3. Counter
# ==========================================
data = ['a', 'a', 'b', 'c']
c = Counter(data)        # -> O(N) where N is len(data)

c["a"] += 1              # -> O(1) average (Update count)
c["z"]                   # -> O(1) average (Returns 0 for missing keys)

# K is the number of elements requested, N is total unique elements
c.most_common(2)         # -> O(N log K) (Returns list of top K most common elements)
c.update(['b', 'c'])     # -> O(M) where M is the size of the new batch


# ==========================================
# 4. Double-Ended Queue (deque)
# ==========================================
dq = deque([1, 2, 3])    # -> O(N) to initialize from iterable

dq.append(4)             # -> O(1) (Add to right)
dq.appendleft(0)         # -> O(1) (Add to left)

right_val = dq.pop()     # -> O(1) (Remove from right)
left_val = dq.popleft()  # -> O(1) (Remove from left)

dq[0]                    # -> O(1) (Peek left)
dq[-1]                   # -> O(1) (Peek right)
dq[5]                    # -> O(N) (Random access in the middle is SLOW)

dq.rotate(1)             # -> O(K) where K is the number of steps rotated


# ==========================================
# 5. OrderedDict
# ==========================================
od = OrderedDict()

od["a"] = 1              # -> O(1) average (Insertion)
od["b"] = 2

od.move_to_end("a")              # -> O(1) (Moves key to the right/end)
od.move_to_end("b", last=False)  # -> O(1) (Moves key to the left/beginning)

last_item = od.popitem()         # -> O(1) (Pops rightmost / LIFO)
first_item = od.popitem(last=False) # -> O(1) (Pops leftmost / FIFO)