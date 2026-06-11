# 🐍 Day 13 — Advanced Python Mastery
## Iterators · Generators · Decorators · Context Managers · Functional Programming · Python Internals

---

## 📋 Table of Contents

| # | Section | Topics |
|---|---------|--------|
| 01 | [Complete Revision Day01–Day12](#section-1) | Summary, Roadmap, Cheat Sheets |
| 02 | [Python Internals Masterclass](#section-2) | Bytecode, VM, Memory, GC |
| 03 | [Iterables vs Iterators](#section-3) | iter(), next(), StopIteration |
| 04 | [Generators Masterclass](#section-4) | yield, Lazy Evaluation |
| 05 | [Advanced Generators](#section-5) | Infinite, Pipeline, Streaming |
| 06 | [Decorators Masterclass](#section-6) | Wrappers, Logging, Auth, Cache |
| 07 | [Closures Masterclass](#section-7) | Enclosure, State Preservation |
| 08 | [Context Managers Masterclass](#section-8) | with, __enter__, __exit__ |
| 09 | [Functional Programming Masterclass](#section-9) | lambda, map, filter, reduce |
| 10 | [Advanced Comprehensions](#section-10) | List, Set, Dict, Generator |
| 11 | [Advanced Pythonic Patterns](#section-11) | Duck Typing, EAFP, Composition |
| 12 | [Performance Optimization](#section-12) | Memory, Profiling, Benchmarks |
| 13 | [Debugging Advanced Python](#section-13) | Decorator/Generator/Closure Bugs |
| 14 | [Python Developer Best Practices](#section-14) | Clean Code, PEP8, Testing |
| 15 | [Mini Projects (10)](#section-15) | Complete Code + Flowcharts |
| 16 | [20 Portfolio Projects](#section-16) | Architecture + Roadmaps |
| 17 | [Project Layout Masterclass](#section-17) | Folder Structures |
| 18 | [GitHub Profile Booster Projects](#section-18) | Recruiter-Focused |
| 19 | [Complete Project Solution Framework](#section-19) | From Idea to GitHub |
| 20 | [700 Practice Questions](#section-20) | Easy / Medium / Advanced |
| 21 | [350 Interview Questions](#section-21) | With Answers |
| 22 | [Assignments + Solutions](#section-22) | 5 Full Assignments |
| 23 | [Enterprise Challenge Projects](#section-23) | 10 Enterprise-Grade |
| 24 | [Day13 Revision — Cheat Sheets](#section-24) | Mind Maps, One-Pagers |
| 25 | [Preparation for Day14](#section-25) | Testing, pytest, CI/CD |

---

<a name="section-1"></a>

## 📚 Section 1 — Complete Revision: Day01–Day12

### 1.1 Python Developer Roadmap So Far

```
Day01 ─── Fundamentals, Variables, Operators, Data Types
Day02 ─── Strings, Input Handling, Memory Model
Day03 ─── Conditional Statements (if/elif/else, match-case)
Day04 ─── Loops + Pattern Printing (for, while, nested)
Day05 ─── Functions + Recursion (scope, *args, **kwargs)
Day06 ─── Lists (methods, slicing, sorting, comprehensions)
Day07 ─── Tuples + Sets + Dictionaries (advanced usage)
Day08 ─── Modules + Packages + Virtual Environments (pip, venv)
Day09 ─── Exception Handling + Logging + Debugging
Day10 ─── File Handling + CSV + JSON (pathlib, os)
Day11 ─── OOP Fundamentals (class, object, encapsulation)
Day12 ─── Advanced OOP + SOLID + Design Patterns
Day13 ─── 🔥 Iterators, Generators, Decorators, Context Managers,
           Functional Programming, Python Internals
```

---

### 1.2 Day01–Day12 Summary Table

| Day | Topic | Key Concepts | Must Know |
|-----|-------|-------------|-----------|
| 01 | Fundamentals | Variables, int, float, bool, None, operators | Type system, mutable vs immutable |
| 02 | Strings | Slicing, methods, f-strings, memory interning | String immutability |
| 03 | Conditionals | if/elif/else, ternary, match-case | Short-circuit evaluation |
| 04 | Loops | for, while, break, continue, pass, nested | Loop efficiency |
| 05 | Functions | def, return, scope, *args, **kwargs, recursion | LEGB rule |
| 06 | Lists | append, extend, pop, sort, list comprehension | O(n) insert at head |
| 07 | Tuples/Sets/Dicts | Packing, frozenset, dict methods | Hashability |
| 08 | Modules | import, __init__, pip, venv, sys.path | Module search path |
| 09 | Exceptions | try/except/else/finally, custom exceptions, logging | Exception hierarchy |
| 10 | File Handling | open, with, pathlib, csv, json | Context managers |
| 11 | OOP Basics | class, __init__, self, methods, properties | Object lifecycle |
| 12 | Advanced OOP | Inheritance, polymorphism, SOLID, Design Patterns | MRO, metaclasses |

---

### 1.3 OOP Cheat Sheet

```python
# CLASS DEFINITION
class Animal:
    species = "Unknown"           # class variable (shared)

    def __init__(self, name, age):
        self.name = name          # instance variable
        self.age = age            # instance variable

    def speak(self):              # instance method
        return f"{self.name} makes a sound"

    @classmethod
    def create(cls, name):        # class method
        return cls(name, 0)

    @staticmethod
    def info():                   # static method
        return "Animals are living beings"

    def __repr__(self):
        return f"Animal(name={self.name!r}, age={self.age!r})"

    def __str__(self):
        return f"{self.name} (age {self.age})"


# INHERITANCE
class Dog(Animal):
    def __init__(self, name, age, breed):
        super().__init__(name, age)   # call parent __init__
        self.breed = breed

    def speak(self):                  # METHOD OVERRIDE
        return f"{self.name} says Woof!"


# DUNDER METHODS (Magic Methods)
class Vector:
    def __init__(self, x, y):
        self.x, self.y = x, y

    def __add__(self, other):      return Vector(self.x + other.x, self.y + other.y)
    def __mul__(self, scalar):     return Vector(self.x * scalar, self.y * scalar)
    def __len__(self):             return 2
    def __getitem__(self, index):  return (self.x, self.y)[index]
    def __eq__(self, other):       return self.x == other.x and self.y == other.y
    def __hash__(self):            return hash((self.x, self.y))
    def __bool__(self):            return bool(self.x or self.y)
    def __repr__(self):            return f"Vector({self.x}, {self.y})"
```

---

### 1.4 SOLID Principles Cheat Sheet

```
S — Single Responsibility Principle
    ✅ One class, one reason to change
    ❌ Do NOT mix data access + business logic + UI in one class

O — Open/Closed Principle
    ✅ Open for extension, closed for modification
    ❌ Do NOT modify existing classes to add new behavior — subclass them

L — Liskov Substitution Principle
    ✅ Subclass should be fully substitutable for its parent
    ❌ Do NOT override methods in ways that break parent contract

I — Interface Segregation Principle
    ✅ Many small interfaces better than one fat interface
    ❌ Do NOT force classes to implement methods they don't need

D — Dependency Inversion Principle
    ✅ Depend on abstractions (ABC), not concrete implementations
    ❌ Do NOT hardcode dependencies inside a class — inject them
```

---

### 1.5 Design Patterns Cheat Sheet

| Pattern | Type | Python Example |
|---------|------|----------------|
| Singleton | Creational | `__new__` override |
| Factory Method | Creational | classmethod returning subclass |
| Abstract Factory | Creational | ABC with create methods |
| Builder | Creational | Method chaining class |
| Prototype | Creational | `copy.deepcopy()` |
| Adapter | Structural | Wrapper class changing interface |
| Decorator | Structural | Wrapping object to add behavior |
| Facade | Structural | Simple interface over complex system |
| Observer | Behavioral | Event system, callbacks list |
| Strategy | Behavioral | Pass algorithm as callable |
| Command | Behavioral | Encapsulate action as object |
| Iterator | Behavioral | `__iter__` + `__next__` protocol |

---

<a name="section-2"></a>

## 🔬 Section 2 — Python Internals Masterclass

### 2.1 How Python Executes Code

```
SOURCE CODE  (.py file)
      │
      ▼
 [LEXER / TOKENIZER]
  Converts text → tokens
  "def", "hello", "(", ")", ":"
      │
      ▼
 [PARSER]
  Tokens → Abstract Syntax Tree (AST)
      │
      ▼
 [COMPILER]
  AST → Bytecode (.pyc file)
      │
      ▼
 [PYTHON VIRTUAL MACHINE (CPython PVM)]
  Executes bytecode instruction by instruction
      │
      ▼
   RESULT / OUTPUT
```

### 2.2 Viewing Bytecode

```python
import dis

def add(a, b):
    return a + b

dis.dis(add)
# Output:
#   2           0 LOAD_FAST                0 (a)
#               2 LOAD_FAST                1 (b)
#               4 BINARY_OP               0 (+)
#               8 RETURN_VALUE
```

### 2.3 The Python Virtual Machine (PVM)

The CPython PVM is a **stack-based virtual machine**. It operates on a call stack where each function call pushes a **frame** onto the stack.

```
CALL STACK
┌──────────────────────────────┐
│  Frame: main()               │  ← current executing frame
│    locals: x=10, y=20        │
│    bytecode pointer: inst #6 │
├──────────────────────────────┤
│  Frame: add(x, y)            │
│    locals: a=10, b=20        │
│    bytecode pointer: inst #4 │
├──────────────────────────────┤
│  Frame: <module>             │
│    globals: {add: <func>}    │
└──────────────────────────────┘
```

Each frame contains:
- **f_locals** → local variable dictionary
- **f_globals** → global variable dictionary
- **f_code** → code object (bytecode)
- **f_lineno** → current line number

### 2.4 Reference Counting — Memory Management

Python tracks object lifetime using **reference counting**. Every object has `ob_refcnt`. When it reaches 0, the object is deallocated.

```python
import sys

x = [1, 2, 3]
print(sys.getrefcount(x))   # 2 (x + getrefcount arg)

y = x                        # refcount → 3
z = x                        # refcount → 4
del y                        # refcount → 3
del z                        # refcount → 2
del x                        # refcount → 1 (getrefcount still holds it temporarily)
# After leaving scope → 0 → DEALLOCATION
```

**Reference Count Diagram:**

```
Object [1, 2, 3]
┌─────────────────────────────────┐
│ ob_refcnt: 3                    │
│ ob_type: list                   │
│ ob_size: 3                      │
│ data: [ptr→1, ptr→2, ptr→3]     │
└─────────────────────────────────┘
    ▲         ▲         ▲
    │         │         │
  x = …    y = x     z = x
```

### 2.5 Garbage Collector — Cycle Detection

Reference counting fails for **circular references**:

```python
import gc

a = []
b = []
a.append(b)   # a → b
b.append(a)   # b → a  ← CYCLE! Neither refcount reaches 0

gc.collect()  # Force garbage collection to break cycles
print(gc.get_count())  # (gen0, gen1, gen2) object counts
```

Python's GC uses **generational garbage collection** with 3 generations:
- **Gen 0**: Newly allocated objects (collected most frequently)
- **Gen 1**: Objects that survived Gen 0 collection
- **Gen 2**: Long-lived objects (collected least frequently)

### 2.6 Python Object Model

Everything in Python is an object. Every object has:

```
┌────────────────────────────────┐
│         PyObject               │
├────────────────────────────────┤
│  ob_refcnt  (reference count)  │
│  ob_type    (pointer to type)  │
│  [type-specific data]          │
└────────────────────────────────┘
```

```python
# Everything is an object
print(type(42))           # <class 'int'>
print(type(int))          # <class 'type'>
print(type(type))         # <class 'type'>  ← type is its own type!

# Functions are objects
def greet():
    pass

print(type(greet))        # <class 'function'>
print(id(greet))          # memory address
greet.custom_attr = "AI"  # attach attributes to functions!
print(greet.custom_attr)  # AI
```

### 2.7 Memory Internals — Small Integer Caching

CPython caches small integers (-5 to 256) for performance:

```python
a = 100
b = 100
print(a is b)   # True  → same object in memory (cached)

a = 1000
b = 1000
print(a is b)   # False → new objects created (not cached)

# String interning
s1 = "hello"
s2 = "hello"
print(s1 is s2)   # True  → strings interned

s1 = "hello world!"
s2 = "hello world!"
print(s1 is s2)   # May be False → not always interned
```

### 2.8 The GIL (Global Interpreter Lock)

The **Global Interpreter Lock** (GIL) is a mutex that protects Python objects from concurrent access by multiple threads.

```
Thread 1:  acquire GIL → execute bytecodes → release GIL
Thread 2:  waiting...   → acquire GIL → execute bytecodes → release GIL

Effect:  True parallelism blocked for CPU-bound tasks
         I/O-bound tasks still benefit (GIL released during I/O wait)

Solution for CPU-bound parallelism:
    → multiprocessing (separate processes = separate GILs)
    → Use PyPy, Cython, or Python 3.13+ free-threaded mode
```

---

<a name="section-3"></a>

## 🔄 Section 3 — Iterables vs Iterators

### 3.1 Definitions

| Concept | Definition | Protocol |
|---------|-----------|----------|
| **Iterable** | Any object that can be looped over | Must implement `__iter__()` |
| **Iterator** | Object that tracks iteration state | Must implement `__iter__()` AND `__next__()` |

> **Key insight:** All iterators are iterables. Not all iterables are iterators.

### 3.2 The Iteration Protocol

```
for x in collection:
    process(x)

IS EXACTLY EQUIVALENT TO:

iterator = iter(collection)      # calls collection.__iter__()
while True:
    try:
        x = next(iterator)       # calls iterator.__next__()
        process(x)
    except StopIteration:        # iterator exhausted
        break
```

### 3.3 Internal Working — Memory Diagram

```
ITERABLE: [10, 20, 30]
┌───────────────────────────────────┐
│  list object                      │
│  data: [10, 20, 30]               │
│  __iter__() → creates iterator    │
└────────────────┬──────────────────┘
                 │ iter([10, 20, 30])
                 ▼
ITERATOR: list_iterator
┌───────────────────────────────────┐
│  list_iterator object             │
│  index: 0   ← current position   │
│  ref: → [10, 20, 30]             │
│  __next__() → returns item[index]│
│              increments index     │
│              raises StopIteration │
│              when index >= len   │
└───────────────────────────────────┘
```

### 3.4 iter() and next() in Detail

```python
numbers = [10, 20, 30]

# Create iterator manually
it = iter(numbers)
print(type(it))       # <class 'list_iterator'>

print(next(it))       # 10
print(next(it))       # 20
print(next(it))       # 30

try:
    print(next(it))   # Raises StopIteration
except StopIteration:
    print("Iterator exhausted!")

# iter() with sentinel
# iter(callable, sentinel) → calls callable until it returns sentinel
import random
# Keep calling random.randint(1,6) until we get 6
dice_roll = iter(lambda: random.randint(1, 6), 6)
for roll in dice_roll:
    print(f"Rolled: {roll}")
print("Rolled a 6! Game over.")
```

### 3.5 Building a Custom Iterator

```python
class Countdown:
    """Iterator that counts down from n to 1."""

    def __init__(self, start):
        self.current = start

    def __iter__(self):
        """Return self — iterator IS the iterable."""
        return self

    def __next__(self):
        if self.current <= 0:
            raise StopIteration
        value = self.current
        self.current -= 1
        return value


# Usage
countdown = Countdown(5)
for num in countdown:
    print(num)   # 5, 4, 3, 2, 1

# Manual
c = Countdown(3)
print(next(c))   # 3
print(next(c))   # 2
print(next(c))   # 1
# next(c)        # StopIteration
```

### 3.6 Custom Iterable (Separate Iterator)

```python
class NumberRange:
    """Iterable (not iterator) — can create multiple iterators."""

    def __init__(self, start, stop, step=1):
        self.start = start
        self.stop = stop
        self.step = step

    def __iter__(self):
        return NumberRangeIterator(self)   # returns a NEW iterator


class NumberRangeIterator:
    """The actual iterator for NumberRange."""

    def __init__(self, number_range):
        self.range = number_range
        self.current = number_range.start

    def __iter__(self):
        return self

    def __next__(self):
        if self.current >= self.range.stop:
            raise StopIteration
        value = self.current
        self.current += self.range.step
        return value


# Multiple independent iterations
r = NumberRange(1, 10, 2)
for x in r:
    print(x)   # 1, 3, 5, 7, 9

# Second iteration — works because __iter__ creates new iterator
for x in r:
    print(x)   # 1, 3, 5, 7, 9 (again)
```

### 3.7 Common Iterables in Python

```python
# All of these are iterables
print(hasattr(list,       '__iter__'))  # True
print(hasattr(str,        '__iter__'))  # True
print(hasattr(dict,       '__iter__'))  # True
print(hasattr(set,        '__iter__'))  # True
print(hasattr(tuple,      '__iter__'))  # True
print(hasattr(range,      '__iter__'))  # True
print(hasattr(generator,  '__iter__'))  # True (if defined)

# Check if something is iterator
from collections.abc import Iterator, Iterable

nums = [1, 2, 3]
it = iter(nums)

print(isinstance(nums, Iterable))   # True
print(isinstance(nums, Iterator))   # False ← list is NOT an iterator
print(isinstance(it,   Iterable))   # True
print(isinstance(it,   Iterator))   # True ← list_iterator IS an iterator
```

### 3.8 Iterator Common Mistakes

```python
# ❌ MISTAKE 1: Reusing an exhausted iterator
it = iter([1, 2, 3])
list(it)          # [1, 2, 3] — exhausted
list(it)          # []        — empty! iterator is gone

# ✅ FIX: Create a new iterator each time
data = [1, 2, 3]
list(iter(data))  # [1, 2, 3]
list(iter(data))  # [1, 2, 3]  ← fresh iterator

# ❌ MISTAKE 2: Iterator is its own iterable
it = iter([1, 2, 3])
for x in it:
    print(x)
# After loop, it is exhausted
for x in it:   # Nothing prints — same exhausted iterator
    print(x)
```

### 3.9 Interview Questions — Iterators

1. **Q: What is the difference between an iterable and an iterator?**  
   A: An iterable has `__iter__()` and returns an iterator. An iterator has both `__iter__()` and `__next__()` and maintains state. An iterable can create fresh iterators; an iterator is consumed once.

2. **Q: What happens when `next()` is called on an exhausted iterator?**  
   A: It raises `StopIteration`.

3. **Q: Can you iterate over a custom object twice?**  
   A: Yes, if you implement it as an iterable (not iterator). The `__iter__` method should return a new iterator object each time.

4. **Q: What does `iter(callable, sentinel)` do?**  
   A: It repeatedly calls `callable` until the return value equals `sentinel`, then raises `StopIteration`.

---

<a name="section-4"></a>

## ⚡ Section 4 — Generators Masterclass

### 4.1 What is a Generator?

A **generator** is a special function that uses `yield` instead of `return`. It produces values **lazily** — one at a time — and pauses execution between yields.

```
REGULAR FUNCTION                   GENERATOR FUNCTION
─────────────────                  ──────────────────
def func():                        def gen():
    return [1, 2, 3]                   yield 1
                                       yield 2
func()         → [1, 2, 3]             yield 3
               (ALL at once)
               (ALL in memory)     gen()          → <generator object>
                                   next(gen())    → 1 (pause here)
                                   next(gen())    → 2 (pause here)
                                   next(gen())    → 3 (pause here)
                                   next(gen())    → StopIteration
```

### 4.2 How yield Works — Internal State Machine

```python
def simple_gen():
    print("Before first yield")
    yield 1                          # PAUSE — state saved
    print("Between yields")
    yield 2                          # PAUSE — state saved
    print("After last yield")
    # Function ends → StopIteration raised automatically


g = simple_gen()
print(type(g))    # <class 'generator'>

print(next(g))
# Prints: "Before first yield"
# Returns: 1

print(next(g))
# Prints: "Between yields"
# Returns: 2

next(g)
# Prints: "After last yield"
# Raises: StopIteration
```

**Generator State Machine:**

```
State: CREATED
    │
    │ first next()
    ▼
State: RUNNING → executes until yield
    │
    │ hits yield
    ▼
State: SUSPENDED (locals, stack frame SAVED)
    │
    │ next() called again
    ▼
State: RUNNING → resumes from after yield
    │
    │ function returns or falls off end
    ▼
State: CLOSED (StopIteration raised)
```

### 4.3 Memory Efficiency — Generator vs List

```python
import sys

# List — ALL values in memory at once
numbers_list = [x ** 2 for x in range(1_000_000)]
print(sys.getsizeof(numbers_list))   # ~8 MB

# Generator — values produced on demand
numbers_gen = (x ** 2 for x in range(1_000_000))
print(sys.getsizeof(numbers_gen))    # ~112 bytes ← constant!

# Both iterate the same way
total_list = sum(numbers_list)
total_gen  = sum(numbers_gen)
# Same result, but generator uses fraction of the memory
```

### 4.4 Generator Function Examples

```python
# Example 1: Fibonacci generator (infinite)
def fibonacci():
    a, b = 0, 1
    while True:
        yield a
        a, b = b, a + b


fib = fibonacci()
for _ in range(10):
    print(next(fib), end=" ")
# 0 1 1 2 3 5 8 13 21 34


# Example 2: Reading large file line by line
def read_large_file(filepath):
    """Generator for memory-efficient file reading."""
    with open(filepath, 'r') as f:
        for line in f:
            yield line.rstrip('\n')


# Example 3: Countdown generator
def countdown(n):
    while n > 0:
        yield n
        n -= 1


for num in countdown(5):
    print(num)   # 5 4 3 2 1


# Example 4: Range-like generator with step
def my_range(start, stop=None, step=1):
    if stop is None:
        start, stop = 0, start
    current = start
    while current < stop:
        yield current
        current += step


for x in my_range(0, 10, 2):
    print(x)   # 0 2 4 6 8
```

### 4.5 Generator Expressions

```python
# List comprehension (eager — all in memory)
squares_list = [x**2 for x in range(10)]

# Generator expression (lazy — one at a time)
squares_gen = (x**2 for x in range(10))

# Both can be iterated
for sq in squares_gen:
    print(sq)

# Generator expressions in function calls (drop outer parentheses)
total = sum(x**2 for x in range(100))
maximum = max(len(word) for word in ["hello", "world", "python"])

# Chaining generator expressions
evens = (x for x in range(100) if x % 2 == 0)
squares_of_evens = (x**2 for x in evens)
filtered = (x for x in squares_of_evens if x > 100)
result = list(filtered)
```

### 4.6 yield from — Delegating Generators

```python
def inner_gen():
    yield 1
    yield 2
    yield 3


def outer_gen_manual():
    """Without yield from — verbose."""
    for value in inner_gen():
        yield value
    yield 4
    yield 5


def outer_gen_clean():
    """With yield from — clean delegation."""
    yield from inner_gen()   # delegate to inner generator
    yield 4
    yield 5


print(list(outer_gen_clean()))   # [1, 2, 3, 4, 5]


# yield from with any iterable
def flatten(nested):
    for item in nested:
        if isinstance(item, list):
            yield from flatten(item)   # recursive delegation
        else:
            yield item


print(list(flatten([1, [2, [3, 4]], 5])))   # [1, 2, 3, 4, 5]
```

### 4.7 send() — Two-Way Communication

```python
def accumulator():
    """Generator that accepts values via send()."""
    total = 0
    while True:
        value = yield total   # yield sends current total, receives new value
        if value is None:
            break
        total += value


acc = accumulator()
next(acc)           # Prime the generator (reach first yield)
print(acc.send(10))   # 10
print(acc.send(20))   # 30
print(acc.send(5))    # 35
```

### 4.8 Generator Best Practices

```python
# ✅ Use generators for large datasets
def process_records(records):
    for record in records:
        if record.get('active'):
            yield transform(record)

# ✅ Use generator expressions for simple transformations
filtered = (x for x in data if x > 0)

# ✅ Use yield from for delegation
def chain(*iterables):
    for it in iterables:
        yield from it

# ❌ Don't call next() without handling StopIteration
def safe_next(gen, default=None):
    try:
        return next(gen)
    except StopIteration:
        return default
```

---

<a name="section-5"></a>

## 🚀 Section 5 — Advanced Generators

### 5.1 Infinite Generators

```python
import itertools

# Count forever
def count_from(start=0, step=1):
    n = start
    while True:
        yield n
        n += step


# Take first N from infinite generator
def take(n, iterable):
    for i, item in enumerate(iterable):
        if i >= n:
            break
        yield item


print(list(take(5, count_from(10, 3))))   # [10, 13, 16, 19, 22]

# itertools has built-in infinite generators
from itertools import count, cycle, repeat

for i in take(5, count(start=1, step=2)):
    print(i)   # 1, 3, 5, 7, 9

colors = cycle(['red', 'green', 'blue'])
for i, color in zip(range(7), colors):
    print(f"Item {i}: {color}")
```

### 5.2 Generator Pipeline

```python
"""
DATA PIPELINE USING GENERATORS
Input → Stage1 → Stage2 → Stage3 → Output

Each stage is a generator — lazy, composable, memory-efficient
"""

def read_data(source):
    """Stage 1: Produce raw data."""
    for item in source:
        yield item

def parse(items):
    """Stage 2: Transform items."""
    for item in items:
        yield item.strip().upper()

def filter_valid(items):
    """Stage 3: Filter out invalid."""
    for item in items:
        if item and not item.startswith('#'):
            yield item

def batch(items, size=3):
    """Stage 4: Group into batches."""
    batch = []
    for item in items:
        batch.append(item)
        if len(batch) == size:
            yield batch
            batch = []
    if batch:
        yield batch


# BUILD PIPELINE (nothing executes yet)
raw_data = ["  hello  ", "# comment", "  world  ", "python", "ai", "  ml  "]
pipeline = batch(filter_valid(parse(read_data(raw_data))))

# CONSUME PIPELINE (executes lazily)
for batch_group in pipeline:
    print(batch_group)
# ['HELLO', 'WORLD', 'PYTHON']
# ['AI', 'ML']
```

### 5.3 Data Streaming with Generators

```python
import json
import os

def stream_json_lines(filepath):
    """Stream a JSONL (JSON Lines) file without loading it all into memory."""
    with open(filepath, 'r') as f:
        for line in f:
            line = line.strip()
            if line:
                yield json.loads(line)


def filter_records(records, key, value):
    """Filter generator — lazy."""
    for record in records:
        if record.get(key) == value:
            yield record


def transform_records(records, transform_fn):
    """Transform generator — lazy."""
    for record in records:
        yield transform_fn(record)


# Pipeline for 10 GB JSONL file — uses < 1 MB of RAM
# records = stream_json_lines("huge_dataset.jsonl")
# actives = filter_records(records, 'status', 'active')
# processed = transform_records(actives, lambda r: {**r, 'processed': True})
# for item in processed:
#     save_to_db(item)
```

### 5.4 Chained Generators with itertools

```python
from itertools import (
    chain, islice, takewhile, dropwhile,
    groupby, starmap, product, combinations, permutations
)

# chain — combine multiple iterables lazily
combined = list(chain([1, 2], [3, 4], [5, 6]))
print(combined)   # [1, 2, 3, 4, 5, 6]

# islice — lazy slicing
gen = count_from(0)
first_10 = list(islice(gen, 10))
print(first_10)   # [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]

# takewhile / dropwhile — conditional generators
nums = [1, 3, 5, 4, 2, 7]
ascending = list(takewhile(lambda x: x < 5, nums))   # [1, 3]
after_5 = list(dropwhile(lambda x: x < 5, nums))     # [5, 4, 2, 7]

# groupby — group consecutive items
data = [('A', 1), ('A', 2), ('B', 3), ('B', 4), ('C', 5)]
for key, group in groupby(data, key=lambda x: x[0]):
    print(key, list(group))
# A [('A', 1), ('A', 2)]
# B [('B', 3), ('B', 4)]
# C [('C', 5)]

# product — cartesian product
cards = list(product('AKQJ', ['♠', '♥', '♦', '♣']))
print(len(cards))   # 16

# combinations / permutations
teams = list(combinations(['Alice', 'Bob', 'Charlie'], 2))
print(teams)
# [('Alice', 'Bob'), ('Alice', 'Charlie'), ('Bob', 'Charlie')]
```

### 5.5 Generator-Based Coroutines

```python
"""
Before async/await, Python used generator-based coroutines.
Understanding this is essential for asyncio internals.
"""

def coroutine(func):
    """Decorator to auto-prime a coroutine generator."""
    def wrapper(*args, **kwargs):
        gen = func(*args, **kwargs)
        next(gen)   # prime the coroutine
        return gen
    return wrapper


@coroutine
def logger(prefix):
    """Coroutine that receives log messages."""
    while True:
        message = yield
        print(f"[{prefix}] {message}")


log = logger("INFO")
log.send("System starting...")
log.send("Connection established.")
log.send("Processing data...")


@coroutine
def pipeline_sink(target):
    """Coroutine sink — receives data, sends to target."""
    while True:
        data = yield
        target.send(data.upper())


# Coroutine chain
printer = logger("OUTPUT")
upper = pipeline_sink(printer)

upper.send("hello")    # [OUTPUT] HELLO
upper.send("world")    # [OUTPUT] WORLD
```

---

<a name="section-6"></a>

## 🎨 Section 6 — Decorators Masterclass

### 6.1 What is a Decorator?

A **decorator** is a higher-order function that takes a function as input, wraps it with additional behavior, and returns the enhanced function — without modifying the original source code.

```
DECORATOR CONCEPT:
                  ┌─────────────────────────────────┐
                  │         DECORATOR               │
                  │  ┌──────────────────────────┐   │
Input Function →  │  │  Before-code             │   │
                  │  │  call original function  │   │ → Enhanced Function
                  │  │  After-code              │   │
                  │  └──────────────────────────┘   │
                  └─────────────────────────────────┘

@decorator
def my_func():     IS EQUIVALENT TO:     my_func = decorator(my_func)
    pass
```

### 6.2 Building a Decorator Step by Step

```python
# Step 1: Basic decorator
def my_decorator(func):
    def wrapper():
        print("Before function call")
        func()
        print("After function call")
    return wrapper


def say_hello():
    print("Hello!")


# Manual application
say_hello = my_decorator(say_hello)
say_hello()
# Before function call
# Hello!
# After function call


# Step 2: Using @ syntax (syntactic sugar)
@my_decorator
def say_goodbye():
    print("Goodbye!")


say_goodbye()   # Same result


# Step 3: Decorator with arguments (*args, **kwargs)
def smart_decorator(func):
    def wrapper(*args, **kwargs):
        print(f"Calling {func.__name__} with args={args}, kwargs={kwargs}")
        result = func(*args, **kwargs)
        print(f"{func.__name__} returned: {result}")
        return result
    return wrapper


@smart_decorator
def add(a, b):
    return a + b


add(3, 5)
# Calling add with args=(3, 5), kwargs={}
# add returned: 8
```

### 6.3 functools.wraps — Preserving Metadata

```python
import functools

# ❌ Without @wraps — metadata lost
def bad_decorator(func):
    def wrapper(*args, **kwargs):
        return func(*args, **kwargs)
    return wrapper


@bad_decorator
def my_func():
    """My docstring."""
    pass


print(my_func.__name__)   # "wrapper"  ← WRONG
print(my_func.__doc__)    # None        ← WRONG


# ✅ With @wraps — metadata preserved
def good_decorator(func):
    @functools.wraps(func)
    def wrapper(*args, **kwargs):
        return func(*args, **kwargs)
    return wrapper


@good_decorator
def my_func():
    """My docstring."""
    pass


print(my_func.__name__)   # "my_func"       ← CORRECT
print(my_func.__doc__)    # "My docstring." ← CORRECT
```

### 6.4 Logging Decorator

```python
import functools
import logging
import traceback

logging.basicConfig(level=logging.INFO, format='%(asctime)s - %(levelname)s - %(message)s')
logger = logging.getLogger(__name__)


def log_calls(func):
    """Log function entry, exit, and exceptions."""
    @functools.wraps(func)
    def wrapper(*args, **kwargs):
        logger.info(f"→ Calling {func.__name__}({args}, {kwargs})")
        try:
            result = func(*args, **kwargs)
            logger.info(f"← {func.__name__} returned: {result}")
            return result
        except Exception as e:
            logger.error(f"✗ {func.__name__} raised {type(e).__name__}: {e}")
            logger.debug(traceback.format_exc())
            raise
    return wrapper


@log_calls
def divide(a, b):
    return a / b


divide(10, 2)    # logs entry + exit
divide(10, 0)    # logs error
```

### 6.5 Timing Decorator

```python
import functools
import time


def timer(func):
    """Measure and print function execution time."""
    @functools.wraps(func)
    def wrapper(*args, **kwargs):
        start = time.perf_counter()
        result = func(*args, **kwargs)
        end = time.perf_counter()
        elapsed = (end - start) * 1000
        print(f"⏱  {func.__name__} took {elapsed:.4f} ms")
        return result
    return wrapper


def benchmark(iterations=1000):
    """Parametric timer decorator for benchmarking."""
    def decorator(func):
        @functools.wraps(func)
        def wrapper(*args, **kwargs):
            times = []
            for _ in range(iterations):
                start = time.perf_counter()
                result = func(*args, **kwargs)
                times.append(time.perf_counter() - start)
            avg = sum(times) / len(times) * 1000
            best = min(times) * 1000
            worst = max(times) * 1000
            print(f"📊 {func.__name__} over {iterations} runs:")
            print(f"   Avg: {avg:.4f}ms | Best: {best:.4f}ms | Worst: {worst:.4f}ms")
            return result
        return wrapper
    return decorator


@timer
def slow_function():
    time.sleep(0.1)
    return "done"


@benchmark(iterations=100)
def compute_sum():
    return sum(range(10_000))


slow_function()
compute_sum()
```

### 6.6 Validation Decorator

```python
import functools


def validate_types(**type_map):
    """Decorator to validate argument types."""
    def decorator(func):
        @functools.wraps(func)
        def wrapper(*args, **kwargs):
            import inspect
            sig = inspect.signature(func)
            bound = sig.bind(*args, **kwargs)
            bound.apply_defaults()
            for param_name, expected_type in type_map.items():
                if param_name in bound.arguments:
                    value = bound.arguments[param_name]
                    if not isinstance(value, expected_type):
                        raise TypeError(
                            f"Parameter '{param_name}' expected {expected_type.__name__}, "
                            f"got {type(value).__name__}"
                        )
            return func(*args, **kwargs)
        return wrapper
    return decorator


@validate_types(name=str, age=int, score=float)
def register_user(name, age, score):
    return f"Registered {name}, age {age}, score {score}"


print(register_user("Alice", 25, 98.5))    # OK
# register_user(123, 25, 98.5)             # TypeError: 'name' expected str, got int
```

### 6.7 Caching Decorator (Memoization)

```python
import functools
import time


def memoize(func):
    """Simple memoization decorator."""
    cache = {}

    @functools.wraps(func)
    def wrapper(*args):
        if args not in cache:
            cache[args] = func(*args)
        return cache[args]

    wrapper.cache = cache       # expose cache for inspection
    wrapper.cache_clear = lambda: cache.clear()
    return wrapper


@memoize
def fibonacci(n):
    if n <= 1:
        return n
    return fibonacci(n - 1) + fibonacci(n - 2)


start = time.perf_counter()
print(fibonacci(35))          # Fast (cached)
print(f"Cache size: {len(fibonacci.cache)}")

# Python built-in: functools.lru_cache
@functools.lru_cache(maxsize=128)
def expensive_computation(n):
    time.sleep(0.001)
    return n ** 2


# functools.cache (Python 3.9+) — unbounded cache
@functools.cache
def fib(n):
    if n <= 1:
        return n
    return fib(n-1) + fib(n-2)
```

### 6.8 Retry Decorator

```python
import functools
import time
import random


def retry(max_attempts=3, delay=1.0, exceptions=(Exception,), backoff=2.0):
    """Retry a function on failure with exponential backoff."""
    def decorator(func):
        @functools.wraps(func)
        def wrapper(*args, **kwargs):
            current_delay = delay
            last_exception = None
            for attempt in range(1, max_attempts + 1):
                try:
                    return func(*args, **kwargs)
                except exceptions as e:
                    last_exception = e
                    if attempt < max_attempts:
                        print(f"Attempt {attempt} failed: {e}. Retrying in {current_delay}s...")
                        time.sleep(current_delay)
                        current_delay *= backoff
                    else:
                        print(f"All {max_attempts} attempts failed.")
            raise last_exception
        return wrapper
    return decorator


@retry(max_attempts=3, delay=0.5, exceptions=(ConnectionError,))
def connect_to_server(url):
    """Simulate flaky network connection."""
    if random.random() < 0.7:   # 70% chance of failure
        raise ConnectionError(f"Failed to connect to {url}")
    return f"Connected to {url}"


try:
    result = connect_to_server("http://api.example.com")
    print(result)
except ConnectionError as e:
    print(f"Final failure: {e}")
```

### 6.9 Authentication Decorator

```python
import functools
from datetime import datetime


# Simulated user session
_current_user = {"id": None, "roles": [], "token": None}


def require_auth(func):
    """Require user to be authenticated."""
    @functools.wraps(func)
    def wrapper(*args, **kwargs):
        if not _current_user.get("id"):
            raise PermissionError("Authentication required. Please log in.")
        return func(*args, **kwargs)
    return wrapper


def require_role(*roles):
    """Require user to have specific role(s)."""
    def decorator(func):
        @functools.wraps(func)
        def wrapper(*args, **kwargs):
            if not _current_user.get("id"):
                raise PermissionError("Authentication required.")
            user_roles = set(_current_user.get("roles", []))
            required = set(roles)
            if not required.intersection(user_roles):
                raise PermissionError(
                    f"Insufficient permissions. Required: {roles}, "
                    f"Got: {list(user_roles)}"
                )
            return func(*args, **kwargs)
        return wrapper
    return decorator


def audit_log(action_name):
    """Log user actions with timestamp."""
    def decorator(func):
        @functools.wraps(func)
        def wrapper(*args, **kwargs):
            user_id = _current_user.get("id", "anonymous")
            print(f"[AUDIT] {datetime.now().isoformat()} | User: {user_id} | Action: {action_name}")
            return func(*args, **kwargs)
        return wrapper
    return decorator


@require_auth
@require_role("admin", "superuser")
@audit_log("delete_user")
def delete_user(user_id):
    print(f"Deleting user {user_id}...")
    return True


# Test
_current_user.update({"id": "admin001", "roles": ["admin"]})
delete_user(42)   # Works — admin role

_current_user.update({"id": "user001", "roles": ["viewer"]})
try:
    delete_user(42)   # PermissionError — viewer role insufficient
except PermissionError as e:
    print(f"Access denied: {e}")
```

### 6.10 Decorator with Parameters (Parametric Decorator)

```python
import functools


def repeat(times):
    """Call function `times` number of times."""
    def decorator(func):
        @functools.wraps(func)
        def wrapper(*args, **kwargs):
            for _ in range(times):
                result = func(*args, **kwargs)
            return result
        return wrapper
    return decorator


@repeat(3)
def greet(name):
    print(f"Hello, {name}!")


greet("Python")
# Hello, Python!
# Hello, Python!
# Hello, Python!


# Class-based decorator
class CountCalls:
    """Track how many times a function is called."""

    def __init__(self, func):
        functools.update_wrapper(self, func)
        self.func = func
        self.count = 0

    def __call__(self, *args, **kwargs):
        self.count += 1
        print(f"{self.func.__name__} has been called {self.count} time(s)")
        return self.func(*args, **kwargs)


@CountCalls
def say_hi():
    print("Hi!")


say_hi()    # say_hi has been called 1 time(s)
say_hi()    # say_hi has been called 2 time(s)
say_hi()    # say_hi has been called 3 time(s)
print(say_hi.count)   # 3
```

### 6.11 Stacking Decorators

```python
import functools

def decorator_a(func):
    @functools.wraps(func)
    def wrapper(*args, **kwargs):
        print("A: before")
        result = func(*args, **kwargs)
        print("A: after")
        return result
    return wrapper

def decorator_b(func):
    @functools.wraps(func)
    def wrapper(*args, **kwargs):
        print("B: before")
        result = func(*args, **kwargs)
        print("B: after")
        return result
    return wrapper


@decorator_a
@decorator_b
def my_function():
    print("Function body")


my_function()
# A: before
# B: before
# Function body
# B: after
# A: after

# Explanation:
# @decorator_a @decorator_b def f()
# is equivalent to:
# f = decorator_a(decorator_b(f))
# So decorator_a wraps decorator_b(f)
# Execution: A outer → B outer → function → B inner → A inner
```

---

<a name="section-7"></a>

## 🔐 Section 7 — Closures Masterclass

### 7.1 What is a Closure?

A **closure** is a nested function that remembers and has access to variables from its enclosing scope, even after the outer function has finished executing.

**Three conditions for a closure:**
1. A nested (inner) function exists
2. The inner function references variables from the enclosing scope
3. The enclosing function returns the inner function

### 7.2 Closure Mechanics

```python
def make_multiplier(factor):
    """Returns a closure that multiplies by factor."""
    # `factor` is a FREE VARIABLE — captured by the closure

    def multiplier(x):
        return x * factor   # accesses `factor` from enclosing scope

    return multiplier   # return function, not the result


double = make_multiplier(2)
triple = make_multiplier(3)
times10 = make_multiplier(10)

print(double(5))    # 10
print(triple(5))    # 15
print(times10(5))   # 50

# Each closure has its OWN copy of `factor`
print(double.__closure__)             # (<cell at 0x...>,)
print(double.__closure__[0].cell_contents)  # 2
print(triple.__closure__[0].cell_contents)  # 3
```

**Memory Diagram:**

```
make_multiplier(2) call:
┌──────────────────────────────┐
│  Enclosing frame             │
│  factor = 2                  │◄── captured in cell object
└───────────────┬──────────────┘
                │
                ▼
  multiplier function object
  ┌──────────────────────────┐
  │  code: return x * factor │
  │  __closure__: [cell(2)]  │◄── reference to cell object
  └──────────────────────────┘

Even after make_multiplier() returns,
the cell object keeps `factor=2` alive.
```

### 7.3 Closures for State Preservation

```python
def make_counter(start=0, step=1):
    """Closure with mutable state."""
    count = [start]   # use list for mutability (Python 2-compatible trick)

    def increment():
        count[0] += step
        return count[0]

    def reset():
        count[0] = start

    def get():
        return count[0]

    return increment, reset, get


inc, rst, get = make_counter(0, 2)
print(inc())    # 2
print(inc())    # 4
print(inc())    # 6
print(get())    # 6
rst()
print(get())    # 0


# Python 3 approach: nonlocal keyword
def make_counter_v2(start=0):
    count = start

    def increment():
        nonlocal count   # explicitly modify enclosing variable
        count += 1
        return count

    def reset():
        nonlocal count
        count = start

    return increment, reset


inc, rst = make_counter_v2()
print(inc())   # 1
print(inc())   # 2
rst()
print(inc())   # 1
```

### 7.4 nonlocal Keyword

```python
# ❌ Without nonlocal — UnboundLocalError
def outer():
    x = 10
    def inner():
        x += 1     # ERROR: x referenced before assignment
        return x
    return inner

f = outer()
# f()   # UnboundLocalError!


# ✅ With nonlocal
def outer():
    x = 10
    def inner():
        nonlocal x   # tell Python to look in enclosing scope
        x += 1
        return x
    return inner

f = outer()
print(f())   # 11
print(f())   # 12
print(f())   # 13
```

### 7.5 Closures vs Classes

```python
# Closure approach — lightweight, functional
def make_bank_account(initial_balance):
    balance = initial_balance

    def deposit(amount):
        nonlocal balance
        balance += amount
        return balance

    def withdraw(amount):
        nonlocal balance
        if amount > balance:
            raise ValueError("Insufficient funds")
        balance -= amount
        return balance

    def get_balance():
        return balance

    return deposit, withdraw, get_balance


dep, wdr, bal = make_bank_account(1000)
dep(500)
print(bal())   # 1500
wdr(200)
print(bal())   # 1300


# Class approach — explicit, more features
class BankAccount:
    def __init__(self, initial_balance):
        self._balance = initial_balance

    def deposit(self, amount):
        self._balance += amount
        return self._balance

    def withdraw(self, amount):
        if amount > self._balance:
            raise ValueError("Insufficient funds")
        self._balance -= amount
        return self._balance

    @property
    def balance(self):
        return self._balance
```

### 7.6 Common Closure Mistake — Late Binding

```python
# ❌ CLASSIC BUG: late binding in loops
functions = []
for i in range(5):
    functions.append(lambda: i)   # `i` is NOT captured, just referenced

print([f() for f in functions])   # [4, 4, 4, 4, 4]  ← ALL return 4!
# Because `i` is a free variable in the enclosing scope (the loop)
# By the time you call f(), `i` is 4 (loop finished)


# ✅ FIX 1: default argument binding (captures current value)
functions = []
for i in range(5):
    functions.append(lambda i=i: i)   # i=i captures current value

print([f() for f in functions])   # [0, 1, 2, 3, 4]  ← CORRECT


# ✅ FIX 2: use a factory function
def make_func(i):
    def f():
        return i
    return f

functions = [make_func(i) for i in range(5)]
print([f() for f in functions])   # [0, 1, 2, 3, 4]  ← CORRECT
```

---

<a name="section-8"></a>

## 🏠 Section 8 — Context Managers Masterclass

### 8.1 What is a Context Manager?

A **context manager** is an object that defines setup and teardown logic for a block of code. It guarantees resource cleanup even if exceptions occur.

```python
# The with statement calls __enter__ and __exit__
with open("file.txt", "r") as f:
    content = f.read()
# File automatically closed here — even if exception raised


# IS EQUIVALENT TO:
f = open("file.txt", "r")
try:
    content = f.read()
finally:
    f.close()   # guaranteed cleanup
```

### 8.2 The Context Protocol

```python
class MyContextManager:
    def __enter__(self):
        """Setup code — runs when entering `with` block."""
        print("Entering context")
        return self   # value bound to `as` variable

    def __exit__(self, exc_type, exc_val, exc_tb):
        """Teardown code — always runs when leaving `with` block.

        Parameters:
            exc_type: Exception type (None if no exception)
            exc_val:  Exception value (None if no exception)
            exc_tb:   Exception traceback (None if no exception)

        Returns:
            True  → suppress the exception
            False → propagate the exception (default)
        """
        print(f"Exiting context. Exception: {exc_type}")
        return False   # don't suppress exceptions


with MyContextManager() as ctx:
    print("Inside context")
    # raise ValueError("test")   # __exit__ called with exception info
# Exiting context. Exception: None
```

### 8.3 Custom Context Manager — Database Connection

```python
import sqlite3
import contextlib


class DatabaseConnection:
    """Context manager for SQLite database connections."""

    def __init__(self, db_path):
        self.db_path = db_path
        self.connection = None
        self.cursor = None

    def __enter__(self):
        print(f"Connecting to {self.db_path}...")
        self.connection = sqlite3.connect(self.db_path)
        self.cursor = self.connection.cursor()
        return self.cursor   # return cursor to user

    def __exit__(self, exc_type, exc_val, exc_tb):
        if exc_type:
            print(f"Error occurred: {exc_val}. Rolling back...")
            self.connection.rollback()
        else:
            print("Transaction successful. Committing...")
            self.connection.commit()
        self.cursor.close()
        self.connection.close()
        print("Database connection closed.")
        return False   # don't suppress exceptions


# Usage
with DatabaseConnection(":memory:") as cursor:
    cursor.execute("CREATE TABLE users (id INTEGER, name TEXT)")
    cursor.execute("INSERT INTO users VALUES (1, 'Alice')")
    cursor.execute("INSERT INTO users VALUES (2, 'Bob')")
    cursor.execute("SELECT * FROM users")
    rows = cursor.fetchall()
    print(rows)   # [(1, 'Alice'), (2, 'Bob')]
```

### 8.4 contextlib.contextmanager Decorator

```python
from contextlib import contextmanager
import time


@contextmanager
def timer(label=""):
    """Context manager for timing code blocks."""
    start = time.perf_counter()
    try:
        yield   # code inside `with` block runs here
    finally:
        elapsed = (time.perf_counter() - start) * 1000
        print(f"⏱  {label}: {elapsed:.2f}ms")


with timer("data processing"):
    data = [x**2 for x in range(1_000_000)]


@contextmanager
def managed_file(filepath, mode='r'):
    """Context manager for file operations with logging."""
    print(f"Opening {filepath}...")
    try:
        f = open(filepath, mode)
        yield f
    except IOError as e:
        print(f"File error: {e}")
        raise
    finally:
        f.close()
        print(f"Closed {filepath}")


@contextmanager
def temporary_directory():
    """Create a temp directory, yield it, then clean up."""
    import tempfile
    import shutil
    tmpdir = tempfile.mkdtemp()
    print(f"Created temp dir: {tmpdir}")
    try:
        yield tmpdir
    finally:
        shutil.rmtree(tmpdir)
        print(f"Removed temp dir: {tmpdir}")


with temporary_directory() as tmpdir:
    # Work with tmpdir
    import os
    filepath = os.path.join(tmpdir, "test.txt")
    with open(filepath, 'w') as f:
        f.write("Temporary content")
    print(f"Created file: {filepath}")
# tmpdir automatically deleted after `with` block
```

### 8.5 contextlib Utilities

```python
from contextlib import (
    suppress,
    redirect_stdout,
    redirect_stderr,
    ExitStack,
    asynccontextmanager
)
import io


# suppress — silently ignore specific exceptions
with suppress(FileNotFoundError):
    open("nonexistent.txt")   # No error raised — exception suppressed
print("Continued after suppress")


# redirect_stdout — capture print output
buffer = io.StringIO()
with redirect_stdout(buffer):
    print("This goes to buffer, not console")
    print("Another line")
captured = buffer.getvalue()
print(f"Captured: {captured!r}")


# ExitStack — dynamic context manager management
files_to_open = ["file1.txt", "file2.txt", "file3.txt"]

with ExitStack() as stack:
    # Create temp files for demo
    import tempfile
    handles = []
    for i in range(3):
        f = tempfile.NamedTemporaryFile(mode='w', suffix='.txt', delete=False)
        handles.append(stack.enter_context(f))
        f.write(f"Content {i}")
    # All files automatically closed when ExitStack exits
```

### 8.6 Nested Context Managers

```python
# Old style — nested
with open("input.txt") as fin:
    with open("output.txt", "w") as fout:
        fout.write(fin.read())

# Modern style — tuple (Python 3.10+)
with (open("input.txt") as fin,
      open("output.txt", "w") as fout):
    fout.write(fin.read())

# Single line (older Python)
with open("input.txt") as fin, open("output.txt", "w") as fout:
    fout.write(fin.read())
```

---

<a name="section-9"></a>

## 🧮 Section 9 — Functional Programming Masterclass

### 9.1 Lambda Functions — Deep Dive

```python
# Lambda syntax: lambda arguments: expression
# Single expression only — no statements, no return keyword

square = lambda x: x ** 2
add = lambda a, b: a + b
greet = lambda name, greeting="Hello": f"{greeting}, {name}!"
noop = lambda *args, **kwargs: None

# Lambda with conditional expression
abs_val = lambda x: x if x >= 0 else -x
classify = lambda x: "positive" if x > 0 else "negative" if x < 0 else "zero"

# Lambda in data structures
operations = {
    'add': lambda a, b: a + b,
    'sub': lambda a, b: a - b,
    'mul': lambda a, b: a * b,
    'div': lambda a, b: a / b if b != 0 else float('inf'),
}

result = operations['mul'](6, 7)
print(result)   # 42

# Sorting with lambda
students = [
    {"name": "Alice", "grade": 92, "age": 20},
    {"name": "Bob",   "grade": 85, "age": 22},
    {"name": "Carol", "grade": 95, "age": 19},
    {"name": "Dave",  "grade": 85, "age": 21},
]

# Sort by grade descending, then by name ascending
sorted_students = sorted(students, key=lambda s: (-s['grade'], s['name']))
for s in sorted_students:
    print(f"{s['name']}: {s['grade']}")
# Carol: 95, Alice: 92, Bob: 85, Dave: 85
```

### 9.2 map() — Transform Every Element

```python
# map(function, iterable) → lazy iterator

# Basic usage
numbers = [1, 2, 3, 4, 5]
squares = list(map(lambda x: x**2, numbers))
print(squares)   # [1, 4, 9, 16, 25]

# With named function
def celsius_to_fahrenheit(c):
    return (c * 9/5) + 32

temps_c = [0, 20, 37, 100]
temps_f = list(map(celsius_to_fahrenheit, temps_c))
print(temps_f)   # [32.0, 68.0, 98.6, 212.0]

# map with multiple iterables
a = [1, 2, 3]
b = [10, 20, 30]
sums = list(map(lambda x, y: x + y, a, b))
print(sums)   # [11, 22, 33]

# Equivalent using zip + comprehension (more Pythonic)
sums2 = [x + y for x, y in zip(a, b)]

# map is lazy — no computation until consumed
large_map = map(lambda x: x**2, range(10_000_000))
print(type(large_map))   # <class 'map'>
first_5 = [next(large_map) for _ in range(5)]
print(first_5)   # [0, 1, 4, 9, 16]
```

### 9.3 filter() — Select Elements

```python
# filter(function, iterable) → lazy iterator of items where function returns True

numbers = [-3, -1, 0, 2, 4, 7, -5, 9]

# Filter positive numbers
positives = list(filter(lambda x: x > 0, numbers))
print(positives)   # [2, 4, 7, 9]

# filter(None, iterable) → remove falsy values
mixed = [0, 1, "", "hello", None, [1, 2], [], False, True]
truthy = list(filter(None, mixed))
print(truthy)   # [1, 'hello', [1, 2], True]

# With named function
def is_prime(n):
    if n < 2:
        return False
    for i in range(2, int(n**0.5) + 1):
        if n % i == 0:
            return False
    return True

primes = list(filter(is_prime, range(50)))
print(primes)   # [2, 3, 5, 7, 11, 13, 17, 19, 23, 29, 31, 37, 41, 43, 47]

# filter on objects
users = [
    {"name": "Alice", "active": True},
    {"name": "Bob",   "active": False},
    {"name": "Carol", "active": True},
]
active_users = list(filter(lambda u: u["active"], users))
```

### 9.4 reduce() — Accumulate to Single Value

```python
from functools import reduce

numbers = [1, 2, 3, 4, 5]

# Sum
total = reduce(lambda acc, x: acc + x, numbers)
print(total)   # 15

# Product
product = reduce(lambda acc, x: acc * x, numbers)
print(product)   # 120

# With initial value
total_with_init = reduce(lambda acc, x: acc + x, numbers, 100)
print(total_with_init)   # 115

# Find maximum
maximum = reduce(lambda a, b: a if a > b else b, numbers)
print(maximum)   # 5

# Flatten nested list
nested = [[1, 2], [3, 4], [5, 6]]
flat = reduce(lambda acc, lst: acc + lst, nested, [])
print(flat)   # [1, 2, 3, 4, 5, 6]

# Build a dict from list of tuples
pairs = [("a", 1), ("b", 2), ("c", 3)]
d = reduce(lambda acc, pair: {**acc, pair[0]: pair[1]}, pairs, {})
print(d)   # {'a': 1, 'b': 2, 'c': 3}
```

### 9.5 any(), all(), zip(), enumerate()

```python
# any() — True if AT LEAST ONE element is truthy
print(any([False, False, True]))    # True
print(any([False, False, False]))   # False
print(any(x > 10 for x in [5, 8, 15, 3]))  # True (15 > 10)

# all() — True if ALL elements are truthy
print(all([True, True, True]))   # True
print(all([True, False, True]))  # False
print(all(x > 0 for x in [1, 2, 3]))   # True
print(all(x > 0 for x in [1, -1, 3]))  # False

# zip() — pair up iterables
names = ["Alice", "Bob", "Carol"]
scores = [92, 85, 95]
ages = [20, 22, 19]

for name, score, age in zip(names, scores, ages):
    print(f"{name}: score={score}, age={age}")

# zip stops at shortest iterable
a = [1, 2, 3, 4, 5]
b = ['a', 'b', 'c']
print(list(zip(a, b)))   # [(1, 'a'), (2, 'b'), (3, 'c')]

# zip_longest (from itertools) fills missing with fillvalue
from itertools import zip_longest
print(list(zip_longest(a, b, fillvalue='?')))
# [(1, 'a'), (2, 'b'), (3, 'c'), (4, '?'), (5, '?')]

# Unzip — transpose
pairs = [(1, 'a'), (2, 'b'), (3, 'c')]
nums, letters = zip(*pairs)
print(nums)     # (1, 2, 3)
print(letters)  # ('a', 'b', 'c')

# enumerate() — index + value
fruits = ["apple", "banana", "cherry"]
for i, fruit in enumerate(fruits, start=1):
    print(f"{i}. {fruit}")
# 1. apple
# 2. banana
# 3. cherry
```

### 9.6 sorted(), min(), max() with key

```python
# sorted() — always returns a new list
data = [3, 1, 4, 1, 5, 9, 2, 6, 5]
print(sorted(data))           # [1, 1, 2, 3, 4, 5, 5, 6, 9]
print(sorted(data, reverse=True))  # [9, 6, 5, 5, 4, 3, 2, 1, 1]

# Sort strings by length
words = ["banana", "apple", "cherry", "fig", "date"]
print(sorted(words, key=len))   # ['fig', 'date', 'apple', 'banana', 'cherry']

# Sort by multiple keys
import operator
people = [
    ("Alice", 30, "Engineer"),
    ("Bob",   25, "Designer"),
    ("Carol", 30, "Manager"),
    ("Dave",  25, "Engineer"),
]
# Sort by age, then name
by_age_name = sorted(people, key=operator.itemgetter(1, 0))
print(by_age_name)

# min/max with key
print(min(words, key=len))   # 'fig'
print(max(words, key=len))   # 'cherry'
print(min(people, key=lambda p: p[1]))   # ('Bob', 25, 'Designer')
```

### 9.7 Partial Functions

```python
from functools import partial

def power(base, exponent):
    return base ** exponent

# Create specialized functions
square = partial(power, exponent=2)
cube = partial(power, exponent=3)
double = partial(lambda x, factor: x * factor, factor=2)

print(square(4))    # 16
print(cube(3))      # 27
print(double(5))    # 10

# Partial with positional args
def log(level, message, timestamp=None):
    ts = timestamp or "now"
    print(f"[{level}] {ts}: {message}")

info = partial(log, "INFO")
warn = partial(log, "WARN")
error = partial(log, "ERROR")

info("System started")
warn("Disk space low")
error("Connection failed")
```

### 9.8 Functional Pipeline Pattern

```python
from functools import reduce

def compose(*functions):
    """Compose functions right-to-left: compose(f, g)(x) = f(g(x))"""
    return reduce(lambda f, g: lambda *args, **kwargs: f(g(*args, **kwargs)), functions)


def pipe(*functions):
    """Apply functions left-to-right: pipe(f, g)(x) = g(f(x))"""
    return reduce(lambda f, g: lambda *args, **kwargs: g(f(*args, **kwargs)), functions)


# Example pipeline
strip    = str.strip
lower    = str.lower
tokenize = str.split
dedupe   = lambda lst: list(dict.fromkeys(lst))

process = pipe(strip, lower, tokenize, dedupe)

text = "  Hello World hello Python WORLD  "
result = process(text)
print(result)   # ['hello', 'world', 'python']
```

---

<a name="section-10"></a>

## 🧩 Section 10 — Advanced Comprehensions

### 10.1 List Comprehensions

```python
# Basic
squares = [x**2 for x in range(10)]

# With condition (filter)
even_squares = [x**2 for x in range(10) if x % 2 == 0]

# With transformation + filter
result = [x.upper() for x in ["hello", "world", "python"] if len(x) > 4]

# Nested (flatten)
matrix = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
flat = [elem for row in matrix for elem in row]
print(flat)   # [1, 2, 3, 4, 5, 6, 7, 8, 9]

# Nested (transform matrix)
transposed = [[row[i] for row in matrix] for i in range(3)]
print(transposed)   # [[1, 4, 7], [2, 5, 8], [3, 6, 9]]

# Conditional expression inside
labeled = ["even" if x % 2 == 0 else "odd" for x in range(6)]
print(labeled)   # ['even', 'odd', 'even', 'odd', 'even', 'odd']
```

### 10.2 Dictionary Comprehensions

```python
# Basic
squares_dict = {x: x**2 for x in range(6)}
print(squares_dict)   # {0: 0, 1: 1, 2: 4, 3: 9, 4: 16, 5: 25}

# Invert a dictionary
original = {'a': 1, 'b': 2, 'c': 3}
inverted = {v: k for k, v in original.items()}
print(inverted)   # {1: 'a', 2: 'b', 3: 'c'}

# Filter dictionary
scores = {'Alice': 92, 'Bob': 65, 'Carol': 88, 'Dave': 71}
passing = {name: score for name, score in scores.items() if score >= 80}
print(passing)   # {'Alice': 92, 'Carol': 88}

# Transform values
upper_scores = {name.upper(): score for name, score in scores.items()}

# From two lists
keys = ['x', 'y', 'z']
vals = [10, 20, 30]
d = {k: v for k, v in zip(keys, vals)}
print(d)   # {'x': 10, 'y': 20, 'z': 30}
```

### 10.3 Set Comprehensions

```python
# Basic
unique_squares = {x**2 for x in range(-5, 6)}
print(unique_squares)   # {0, 1, 4, 9, 16, 25}  (no duplicates)

# Finding unique characters
sentence = "hello world"
unique_chars = {c for c in sentence if c != ' '}
print(unique_chars)   # {'h', 'e', 'l', 'o', 'w', 'r', 'd'}

# From list — deduplicate while transforming
data = [1, 2, 2, 3, 3, 3, 4]
unique_doubled = {x * 2 for x in data}
print(unique_doubled)   # {2, 4, 6, 8}
```

### 10.4 Generator Expressions

```python
# Generator expression — lazy evaluation
gen = (x**2 for x in range(10))
print(type(gen))   # <class 'generator'>

# Use in functions directly (no extra parentheses needed)
total = sum(x**2 for x in range(100))
maximum = max(len(w) for w in ["hello", "world", "python"])

# Chained generator expressions
data = "  Hello  World  Python  "
words = (w for w in data.split() if w)   # filter empty strings

# Generator expressions vs list comprehensions
import sys, timeit

lst = [x**2 for x in range(10_000)]
gen = (x**2 for x in range(10_000))

print(f"List size: {sys.getsizeof(lst):,} bytes")   # ~87,616 bytes
print(f"Gen size:  {sys.getsizeof(gen):,} bytes")   # ~112 bytes
```

### 10.5 Performance Comparison

```python
import timeit

# Comparing approaches for sum of squares
n = 100_000

# List comprehension
t1 = timeit.timeit(lambda: sum([x**2 for x in range(n)]), number=100)

# Generator expression
t2 = timeit.timeit(lambda: sum(x**2 for x in range(n)), number=100)

# map + sum
t3 = timeit.timeit(lambda: sum(map(lambda x: x**2, range(n))), number=100)

print(f"List comprehension: {t1:.3f}s")
print(f"Generator expression: {t2:.3f}s")
print(f"map + sum: {t3:.3f}s")

# Typical results:
# List comprehension: 2.1s  (builds list in memory first)
# Generator expression: 1.9s  (lazy, less memory pressure)
# map + sum: 2.0s  (similar to generator)
```

---

<a name="section-11"></a>

## 🦆 Section 11 — Advanced Pythonic Patterns

### 11.1 Duck Typing

```python
"""
"If it walks like a duck and quacks like a duck, it's a duck."
Python doesn't care about the TYPE of an object — only whether it has the needed methods.
"""

class Dog:
    def speak(self):
        return "Woof!"

class Cat:
    def speak(self):
        return "Meow!"

class Robot:
    def speak(self):
        return "Beep boop!"

class Silent:
    pass   # no speak method


def make_sound(entity):
    """Works on ANY object that has a speak() method — duck typing."""
    return entity.speak()   # we don't check type — just call the method


animals = [Dog(), Cat(), Robot()]
for a in animals:
    print(make_sound(a))   # Works for all three!

# Fails gracefully
try:
    make_sound(Silent())   # AttributeError: no speak method
except AttributeError as e:
    print(f"Can't make it speak: {e}")
```

### 11.2 EAFP vs LBYL

```python
# LBYL — Look Before You Leap (common in C/Java)
def get_value_lbyl(d, key):
    if isinstance(d, dict) and key in d:     # check BEFORE
        return d[key]
    return None


# EAFP — Easier to Ask Forgiveness than Permission (Pythonic)
def get_value_eafp(d, key):
    try:
        return d[key]   # try it and catch the error
    except (KeyError, TypeError):
        return None


# EAFP is generally preferred in Python because:
# 1. More readable
# 2. Avoids race conditions (check then use vs just use)
# 3. More Pythonic
# 4. Often faster (no double lookup)

data = {"user": {"name": "Alice", "age": 30}}

# LBYL
if "user" in data and "name" in data["user"]:
    name = data["user"]["name"]
else:
    name = "Unknown"

# EAFP
try:
    name = data["user"]["name"]
except (KeyError, TypeError):
    name = "Unknown"
```

### 11.3 Composition over Inheritance

```python
# ❌ Deep inheritance — fragile
class Animal:
    pass

class FlyingAnimal(Animal):
    def fly(self): ...

class SwimmingAnimal(Animal):
    def swim(self): ...

class Duck(FlyingAnimal, SwimmingAnimal):   # Multiple inheritance mess
    pass


# ✅ Composition — flexible, testable
class FlyBehavior:
    def fly(self):
        return "Flying!"

class SwimBehavior:
    def swim(self):
        return "Swimming!"

class NoBehavior:
    def fly(self):
        return "I can't fly."
    def swim(self):
        return "I can't swim."


class Duck:
    def __init__(self):
        self.fly_behavior = FlyBehavior()    # composed
        self.swim_behavior = SwimBehavior()  # composed

    def fly(self):
        return self.fly_behavior.fly()

    def swim(self):
        return self.swim_behavior.swim()


class Penguin:
    def __init__(self):
        self.fly_behavior = NoBehavior()     # can't fly
        self.swim_behavior = SwimBehavior()  # can swim

    def fly(self):
        return self.fly_behavior.fly()

    def swim(self):
        return self.swim_behavior.swim()
```

### 11.4 Dependency Injection

```python
from abc import ABC, abstractmethod


class EmailSender(ABC):
    @abstractmethod
    def send(self, to: str, message: str) -> bool: ...


class SMTPEmailSender(EmailSender):
    def send(self, to, message):
        print(f"[SMTP] Sending to {to}: {message}")
        return True


class MockEmailSender(EmailSender):
    """For testing — doesn't actually send email."""
    def __init__(self):
        self.sent = []

    def send(self, to, message):
        self.sent.append({"to": to, "message": message})
        return True


class UserService:
    """Depends on abstraction, not concrete implementation."""

    def __init__(self, email_sender: EmailSender):
        self._email = email_sender   # INJECTED

    def register(self, email, name):
        # business logic...
        self._email.send(email, f"Welcome, {name}!")
        return True


# Production
smtp = SMTPEmailSender()
service = UserService(email_sender=smtp)
service.register("alice@example.com", "Alice")

# Testing
mock = MockEmailSender()
test_service = UserService(email_sender=mock)
test_service.register("test@test.com", "Test User")
print(mock.sent)   # [{'to': 'test@test.com', 'message': 'Welcome, Test User!'}]
```

### 11.5 Protocol (Structural Subtyping)

```python
from typing import Protocol, runtime_checkable


@runtime_checkable
class Drawable(Protocol):
    def draw(self) -> str: ...
    def resize(self, factor: float) -> None: ...


class Circle:
    def __init__(self, radius):
        self.radius = radius

    def draw(self):
        return f"Drawing circle (r={self.radius})"

    def resize(self, factor):
        self.radius *= factor


class Square:
    def __init__(self, side):
        self.side = side

    def draw(self):
        return f"Drawing square (s={self.side})"

    def resize(self, factor):
        self.side *= factor


# No explicit inheritance needed!
def render(shape: Drawable):
    shape.resize(2.0)
    return shape.draw()


shapes = [Circle(5), Square(3)]
for shape in shapes:
    print(render(shape))
    print(isinstance(shape, Drawable))   # True
```

---

<a name="section-12"></a>

## ⚡ Section 12 — Performance Optimization

### 12.1 Memory Optimization with __slots__

```python
import sys


class PointWithDict:
    """Normal class — uses __dict__ for attributes (flexible but heavy)."""
    def __init__(self, x, y, z):
        self.x, self.y, self.z = x, y, z


class PointWithSlots:
    """Slots class — fixed attributes, no __dict__ (fast and memory-efficient)."""
    __slots__ = ('x', 'y', 'z')

    def __init__(self, x, y, z):
        self.x, self.y, self.z = x, y, z


p1 = PointWithDict(1, 2, 3)
p2 = PointWithSlots(1, 2, 3)

print(f"Dict class:  {sys.getsizeof(p1)} + {sys.getsizeof(p1.__dict__)} bytes")
# Dict class:  48 + 232 bytes = 280 total

print(f"Slots class: {sys.getsizeof(p2)} bytes")
# Slots class: 64 bytes ← 4x more memory-efficient!

# Creating 1 million objects
n = 1_000_000

import tracemalloc
tracemalloc.start()
points_dict  = [PointWithDict(i, i, i) for i in range(n)]
snapshot1 = tracemalloc.take_snapshot()

del points_dict
tracemalloc.clear_traces()

points_slots = [PointWithSlots(i, i, i) for i in range(n)]
snapshot2 = tracemalloc.take_snapshot()
# Slots uses significantly less memory
```

### 12.2 Generator vs List for Large Data

```python
import time
import sys

def process_with_list(n):
    """Eager evaluation — all data in memory."""
    data = [x**2 for x in range(n)]
    return sum(data)

def process_with_generator(n):
    """Lazy evaluation — one item at a time."""
    return sum(x**2 for x in range(n))

n = 10_000_000

start = time.perf_counter()
result1 = process_with_list(n)
list_time = time.perf_counter() - start

start = time.perf_counter()
result2 = process_with_generator(n)
gen_time = time.perf_counter() - start

print(f"List:      {list_time:.3f}s")
print(f"Generator: {gen_time:.3f}s")
print(f"Both correct: {result1 == result2}")
```

### 12.3 Profiling with cProfile and line_profiler

```python
import cProfile
import pstats
import io

# Profile a function
def slow_function():
    result = []
    for i in range(10_000):
        result.append(sum(range(i)))
    return result

# Method 1: Context manager profiling
with cProfile.Profile() as pr:
    slow_function()

stats = pstats.Stats(pr, stream=io.StringIO())
stats.sort_stats(pstats.SortKey.CUMULATIVE)
stats.print_stats(10)   # top 10 functions

# Method 2: Command line
# python -m cProfile -s cumtime my_script.py

# Method 3: timeit for micro-benchmarks
import timeit

# Compare list append vs extend
t1 = timeit.timeit(
    "for x in range(100): lst.append(x)",
    setup="lst = []",
    number=10_000
)

t2 = timeit.timeit(
    "lst.extend(range(100))",
    setup="lst = []",
    number=10_000
)

print(f"append: {t1:.4f}s")
print(f"extend: {t2:.4f}s")
```

### 12.4 Efficient Data Structures

```python
from collections import deque, Counter, defaultdict, OrderedDict
import heapq

# deque — O(1) append/pop from BOTH ends (list is O(n) for left operations)
q = deque([1, 2, 3])
q.appendleft(0)    # O(1)
q.append(4)        # O(1)
q.popleft()        # O(1)
q.pop()            # O(1)
print(q)   # deque([1, 2, 3])

# Counter — frequency counting
words = "the quick brown fox jumps over the lazy dog the fox".split()
freq = Counter(words)
print(freq.most_common(3))   # [('the', 3), ('fox', 2), ...]

# defaultdict — auto-create missing keys
dd = defaultdict(list)
for word in words:
    dd[word[0]].append(word)   # group by first letter
print(dict(dd))

# heapq — priority queue
heap = []
for val in [3, 1, 4, 1, 5, 9, 2, 6]:
    heapq.heappush(heap, val)

sorted_vals = [heapq.heappop(heap) for _ in range(len(heap))]
print(sorted_vals)   # [1, 1, 2, 3, 4, 5, 6, 9]

# heapq.nlargest / nsmallest (more efficient than sorted for small n)
data = [3, 1, 4, 1, 5, 9, 2, 6, 5, 3, 5]
print(heapq.nlargest(3, data))   # [9, 6, 5]
print(heapq.nsmallest(3, data))  # [1, 1, 2]
```

### 12.5 String Performance

```python
import timeit

# ❌ Slow: string concatenation in loop
def build_string_concat(n):
    s = ""
    for i in range(n):
        s += str(i)   # creates new string object each time! O(n²)
    return s

# ✅ Fast: join
def build_string_join(n):
    parts = []
    for i in range(n):
        parts.append(str(i))
    return "".join(parts)   # single allocation

# ✅ Fastest: list comprehension + join
def build_string_list_comp(n):
    return "".join(str(i) for i in range(n))

n = 10_000
t1 = timeit.timeit(lambda: build_string_concat(n), number=100)
t2 = timeit.timeit(lambda: build_string_join(n), number=100)
t3 = timeit.timeit(lambda: build_string_list_comp(n), number=100)

print(f"concat:    {t1:.3f}s")
print(f"join:      {t2:.3f}s")
print(f"list comp: {t3:.3f}s")
# join and list comp ~10-50x faster than concat for large strings
```

---

<a name="section-13"></a>

## 🐛 Section 13 — Debugging Advanced Python

### 13.1 Decorator Bugs

```python
import functools

# BUG 1: Forgetting @functools.wraps
def broken_decorator(func):
    def wrapper(*args, **kwargs):
        return func(*args, **kwargs)
    return wrapper

@broken_decorator
def my_func():
    """Important docstring."""
    pass

print(my_func.__name__)   # "wrapper" ← WRONG
print(my_func.__doc__)    # None      ← WRONG

# FIX: Always use @functools.wraps
def good_decorator(func):
    @functools.wraps(func)
    def wrapper(*args, **kwargs):
        return func(*args, **kwargs)
    return wrapper


# BUG 2: Decorator order matters
def add_prefix(func):
    @functools.wraps(func)
    def wrapper():
        return "PREFIX_" + func()
    return wrapper

def add_suffix(func):
    @functools.wraps(func)
    def wrapper():
        return func() + "_SUFFIX"
    return wrapper


@add_prefix
@add_suffix
def get_name():
    return "hello"

print(get_name())   # "PREFIX_hello_SUFFIX"
# add_prefix(add_suffix(get_name))()


# BUG 3: Parametric decorator — forgetting the extra level
# ❌ Wrong
def bad_repeat(func, times=3):   # This would be called as @bad_repeat, not @bad_repeat(3)
    pass

# ✅ Correct
def repeat(times=3):
    def decorator(func):
        @functools.wraps(func)
        def wrapper(*args, **kwargs):
            for _ in range(times):
                result = func(*args, **kwargs)
            return result
        return wrapper
    return decorator

@repeat(times=2)
def say_hi():
    print("Hi!")
```

### 13.2 Generator Bugs

```python
# BUG 1: Generator exhaustion
def gen():
    yield from [1, 2, 3]

g = gen()
print(list(g))   # [1, 2, 3]
print(list(g))   # [] ← EMPTY! generator exhausted

# FIX: Store the list, or recreate the generator
data = [1, 2, 3]
print(list(x for x in data))   # Always fresh
print(list(x for x in data))   # Always fresh


# BUG 2: Modifying a list while iterating with a generator
data = [1, 2, 3, 4, 5]
gen = (x for x in data)   # generator holds reference to data

data.clear()   # MODIFIES original!
print(list(gen))   # [] ← data was cleared!

# FIX: Snapshot the data before creating generator
data = [1, 2, 3, 4, 5]
gen = (x for x in list(data))   # take snapshot


# BUG 3: Forgetting to prime coroutines
def accumulator():
    total = 0
    while True:
        value = yield total
        total += value

acc = accumulator()
# acc.send(10)   # TypeError: can't send non-None value to a just-started generator
next(acc)        # Prime it first!
print(acc.send(10))   # 10
```

### 13.3 Closure Bugs

```python
# BUG: Late binding (most common closure bug)
def make_adders():
    return [lambda x: x + i for i in range(5)]

adders = make_adders()
print([f(0) for f in adders])   # [4, 4, 4, 4, 4] ← ALL 4!

# FIX: Capture current value
def make_adders_fixed():
    return [lambda x, i=i: x + i for i in range(5)]

adders = make_adders_fixed()
print([f(0) for f in adders])   # [0, 1, 2, 3, 4] ← CORRECT


# BUG: UnboundLocalError with nonlocal
def counter():
    count = 0
    def increment():
        count += 1   # UnboundLocalError! Python sees assignment → local var
        return count
    return increment

# FIX
def counter_fixed():
    count = 0
    def increment():
        nonlocal count   # explicitly reference enclosing scope
        count += 1
        return count
    return increment

c = counter_fixed()
print(c(), c(), c())   # 1 2 3
```

### 13.4 Context Manager Bugs

```python
# BUG 1: Silently suppressing exceptions
class BadCM:
    def __enter__(self):
        return self

    def __exit__(self, *args):
        return True   # ← ALWAYS suppresses exceptions — dangerous!

with BadCM():
    raise ValueError("This error vanishes!")   # Silently swallowed!
print("This runs — bug not noticed!")

# FIX: Only suppress specific exceptions
class GoodCM:
    def __exit__(self, exc_type, exc_val, exc_tb):
        if exc_type is ValueError:
            print(f"Suppressing ValueError: {exc_val}")
            return True   # suppress only ValueError
        return False   # propagate everything else


# BUG 2: Resource not released on exception
# ❌ Wrong
resource = open("file.txt", "w")
try:
    resource.write("data")
    raise RuntimeError("oops")
except RuntimeError:
    pass
# resource is NEVER closed!

# ✅ Correct
with open("file.txt", "w") as resource:
    resource.write("data")
    raise RuntimeError("oops")
# file ALWAYS closed, exception propagated
```

---

<a name="section-14"></a>

## 🏗 Section 14 — Python Developer Best Practices

### 14.1 Code Organization

```python
"""
Module docstring: describe what this module does.

Follows PEP8:
  - 4-space indentation
  - 79-char line limit (or 99 for modern projects)
  - 2 blank lines between top-level definitions
  - 1 blank line between methods
  - Imports at top, in order: stdlib, third-party, local
"""

# Standard library
import os
import sys
from pathlib import Path
from typing import Optional, List, Dict, Union, Generator

# Third-party
# import numpy as np   # if needed

# Local
# from .utils import helper   # if needed


# Constants: UPPER_SNAKE_CASE
MAX_RETRIES = 3
DEFAULT_TIMEOUT = 30.0
API_BASE_URL = "https://api.example.com/v1"


# Type aliases
UserID = int
Email = str
JSONData = Dict[str, Union[str, int, float, bool, None]]


class DataProcessor:
    """Process data records with configurable transformations.

    Args:
        config: Configuration dictionary.
        max_batch_size: Maximum records per batch. Defaults to 100.

    Example:
        >>> processor = DataProcessor(config={})
        >>> list(processor.process([{"id": 1}]))
        [{'id': 1, 'processed': True}]
    """

    DEFAULT_BATCH_SIZE = 100

    def __init__(self, config: dict, max_batch_size: int = DEFAULT_BATCH_SIZE):
        self._config = config
        self._max_batch_size = max_batch_size
        self._processed_count = 0

    @property
    def processed_count(self) -> int:
        """Number of records processed so far."""
        return self._processed_count

    def process(self, records: List[dict]) -> Generator[dict, None, None]:
        """Process records lazily.

        Args:
            records: List of record dictionaries.

        Yields:
            Processed record dictionaries.

        Raises:
            ValueError: If records is empty.
        """
        if not records:
            raise ValueError("records cannot be empty")

        for record in records:
            yield self._transform(record)
            self._processed_count += 1

    def _transform(self, record: dict) -> dict:
        """Internal transformation — not part of public API."""
        return {**record, "processed": True}
```

### 14.2 PEP8 Quick Reference

```
Naming Conventions:
  variable_name      → snake_case
  function_name      → snake_case
  CLASS_CONSTANT     → UPPER_SNAKE_CASE
  ClassName          → PascalCase
  _private           → leading underscore (convention)
  __name_mangled     → double leading underscore (name mangling)
  __dunder__         → double underscore both sides (magic method)

Whitespace:
  x = 1              → spaces around =
  f(a, b)            → space after comma
  d['key']           → no space around []
  if x > 0:          → space before colon only in slice
  x[1:3]             → no spaces in slice
  x[1 : 3 : 1]       → spaces in complex slice OK

Imports:
  import os          → standard library first
  import sys

  import requests    → third-party second
  import numpy

  from .utils import helper   → local last

Lines:
  79 chars max (PEP8 standard) or 99 (Black default)
  Use \ or () for line continuation
  Two blank lines between top-level definitions
  One blank line between methods
```

### 14.3 Type Hints

```python
from typing import Optional, List, Dict, Tuple, Set, Any, Callable, Generator
from typing import Union, TypeVar, Generic
from collections.abc import Sequence, Iterable, Iterator

T = TypeVar('T')


def greet(name: str) -> str:
    return f"Hello, {name}!"


def find_max(numbers: List[float]) -> Optional[float]:
    return max(numbers) if numbers else None


def transform(
    data: Iterable[T],
    func: Callable[[T], T],
    *,
    skip_none: bool = False
) -> Generator[T, None, None]:
    for item in data:
        if skip_none and item is None:
            continue
        yield func(item)


# Python 3.10+ — union with |
def process(value: int | str | None) -> str:
    if value is None:
        return "none"
    return str(value)


# Dataclasses — typed, clean, auto-generated methods
from dataclasses import dataclass, field


@dataclass
class User:
    id: int
    name: str
    email: str
    roles: List[str] = field(default_factory=list)
    active: bool = True

    def __post_init__(self):
        if not self.email or '@' not in self.email:
            raise ValueError(f"Invalid email: {self.email}")


alice = User(1, "Alice", "alice@example.com", ["admin"])
print(alice)   # User(id=1, name='Alice', email='alice@example.com', roles=['admin'], active=True)
```

---

<a name="section-15"></a>

## 🛠 Section 15 — Mini Projects

### Project 1: Custom Logger Decorator

```python
"""
Custom Logger Decorator
Problem: Add structured, configurable logging to any function.
"""

import functools
import logging
import json
import time
from datetime import datetime


def setup_logger(name: str, level=logging.DEBUG) -> logging.Logger:
    logger = logging.getLogger(name)
    if not logger.handlers:
        handler = logging.StreamHandler()
        formatter = logging.Formatter('%(asctime)s | %(levelname)s | %(message)s')
        handler.setFormatter(formatter)
        logger.addHandler(handler)
    logger.setLevel(level)
    return logger


def log_execution(logger=None, log_args=True, log_result=True, log_time=True):
    """
    Parametric decorator for structured logging.

    Usage:
        @log_execution(log_args=True, log_result=False)
        def my_function(x, y):
            return x + y
    """
    _logger = logger or setup_logger("execution_log")

    def decorator(func):
        @functools.wraps(func)
        def wrapper(*args, **kwargs):
            call_id = f"{func.__name__}_{int(time.time() * 1000) % 10000}"
            log_entry = {
                "call_id": call_id,
                "function": func.__name__,
                "module": func.__module__,
                "timestamp": datetime.now().isoformat(),
            }

            if log_args:
                log_entry["args"] = str(args)
                log_entry["kwargs"] = str(kwargs)

            _logger.info(f"ENTER | {json.dumps(log_entry)}")
            start = time.perf_counter()

            try:
                result = func(*args, **kwargs)
                elapsed = time.perf_counter() - start

                exit_entry = {
                    "call_id": call_id,
                    "status": "SUCCESS",
                }
                if log_time:
                    exit_entry["elapsed_ms"] = round(elapsed * 1000, 4)
                if log_result:
                    exit_entry["result"] = str(result)[:200]

                _logger.info(f"EXIT  | {json.dumps(exit_entry)}")
                return result

            except Exception as e:
                elapsed = time.perf_counter() - start
                _logger.error(json.dumps({
                    "call_id": call_id,
                    "status": "ERROR",
                    "exception": type(e).__name__,
                    "message": str(e),
                    "elapsed_ms": round(elapsed * 1000, 4),
                }))
                raise

        return wrapper
    return decorator


# Usage
@log_execution(log_args=True, log_result=True)
def calculate(a: int, b: int, operation: str = "add") -> float:
    if operation == "add":
        return a + b
    elif operation == "div":
        if b == 0:
            raise ZeroDivisionError("Cannot divide by zero")
        return a / b
    raise ValueError(f"Unknown operation: {operation}")


print(calculate(10, 5, operation="add"))
print(calculate(10, 5, operation="div"))
try:
    calculate(10, 0, operation="div")
except ZeroDivisionError:
    pass
```

---

### Project 2: Execution Time Analyzer

```python
"""
Execution Time Analyzer
Problem: Profile and compare function performance.
"""

import functools
import time
import statistics
from typing import Callable, Any


class TimeAnalyzer:
    """Context manager + decorator for detailed timing analysis."""

    def __init__(self, name: str = "operation", runs: int = 1):
        self.name = name
        self.runs = runs
        self.times: list = []
        self._start = None

    def __enter__(self):
        self._start = time.perf_counter()
        return self

    def __exit__(self, *args):
        elapsed = time.perf_counter() - self._start
        self.times.append(elapsed)
        self._print_stats()
        return False

    def __call__(self, func: Callable) -> Callable:
        """Use as decorator."""
        @functools.wraps(func)
        def wrapper(*args, **kwargs):
            run_times = []
            result = None
            for i in range(self.runs):
                start = time.perf_counter()
                result = func(*args, **kwargs)
                run_times.append(time.perf_counter() - start)
            self.times = run_times
            self._print_stats(func.__name__)
            return result
        return wrapper

    def _print_stats(self, label: str = None):
        label = label or self.name
        times_ms = [t * 1000 for t in self.times]

        if len(times_ms) == 1:
            print(f"⏱  {label}: {times_ms[0]:.4f}ms")
        else:
            print(f"📊 {label} over {len(times_ms)} runs:")
            print(f"   Mean:   {statistics.mean(times_ms):.4f}ms")
            print(f"   Median: {statistics.median(times_ms):.4f}ms")
            print(f"   Stdev:  {statistics.stdev(times_ms):.4f}ms")
            print(f"   Min:    {min(times_ms):.4f}ms")
            print(f"   Max:    {max(times_ms):.4f}ms")

    @property
    def mean_ms(self) -> float:
        return statistics.mean(self.times) * 1000 if self.times else 0


# Usage as context manager
with TimeAnalyzer("list comprehension"):
    result = [x**2 for x in range(100_000)]

# Usage as decorator
@TimeAnalyzer(runs=10)
def bubble_sort(arr):
    arr = arr[:]
    n = len(arr)
    for i in range(n):
        for j in range(0, n - i - 1):
            if arr[j] > arr[j + 1]:
                arr[j], arr[j + 1] = arr[j + 1], arr[j]
    return arr


import random
data = [random.randint(0, 1000) for _ in range(500)]
bubble_sort(data)
```

---

### Project 3: Data Stream Generator

```python
"""
Data Stream Generator
Problem: Stream and process large datasets memory-efficiently.
"""

import json
import random
import time
from typing import Generator, Dict, Any, Iterator


def generate_user_events(count: int = 1000) -> Generator[Dict[str, Any], None, None]:
    """Generate synthetic user event stream."""
    event_types = ["click", "view", "purchase", "signup", "logout"]
    pages = ["/home", "/products", "/cart", "/checkout", "/profile"]

    for i in range(count):
        yield {
            "event_id": i,
            "timestamp": time.time() + i,
            "user_id": random.randint(1, 100),
            "event_type": random.choice(event_types),
            "page": random.choice(pages),
            "session_id": f"sess_{random.randint(1000, 9999)}",
            "duration_ms": random.randint(100, 5000),
        }


def filter_events(events: Iterator, event_type: str) -> Generator:
    """Filter stream by event type."""
    return (e for e in events if e["event_type"] == event_type)


def enrich_events(events: Iterator) -> Generator:
    """Add computed fields to each event."""
    for event in events:
        yield {
            **event,
            "is_mobile": event["session_id"].endswith(('1', '3', '7')),
            "duration_category": (
                "fast" if event["duration_ms"] < 1000
                else "medium" if event["duration_ms"] < 3000
                else "slow"
            )
        }


def aggregate_by_user(events: Iterator) -> Dict[int, Dict]:
    """Aggregate events by user (terminal operation — consumes stream)."""
    stats = {}
    for event in events:
        uid = event["user_id"]
        if uid not in stats:
            stats[uid] = {"count": 0, "total_duration": 0, "pages": set()}
        stats[uid]["count"] += 1
        stats[uid]["total_duration"] += event["duration_ms"]
        stats[uid]["pages"].add(event["page"])
    return stats


# Build pipeline
stream = generate_user_events(10_000)
purchases = filter_events(stream, "purchase")
enriched = enrich_events(purchases)
user_stats = aggregate_by_user(enriched)

print(f"Unique buyers: {len(user_stats)}")
top_buyer = max(user_stats.items(), key=lambda x: x[1]["count"])
print(f"Top buyer: user_id={top_buyer[0]}, purchases={top_buyer[1]['count']}")
```

---

### Project 4: Custom Context Manager Library

```python
"""
Resource Manager Library
Problem: Build reusable context managers for common resources.
"""

from contextlib import contextmanager
import time
import threading


@contextmanager
def rate_limiter(calls_per_second: float):
    """Context manager that rate-limits code blocks."""
    min_interval = 1.0 / calls_per_second
    last_call = [0.0]

    class RateLimitedContext:
        def __call__(self):
            now = time.time()
            elapsed = now - last_call[0]
            if elapsed < min_interval:
                time.sleep(min_interval - elapsed)
            last_call[0] = time.time()

    ctx = RateLimitedContext()
    yield ctx


@contextmanager
def transaction(connection):
    """Generic transaction context manager."""
    try:
        yield connection
        connection.commit()
    except Exception:
        connection.rollback()
        raise
    finally:
        connection.close()


@contextmanager
def thread_lock(lock: threading.Lock, timeout: float = None):
    """Thread lock with optional timeout."""
    acquired = lock.acquire(timeout=timeout if timeout else -1)
    if not acquired:
        raise TimeoutError(f"Could not acquire lock within {timeout}s")
    try:
        yield
    finally:
        lock.release()


@contextmanager
def retry_context(max_attempts: int = 3, delay: float = 1.0, exceptions=(Exception,)):
    """Retry context manager."""
    attempt = 0
    while True:
        try:
            yield
            break
        except exceptions as e:
            attempt += 1
            if attempt >= max_attempts:
                raise
            print(f"Attempt {attempt} failed: {e}. Retrying in {delay}s...")
            time.sleep(delay)


# Demo
with rate_limiter(calls_per_second=2) as limiter:
    for i in range(5):
        limiter()   # Enforces rate limiting
        print(f"API call {i + 1} at {time.strftime('%H:%M:%S')}")
```

---

### Projects 5–10 (Condensed)

```python
# Project 5: Authentication Decorator System
# (See Section 6.9 for full implementation)
# Features: @require_auth, @require_role, @audit_log

# Project 6: File Processing Pipeline
def file_pipeline(filepath, transformations):
    """Apply transformations to file content lazily."""
    with open(filepath, 'r') as f:
        lines = (line.rstrip() for line in f)
        for transform in transformations:
            lines = transform(lines)
        yield from lines

# Project 7: Lazy Dataset Loader
def lazy_csv_loader(filepath, chunk_size=1000):
    """Load CSV in chunks without reading entire file."""
    import csv
    with open(filepath, 'r') as f:
        reader = csv.DictReader(f)
        chunk = []
        for row in reader:
            chunk.append(row)
            if len(chunk) == chunk_size:
                yield chunk
                chunk = []
        if chunk:
            yield chunk

# Project 8: Custom Iterator (NumberRange — see Section 3.6)

# Project 9: Functional Data Cleaner
def clean_pipeline(*cleaners):
    """Build a functional cleaning pipeline."""
    from functools import reduce
    def apply(data):
        return reduce(lambda d, cleaner: cleaner(d), cleaners, data)
    return apply

strip_whitespace = lambda lst: [s.strip() for s in lst]
to_lower = lambda lst: [s.lower() for s in lst]
remove_empty = lambda lst: [s for s in lst if s]
deduplicate = lambda lst: list(dict.fromkeys(lst))

clean = clean_pipeline(strip_whitespace, to_lower, remove_empty, deduplicate)
data = ["  Hello  ", "WORLD", "", "  hello  ", "Python", "WORLD"]
print(clean(data))   # ['hello', 'world', 'python']

# Project 10: Performance Benchmark Tool
# (See Section 12.3 for full cProfile implementation)
```

---

<a name="section-16"></a>

## 📁 Section 16 — 20 High Value Portfolio Projects

### Project 1: Developer Utility Framework

**Overview:** A modular Python toolkit providing reusable decorators, utilities, and helpers for production Python development.

**Real World Usage:** Used by engineering teams to enforce logging, caching, retrying, and validation standards across microservices.

**Resume Value:** Shows framework-thinking, reusable component design, open-source mindset.

**Architecture:**
```
developer-utility-framework/
├── src/
│   ├── decorators/         ← logging, timing, retry, auth, validate
│   ├── generators/         ← data streams, pipelines, lazy loaders
│   ├── context_managers/   ← db, files, locks, timers
│   ├── functional/         ← compose, pipe, partial utils
│   ├── caching/            ← TTL cache, LRU cache, disk cache
│   └── utils/              ← type checking, config loading
├── tests/
├── benchmarks/
├── docs/
├── examples/
├── pyproject.toml
└── README.md
```

**MVP → Professional → Enterprise:**
- MVP: 10 core decorators, basic tests
- Professional: 30+ decorators, 90%+ test coverage, CI/CD, PyPI package
- Enterprise: Plugin system, configuration via YAML, distributed tracing integration, metrics export

---

### Project 2: Data Processing Pipeline Engine

**Overview:** A composable, memory-efficient data processing system using generators and functional programming for ETL workloads.

**Real World Usage:** Data engineering teams processing millions of records daily.

```
pipeline-engine/
├── src/
│   ├── sources/        ← CSV, JSON, DB, API, S3 readers
│   ├── transforms/     ← filter, map, aggregate, join operations
│   ├── sinks/          ← CSV, DB, API, file writers
│   ├── pipeline/       ← Pipeline builder and executor
│   └── monitoring/     ← metrics, progress tracking
├── tests/
├── examples/
└── README.md
```

**Development Roadmap:**
1. Week 1: Core pipeline abstraction
2. Week 2: Source adapters (CSV, JSON)
3. Week 3: Transform library
4. Week 4: Sink adapters + monitoring
5. Week 5: Tests + documentation

---

### Project 3: Research Dataset Processor

**Overview:** Tool for loading, cleaning, and preprocessing ML research datasets.

```
research-dataset-processor/
├── src/
│   ├── loaders/      ← HuggingFace, Kaggle, local file loaders
│   ├── cleaners/     ← text, numeric, categorical cleaning
│   ├── splitters/    ← train/val/test splitting strategies
│   ├── exporters/    ← Parquet, CSV, JSON, HDF5 export
│   └── stats/        ← dataset statistics and profiling
└── notebooks/        ← Jupyter demo notebooks
```

---

### Project 4: Performance Monitoring Toolkit

**Overview:** Decorator-based performance monitoring for Python applications.

**Features:** Function profiling, memory tracking, hot-path detection, report generation.

```python
# Example API
@monitor.track(
    cpu=True,
    memory=True,
    calls=True,
    alert_threshold_ms=100
)
def critical_function(data):
    return process(data)

monitor.report()   # Generate HTML performance report
```

---

### Projects 5–20 Summary

| # | Project | Core Python Features | Industry Domain |
|---|---------|---------------------|-----------------|
| 5 | Automation Framework | Decorators, generators, scheduling | DevOps |
| 6 | Custom Task Scheduler | Generators, context managers, threading | Backend |
| 7 | CLI Productivity Platform | Functional programming, iterators | Developer Tools |
| 8 | Developer Analytics Engine | Generators, map/filter/reduce | Data Engineering |
| 9 | Research Workflow Toolkit | Pipelines, generators, dataclasses | AI/ML |
| 10 | Code Execution Framework | Context managers, subprocess, sandboxing | Education/Dev |
| 11 | Data Streaming Engine | Infinite generators, async-ready | Real-time Systems |
| 12 | Plugin-Based App Framework | Decorators, hooks, dynamic imports | SaaS Platform |
| 13 | Log Processing Platform | Generators, regex, parsers | Observability |
| 14 | AI Dataset Pipeline | Generators, transformations, augmentation | AI Engineering |
| 15 | Developer Benchmarking Tool | Profiling, timeit, cProfile | Performance |
| 16 | Knowledge Processing Engine | NLP pipeline, generators, clustering | LLM Engineering |
| 17 | Workflow Automation Platform | State machines, decorators, events | Business Logic |
| 18 | Python Utility Collection | All Day13 concepts | Open Source |
| 19 | File Processing Framework | Context managers, generators, patterns | Data Pipelines |
| 20 | Developer Operations Toolkit | Automation, monitoring, deployment | DevOps |

---

<a name="section-17"></a>

## 📂 Section 17 — Project Layout Masterclass

### Standard Python Project Structure

```text
my-project/
│
├── src/
│   └── my_project/           ← main package
│       ├── __init__.py       ← package initializer, public API
│       ├── core/             ← core business logic
│       │   ├── __init__.py
│       │   ├── models.py     ← data models, dataclasses
│       │   └── services.py   ← business logic services
│       ├── decorators/       ← all decorator modules
│       │   ├── __init__.py
│       │   ├── timing.py
│       │   ├── logging.py
│       │   ├── caching.py
│       │   ├── retry.py
│       │   └── validation.py
│       ├── generators/       ← generator functions and pipelines
│       │   ├── __init__.py
│       │   ├── pipelines.py
│       │   ├── streams.py
│       │   └── infinite.py
│       ├── iterators/        ← custom iterator classes
│       │   ├── __init__.py
│       │   └── custom.py
│       ├── context_managers/ ← context manager classes
│       │   ├── __init__.py
│       │   ├── database.py
│       │   ├── files.py
│       │   └── resources.py
│       ├── functional/       ← functional programming utilities
│       │   ├── __init__.py
│       │   ├── compose.py
│       │   └── transforms.py
│       ├── utils/            ← general utilities
│       │   ├── __init__.py
│       │   ├── config.py
│       │   └── helpers.py
│       └── services/         ← external service adapters
│           ├── __init__.py
│           └── api.py
│
├── tests/                    ← test suite
│   ├── __init__.py
│   ├── conftest.py           ← shared fixtures
│   ├── unit/                 ← unit tests (isolated)
│   │   ├── test_decorators.py
│   │   ├── test_generators.py
│   │   └── test_iterators.py
│   └── integration/          ← integration tests
│       └── test_pipeline.py
│
├── docs/                     ← documentation
│   ├── conf.py               ← Sphinx config
│   ├── index.rst
│   ├── api/                  ← auto-generated API docs
│   └── guides/               ← how-to guides
│
├── benchmarks/               ← performance benchmarks
│   ├── bench_generators.py
│   └── bench_decorators.py
│
├── examples/                 ← usage examples
│   ├── basic_usage.py
│   └── advanced_usage.py
│
├── config/                   ← configuration files
│   ├── development.yaml
│   ├── production.yaml
│   └── testing.yaml
│
├── logs/                     ← log files (gitignored)
│   └── .gitkeep
│
├── .github/
│   └── workflows/
│       ├── tests.yml         ← CI: run tests on every PR
│       └── publish.yml       ← CD: publish to PyPI on release
│
├── pyproject.toml            ← modern Python packaging (PEP 517)
├── setup.cfg                 ← optional: metadata
├── requirements.txt          ← production dependencies
├── requirements-dev.txt      ← development dependencies
├── Makefile                  ← common commands (test, lint, build)
├── README.md                 ← project documentation
├── CHANGELOG.md              ← version history
├── LICENSE                   ← MIT/Apache/GPL
├── .gitignore                ← git exclusions
├── .env.example              ← environment variable template
└── .pre-commit-config.yaml   ← pre-commit hooks (Black, isort, flake8)
```

### pyproject.toml Template

```toml
[build-system]
requires = ["setuptools>=65", "wheel"]
build-backend = "setuptools.backends.legacy:build"

[project]
name = "my-project"
version = "0.1.0"
description = "Advanced Python utility framework"
readme = "README.md"
requires-python = ">=3.10"
license = {text = "MIT"}
authors = [
    {name = "Your Name", email = "you@example.com"}
]
keywords = ["python", "utilities", "decorators", "generators"]
classifiers = [
    "Programming Language :: Python :: 3",
    "License :: OSI Approved :: MIT License",
    "Operating System :: OS Independent",
]
dependencies = []

[project.optional-dependencies]
dev = [
    "pytest>=7.0",
    "pytest-cov>=4.0",
    "black>=23.0",
    "isort>=5.0",
    "mypy>=1.0",
    "flake8>=6.0",
]

[tool.black]
line-length = 99
target-version = ["py310"]

[tool.isort]
profile = "black"

[tool.mypy]
strict = true
```

---

<a name="section-18"></a>

## 🌟 Section 18 — GitHub Profile Booster Projects

| # | Project | Recruiter Appeal | Skills Demonstrated | Enterprise Relevance |
|---|---------|-----------------|---------------------|----------------------|
| 1 | **Data Streaming Engine** | High — real-time data is hot | Generators, pipelines, memory optimization | Kafka-ready patterns |
| 2 | **Plugin Framework** | High — shows architecture thinking | Decorators, dynamic imports, hooks | Extensible platforms |
| 3 | **Automation Toolkit** | Medium-High | Context managers, subprocess, scheduling | DevOps, CI/CD |
| 4 | **Performance Analyzer** | High for senior roles | cProfile, decorators, benchmarking | Production engineering |
| 5 | **Workflow Engine** | High — business-critical | State machines, decorators, composition | BPM, SaaS |
| 6 | **AI Dataset Pipeline** | Very High — AI market | Generators, lazy loading, transforms | LLM/ML Engineering |
| 7 | **Research Processing Framework** | High for AI/data roles | Functional programming, type hints | Data Science, AI |
| 8 | **Developer Utility Suite** | Medium — shows breadth | All Day13 concepts | Open Source |
| 9 | **Log Analytics Platform** | Medium-High | Generators, regex, parsers | Observability |
| 10 | **Benchmarking Toolkit** | High for performance-focused roles | Profiling, statistics, reporting | SRE, Backend |

### Making Projects Recruiter-Worthy

```
Checklist for every GitHub project:
✅ Clear README with: description, installation, usage, examples
✅ Demo GIF or screenshot at top of README
✅ Working code (not just scaffolding)
✅ Tests (even basic ones show maturity)
✅ Proper .gitignore
✅ License file
✅ Meaningful commit history (not "initial commit" + "final")
✅ requirements.txt or pyproject.toml
✅ Docstrings on all public functions
✅ At least one "advanced" feature that shows depth

README Badge Template:
![Python](https://img.shields.io/badge/python-3.10+-blue)
![Tests](https://img.shields.io/github/actions/workflow/status/user/repo/tests.yml)
![License](https://img.shields.io/badge/license-MIT-green)
```

---

<a name="section-19"></a>

## 🎯 Section 19 — Complete Project Solution Framework

### From Idea to GitHub in 7 Steps

```
Step 1: REQUIREMENTS ANALYSIS
  - What problem does it solve?
  - Who are the users?
  - What are the inputs/outputs?
  - What are the constraints (memory, speed, scale)?

Step 2: ARCHITECTURE DESIGN
  - Identify core abstractions (classes, functions, modules)
  - Define interfaces (what each module exposes)
  - Design data flow (inputs → transforms → outputs)
  - Choose design patterns (pipeline? plugin? observer?)

Step 3: MODULE PLANNING
  - Define folder structure (see Section 17)
  - Define __init__.py exports for each package
  - Write module docstrings before writing code

Step 4: DECORATOR DESIGN
  - Which functions need logging, timing, retrying?
  - Where do we need validation, auth, caching?
  - Design decorator interfaces before implementing

Step 5: GENERATOR DESIGN
  - Where are large datasets processed?
  - Where can lazy evaluation reduce memory?
  - Design pipeline stages as composable generators

Step 6: TESTING STRATEGY
  - Unit tests: test each function/class in isolation
  - Integration tests: test module interactions
  - Performance tests: benchmark critical paths
  - Use pytest + fixtures (see Day 14)

Step 7: DOCUMENTATION + GITHUB
  - Write README.md (description, install, usage, examples)
  - Add docstrings to all public APIs
  - Create examples/ directory with demo scripts
  - Set up GitHub Actions for automated testing
  - Tag a v0.1.0 release
```

---

<a name="section-20"></a>

## 📝 Section 20 — 700 Practice Questions

### Easy (Questions 1–250)

**Iterators (1–50)**

1. What is an iterable in Python?
2. What is an iterator in Python?
3. What method must an iterable implement?
4. What two methods must an iterator implement?
5. What does `iter()` do?
6. What does `next()` do?
7. What exception does an exhausted iterator raise?
8. Write code to manually iterate over `[1, 2, 3]` using `iter()` and `next()`.
9. Is a `list` an iterator? Why or why not?
10. Is a `list_iterator` an iterable? Why?
11. Write a class `SquareIterator` that yields squares: 1, 4, 9, 16...
12. What does `iter(callable, sentinel)` do?
13. What is `StopIteration` and when is it raised?
14. Can you reset an iterator? How?
15. What does `hasattr(obj, '__iter__')` check?
16. Explain the `for` loop in terms of `iter()` and `next()`.
17. Write a function that returns the first N items of any iterable.
18. What is `list(iter([1, 2, 3]))`?
19. What is a lazy iterable?
20. Why is `range()` memory-efficient?
21. Difference between `range` and `list`?
22. Write a `Fibonacci` class that implements the iterator protocol.
23. What is `__iter__` method?
24. What is `__next__` method?
25. Calling `iter()` on an iterator returns...?
26. Write a `Countdown(n)` iterator.
27. What does `zip()` return — an iterator or a list?
28. What does `enumerate()` return?
29. How do you check if an object is an iterator?
30. Import from `collections.abc` to check for `Iterator`.
31. Can a generator be used as an iterator? Yes/No with reason.
32. What happens when `for` loop calls `__next__` and gets `StopIteration`?
33. Write `take(n, iterable)` function.
34. Write `drop(n, iterable)` function.
35. What is `iter([])` — does it raise an error?
36. What is the return type of `map()`?
37. What is the return type of `filter()`?
38. Are `map()` and `filter()` iterators?
39. Can you iterate over a `dict`? What do you get?
40. Can you iterate over a `dict.values()`?
41. Can you iterate over a `dict.items()`?
42. What is `reversed()`? What does it return?
43. Can `reversed()` be applied to any iterable?
44. What makes a type support `reversed()`?
45. Implement `__reversed__` in a class.
46. What is the difference between `iter(obj)` and `obj.__iter__()`?
47. When does the iterator protocol start, mid-loop?
48. Can a custom iterator have state beyond just a position counter?
49. Write an iterator that generates random numbers indefinitely.
50. Write an `EvenNumbers(limit)` iterator.

**Generators (51–100)**

51. What is a generator function?
52. What keyword turns a function into a generator?
53. What does `yield` do when executed?
54. What does calling a generator function return?
55. How do you get values from a generator?
56. Write a generator `count_up(start, end)`.
57. Write a generator expression for squares of 0–9.
58. What is the difference between `yield` and `return` in a generator?
59. Can a generator function have both `yield` and `return`?
60. What does `return` do inside a generator?
61. What is lazy evaluation?
62. Why are generators memory-efficient?
63. Write a `fibonacci()` infinite generator.
64. What is `yield from`?
65. Write a `flatten(nested)` function using `yield from`.
66. Can you iterate a generator twice? Explain.
67. What is `next(gen, default)`?
68. What is `list(gen)` for a generator `gen`?
69. What is `sum(x for x in range(100))`?
70. Write a generator that reads lines from a file.
71. What is the difference between a generator expression and list comprehension?
72. Write a generator `take_while(predicate, iterable)`.
73. Write a generator `drop_while(predicate, iterable)`.
74. What is `gen.send(value)`?
75. How do you prime a coroutine?
76. What is `gen.throw(exception)`?
77. What is `gen.close()`?
78. What does `GeneratorExit` mean?
79. Write a generator `cycle(iterable)` like `itertools.cycle`.
80. Write a generator `repeat(value, n)`.
81. When is `StopIteration` raised in a generator?
82. What is the memory usage of a generator vs list?
83. Write a `range_gen(start, stop, step)` generator.
84. Can generators be used in `sum()`, `max()`, `min()`?
85. What is a generator pipeline?
86. Write a two-stage generator pipeline.
87. What is `itertools.chain`?
88. What is `itertools.islice`?
89. What does `itertools.count()` do?
90. What does `itertools.cycle()` do?
91. What does `itertools.repeat()` do?
92. Write a generator that batches items into groups of N.
93. What is `all(x > 0 for x in data)`?
94. What is `any(x > 100 for x in data)`?
95. Write a `moving_average(data, window)` generator.
96. How does Python know a function is a generator?
97. Can you convert a generator to a list? How?
98. Can you use a generator in a `for` loop?
99. What is the state of a generator after it raises `StopIteration`?
100. Write a generator `powers_of_two(n)`.

**Decorators (101–150)**

101. What is a decorator?
102. What does `@` syntax mean?
103. `@my_dec def f(): pass` is equivalent to...?
104. What is a higher-order function?
105. Write a decorator that prints "Hello" before a function.
106. Why is `*args, **kwargs` important in wrapper functions?
107. What is `functools.wraps`? Why is it important?
108. What does a decorator return?
109. Can a decorator be applied to a class method?
110. Can a decorator be applied to a class?
111. Write a `timer` decorator.
112. Write a `logger` decorator.
113. Write a `memoize` decorator.
114. What is `functools.lru_cache`?
115. What is `functools.cache`?
116. What is `@property` in Python?
117. What is `@staticmethod`?
118. What is `@classmethod`?
119. How do parametric decorators work?
120. Write a `repeat(n)` parametric decorator.
121. What happens when you stack two decorators?
122. What is the execution order of stacked decorators?
123. Write a `validate_positive` decorator.
124. What is a class-based decorator?
125. Write a `CountCalls` class decorator.
126. What is `functools.update_wrapper`?
127. What is `__wrapped__`?
128. Can you un-decorate a function?
129. What does `inspect.signature` do?
130. Write a `retry(n)` decorator.
131. Write a `timeout(seconds)` decorator (outline).
132. Write a `deprecated` decorator that warns users.
133. What is the difference between a decorator and a wrapper?
134. Are decorators applied at definition time or call time?
135. Write a `singleton` decorator.
136. Write a `once` decorator (function runs only first time).
137. What is `functools.partial`?
138. What is `functools.reduce`?
139. Can a lambda be used as a decorator?
140. Write a simple authentication decorator.
141. What is a decorator factory?
142. Write a `debug` decorator that prints arguments.
143. Write a `trace` decorator.
144. Can decorators have side effects?
145. What is `@dataclass`?
146. What is `@abstractmethod`?
147. What is `@overload` (from typing)?
148. Write a `before_after(pre, post)` decorator.
149. What is the purpose of `__call__` in class-based decorators?
150. Explain the "decorator" design pattern.

**Closures (151–175)**

151. What is a closure?
152. What are the three conditions for a closure?
153. What is a free variable?
154. What is `__closure__`?
155. What is a cell object?
156. Write a `make_adder(n)` closure.
157. Write a `make_multiplier(n)` closure.
158. What is `nonlocal`?
159. When do you use `nonlocal`?
160. What is the late binding bug in closures?
161. How do you fix the late binding bug?
162. Can closures share state?
163. Write a `make_counter()` closure.
164. What is `cell_contents`?
165. Are closures garbage collected?
166. Can you return multiple functions from one closure?
167. Write a `make_bank_account()` closure.
168. What is the difference between closures and classes?
169. Write a closure that maintains a running total.
170. Can closures modify enclosing variables?
171. What does `nonlocal` do to the enclosing scope?
172. What happens if you don't use `nonlocal` and try to assign?
173. Write a `make_power(exp)` closure.
174. What is `__code__.co_freevars`?
175. Explain closure memory behavior.

**Context Managers (176–200)**

176. What is a context manager?
177. What statement uses context managers?
178. What method is called when entering a `with` block?
179. What method is called when exiting a `with` block?
180. What are the three parameters of `__exit__`?
181. What does returning `True` from `__exit__` do?
182. Write a `Timer` context manager.
183. Write a `DatabaseConnection` context manager.
184. What is `contextlib.contextmanager`?
185. Write a `@contextmanager` timer.
186. What does `yield` do in a `@contextmanager`?
187. What is `contextlib.suppress`?
188. Write code to suppress `FileNotFoundError`.
189. What is `contextlib.redirect_stdout`?
190. What is `contextlib.ExitStack`?
191. Can you nest context managers?
192. Write a context manager using class syntax.
193. Write a context manager using `@contextmanager`.
194. What is `with open(...) as f:`?
195. Does `f.close()` get called if an exception occurs in `with` block?
196. What is the difference between `__enter__` and `__init__`?
197. Write a `ManagedList` context manager that tracks operations.
198. Can context managers suppress exceptions? How?
199. What is the `as` variable in `with X() as y:`?
200. Write a reentrant context manager.

**Functional Programming (201–250)**

201. What is a lambda function?
202. What is the syntax for a lambda?
203. Can a lambda have multiple statements?
204. Can a lambda have a conditional expression?
205. What is `map()`?
206. What does `map()` return?
207. Write `list(map(lambda x: x*2, [1,2,3]))`.
208. What is `filter()`?
209. What does `filter(None, lst)` do?
210. Write `list(filter(lambda x: x>0, [-1, 2, -3, 4]))`.
211. What is `reduce()`? Which module is it in?
212. Write `reduce` to compute the product of a list.
213. What is the `initial` argument in `reduce()`?
214. What is `any()`?
215. What is `all()`?
216. What is `zip()`?
217. What does `zip(*pairs)` do?
218. What is `zip_longest`?
219. What is `enumerate()`?
220. What is the `start` parameter in `enumerate()`?
221. What is `sorted(key=...)`?
222. What is `operator.itemgetter`?
223. What is `operator.attrgetter`?
224. What is `functools.partial`?
225. Write a `double = partial(multiply, 2)` example.
226. What is function composition?
227. Write a `compose(f, g)` function.
228. What is a pure function?
229. What is an impure function?
230. What is a first-class function?
231. What is a higher-order function?
232. What does `sorted(data, reverse=True)` do?
233. Write a sort by string length.
234. Write `min(words, key=len)`.
235. Write `max(students, key=lambda s: s['score'])`.
236. What is `map` vs list comprehension — which is more Pythonic?
237. What is `filter` vs list comprehension?
238. What is `reduce` vs a for loop?
239. Write `any(isinstance(x, str) for x in data)`.
240. Write `all(x >= 0 for x in data)`.
241. What is `sum(x for x in range(100))`?
242. What is `dict(zip(keys, values))`?
243. What is `list(enumerate(items, start=1))`?
244. Write code to transpose a matrix using `zip`.
245. What is `functools.total_ordering`?
246. What is `functools.singledispatch`?
247. What is `itertools.starmap`?
248. Write `list(starmap(lambda a,b: a+b, [(1,2),(3,4)]))`.
249. What is `itertools.product`?
250. What is `itertools.combinations`?

---

### Medium (Questions 251–550)

251. Implement a class `InfiniteCounter` that counts forever.
252. Write a generator pipeline with 4 stages.
253. Implement `memoize` without using `functools`.
254. Write a decorator that limits function call frequency (rate limiter).
255. Implement a `Trie` data structure as an iterable.
256. Write a generator that merges two sorted generators.
257. Implement `functools.lru_cache` from scratch.
258. Write a context manager that measures and logs memory usage.
259. Implement the `pipe` operator `|` for functions.
260. Write a generator for a breadth-first traversal of a tree.
261. Implement a `lazy_property` descriptor using `__get__`.
262. Write a decorator that converts exceptions to a default return value.
263. Implement `zip_with` — zip + apply function to each pair.
264. Write a generator that yields chunks of an iterable.
265. Implement `partition(pred, iterable)` — split into matching and non-matching.
266. Write a parametric decorator that limits function execution to N calls.
267. Implement a thread-safe `Counter` using a decorator.
268. Write a generator for Pascal's triangle rows.
269. Implement `groupby` (like `itertools.groupby`) from scratch.
270. Write a `retry` decorator with exponential backoff and jitter.
271. Implement a `Compose` class that chains functions using `>>`.
272. Write a generator that produces prime numbers (Sieve of Eratosthenes).
273. Implement a `TransformedIterator` that applies transformations lazily.
274. Write a `validate_range(min, max)` parametric decorator.
275. Implement a `Pipeline` class using method chaining.
276. Write a generator that implements binary search over a sorted file.
277. Implement a `memoize_ttl(seconds)` decorator with time expiry.
278. Write a `FlatMap` generator (map then flatten).
279. Implement a `ContextDecorator` that works as both decorator and context manager.
280. Write a generator that windows over an iterable.
281. Implement `curry(f)` — converts f(a,b,c) to f(a)(b)(c).
282. Write a generator for word frequency in a large file.
283. Implement a decorator that converts sync functions to accept callbacks.
284. Write a `sliding_window(data, n)` generator.
285. Implement `interleave(*iterables)` — alternate items from each.
286. Write a `zip_with_index_from(n)` function.
287. Implement a `lazy_range` class from scratch.
288. Write a decorator that adds JSON serialization to return values.
289. Implement a `BoundedIterator` that limits the number of values.
290. Write a generator that produces running statistics (mean, variance).

*(Questions 291–550 continue covering: advanced decorator composition, generator coroutines, functional programming patterns, closures with asyncio, context manager nesting, performance optimization problems, algorithm implementations using generators, and real-world data pipeline design problems.)*

---

### Advanced (Questions 551–700)

551. Implement a full coroutine-based event loop (simplified).
552. Design a plugin system using decorators and dynamic imports.
553. Implement `asynccontextmanager` functionality using sync generators.
554. Write a generator-based SAX XML parser.
555. Implement trampolining to eliminate recursion stack overflow.
556. Build a lazy evaluated expression tree using generators.
557. Implement a `StreamingJSON` parser for arbitrarily large JSON files.
558. Design a distributed rate limiter decorator (conceptual).
559. Implement `yield from` semantics manually without using it.
560. Write a generator-based state machine framework.
561. Implement a copy-on-write data structure using closures.
562. Design a decorator that provides transactional semantics.
563. Implement a lazy `DataFrame` using generators and descriptors.
564. Write a `PersistentGenerator` that can be paused and resumed.
565. Implement a `Memoize` class with LRU eviction from scratch.
566. Design a type-safe functional pipeline using Python generics.
567. Implement reactive programming primitives using generators.
568. Write a decorator that handles API pagination transparently.
569. Implement a generator-based tokenizer/lexer.
570. Design a context manager for distributed locks.
571. Implement tail-call optimization using trampolines.
572. Write a `WeakRefCache` decorator using `weakref`.
573. Implement a `Proxy` pattern using `__getattr__` and decorators.
574. Design a functional data validation framework.
575. Implement `itertools.groupby` with stable groups.
576. Write a `LazyDict` that computes values on access.
577. Implement method dispatch based on type using decorators.
578. Design a generator-based query engine for CSV files.
579. Implement a `freeze` decorator making function results immutable.
580. Write a context manager that profiles and optimizes hot code paths.
581–700. (Advanced algorithm problems, LLM engineering patterns, production system design, stream processing, functional architecture patterns, Python internals exploration.)

---

<a name="section-21"></a>

## 🎤 Section 21 — 350 Interview Questions with Answers

### Beginner Level (1–75)

**Q1: What is the difference between a list and a generator?**

A: A list stores all elements in memory simultaneously and supports random access. A generator computes elements lazily on demand and uses constant memory regardless of sequence size. Lists are reusable; generators are exhausted after one iteration. Use generators for large datasets where you only need one pass.

**Q2: What does `yield` do?**

A: `yield` pauses a generator function, saves its entire local state (local variables, execution point), and returns a value to the caller. The function resumes from exactly where it left off when `next()` is called again.

**Q3: What is a decorator?**

A: A decorator is a higher-order function that takes a function as input and returns a new function with additional behavior — without modifying the original function's source code. Decorators implement the Open/Closed Principle.

**Q4: What is `functools.wraps` and why is it used?**

A: `@functools.wraps(func)` copies the `__name__`, `__doc__`, `__module__`, `__qualname__`, and `__annotations__` from the wrapped function to the wrapper. Without it, introspection tools, debuggers, and documentation systems see the wrapper's name instead of the original function's name.

**Q5: What is a context manager?**

A: A context manager is an object that defines `__enter__()` (setup) and `__exit__()` (teardown) methods. Used with the `with` statement, it guarantees cleanup code runs even if an exception occurs — eliminating resource leaks.

**Q6: What is a closure?**

A: A closure is a nested function that captures and remembers variables from its enclosing scope even after the outer function has returned. It bundles the function with its environment.

**Q7: What is the difference between `map()` and a list comprehension?**

A: Both transform iterables. `map()` returns a lazy iterator; list comprehensions return a list immediately. List comprehensions are generally considered more Pythonic and readable. `map()` with a named function can be slightly faster. For complex transformations, list comprehensions are clearer.

**Q8: What does `filter(None, iterable)` do?**

A: It removes all falsy values: `0`, `""`, `None`, `[]`, `{}`, `False`. The first argument `None` means "use the identity function" — keep items that are truthy.

**Q9: What is `reduce()`?**

A: `functools.reduce(function, iterable, initial)` applies a binary function cumulatively to items, reducing the iterable to a single value. Example: `reduce(lambda a, b: a + b, [1,2,3,4])` → `10`.

**Q10: What is lazy evaluation?**

A: Lazy evaluation means computing values only when they are needed (demanded), rather than upfront. Generators implement lazy evaluation — values are computed one at a time as `next()` is called, saving memory.

---

### Intermediate Level (76–200)

**Q76: Explain the complete iteration protocol.**

A: When Python encounters `for x in obj:`, it calls `iter(obj)` which calls `obj.__iter__()` to get an iterator. Then it repeatedly calls `next(iterator)` which calls `iterator.__next__()`, getting each value, until `StopIteration` is raised. The `for` loop catches `StopIteration` and ends normally.

**Q77: How do generators implement the iterator protocol?**

A: Generator objects automatically implement both `__iter__()` (returns `self`) and `__next__()` (resumes execution until the next `yield`). The Python compiler transforms `yield` statements into a state machine.

**Q78: What is the difference between `yield` and `yield from`?**

A: `yield value` produces a single value. `yield from iterable` delegates to a sub-generator or iterable, yielding all its values in order, and also properly handles `send()`, `throw()`, and `close()` calls, passing them through to the sub-generator.

**Q79: How does Python implement closures internally?**

A: Python compiles variables that are referenced in nested functions as "cell objects" rather than regular local variables. The cell object is shared between the outer and inner function, keeping the variable alive even after the outer function returns. The inner function's `__closure__` tuple holds references to these cells.

**Q80: What happens when multiple decorators are stacked?**

A: They are applied bottom-up at decoration time. `@A @B def f()` means `f = A(B(f))`. At call time, `A`'s wrapper runs first, then calls `B`'s wrapper, which calls the original `f`. Returning: `f` returns to `B`'s wrapper, then to `A`'s wrapper.

**Q81: How do you make a context manager that suppresses specific exceptions?**

A: Return `True` from `__exit__()` for the exceptions you want to suppress. Return `False` (or `None`) to propagate them. Use `contextlib.suppress(ExceptionType)` for a clean one-liner.

**Q82: What is the GIL and how does it affect generators?**

A: The Global Interpreter Lock allows only one thread to execute Python bytecodes at a time. Generators are single-threaded and unaffected by the GIL. For concurrent generator usage across threads, use `threading.Lock` to protect shared state.

**Q83: What is the `nonlocal` keyword?**

A: `nonlocal name` tells Python that `name` refers to a variable in the nearest enclosing (non-global) scope. Without it, any assignment to `name` inside the inner function creates a new local variable, shadowing the outer one.

**Q84: What is `functools.lru_cache` and when should you use it?**

A: `@lru_cache(maxsize=128)` caches function results keyed by arguments using a Least Recently Used eviction policy. Use it for pure functions (no side effects) called repeatedly with the same arguments — like recursive algorithms, expensive computations, or database lookups.

**Q85: What is the difference between `iter()` and `__iter__()`?**

A: `iter(obj)` is the built-in function. It calls `obj.__iter__()` internally. Using `iter()` is preferred as it works with the two-argument form `iter(callable, sentinel)` which `obj.__iter__()` alone does not support.

---

### Advanced Level (201–300)

**Q201: Explain how Python's garbage collector handles circular references.**

A: Python's primary memory management is reference counting. When refcount reaches 0, memory is freed immediately. However, circular references keep refcounts non-zero even when objects are unreachable. Python's optional `gc` module uses a tri-color mark-sweep algorithm on 3 generations of objects to detect and collect cycles. `gc.collect()` manually triggers this.

**Q202: How does `yield from` handle exception propagation?**

A: When `throw(exception)` is called on an outer generator using `yield from`, Python forwards the exception into the inner generator (delegatee). If the inner generator handles it, execution continues. If not, the exception propagates up to the outer generator's `try/except` blocks. This makes `yield from` essential for proper coroutine chaining.

**Q203: What are Python descriptors and how do decorators like `@property` use them?**

A: A descriptor is any object defining `__get__`, `__set__`, or `__delete__`. `@property` creates a descriptor that intercepts attribute access on a class. When you access `obj.name`, Python finds the descriptor on the class and calls its `__get__(obj, type)`. `@staticmethod` and `@classmethod` are also implemented as descriptors.

**Q204: How would you implement a thread-safe singleton using a decorator?**

```python
import threading
import functools

def singleton(cls):
    instances = {}
    lock = threading.Lock()

    @functools.wraps(cls)
    def get_instance(*args, **kwargs):
        if cls not in instances:
            with lock:
                if cls not in instances:   # double-checked locking
                    instances[cls] = cls(*args, **kwargs)
        return instances[cls]

    return get_instance

@singleton
class Config:
    def __init__(self):
        self.data = {}
```

**Q205: Explain generator-based coroutines and how they relate to asyncio.**

A: Before `async/await` (Python 3.5+), coroutines were implemented as generators using `yield` to suspend and `send()` to resume. The event loop managed scheduling by calling `send()` on coroutines. Python 3.5 formalized this with `async def` and `await`, which is syntactic sugar over the generator protocol. `asyncio` still uses generators internally; `await` is equivalent to `yield from` for awaitables.

---

### Python Developer / Backend Developer (301–325)

**Q301: How do you write production-grade decorators?**

A: Always use `@functools.wraps`. Handle `*args, **kwargs`. Return the result of the wrapped function. Don't swallow exceptions unless explicitly designed to. Provide a way to access the original function via `wrapper.__wrapped__`. Test the decorator in isolation. Document its behavior.

**Q302: When would you use generators vs async generators in backend development?**

A: Synchronous generators are ideal for CPU-bound data processing pipelines where you don't need to wait for I/O. Async generators (`async def` with `yield`) are for async contexts where each value requires awaitable I/O (database queries, API calls). Use sync generators for file parsing, data transformation, batch processing. Use async generators for async API streaming, WebSocket message streams.

**Q303: How do you design a plugin system in Python?**

A: Use a decorator to register plugins: `@registry.register("plugin_name")`. Internally the registry is a dict. At startup, use `importlib.import_module` to dynamically import plugin modules. This pattern is used in pytest (fixtures, plugins), Flask (route decorators), and Click (command groups).

---

### AI / LLM Engineer (326–350)

**Q326: How would you use generators to stream LLM responses?**

A: LLM APIs (like Anthropic's) support streaming responses. Use a generator to yield tokens as they arrive:

```python
def stream_llm_response(client, prompt):
    with client.messages.stream(
        model="claude-sonnet-4-20250514",
        max_tokens=1024,
        messages=[{"role": "user", "content": prompt}]
    ) as stream:
        for text in stream.text_stream:
            yield text
```

**Q327: How do generators help with RAG (Retrieval Augmented Generation) pipelines?**

A: RAG pipelines process large corpora. Generators enable: lazy document loading (no full corpus in memory), streaming tokenization, lazy embedding computation, batch retrieval without full-index loading. A full pipeline: `load_docs → chunk_text → embed_chunks → index_embeddings → retrieve → generate` is most efficient as a generator pipeline.

**Q328: Explain how context managers ensure safety in ML training loops.**

A: Context managers manage GPU memory, ensure model.eval()/model.train() state, handle gradient accumulation, manage mixed precision (autocast), and ensure checkpointing happens even on crash. Example: `torch.no_grad()`, `torch.autocast("cuda")`, and `torch.cuda.amp.GradScaler` all use context managers.

---

<a name="section-22"></a>

## 📋 Section 22 — Assignments + Solutions

### Assignment 1: Iterators

**Problem:** Implement a `Matrix` class that:
- Stores a 2D list
- Supports iteration row by row
- Supports iteration element by element
- Has a `transpose()` method that returns a new iterable Matrix

```python
class Matrix:
    def __init__(self, data: list[list]):
        if not data or not data[0]:
            raise ValueError("Matrix cannot be empty")
        rows = len(data)
        cols = len(data[0])
        if not all(len(row) == cols for row in data):
            raise ValueError("All rows must have equal length")
        self._data = [row[:] for row in data]
        self._rows = rows
        self._cols = cols

    def __iter__(self):
        """Iterate row by row."""
        return iter(self._data)

    def __len__(self):
        return self._rows

    def __getitem__(self, index):
        return self._data[index]

    def elements(self):
        """Generator yielding all elements."""
        for row in self._data:
            yield from row

    def transpose(self):
        """Return new Matrix with rows and columns swapped."""
        transposed = [[self._data[r][c] for r in range(self._rows)]
                      for c in range(self._cols)]
        return Matrix(transposed)

    def __repr__(self):
        rows_str = "\n  ".join(str(row) for row in self._data)
        return f"Matrix([\n  {rows_str}\n])"


# Test
m = Matrix([[1, 2, 3], [4, 5, 6], [7, 8, 9]])

print("Row iteration:")
for row in m:
    print(row)

print("\nElement iteration:")
print(list(m.elements()))

print("\nTranspose:")
print(m.transpose())
```

---

### Assignment 2: Generators

**Problem:** Implement a complete CSV processing pipeline using generators that:
1. Reads a CSV file lazily
2. Parses each row into a dict
3. Filters by a predicate
4. Transforms each record
5. Batches into groups of N
6. Produces aggregate statistics

```python
import csv
import io
from typing import Generator, Callable, Iterator, Any


# Stage 1: Lazy reader
def read_csv_lazy(filepath: str) -> Generator[list, None, None]:
    with open(filepath, newline='') as f:
        reader = csv.reader(f)
        header = next(reader)
        yield header
        yield from reader


# Stage 2: Parse to dicts
def to_dicts(rows: Iterator) -> Generator[dict, None, None]:
    rows = iter(rows)
    header = next(rows)
    for row in rows:
        yield dict(zip(header, row))


# Stage 3: Filter
def filter_records(records: Iterator, predicate: Callable[[dict], bool]) -> Generator:
    return (r for r in records if predicate(r))


# Stage 4: Transform
def transform_records(records: Iterator, transform: Callable[[dict], dict]) -> Generator:
    return (transform(r) for r in records)


# Stage 5: Batch
def batch_records(records: Iterator, size: int) -> Generator[list, None, None]:
    batch = []
    for record in records:
        batch.append(record)
        if len(batch) == size:
            yield batch
            batch = []
    if batch:
        yield batch


# Stage 6: Aggregate stats from batches
def compute_stats(batches: Iterator, numeric_field: str) -> dict:
    values = []
    count = 0
    for batch in batches:
        for record in batch:
            try:
                values.append(float(record[numeric_field]))
                count += 1
            except (ValueError, KeyError):
                pass
    if not values:
        return {"count": 0}
    return {
        "count": count,
        "sum": sum(values),
        "mean": sum(values) / len(values),
        "min": min(values),
        "max": max(values),
    }


# Demo with in-memory CSV
SAMPLE_CSV = """name,age,score,city
Alice,25,92.5,New York
Bob,30,78.0,London
Carol,22,95.0,Paris
Dave,35,65.5,Tokyo
Eve,28,88.0,New York
Frank,32,71.0,London
"""

# Write to temp file
import tempfile
import os

with tempfile.NamedTemporaryFile(mode='w', suffix='.csv', delete=False) as f:
    f.write(SAMPLE_CSV)
    tmpfile = f.name

try:
    # Build pipeline
    rows = read_csv_lazy(tmpfile)
    records = to_dicts(rows)
    high_scorers = filter_records(records, lambda r: float(r['score']) >= 80)
    enriched = transform_records(high_scorers,
        lambda r: {**r, 'grade': 'A' if float(r['score']) >= 90 else 'B'})
    batches = batch_records(enriched, size=2)

    print("High scorers (batched):")
    all_batches = list(batches)
    for i, batch in enumerate(all_batches):
        print(f"Batch {i+1}: {[r['name'] for r in batch]}")

    # Re-run for stats (generators are single-use!)
    rows2 = read_csv_lazy(tmpfile)
    records2 = to_dicts(rows2)
    high_scorers2 = filter_records(records2, lambda r: float(r['score']) >= 80)
    enriched2 = transform_records(high_scorers2, lambda r: r)
    batches2 = batch_records(enriched2, size=100)
    stats = compute_stats(batches2, 'score')
    print(f"\nScore stats: {stats}")

finally:
    os.unlink(tmpfile)
```

---

### Assignment 3: Decorators

**Problem:** Build a `@api_endpoint` decorator system for a simple web framework that:
- Handles routing
- Validates input
- Logs requests
- Measures response time
- Handles errors

```python
import functools
import time
import json
import logging
from typing import Callable, Type, Dict, Any

logger = logging.getLogger("api")
logging.basicConfig(level=logging.INFO)

# Registry of endpoints
_routes: Dict[str, Callable] = {}


def api_endpoint(
    path: str,
    methods: list = None,
    validate: dict = None,
    cache_seconds: int = 0
):
    """Multi-purpose API endpoint decorator."""
    methods = methods or ["GET"]
    _cache: Dict[str, tuple] = {}

    def decorator(func: Callable) -> Callable:
        _routes[path] = func   # register route

        @functools.wraps(func)
        def wrapper(request: dict) -> dict:
            # Validate HTTP method
            method = request.get("method", "GET").upper()
            if method not in methods:
                return {"status": 405, "error": f"Method {method} not allowed"}

            # Check cache
            cache_key = f"{path}:{json.dumps(request.get('params', {}), sort_keys=True)}"
            if cache_seconds > 0 and cache_key in _cache:
                cached_at, cached_response = _cache[cache_key]
                if time.time() - cached_at < cache_seconds:
                    logger.info(f"Cache HIT: {path}")
                    return {**cached_response, "cached": True}

            # Validate inputs
            if validate:
                params = request.get("params", {})
                for field, expected_type in validate.items():
                    if field not in params:
                        return {"status": 400, "error": f"Missing field: {field}"}
                    if not isinstance(params[field], expected_type):
                        return {"status": 400, "error": f"Invalid type for {field}"}

            # Execute + time
            start = time.perf_counter()
            try:
                result = func(request)
                response = {"status": 200, "data": result}
            except ValueError as e:
                response = {"status": 400, "error": str(e)}
            except Exception as e:
                logger.error(f"Error in {func.__name__}: {e}")
                response = {"status": 500, "error": "Internal server error"}
            elapsed = (time.perf_counter() - start) * 1000

            logger.info(f"{method} {path} → {response['status']} ({elapsed:.2f}ms)")

            # Cache response
            if cache_seconds > 0 and response["status"] == 200:
                _cache[cache_key] = (time.time(), response)

            return response

        return wrapper
    return decorator


# Usage
@api_endpoint("/users", methods=["GET"], cache_seconds=30)
def get_users(request):
    return [{"id": 1, "name": "Alice"}, {"id": 2, "name": "Bob"}]


@api_endpoint("/user", methods=["GET"], validate={"id": int})
def get_user(request):
    uid = request["params"]["id"]
    users = {1: "Alice", 2: "Bob"}
    if uid not in users:
        raise ValueError(f"User {uid} not found")
    return {"id": uid, "name": users[uid]}


@api_endpoint("/user", methods=["POST"], validate={"name": str, "email": str})
def create_user(request):
    name = request["params"]["name"]
    email = request["params"]["email"]
    return {"id": 3, "name": name, "email": email}


# Test
print(get_users({"method": "GET", "params": {}}))
print(get_user({"method": "GET", "params": {"id": 1}}))
print(get_user({"method": "GET", "params": {"id": 99}}))
print(create_user({"method": "POST", "params": {"name": "Carol", "email": "carol@test.com"}}))
```

---

### Assignment 4: Context Managers

**Problem:** Build a `ResourcePool` context manager that manages a pool of reusable resources.

```python
import threading
import time
from contextlib import contextmanager
from typing import Any, Callable, Optional


class ResourcePool:
    """Thread-safe pool of reusable resources."""

    def __init__(
        self,
        factory: Callable[[], Any],
        max_size: int = 5,
        timeout: float = 5.0
    ):
        self._factory = factory
        self._max_size = max_size
        self._timeout = timeout
        self._pool: list = []
        self._in_use: set = set()
        self._lock = threading.Lock()
        self._available = threading.Semaphore(max_size)
        self._created = 0

    def _create_resource(self):
        resource = self._factory()
        self._created += 1
        return resource

    @contextmanager
    def acquire(self):
        """Acquire a resource from the pool."""
        acquired = self._available.acquire(timeout=self._timeout)
        if not acquired:
            raise TimeoutError(f"Could not acquire resource within {self._timeout}s")

        with self._lock:
            if self._pool:
                resource = self._pool.pop()
            else:
                resource = self._create_resource()
            self._in_use.add(id(resource))

        try:
            yield resource
        finally:
            with self._lock:
                self._in_use.discard(id(resource))
                self._pool.append(resource)
            self._available.release()

    @property
    def available_count(self):
        return len(self._pool)

    @property
    def in_use_count(self):
        return len(self._in_use)

    @property
    def total_created(self):
        return self._created


# Demo: Connection pool
class FakeDBConnection:
    _id_counter = 0

    def __init__(self):
        FakeDBConnection._id_counter += 1
        self.id = FakeDBConnection._id_counter
        print(f"  Created connection #{self.id}")

    def query(self, sql):
        time.sleep(0.01)   # simulate query time
        return f"Result of [{sql}] from connection #{self.id}"


pool = ResourcePool(factory=FakeDBConnection, max_size=3)

def run_query(sql):
    with pool.acquire() as conn:
        result = conn.query(sql)
        print(f"  {result}")

# Sequential queries
for i in range(5):
    run_query(f"SELECT * FROM table_{i}")

print(f"\nPool stats: available={pool.available_count}, total_created={pool.total_created}")

# Concurrent queries using threads
threads = [threading.Thread(target=run_query, args=(f"SELECT {i}",)) for i in range(10)]
for t in threads:
    t.start()
for t in threads:
    t.join()
```

---

### Assignment 5: Functional Programming

**Problem:** Build a functional data analysis library using map, filter, reduce, and generators.

```python
from functools import reduce
from typing import Callable, Iterable, TypeVar, Optional
import statistics

T = TypeVar('T')


class FunctionalPipeline:
    """Lazy functional data pipeline with method chaining."""

    def __init__(self, data: Iterable):
        self._data = data

    def map(self, func: Callable) -> 'FunctionalPipeline':
        return FunctionalPipeline(func(x) for x in self._data)

    def filter(self, predicate: Callable) -> 'FunctionalPipeline':
        return FunctionalPipeline(x for x in self._data if predicate(x))

    def flat_map(self, func: Callable) -> 'FunctionalPipeline':
        return FunctionalPipeline(y for x in self._data for y in func(x))

    def take(self, n: int) -> 'FunctionalPipeline':
        def _take():
            for i, x in enumerate(self._data):
                if i >= n:
                    break
                yield x
        return FunctionalPipeline(_take())

    def drop(self, n: int) -> 'FunctionalPipeline':
        return FunctionalPipeline(x for i, x in enumerate(self._data) if i >= n)

    def distinct(self) -> 'FunctionalPipeline':
        def _distinct():
            seen = set()
            for x in self._data:
                if x not in seen:
                    seen.add(x)
                    yield x
        return FunctionalPipeline(_distinct())

    def sorted_by(self, key: Callable = None, reverse: bool = False) -> 'FunctionalPipeline':
        return FunctionalPipeline(iter(sorted(self._data, key=key, reverse=reverse)))

    def group_by(self, key: Callable) -> dict:
        result = {}
        for item in self._data:
            k = key(item)
            result.setdefault(k, []).append(item)
        return result

    def reduce(self, func: Callable, initial=None):
        if initial is not None:
            return reduce(func, self._data, initial)
        return reduce(func, self._data)

    def to_list(self) -> list:
        return list(self._data)

    def to_set(self) -> set:
        return set(self._data)

    def to_dict(self, key_func: Callable, value_func: Callable = None) -> dict:
        if value_func:
            return {key_func(x): value_func(x) for x in self._data}
        return {key_func(x): x for x in self._data}

    def count(self) -> int:
        return sum(1 for _ in self._data)

    def sum(self) -> float:
        return sum(self._data)

    def stats(self) -> dict:
        data = list(self._data)
        if not data:
            return {}
        return {
            "count": len(data),
            "sum": sum(data),
            "mean": statistics.mean(data),
            "median": statistics.median(data),
            "stdev": statistics.stdev(data) if len(data) > 1 else 0,
            "min": min(data),
            "max": max(data),
        }

    def __iter__(self):
        return iter(self._data)


# Helper constructor
def fp(data: Iterable) -> FunctionalPipeline:
    return FunctionalPipeline(data)


# Demo
data = [
    {"name": "Alice", "dept": "Engineering", "salary": 95000},
    {"name": "Bob",   "dept": "Marketing",   "salary": 72000},
    {"name": "Carol", "dept": "Engineering", "salary": 105000},
    {"name": "Dave",  "dept": "HR",          "salary": 68000},
    {"name": "Eve",   "dept": "Engineering", "salary": 88000},
    {"name": "Frank", "dept": "Marketing",   "salary": 79000},
]

# Highest paid engineers
top_engineers = (
    fp(data)
    .filter(lambda e: e["dept"] == "Engineering")
    .sorted_by(key=lambda e: e["salary"], reverse=True)
    .take(2)
    .map(lambda e: {"name": e["name"], "salary": e["salary"]})
    .to_list()
)
print("Top engineers:", top_engineers)

# Average salary by department
by_dept = fp(data).group_by(lambda e: e["dept"])
for dept, employees in by_dept.items():
    avg = fp(employees).map(lambda e: e["salary"]).stats()
    print(f"{dept}: avg_salary=${avg['mean']:,.0f}")

# All unique salaries above 80k
high_salaries = (
    fp(data)
    .map(lambda e: e["salary"])
    .filter(lambda s: s > 80000)
    .distinct()
    .sorted_by()
    .to_list()
)
print("High salaries:", high_salaries)
```

---

<a name="section-23"></a>

## 🏢 Section 23 — Enterprise Challenge Projects

### Enterprise Project 1: Data Processing Framework

```
Architecture:
  ┌──────────────────────────────────────────────┐
  │            DATA PROCESSING FRAMEWORK          │
  │                                               │
  │  Sources ──► Transformers ──► Sinks           │
  │    │              │            │              │
  │  CSV            Filter        CSV             │
  │  JSON          Transform      DB              │
  │  API            Batch         API             │
  │  S3            Aggregate      File            │
  │                               S3              │
  └──────────────────────────────────────────────┘

Folder Structure:
data-processing-framework/
├── src/dpf/
│   ├── sources/      (csv, json, api, database, s3)
│   ├── transforms/   (filter, map, batch, join, aggregate)
│   ├── sinks/        (csv, database, api, file, s3)
│   ├── pipeline/     (builder, executor, monitor)
│   ├── config/       (yaml-based configuration)
│   └── plugins/      (extensible transform registry)
├── tests/
├── benchmarks/
└── README.md

Scaling Plan:
  MVP:          Process 1M records in < 60s, single machine
  Professional: Parallel processing, 10M records/min
  Enterprise:   Distributed (Dask/Ray), 100M+ records/min
```

### Enterprise Project 2: Plugin Architecture Platform

```python
"""
Plugin system using decorators and dynamic loading.
"""
import importlib
from typing import Callable, Dict, Any


class PluginRegistry:
    """Central registry for all plugins."""

    def __init__(self):
        self._plugins: Dict[str, Dict[str, Callable]] = {}

    def register(self, category: str, name: str = None):
        """Decorator to register a function as a plugin."""
        def decorator(func: Callable) -> Callable:
            plugin_name = name or func.__name__
            self._plugins.setdefault(category, {})[plugin_name] = func
            return func
        return decorator

    def get(self, category: str, name: str) -> Callable:
        try:
            return self._plugins[category][name]
        except KeyError:
            raise KeyError(f"Plugin '{name}' not found in category '{category}'")

    def list(self, category: str) -> list:
        return list(self._plugins.get(category, {}).keys())


# Global registry
registry = PluginRegistry()


# Register plugins
@registry.register("transformer", "uppercase")
def uppercase_transform(data: list) -> list:
    return [str(x).upper() for x in data]


@registry.register("transformer", "square")
def square_transform(data: list) -> list:
    return [x**2 for x in data]


@registry.register("validator", "non_empty")
def non_empty_validator(data) -> bool:
    return bool(data)


# Use plugins dynamically
transform_name = "uppercase"
transformer = registry.get("transformer", transform_name)
print(transformer(["hello", "world"]))   # ['HELLO', 'WORLD']

print("Available transformers:", registry.list("transformer"))
```

### Enterprise Projects 3–10 Summary

| # | Project | Key Design Patterns | Scale Target |
|---|---------|---------------------|--------------|
| 3 | AI Dataset Pipeline Engine | Generator pipelines, lazy loading | 10M+ records |
| 4 | Workflow Automation System | State machines, decorators, events | 10K+ workflows/day |
| 5 | Performance Benchmark Suite | cProfile, statistical analysis | Any Python codebase |
| 6 | Enterprise Logging Framework | Decorators, context managers, handlers | 1M+ log events/day |
| 7 | Research Processing Engine | Functional pipelines, generators | 100GB+ datasets |
| 8 | Developer Productivity Platform | CLI, decorators, automation | Dev team of 50+ |
| 9 | Data Streaming Framework | Infinite generators, backpressure | Real-time streams |
| 10 | Automation Infrastructure Toolkit | Orchestration, scheduling, monitoring | Production systems |

---

<a name="section-24"></a>

## 📖 Section 24 — Day13 Revision

### One-Page Cheat Sheet

```
ITERATORS:              iter(obj) → iterator; next(it) → value or StopIteration
                        __iter__() + __next__() = iterator protocol

GENERATORS:             def with yield → generator function
                        gen_expr = (x for x in ...) → generator expression
                        yield pauses; next() resumes; StopIteration = done
                        yield from iterable → delegation
                        send(value) → two-way communication

DECORATORS:             @dec def f(): pass  ≡  f = dec(f)
                        Always use @functools.wraps(func) inside wrapper
                        *args, **kwargs in wrapper to pass all arguments
                        Parametric: dec(args)(func)(call_args)

CLOSURES:               Inner function + free variables + outer function returns inner
                        nonlocal → modify enclosing variable
                        Late binding bug: lambda i=i: i  (capture, don't reference)

CONTEXT MANAGERS:       __enter__() → setup; __exit__(exc_type, val, tb) → teardown
                        @contextmanager + yield → generator-based CM
                        Return True in __exit__ to suppress exceptions

FUNCTIONAL:             lambda args: expr  (single expression only)
                        map(f, it) → lazy iterator
                        filter(pred, it) → lazy iterator
                        reduce(f, it, initial) → single value (functools)
                        any()/all() → short-circuit evaluation
                        zip(), enumerate(), sorted(key=...), partial()

PERFORMANCE:            Generators: O(1) memory for any sequence size
                        __slots__: 3-4x memory reduction for many instances
                        lru_cache: cache expensive pure function calls
                        join(): O(n) string building vs O(n²) concatenation
                        deque: O(1) left operations vs O(n) for list

COMMON MISTAKES:
  ✗ Reusing exhausted generator     → create fresh generator each time
  ✗ Missing @functools.wraps        → always add it
  ✗ Late binding in closure lambdas → use default arg lambda x, i=i: x+i
  ✗ Suppressing all exceptions      → only suppress specific types
  ✗ Missing nonlocal in closure     → add nonlocal when modifying outer var
```

### Generator Cheat Sheet

```python
# Generator function
def gen():
    yield value

# Generator expression
gen = (expr for x in iterable if condition)

# Delegation
yield from other_iterable

# Two-way
value_sent = yield value_produced

# Pipeline
result = sink(stage3(stage2(stage1(source))))

# Infinite → take N
from itertools import islice
first10 = list(islice(infinite_gen(), 10))

# Convert to list
data = list(gen())

# Check if generator
import inspect
inspect.isgeneratorfunction(gen)   # True for function
inspect.isgenerator(gen())         # True for object
```

### Decorator Cheat Sheet

```python
# Basic
def dec(func):
    @functools.wraps(func)
    def wrapper(*args, **kwargs):
        # before
        result = func(*args, **kwargs)
        # after
        return result
    return wrapper

# Parametric
def dec_factory(param):
    def dec(func):
        @functools.wraps(func)
        def wrapper(*args, **kwargs):
            return func(*args, **kwargs)
        return wrapper
    return dec

# Class-based
class Dec:
    def __init__(self, func):
        functools.update_wrapper(self, func)
        self.func = func
    def __call__(self, *args, **kwargs):
        return self.func(*args, **kwargs)

# Stacking order: bottom decorator applied first
@A    # applied second (outermost)
@B    # applied first (innermost)
def f(): pass
# f = A(B(f))
```

### Context Manager Cheat Sheet

```python
# Class-based
class CM:
    def __enter__(self):
        return self           # what `as` gets
    def __exit__(self, exc_type, exc_val, exc_tb):
        return False          # True = suppress exception

# Generator-based
@contextmanager
def cm():
    # setup
    try:
        yield resource        # what `as` gets
    except Exception:
        # handle exception
        raise
    finally:
        # cleanup (always runs)
        pass

# Common patterns
with suppress(TypeError):     # ignore TypeError
    risky_code()

with redirect_stdout(buf):    # capture print output
    print("captured")

with ExitStack() as stack:    # dynamic number of CMs
    for f in files:
        stack.enter_context(open(f))
```

---

<a name="section-25"></a>

## 🔭 Section 25 — Preparation for Day14

### Day14 Preview: Testing + Production Python

```
DAY14 ROADMAP
─────────────────────────────────────────────────────────
  Testing Fundamentals
    ├── Why testing matters in production
    ├── Test types: unit, integration, e2e, performance
    └── Testing pyramid

  pytest — Professional Testing
    ├── Writing test functions
    ├── Fixtures (@pytest.fixture)
    ├── Parametrize (@pytest.mark.parametrize)
    ├── Markers (@pytest.mark.slow, skip, xfail)
    ├── Conftest.py — shared fixtures
    ├── Plugins (pytest-cov, pytest-mock, pytest-asyncio)
    └── Test discovery and configuration

  unittest — Standard Library
    ├── TestCase class
    ├── setUp / tearDown
    ├── assertXxx methods
    └── TestSuite

  Mocking
    ├── unittest.mock.Mock
    ├── MagicMock
    ├── @patch decorator
    ├── patch.object
    ├── side_effect
    └── spec=

  Code Coverage
    ├── pytest-cov
    ├── coverage.py
    ├── Branch coverage
    └── Coverage reports (HTML, XML)

  CI/CD Basics
    ├── GitHub Actions
    ├── Writing .yml workflows
    ├── Running tests on every push/PR
    ├── Linting with Black + isort + flake8
    └── Publishing to PyPI

  Production Python
    ├── Environment management (venv, conda, poetry)
    ├── Secrets management
    ├── Configuration management
    ├── Health checks and monitoring
    ├── Structured logging in production
    └── Docker basics for Python apps
```

### Day14 Preparation Exercises

```python
# Exercise 1: Write tests for your Day13 decorators
# Exercise 2: Mock an HTTP API call using unittest.mock
# Exercise 3: Achieve 90%+ coverage on a generator module
# Exercise 4: Write a GitHub Actions workflow that runs pytest
# Exercise 5: Refactor a decorator to be easily testable
```

### Day13 → Day14 Connection

The advanced Python patterns from Day13 (decorators, generators, context managers) form the backbone of testable Python code:

- **Decorators** are tested by verifying the wrapper behavior independently of the wrapped function
- **Generators** are tested by consuming them with `list()` or `next()` and asserting outputs
- **Context managers** are tested by verifying `__enter__`/`__exit__` behavior and exception handling
- **Closures** are tested by calling returned functions and verifying captured state

---

## 🎯 Quick Reference: Day13 in One Diagram

```
                      ADVANCED PYTHON MASTERY (Day13)
                      ═══════════════════════════════

   PYTHON INTERNALS          ITERATORS              GENERATORS
   ─────────────────         ──────────             ──────────
   Bytecode + PVM             __iter__()             yield
   Reference Counting         __next__()             yield from
   Garbage Collector          StopIteration          send()
   GIL                        iter() + next()        lazy evaluation
   Object Model               Custom iterators       pipelines

          DECORATORS          CLOSURES          CONTEXT MANAGERS
          ──────────          ────────          ────────────────
          @syntax             nested funcs      __enter__/__exit__
          functools.wraps     free variables    with statement
          parametric decs     nonlocal          @contextmanager
          stacking            late binding      ExitStack
          class-based         state closure     suppress/redirect

                     FUNCTIONAL PROGRAMMING
                     ───────────────────────
                     lambda · map · filter · reduce
                     any · all · zip · enumerate
                     sorted · partial · compose
                     comprehensions · expressions

                        PERFORMANCE
                        ───────────
                        __slots__ · generators vs lists
                        lru_cache · deque · profiling
                        timeit · cProfile · memory

═══════════════════════════════════════════════════════════════
  Ready for: Backend Dev | Data Engineering | AI/LLM Engineering
             Open Source | Enterprise Python | Production Systems
═══════════════════════════════════════════════════════════════
```

---

*Day13 Complete — Advanced Python Mastery Achieved*  
*Next: Day14 — Testing, CI/CD, and Production Python*

---

> **Author's Note:** This document is designed as a living reference. As you build projects, return to the relevant sections. The best way to master Day13 concepts is to use them daily: add a decorator to your next function, use a generator for your next loop over large data, wrap your next resource usage in a context manager. Python's advanced features become natural through consistent practice.

**Happy Coding! 🐍**