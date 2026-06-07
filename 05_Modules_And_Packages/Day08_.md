# 🐍 Python Mastery Series — Day 08
# Modules · Packages · pip · Virtual Environments · Professional Project Architecture

> **"Code that cannot be reused is code written twice."**
> — Every Senior Developer Ever

---

## 📋 Table of Contents

| # | Section | Topics |
|---|---------|--------|
| 1 | [Complete Revision (Day01–Day07)](#section-1) | Cheat Sheets, Mind Maps |
| 2 | [Modular Programming](#section-2) | Why Modules, Real World Systems |
| 3 | [Modules Masterclass](#section-3) | Creating, Importing, Lifecycle |
| 4 | [Import System Deep Dive](#section-4) | All Import Forms, sys.path, Caching |
| 5 | [Built-in Modules Masterclass](#section-5) | math, os, sys, datetime, json + more |
| 6 | [Packages Masterclass](#section-6) | __init__.py, Namespace, Structure |
| 7 | [pip Masterclass](#section-7) | PyPI, Install, Upgrade, Versions |
| 8 | [Virtual Environments Masterclass](#section-8) | venv, Activation, Best Practices |
| 9 | [Requirements Files](#section-9) | requirements.txt, Freeze, Install |
| 10 | [Project Structure Masterclass](#section-10) | Small → Enterprise → AI Projects |
| 11 | [Python Execution Model](#section-11) | Bytecode, .pyc, __pycache__ |
| 12 | [Environment Variables](#section-12) | PATH, PYTHONPATH, Secrets |
| 13 | [Professional Dev Workflow](#section-13) | End-to-End Industry Workflow |
| 14 | [Open Source Workflow](#section-14) | Fork, Clone, PR, Contribution |
| 15 | [Debugging Modules](#section-15) | Import Errors, Circular Imports |
| 16 | [Best Practices](#section-16) | PEP8, Naming, Clean Architecture |
| 17 | [Mini Projects (10)](#section-17) | Full Code, Output, Improvements |
| 18 | [20 Portfolio Projects](#section-18) | GitHub-Ready, Resume Value |
| 19 | [Project Layout Masterclass](#section-19) | Folder Structures, Every Dir Explained |
| 20 | [GitHub Profile Booster Projects (10)](#section-20) | Recruiter Appeal |
| 21 | [Project Solution Framework](#section-21) | Requirements → Deployment |
| 22 | [450 Practice Questions](#section-22) | Easy / Medium / Advanced |
| 23 | [200 Interview Questions](#section-23) | With Detailed Answers |
| 24 | [Assignments + Solutions](#section-24) | 5 Complete Assignments |
| 25 | [Enterprise Challenge Projects](#section-25) | 10 Large-Scale Projects |
| 26 | [Day08 Revision](#section-26) | Cheat Sheets, Mind Maps, One-Pagers |
| 27 | [Preview: Day09 — Exception Handling](#section-27) | What's Coming Next |

---

<a name="section-1"></a>
# 📚 SECTION 1 — Complete Revision: Day01–Day07

## 1.1 — Day-by-Day Summary

```
Day01 → Variables, Data Types, Operators, Type Casting
Day02 → Strings, String Methods, Input Handling, Memory Model
Day03 → if / elif / else, Nested Conditions, Ternary Operator
Day04 → for loops, while loops, break, continue, Pattern Printing
Day05 → Functions, *args, **kwargs, Scope (LEGB), Recursion, Lambda
Day06 → Lists, Slicing, List Comprehension, 2D Lists, Built-in Methods
Day07 → Tuples, Sets, Dictionaries, Hashing, Frozensets, defaultdict
```

---

## 1.2 — Python Data Types Cheat Sheet

| Type | Syntax | Mutable | Ordered | Duplicates | Use Case |
|------|--------|---------|---------|------------|----------|
| `int` | `x = 5` | ✅ | — | — | Counting, IDs |
| `float` | `x = 3.14` | ✅ | — | — | Prices, Scores |
| `str` | `x = "hi"` | ❌ | ✅ | ✅ | Text, Names |
| `bool` | `x = True` | ✅ | — | — | Flags, Switches |
| `list` | `[1, 2, 3]` | ✅ | ✅ | ✅ | Collections |
| `tuple` | `(1, 2, 3)` | ❌ | ✅ | ✅ | Fixed Records |
| `set` | `{1, 2, 3}` | ✅ | ❌ | ❌ | Unique Items |
| `dict` | `{"k": "v"}` | ✅ | ✅ (3.7+) | Keys: ❌ | Key-Value Store |
| `NoneType` | `None` | — | — | — | Absence of Value |

---

## 1.3 — Python Collections Cheat Sheet

```python
# LIST
fruits = ["apple", "banana", "cherry"]
fruits.append("mango")          # Add to end
fruits.insert(1, "grape")       # Insert at index
fruits.remove("banana")         # Remove by value
fruits.pop()                    # Remove last
fruits.sort()                   # Sort ascending
fruits.reverse()                # Reverse in-place
fruits[0]                       # Indexing
fruits[1:3]                     # Slicing
[x.upper() for x in fruits]     # List comprehension

# TUPLE
coords = (10, 20, 30)
x, y, z = coords                # Unpacking
coords[0]                       # Indexing (no modification)
len(coords)                     # Length
coords.count(10)                # Count occurrences

# SET
primes = {2, 3, 5, 7}
primes.add(11)                  # Add element
primes.discard(2)               # Remove safely
primes.union({13, 17})          # Union
primes.intersection({3, 5, 9}) # Intersection
primes.difference({3, 5})      # Difference

# DICTIONARY
student = {"name": "Alice", "age": 20, "grade": "A"}
student["name"]                 # Access by key
student.get("score", 0)        # Safe access with default
student.keys()                  # All keys
student.values()                # All values
student.items()                 # Key-value pairs
student.update({"age": 21})    # Update
del student["grade"]            # Delete key
{k: v for k, v in student.items() if v != "A"}  # Dict comprehension
```

---

## 1.4 — Functions Cheat Sheet

```python
# Basic Function
def greet(name):
    return f"Hello, {name}!"

# Default Arguments
def power(base, exp=2):
    return base ** exp

# *args (Variable Positional)
def add_all(*nums):
    return sum(nums)

# **kwargs (Variable Keyword)
def display(**info):
    for k, v in info.items():
        print(f"{k}: {v}")

# Lambda
square = lambda x: x ** 2

# Recursive Function
def factorial(n):
    return 1 if n <= 1 else n * factorial(n - 1)

# LEGB Rule
x = "global"
def outer():
    x = "enclosing"
    def inner():
        x = "local"
        print(x)    # local
    inner()
    print(x)        # enclosing
outer()
print(x)            # global
```

---

## 1.5 — Hashing Cheat Sheet

```python
# Hash Function
hash("hello")           # Returns integer
hash(42)                # 42
hash((1, 2, 3))         # Tuple is hashable
# hash([1,2,3])         # ERROR: list is unhashable

# Dictionary uses hashing internally
d = {}
d["key"] = "value"
# Python computes hash("key") → bucket → stores value

# Set uses hashing for O(1) membership test
s = {1, 2, 3}
3 in s          # O(1) — instant

# defaultdict
from collections import defaultdict
word_count = defaultdict(int)
for word in ["apple", "banana", "apple"]:
    word_count[word] += 1
# {"apple": 2, "banana": 1}

# Counter
from collections import Counter
Counter("hello world")
# Counter({'l': 3, 'o': 2, 'h': 1, 'e': 1, ' ': 1, 'w': 1, 'r': 1, 'd': 1})
```

---

## 1.6 — Data Structures Mind Map

```
                    PYTHON DATA STRUCTURES
                           │
           ┌───────────────┼───────────────┐
           │               │               │
        SEQUENCE        MAPPING          SET TYPE
           │               │               │
    ┌──────┴──────┐    DICTIONARY      ┌───┴───┐
    │             │    {key: val}      SET  FROZENSET
   LIST         TUPLE                {1,2}  frozenset()
  [1,2,3]      (1,2,3)
  Mutable      Immutable
  Ordered      Ordered
  Duplicates   Duplicates
     │
     ├── list comprehension
     ├── sort(), reverse()
     ├── append(), extend()
     └── slicing [start:stop:step]
```

---

<a name="section-2"></a>
# 🧩 SECTION 2 — Introduction to Modular Programming

## 2.1 — What is Modular Programming?

**Modular Programming** is a software design technique that emphasizes separating the functionality of a program into independent, interchangeable **modules** — each containing everything necessary to execute only one aspect of the desired functionality.

Think of it like building a city:
- You don't build a city in one giant block of concrete
- You have zones: residential, commercial, industrial
- Each zone is independent but connected

```
MONOLITHIC vs MODULAR

MONOLITHIC:                    MODULAR:
┌─────────────────────┐       ┌──────────┐  ┌──────────┐
│                     │       │  Auth    │  │ Payment  │
│  ALL CODE IN ONE    │  →→→  │  Module  │  │  Module  │
│       FILE          │       └──────────┘  └──────────┘
│                     │       ┌──────────┐  ┌──────────┐
│  (10,000+ lines)    │       │  Search  │  │  Orders  │
│                     │       │  Module  │  │  Module  │
└─────────────────────┘       └──────────┘  └──────────┘
```

---

## 2.2 — Why Large Programs Need Modules

| Problem (Monolithic) | Solution (Modular) |
|----------------------|-------------------|
| 10,000+ line files | Small focused files |
| Hard to find bugs | Isolated debugging |
| Team conflicts | Parallel development |
| Duplicate code | Reusable modules |
| Hard to test | Unit testable modules |
| Slow loading | Lazy imports |
| Not reusable | Package and publish |

---

## 2.3 — Real World Modular Systems

### 🟣 Instagram (Meta)
```
instagram/
├── auth/          → Login, Signup, JWT
├── feed/          → Posts, Stories, Reels
├── messaging/     → DMs, Group Chats
├── search/        → User Search, Hashtags
├── notifications/ → Push, Email, In-App
├── media/         → Upload, Compress, CDN
└── analytics/     → Metrics, A/B Testing
```

### 🔴 Netflix
```
netflix/
├── streaming/     → Video delivery, HLS
├── recommendations/ → ML models, A/B testing
├── billing/       → Subscriptions, Payments
├── catalog/       → Content database
├── auth/          → User accounts, profiles
└── player/        → Web, Mobile, TV clients
```

### 🤖 ChatGPT/LLM System
```
llm_system/
├── tokenizer/     → Text → Tokens
├── embeddings/    → Semantic vectors
├── model/         → Transformer inference
├── retrieval/     → RAG, Vector DB
├── safety/        → Content filtering
├── api/           → REST endpoints
└── cache/         → Redis, response cache
```

### 🏦 Banking Application
```
banking/
├── accounts/      → Create, Manage, Close
├── transactions/  → Transfer, History
├── loans/         → Apply, EMI Calculator
├── kyc/           → Identity Verification
├── fraud/         → Detection, Alerts
├── reports/       → Statements, Tax
└── notifications/ → SMS, Email, Push
```

---

## 2.4 — Benefits of Modular Programming

```
MODULAR PROGRAMMING BENEFITS

1. CODE REUSABILITY
   Write once → Use everywhere
   calculator.py → used in 50 different projects

2. MAINTAINABILITY
   Bug in payments? → Fix payments.py only
   No need to touch auth.py or search.py

3. SCALABILITY
   Add new feature → Add new module
   Doesn't break existing code

4. TEAM COLLABORATION
   Developer A → works on auth/
   Developer B → works on payments/
   No conflicts!

5. TESTABILITY
   Test each module independently
   Mock dependencies easily

6. READABILITY
   Small files = easy to understand
   Clear responsibility boundaries
```

---

<a name="section-3"></a>
# 📦 SECTION 3 — Modules Masterclass

## 3.1 — What is a Module?

A **module** is simply a Python file (`.py`) containing Python definitions, functions, classes, and variables that can be **imported and reused** in other Python programs.

```
module = Python file (.py) = reusable code unit

file: calculator.py → becomes → module: calculator
```

---

## 3.2 — Creating Your First Module

```python
# File: calculator.py

"""
Calculator Module
=================
Provides basic arithmetic operations.
Author: Your Name
Version: 1.0.0
"""

# Module-level variable
PI = 3.14159265358979

# Module-level docstring explains purpose


def add(a, b):
    """Add two numbers and return the result."""
    return a + b


def subtract(a, b):
    """Subtract b from a and return the result."""
    return a - b


def multiply(a, b):
    """Multiply two numbers and return the result."""
    return a * b


def divide(a, b):
    """Divide a by b. Raises ValueError if b is zero."""
    if b == 0:
        raise ValueError("Cannot divide by zero!")
    return a / b


def power(base, exponent):
    """Raise base to the power of exponent."""
    return base ** exponent


def square_root(n):
    """Return the square root of n."""
    if n < 0:
        raise ValueError("Cannot compute square root of negative number!")
    return n ** 0.5


# This only runs when calculator.py is run DIRECTLY
# Not when imported as a module
if __name__ == "__main__":
    print("Calculator Module Test")
    print(add(10, 5))       # 15
    print(divide(10, 2))    # 5.0
    print(square_root(16))  # 4.0
```

---

## 3.3 — Using (Importing) Your Module

```python
# File: main.py

import calculator

# Access functions using module_name.function_name
result = calculator.add(10, 5)
print(result)               # 15

# Access module-level variable
print(calculator.PI)        # 3.14159265358979

# Using the module extensively
print(calculator.subtract(20, 8))   # 12
print(calculator.multiply(4, 7))    # 28
print(calculator.divide(100, 4))    # 25.0
print(calculator.power(2, 10))      # 1024
print(calculator.square_root(144))  # 12.0
```

---

## 3.4 — Module Lifecycle (Internal Working)

When you write `import calculator`, Python performs these steps:

```
STEP 1: SEARCH
Python searches for 'calculator' in this order:
  1. sys.modules (cache) → already imported?
  2. Built-in modules (math, os, sys...)
  3. sys.path directories:
     a. Current directory
     b. PYTHONPATH directories
     c. Installation-dependent default

STEP 2: LOAD
  Python finds calculator.py
  Reads the file content

STEP 3: COMPILE
  Python compiles .py → bytecode (.pyc)
  Stores in __pycache__/ directory
  (Skipped if .pyc is newer than .py)

STEP 4: EXECUTE
  Python executes the module top-to-bottom
  Functions/classes are DEFINED (not called)
  Variables are assigned
  __name__ is set to "calculator"

STEP 5: CACHE
  Module stored in sys.modules["calculator"]
  Next import → returns cached version (instant)

STEP 6: BIND
  In your file: name "calculator" → module object
```

---

## 3.5 — The `__name__` Variable

This is one of Python's most important module features:

```python
# File: smart_module.py

def greet(name):
    return f"Hello, {name}!"

def farewell(name):
    return f"Goodbye, {name}!"

print(f"__name__ is: {__name__}")

if __name__ == "__main__":
    # This block ONLY runs when you run: python smart_module.py
    # It does NOT run when you: import smart_module
    print("Running as a script!")
    print(greet("Alice"))
    print(farewell("Bob"))
else:
    print("Imported as a module!")
```

```bash
# Running directly:
$ python smart_module.py
__name__ is: __main__
Running as a script!
Hello, Alice!
Goodbye, Bob!

# When imported:
>>> import smart_module
__name__ is: smart_module
Imported as a module!
```

---

## 3.6 — Module Attributes

```python
import calculator

# Module introspection
print(dir(calculator))         # All names defined in module
print(calculator.__name__)     # "calculator"
print(calculator.__file__)     # "/path/to/calculator.py"
print(calculator.__doc__)      # Module docstring
print(calculator.__package__)  # Package name (None if no package)

# Check if attribute exists
print(hasattr(calculator, "add"))       # True
print(hasattr(calculator, "magic"))     # False

# Get attribute dynamically
func = getattr(calculator, "add")
print(func(3, 4))                       # 7
```

---

## 3.7 — Real-World Module Examples

```python
# File: string_utils.py — Text Processing Utilities

"""
String Utilities Module
=======================
A collection of string processing helpers for NLP pipelines.
"""

import re
import string


def clean_text(text):
    """Remove special characters and extra whitespace."""
    text = re.sub(r'[^\w\s]', '', text)
    text = re.sub(r'\s+', ' ', text)
    return text.strip().lower()


def count_words(text):
    """Count number of words in text."""
    return len(text.split())


def truncate(text, max_length=100, suffix="..."):
    """Truncate text to max_length characters."""
    if len(text) <= max_length:
        return text
    return text[:max_length - len(suffix)] + suffix


def is_palindrome(text):
    """Check if text is a palindrome (ignores spaces, case)."""
    cleaned = text.lower().replace(" ", "")
    return cleaned == cleaned[::-1]


def word_frequency(text):
    """Return dictionary of word frequencies."""
    words = clean_text(text).split()
    freq = {}
    for word in words:
        freq[word] = freq.get(word, 0) + 1
    return freq


def extract_emails(text):
    """Extract all email addresses from text."""
    pattern = r'\b[A-Za-z0-9._%+-]+@[A-Za-z0-9.-]+\.[A-Z|a-z]{2,}\b'
    return re.findall(pattern, text)


def title_case_smart(text):
    """Convert to title case, skip prepositions."""
    small_words = {"a", "an", "the", "and", "but", "or", "in", "on", "at"}
    words = text.lower().split()
    result = []
    for i, word in enumerate(words):
        if i == 0 or word not in small_words:
            result.append(word.capitalize())
        else:
            result.append(word)
    return " ".join(result)


if __name__ == "__main__":
    sample = "Hello, World! This is a test. Visit us at test@example.com"
    print(clean_text(sample))
    print(count_words(sample))
    print(extract_emails(sample))
    print(is_palindrome("racecar"))
    print(word_frequency("the cat sat on the mat"))
```

---

<a name="section-4"></a>
# 🔀 SECTION 4 — Import System Masterclass

## 4.1 — All Forms of Import

### Form 1: `import module`
```python
import math

# Must use module prefix
print(math.pi)          # 3.141592653589793
print(math.sqrt(16))    # 4.0
print(math.ceil(4.2))   # 5
print(math.floor(4.9))  # 4
print(math.factorial(5))# 120

# ADVANTAGE: Clear origin — you know sqrt comes from math
# BEST FOR: Using a few things from large modules
```

### Form 2: `from module import name`
```python
from math import pi, sqrt, ceil, floor, factorial

# Use directly — no prefix needed
print(pi)           # 3.141592653589793
print(sqrt(25))     # 5.0
print(factorial(6)) # 720

# ADVANTAGE: Cleaner code, shorter syntax
# BEST FOR: Using specific things frequently
```

### Form 3: `from module import *` (Star Import)
```python
from math import *

# ALL public names imported
print(pi)       # Works
print(e)        # Works
print(tau)      # Works
print(inf)      # Works

# ❌ DANGER: Pollutes namespace!
# If math had a function called 'open', it would override Python's built-in!
# AVOID in production code — use only in REPL for quick exploration
```

### Form 4: `import module as alias`
```python
import numpy as np              # Industry standard
import pandas as pd             # Industry standard
import matplotlib.pyplot as plt # Industry standard
import datetime as dt
import calculator as calc

# Use with alias
result = calc.add(10, 5)
print(result)                   # 15

# ADVANTAGE: Shorter names, handle name conflicts
# BEST FOR: Long module names, industry conventions
```

### Form 5: `from module import name as alias`
```python
from math import square_root as sqrt_custom
from datetime import datetime as dt

# Custom alias for specific function
now = dt.now()
print(now)
```

---

## 4.2 — Import Search Path (`sys.path`)

```python
import sys

# sys.path is a list of directories Python searches for modules
print(sys.path)

# Typical output:
# ['',                                    ← Current directory (FIRST!)
#  '/usr/lib/python311.zip',
#  '/usr/lib/python3.11',
#  '/usr/lib/python3.11/lib-dynload',
#  '/home/user/.local/lib/python3.11/site-packages',
#  '/usr/lib/python3/dist-packages']

# '' means the current working directory
```

### Modifying `sys.path`
```python
import sys

# Add custom directory to search path
sys.path.insert(0, "/path/to/my/modules")
sys.path.append("/another/path")

# Now Python can find modules in those directories
import my_custom_module
```

### Using `.pth` files (Permanent)
```bash
# Create a .pth file in site-packages
# This permanently adds your path to Python's search

echo "/path/to/my/modules" > $(python -c "import site; print(site.getsitepackages()[0])")/mymodules.pth
```

---

## 4.3 — Absolute vs Relative Imports

### Absolute Imports (Recommended)
```python
# Always specify full path from project root
from myproject.utils.string_utils import clean_text
from myproject.models.user import User
from myproject.database.connection import get_db

# CLEAR: You know exactly where these come from
# WORKS everywhere: scripts, tests, interactive sessions
```

### Relative Imports (Package-internal only)
```python
# Used INSIDE a package to reference sibling modules

# In myproject/api/views.py:
from . import models              # Same package
from .models import User          # Same package, specific name
from ..database import get_db     # Parent package
from ..utils.string_utils import clean_text  # Sibling package

# . = current package
# .. = parent package
# ... = grandparent package

# ❌ Cannot use relative imports in top-level scripts
# ✅ Only inside packages (directories with __init__.py)
```

---

## 4.4 — Module Caching (`sys.modules`)

```python
import sys
import math

# After first import, module is cached
print("math" in sys.modules)    # True

# Second import is INSTANT — returns cached version
import math   # Does nothing extra, just binds name

# View all cached modules
for name in list(sys.modules.keys())[:10]:
    print(name)

# Force reload (useful in development)
import importlib
importlib.reload(math)    # Reloads from disk

# Delete from cache (forces fresh import next time)
del sys.modules["math"]
import math    # Actually imports fresh copy
```

---

## 4.5 — Import System Architecture Diagram

```
PYTHON IMPORT SYSTEM

User Code: import calculator
           │
           ▼
    ┌──────────────────┐
    │ Check sys.modules │ ──── Found? ──→ Return cached module
    │    (cache)        │
    └──────────────────┘
           │
         Not Found
           │
           ▼
    ┌──────────────────────────────────────┐
    │           FINDERS (sys.meta_path)    │
    │                                      │
    │  1. BuiltinImporter                  │
    │     → Checks built-in modules        │
    │     → (math, sys, os, etc.)          │
    │                                      │
    │  2. FrozenImporter                   │
    │     → Checks frozen modules          │
    │                                      │
    │  3. PathFinder                       │
    │     → Searches sys.path directories  │
    └──────────────────────────────────────┘
           │
           ▼
    ┌──────────────────┐
    │     LOADERS      │
    │                  │
    │  Read .py file   │
    │  Compile to .pyc │
    │  Execute module  │
    │  Cache in        │
    │  sys.modules     │
    └──────────────────┘
           │
           ▼
    Return module object to user code
```

---

<a name="section-5"></a>
# 🔧 SECTION 5 — Built-in Modules Masterclass

## 5.1 — `math` Module

```python
import math

# Constants
print(math.pi)          # 3.141592653589793
print(math.e)           # 2.718281828459045
print(math.tau)         # 6.283185307179586 (2π)
print(math.inf)         # inf
print(math.nan)         # nan

# Rounding
print(math.ceil(4.2))   # 5   — rounds UP
print(math.floor(4.9))  # 4   — rounds DOWN
print(math.trunc(4.9))  # 4   — removes decimal

# Powers and Logarithms
print(math.sqrt(144))       # 12.0
print(math.pow(2, 10))      # 1024.0
print(math.log(math.e))     # 1.0   (natural log)
print(math.log(100, 10))    # 2.0   (log base 10)
print(math.log2(1024))      # 10.0  (log base 2)
print(math.log10(10000))    # 4.0

# Trigonometry (input in radians)
print(math.sin(math.pi/2))  # 1.0
print(math.cos(0))           # 1.0
print(math.tan(math.pi/4))  # 0.9999... (≈1.0)
print(math.degrees(math.pi))# 180.0 (radians → degrees)
print(math.radians(180))    # 3.14159... (degrees → radians)

# Other
print(math.factorial(10))   # 3628800
print(math.gcd(48, 64))     # 16
print(math.lcm(4, 6))       # 12  (Python 3.9+)
print(math.isnan(math.nan)) # True
print(math.isinf(math.inf)) # True
print(math.fabs(-5.5))      # 5.5 (absolute value as float)
print(math.comb(10, 3))     # 120 (combinations nCr)
print(math.perm(10, 3))     # 720 (permutations nPr)

# Real World: EMI Calculator
def calculate_emi(principal, annual_rate, months):
    r = annual_rate / (12 * 100)
    emi = principal * r * math.pow(1 + r, months) / (math.pow(1 + r, months) - 1)
    return round(emi, 2)

print(calculate_emi(500000, 8.5, 60))   # Monthly EMI for 5L loan
```

---

## 5.2 — `random` Module

```python
import random

# Basic random
print(random.random())          # 0.0 to 1.0 (float)
print(random.uniform(1, 10))    # Float between 1 and 10
print(random.randint(1, 100))   # Integer 1 to 100 (inclusive)
print(random.randrange(0, 100, 5))  # 0, 5, 10, ..., 95

# Sequences
fruits = ["apple", "banana", "cherry", "date", "elderberry"]
print(random.choice(fruits))        # Pick one random element
print(random.choices(fruits, k=3))  # Pick 3 (with replacement)
print(random.sample(fruits, k=3))   # Pick 3 (without replacement)

random.shuffle(fruits)              # Shuffle IN PLACE
print(fruits)

# Seeding for reproducibility
random.seed(42)
print(random.randint(1, 100))   # Always same result with seed 42
random.seed(42)
print(random.randint(1, 100))   # Same as above

# Gaussian distribution (useful in ML/statistics)
print(random.gauss(mu=0, sigma=1))  # Normal distribution

# Real World: Password Generator
def generate_password(length=12):
    import string
    chars = string.ascii_letters + string.digits + string.punctuation
    return ''.join(random.choices(chars, k=length))

print(generate_password(16))   # e.g., "K#mP2xR@nL5qW!vZ"

# OTP Generator
def generate_otp(digits=6):
    return str(random.randint(10**(digits-1), 10**digits - 1))

print(generate_otp())   # e.g., "847362"
```

---

## 5.3 — `datetime` Module

```python
from datetime import datetime, date, time, timedelta
import datetime as dt

# Current datetime
now = datetime.now()
print(now)                      # 2025-01-15 14:30:45.123456
print(now.year)                 # 2025
print(now.month)                # 1
print(now.day)                  # 15
print(now.hour)                 # 14
print(now.minute)               # 30
print(now.second)               # 45

# Create specific datetime
birthday = datetime(1995, 8, 15, 0, 0, 0)
print(birthday)                 # 1995-08-15 00:00:00

# Date operations
today = date.today()
print(today)                    # 2025-01-15

# timedelta — duration between datetimes
diff = now - birthday
print(diff.days)                # Days since birthday
print(diff.seconds)             # Additional seconds

# Date arithmetic
future = today + timedelta(days=30)
past = today - timedelta(weeks=2)
print(future)
print(past)

# Formatting
print(now.strftime("%d/%m/%Y"))         # 15/01/2025
print(now.strftime("%B %d, %Y"))        # January 15, 2025
print(now.strftime("%I:%M %p"))         # 02:30 PM
print(now.strftime("%A, %d %B %Y"))     # Wednesday, 15 January 2025

# Parsing
date_str = "15-01-2025"
parsed = datetime.strptime(date_str, "%d-%m-%Y")
print(parsed)                   # 2025-01-15 00:00:00

# Age Calculator
def calculate_age(birth_date):
    today = date.today()
    age = today.year - birth_date.year
    if (today.month, today.day) < (birth_date.month, birth_date.day):
        age -= 1
    return age

print(calculate_age(date(1995, 8, 15)))   # Your age

# Days until event
def days_until(event_date):
    today = date.today()
    delta = event_date - today
    return delta.days

print(days_until(date(2025, 12, 31)))   # Days until New Year
```

---

## 5.4 — `os` Module

```python
import os

# Current directory
print(os.getcwd())                      # /home/user/project
os.chdir("/tmp")                        # Change directory
print(os.getcwd())                      # /tmp

# Directory operations
os.mkdir("test_dir")                    # Create directory
os.makedirs("a/b/c", exist_ok=True)    # Create nested dirs
os.rmdir("test_dir")                    # Remove empty dir

# File operations
os.rename("old.txt", "new.txt")        # Rename file
os.remove("file.txt")                   # Delete file

# List directory
files = os.listdir(".")                 # List current dir
print(files)

# Path operations
path = "/home/user/documents/report.pdf"
print(os.path.dirname(path))           # /home/user/documents
print(os.path.basename(path))          # report.pdf
print(os.path.splitext(path))          # ('/home/.../report', '.pdf')
print(os.path.exists(path))            # True/False
print(os.path.isfile(path))            # True if file
print(os.path.isdir("/home/user"))     # True if directory
print(os.path.getsize(path))           # File size in bytes
print(os.path.join("/home", "user", "docs"))  # /home/user/docs

# Environment variables
print(os.environ.get("HOME"))          # /home/user
print(os.environ.get("PATH"))          # System PATH
os.environ["MY_API_KEY"] = "secret"   # Set variable

# System info
print(os.name)                         # 'posix' (Linux/Mac) or 'nt' (Windows)
print(os.cpu_count())                  # Number of CPU cores
print(os.getpid())                     # Current process ID
print(os.getlogin())                   # Current user

# Walk directory tree
for root, dirs, files in os.walk("."):
    for file in files:
        full_path = os.path.join(root, file)
        print(full_path)

# Real World: File Organizer
def organize_downloads(download_path):
    """Organize files by extension."""
    categories = {
        "Images": [".jpg", ".jpeg", ".png", ".gif", ".bmp", ".svg"],
        "Documents": [".pdf", ".doc", ".docx", ".txt", ".xlsx"],
        "Videos": [".mp4", ".avi", ".mkv", ".mov"],
        "Audio": [".mp3", ".wav", ".flac", ".aac"],
        "Code": [".py", ".js", ".html", ".css", ".java", ".cpp"],
    }
    
    for filename in os.listdir(download_path):
        filepath = os.path.join(download_path, filename)
        if not os.path.isfile(filepath):
            continue
        
        _, ext = os.path.splitext(filename)
        ext = ext.lower()
        
        moved = False
        for category, extensions in categories.items():
            if ext in extensions:
                category_path = os.path.join(download_path, category)
                os.makedirs(category_path, exist_ok=True)
                os.rename(filepath, os.path.join(category_path, filename))
                moved = True
                break
        
        if not moved:
            other_path = os.path.join(download_path, "Others")
            os.makedirs(other_path, exist_ok=True)
            os.rename(filepath, os.path.join(other_path, filename))
```

---

## 5.5 — `sys` Module

```python
import sys

# Python version info
print(sys.version)              # 3.11.0 (main, Oct 24 2022...)
print(sys.version_info)         # sys.version_info(major=3, minor=11, ...)
print(sys.version_info.major)   # 3
print(sys.version_info.minor)   # 11

# Platform
print(sys.platform)             # 'linux', 'darwin', 'win32'

# Command line arguments
# Run: python script.py arg1 arg2 arg3
print(sys.argv)                 # ['script.py', 'arg1', 'arg2', 'arg3']
print(sys.argv[0])              # script.py (script name)
print(sys.argv[1:])             # ['arg1', 'arg2', 'arg3']

# Path
print(sys.path)                 # Module search path list
sys.path.insert(0, "/custom")  # Add custom path

# Exit program
# sys.exit(0)    # Exit with code 0 (success)
# sys.exit(1)    # Exit with code 1 (error)

# Max values
print(sys.maxsize)              # 9223372036854775807 (max int)
print(sys.float_info.max)       # Max float

# Memory usage
import sys
x = [1, 2, 3, 4, 5]
print(sys.getsizeof(x))        # Size in bytes: ~120

# Standard I/O
sys.stdout.write("Hello\n")    # Same as print()
sys.stderr.write("Error!\n")   # Write to stderr

# Recursion limit
print(sys.getrecursionlimit()) # 1000 (default)
sys.setrecursionlimit(2000)    # Increase limit
```

---

## 5.6 — `pathlib` Module (Modern Path Handling)

```python
from pathlib import Path

# Create path objects
home = Path.home()                  # Home directory
current = Path.cwd()                # Current directory
p = Path("/home/user/documents")

# Path operations (using / operator!)
file_path = p / "projects" / "readme.md"
print(file_path)                    # /home/user/documents/projects/readme.md

# Path properties
print(file_path.name)              # readme.md
print(file_path.stem)              # readme
print(file_path.suffix)            # .md
print(file_path.parent)            # /home/user/documents/projects
print(file_path.exists())          # True/False
print(file_path.is_file())         # True/False
print(file_path.is_dir())          # True/False

# Create directories
Path("my/nested/dir").mkdir(parents=True, exist_ok=True)

# List files
for f in Path(".").iterdir():
    print(f)

# Pattern matching (glob)
for py_file in Path(".").glob("*.py"):
    print(py_file)

for py_file in Path(".").rglob("*.py"):   # Recursive
    print(py_file)

# Read/Write files
p = Path("hello.txt")
p.write_text("Hello, World!")      # Write
content = p.read_text()            # Read
print(content)

# Resolve absolute path
print(Path("../docs").resolve())   # Absolute path
```

---

## 5.7 — `json` Module

```python
import json

# Python dict → JSON string
data = {
    "name": "Alice",
    "age": 30,
    "skills": ["Python", "ML", "SQL"],
    "address": {
        "city": "Bangalore",
        "country": "India"
    },
    "active": True,
    "score": 9.5
}

# Serialize (dict → JSON string)
json_string = json.dumps(data)
print(json_string)
print(type(json_string))    # <class 'str'>

# Pretty print
json_pretty = json.dumps(data, indent=2, sort_keys=True)
print(json_pretty)

# Deserialize (JSON string → dict)
restored = json.loads(json_string)
print(restored["name"])     # Alice
print(type(restored))       # <class 'dict'>

# Write JSON to file
with open("data.json", "w") as f:
    json.dump(data, f, indent=2)

# Read JSON from file
with open("data.json", "r") as f:
    loaded = json.load(f)
print(loaded["skills"])     # ['Python', 'ML', 'SQL']

# Handle non-serializable types
from datetime import datetime

def json_serializer(obj):
    if isinstance(obj, datetime):
        return obj.isoformat()
    raise TypeError(f"Object of type {type(obj)} is not JSON serializable")

data_with_date = {"timestamp": datetime.now()}
print(json.dumps(data_with_date, default=json_serializer))
```

---

## 5.8 — `collections` Module

```python
from collections import (
    Counter, defaultdict, OrderedDict, 
    namedtuple, deque, ChainMap
)

# Counter — count occurrences
text = "mississippi"
c = Counter(text)
print(c)                        # Counter({'s': 4, 'i': 4, 'p': 2, 'm': 1})
print(c.most_common(2))         # [('s', 4), ('i', 4)]

words = "the quick brown fox jumps over the lazy dog".split()
word_count = Counter(words)
print(word_count.most_common(3))  # Top 3 words

# defaultdict — dict with default value
dd = defaultdict(list)          # Default: empty list
dd["fruits"].append("apple")
dd["fruits"].append("banana")
dd["veggies"].append("carrot")
print(dict(dd))                 # {'fruits': ['apple', 'banana'], 'veggies': ['carrot']}

dd_int = defaultdict(int)       # Default: 0
for char in "hello":
    dd_int[char] += 1
print(dict(dd_int))             # {'h': 1, 'e': 1, 'l': 2, 'o': 1}

# OrderedDict — maintains insertion order (less needed in 3.7+)
od = OrderedDict()
od["first"] = 1
od["second"] = 2
od["third"] = 3
od.move_to_end("first")        # Move to end

# namedtuple — tuple with named fields
Point = namedtuple("Point", ["x", "y"])
p = Point(10, 20)
print(p.x, p.y)                 # 10 20
print(p[0], p[1])               # 10 20 (still indexable)
print(p._asdict())              # OrderedDict([('x', 10), ('y', 20)])

Student = namedtuple("Student", ["name", "age", "grade"])
alice = Student("Alice", 20, "A")
print(alice.name)               # Alice

# deque — double-ended queue (O(1) append/pop from both ends)
dq = deque([1, 2, 3, 4, 5])
dq.appendleft(0)                # Add to front
dq.append(6)                    # Add to end
dq.popleft()                    # Remove from front
dq.pop()                        # Remove from end
print(dq)                       # deque([1, 2, 3, 4, 5])

# deque with maxlen (automatic sliding window)
recent = deque(maxlen=3)
for i in range(6):
    recent.append(i)
print(recent)                   # deque([3, 4, 5], maxlen=3)
```

---

## 5.9 — `itertools` Module

```python
import itertools

# count — infinite counter
counter = itertools.count(start=1, step=2)   # 1, 3, 5, 7, ...
for i, val in enumerate(counter):
    if i >= 5:
        break
    print(val, end=" ")    # 1 3 5 7 9

# cycle — infinite cycle through iterable
seasons = itertools.cycle(["Spring", "Summer", "Autumn", "Winter"])
for i, season in enumerate(seasons):
    if i >= 8:
        break
    print(season, end=" ")  # Spring Summer Autumn Winter Spring ...

# chain — combine multiple iterables
combined = itertools.chain([1, 2, 3], [4, 5], [6])
print(list(combined))       # [1, 2, 3, 4, 5, 6]

# combinations
items = ["A", "B", "C", "D"]
print(list(itertools.combinations(items, 2)))
# [('A','B'), ('A','C'), ('A','D'), ('B','C'), ('B','D'), ('C','D')]

# permutations
print(list(itertools.permutations([1, 2, 3], 2)))
# All ordered pairs

# product — cartesian product
print(list(itertools.product([1, 2], ["a", "b"])))
# [(1,'a'), (1,'b'), (2,'a'), (2,'b')]

# groupby — group consecutive elements
data = [("Alice", "Engineering"), ("Bob", "Engineering"), 
        ("Charlie", "Marketing"), ("Dave", "Marketing")]
for dept, members in itertools.groupby(data, key=lambda x: x[1]):
    print(dept, list(members))

# islice — slice an iterator
gen = (x**2 for x in range(1000000))  # Infinite generator
first_10_squares = list(itertools.islice(gen, 10))
print(first_10_squares)    # [0, 1, 4, 9, 16, 25, 36, 49, 64, 81]
```

---

## 5.10 — `statistics` Module

```python
import statistics

data = [23, 45, 67, 23, 89, 45, 12, 67, 45, 34, 56, 78, 90, 23]

# Central tendency
print(statistics.mean(data))        # Arithmetic mean
print(statistics.median(data))      # Middle value
print(statistics.mode(data))        # Most frequent
print(statistics.multimode(data))   # All modes

# Spread
print(statistics.stdev(data))       # Standard deviation (sample)
print(statistics.variance(data))    # Variance (sample)
print(statistics.pstdev(data))      # Population std dev
print(statistics.pvariance(data))   # Population variance

# Range (not in statistics, but useful)
print(max(data) - min(data))        # Range

# Correlation (Python 3.10+)
x = [1, 2, 3, 4, 5]
y = [2, 4, 5, 4, 5]
print(statistics.correlation(x, y))    # 0.91...
print(statistics.linear_regression(x, y))  # LinearRegression(slope=..., intercept=...)
```

---

## 5.11 — `platform` Module

```python
import platform

print(platform.system())        # 'Linux', 'Windows', 'Darwin'
print(platform.release())       # Kernel version
print(platform.version())       # Detailed version
print(platform.machine())       # 'x86_64', 'arm64'
print(platform.processor())     # CPU info
print(platform.python_version())# '3.11.0'
print(platform.node())          # Hostname
print(platform.uname())         # Complete system info

# Cross-platform code
if platform.system() == "Windows":
    clear_cmd = "cls"
else:
    clear_cmd = "clear"

import os
os.system(clear_cmd)
```

---

<a name="section-6"></a>
# 📁 SECTION 6 — Packages Masterclass

## 6.1 — What is a Package?

A **package** is a directory containing Python modules and a special `__init__.py` file. It's the way Python organizes large codebases into hierarchical structures.

```
module  = single .py file
package = directory with __init__.py + multiple modules
```

**Real World Analogy:**
- **Book** = Package
- **Chapter** = Module
- **Table of Contents** = `__init__.py`

---

## 6.2 — Creating Your First Package

```
mypackage/                  ← Package directory
├── __init__.py             ← Makes it a package (can be empty)
├── math_utils.py           ← Module 1
├── string_utils.py         ← Module 2
└── file_utils.py           ← Module 3
```

```python
# mypackage/__init__.py

"""
MyPackage — Utility Collection
================================
A comprehensive utility library for Python developers.
"""

# Package version
__version__ = "1.0.0"
__author__ = "Your Name"

# Import commonly used items for convenience
from .math_utils import add, subtract, multiply
from .string_utils import clean_text, count_words

# What gets exported when user does: from mypackage import *
__all__ = ["add", "subtract", "multiply", "clean_text", "count_words"]

print(f"MyPackage v{__version__} loaded!")   # Runs on import
```

```python
# mypackage/math_utils.py

def add(a, b):
    return a + b

def subtract(a, b):
    return a - b

def multiply(a, b):
    return a * b

def divide(a, b):
    if b == 0:
        raise ZeroDivisionError("Cannot divide by zero!")
    return a / b
```

```python
# mypackage/string_utils.py

import re

def clean_text(text):
    return re.sub(r'\s+', ' ', text.strip()).lower()

def count_words(text):
    return len(text.split())

def reverse_words(text):
    return ' '.join(text.split()[::-1])
```

---

## 6.3 — Using Your Package

```python
# main.py (in the same parent directory as mypackage/)

# Method 1: Import the package
import mypackage
print(mypackage.add(10, 5))           # Works! (imported in __init__.py)

# Method 2: Import specific module
from mypackage import math_utils
print(math_utils.multiply(3, 7))      # 21

# Method 3: Import specific function
from mypackage.math_utils import divide
print(divide(100, 4))                 # 25.0

# Method 4: Import from package (via __init__.py)
from mypackage import clean_text
print(clean_text("  Hello   World  "))  # "hello world"
```

---

## 6.4 — Sub-packages (Nested Packages)

```
enterprise_toolkit/                    ← Root package
├── __init__.py
├── core/                             ← Sub-package
│   ├── __init__.py
│   ├── validators.py
│   └── converters.py
├── database/                         ← Sub-package
│   ├── __init__.py
│   ├── connection.py
│   └── queries.py
├── api/                              ← Sub-package
│   ├── __init__.py
│   ├── routes.py
│   └── middleware.py
└── utils/                            ← Sub-package
    ├── __init__.py
    ├── logger.py
    └── helpers.py
```

```python
# Using nested packages
from enterprise_toolkit.core.validators import validate_email
from enterprise_toolkit.database.connection import get_connection
from enterprise_toolkit.api.routes import create_app

# Or step by step
import enterprise_toolkit.utils.logger as logger
logger.info("Application started")
```

---

## 6.5 — `__init__.py` Deep Dive

```python
# Advanced __init__.py patterns

# Pattern 1: Lazy Import (performance)
def get_heavy_module():
    from . import heavy_module    # Only imported when needed
    return heavy_module

# Pattern 2: Version checking
import sys
if sys.version_info < (3, 8):
    raise RuntimeError("mypackage requires Python 3.8+")

# Pattern 3: Conditional imports
try:
    import numpy as np
    HAS_NUMPY = True
except ImportError:
    HAS_NUMPY = False

# Pattern 4: Package initialization
_cache = {}
_config = {
    "debug": False,
    "version": "1.0.0"
}

def configure(**kwargs):
    _config.update(kwargs)

def get_config(key, default=None):
    return _config.get(key, default)
```

---

<a name="section-7"></a>
# 🛠️ SECTION 7 — pip Masterclass

## 7.1 — What is pip?

**pip** (Package Installer for Python) is Python's standard package manager. It downloads packages from **PyPI** (Python Package Index) — the world's largest Python package repository.

```
pip = Package Installer for Python
PyPI = Python Package Index (pypi.org)
      → 500,000+ packages available

Timeline:
PyPI → pip downloads → site-packages → import → use
```

---

## 7.2 — pip Commands Reference

```bash
# ─────────────── INSTALLATION ───────────────
pip install requests              # Install latest version
pip install requests==2.28.0      # Install specific version
pip install requests>=2.25.0      # Install >= version
pip install requests>=2.25,<3.0   # Version range
pip install "requests[security]"  # Install with extras
pip install requests rich numpy   # Install multiple packages

# ─────────────── UPGRADING ───────────────
pip install --upgrade requests    # Upgrade to latest
pip install -U requests           # Short form
pip install --upgrade pip         # Upgrade pip itself

# ─────────────── UNINSTALL ───────────────
pip uninstall requests            # Uninstall (asks confirmation)
pip uninstall requests -y         # Uninstall without confirmation
pip uninstall requests numpy pandas -y  # Uninstall multiple

# ─────────────── LISTING ───────────────
pip list                          # List all installed packages
pip list --outdated               # List outdatable packages
pip show requests                 # Show package details
pip show requests numpy           # Show multiple packages

# ─────────────── SEARCH & INFO ───────────────
pip search requests               # Search PyPI (may be disabled)
pip index versions requests       # Show available versions

# ─────────────── REQUIREMENTS ───────────────
pip freeze                        # Show installed = frozen versions
pip freeze > requirements.txt     # Save to file
pip install -r requirements.txt   # Install from file

# ─────────────── DOWNLOAD ───────────────
pip download requests             # Download without installing
pip download -r requirements.txt  # Download all requirements

# ─────────────── CACHE ───────────────
pip cache list                    # List cached packages
pip cache purge                   # Clear pip cache

# ─────────────── CHECK ───────────────
pip check                         # Check for dependency conflicts
```

---

## 7.3 — pip `show` Output Explained

```bash
$ pip show requests

Name: requests
Version: 2.28.2
Summary: Python HTTP for Humans.
Home-page: https://requests.readthedocs.io
Author: Kenneth Reitz
Author-email: me@kennethreitz.org
License: Apache 2.0
Location: /home/user/.local/lib/python3.11/site-packages
Requires: certifi, charset-normalizer, idna, urllib3   ← Dependencies
Required-by: httpx, poetry, pip-tools                  ← Who needs this
```

---

## 7.4 — Version Specifiers

```
Version Specifier Syntax:
========================

package==1.2.3      → Exact version
package>=1.2.3      → 1.2.3 or higher
package<=1.2.3      → 1.2.3 or lower
package!=1.2.3      → Anything except 1.2.3
package~=1.2.3      → Compatible release (>=1.2.3, <1.3.0)
package>=1.0,<2.0   → Range (AND condition)

Examples:
django>=4.0,<5.0    → Django 4.x only
numpy~=1.24.0       → 1.24.x only
requests>=2.25      → 2.25 or higher
```

---

## 7.5 — Essential Packages Every Python Developer Should Know

```bash
# Web & HTTP
pip install requests          # HTTP library
pip install httpx             # Modern async HTTP
pip install aiohttp           # Async HTTP client/server

# Data Science
pip install numpy             # Numerical computing
pip install pandas            # Data manipulation
pip install matplotlib        # Plotting
pip install seaborn           # Statistical visualization
pip install scipy             # Scientific computing

# Machine Learning / AI
pip install scikit-learn      # Classical ML
pip install tensorflow        # Deep learning (Google)
pip install torch             # Deep learning (Meta)
pip install transformers      # HuggingFace NLP

# Web Frameworks
pip install flask             # Micro web framework
pip install django            # Full-stack framework
pip install fastapi           # Modern async API framework
pip install uvicorn           # ASGI server

# Database
pip install sqlalchemy        # ORM
pip install psycopg2          # PostgreSQL
pip install pymongo           # MongoDB
pip install redis             # Redis client

# CLI & Terminal
pip install click             # CLI framework
pip install rich              # Beautiful terminal output
pip install typer             # Modern CLI with type hints

# Testing
pip install pytest            # Testing framework
pip install pytest-cov        # Coverage reporting
pip install faker             # Generate fake data

# Utilities
pip install python-dotenv     # .env file support
pip install pydantic          # Data validation
pip install arrow             # Better datetime
pip install loguru            # Beautiful logging
pip install tqdm              # Progress bars
```

---

<a name="section-8"></a>
# 🏠 SECTION 8 — Virtual Environments Masterclass

## 8.1 — The Problem: Why Virtual Environments?

```
THE DEPENDENCY CONFLICT PROBLEM

Global Python Environment:
│
├── Project A needs → Django==3.2
├── Project B needs → Django==4.1
│
└── CONFLICT! Cannot have two versions of Django installed globally!

Also:
├── Project A needs → numpy==1.21
├── Project C needs → numpy==1.24
│
└── CONFLICT!

SOLUTION: Virtual Environments
Each project gets its OWN isolated Python + packages
```

---

## 8.2 — Virtual Environment Architecture

```
VIRTUAL ENVIRONMENT STRUCTURE

venv/
├── bin/                    (Linux/Mac) or Scripts/ (Windows)
│   ├── python              → Points to Python interpreter
│   ├── python3             → Symlink to python
│   ├── pip                 → pip for THIS environment
│   ├── activate            → Shell script to activate venv
│   ├── activate.fish       → For Fish shell
│   └── deactivate          → Deactivation script
├── lib/
│   └── python3.11/
│       └── site-packages/  → Installed packages GO HERE
│           ├── pip/
│           ├── setuptools/
│           └── (your packages...)
├── include/
└── pyvenv.cfg              → Configuration file
    content: home = /usr/bin/python3
             version = 3.11.0
```

---

## 8.3 — Creating and Using Virtual Environments

```bash
# ─────────────── CREATE ───────────────
python -m venv venv                  # Create venv in ./venv/
python -m venv myenv                 # Custom name
python -m venv .venv                 # Hidden directory (dot prefix)
python3.11 -m venv venv             # Specific Python version

# ─────────────── ACTIVATE ───────────────
# Linux/macOS:
source venv/bin/activate             # bash/zsh
source venv/bin/activate.fish        # fish shell
source venv/bin/activate.csh         # csh

# Windows CMD:
venv\Scripts\activate.bat

# Windows PowerShell:
venv\Scripts\Activate.ps1
# (If error: Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser)

# ─────────────── VERIFY ACTIVATION ───────────────
which python                         # /path/to/project/venv/bin/python
python --version                     # Python 3.11.x
pip list                             # Only shows venv packages

# (venv) prefix appears in prompt:
# (venv) user@machine:~/project$

# ─────────────── INSTALL PACKAGES ───────────────
pip install requests numpy pandas   # Installs in venv only!

# ─────────────── DEACTIVATE ───────────────
deactivate                           # Returns to global Python

# ─────────────── DELETE ───────────────
rm -rf venv/                         # Linux/Mac
rmdir /s venv                        # Windows CMD
```

---

## 8.4 — Virtual Environment Workflow

```
PROFESSIONAL VIRTUAL ENV WORKFLOW

1. New Project
   mkdir my_project && cd my_project
   git init

2. Create venv
   python -m venv venv

3. Add to .gitignore
   echo "venv/" >> .gitignore
   echo ".venv/" >> .gitignore

4. Activate
   source venv/bin/activate

5. Install dependencies
   pip install requests flask python-dotenv

6. Freeze requirements
   pip freeze > requirements.txt

7. Commit requirements.txt (NOT venv/)
   git add requirements.txt
   git commit -m "Add project dependencies"

8. Colleague clones project
   git clone <repo>
   cd <repo>
   python -m venv venv
   source venv/bin/activate
   pip install -r requirements.txt
   # Ready to work!
```

---

## 8.5 — Alternative: `virtualenv` and `conda`

```bash
# virtualenv (faster, more features than venv)
pip install virtualenv
virtualenv venv
virtualenv -p python3.11 venv       # Specific version

# conda (Anaconda — great for data science)
conda create -n myenv python=3.11
conda activate myenv
conda install numpy pandas scikit-learn
conda deactivate
conda env list                      # List all conda envs
conda env remove -n myenv           # Delete env
conda env export > environment.yml  # Export

# Install from conda environment.yml
conda env create -f environment.yml

# pipenv (combines pip + virtualenv)
pip install pipenv
pipenv install requests             # Creates venv + Pipfile
pipenv install pytest --dev         # Dev dependency
pipenv shell                        # Activate venv
pipenv run python script.py         # Run in venv
```

---

<a name="section-9"></a>
# 📋 SECTION 9 — Requirements Files

## 9.1 — `requirements.txt` Format

```txt
# requirements.txt — Production Dependencies

# Exact versions (for reproducibility)
requests==2.28.2
Flask==2.3.2
SQLAlchemy==2.0.15
python-dotenv==1.0.0
pydantic==2.0.3
loguru==0.7.0

# Range versions (for flexibility)
numpy>=1.24.0
pandas>=2.0.0,<3.0.0

# Extras
requests[security]>=2.28.0

# Git repositories (for unreleased packages)
git+https://github.com/user/repo.git@main#egg=package_name

# Local packages
-e .                    # Install current directory as package
-e ./mypackage          # Install local package in editable mode

# Include another requirements file
-r requirements-base.txt
```

---

## 9.2 — Multi-File Requirements Strategy

```
requirements/
├── base.txt          → Shared by all environments
├── development.txt   → Dev tools (testing, linting)
├── production.txt    → Production-only (gunicorn, psycopg2)
└── testing.txt       → Testing tools only
```

```txt
# requirements/base.txt
requests==2.28.2
Flask==2.3.2
SQLAlchemy==2.0.15
python-dotenv==1.0.0

# requirements/development.txt
-r base.txt              # Include base
pytest==7.4.0
pytest-cov==4.1.0
black==23.7.0
flake8==6.0.0
isort==5.12.0
mypy==1.4.1
faker==19.2.0
ipython==8.14.0

# requirements/production.txt
-r base.txt              # Include base
gunicorn==21.2.0
psycopg2-binary==2.9.6
redis==4.6.0

# requirements/testing.txt
-r base.txt
pytest==7.4.0
pytest-cov==4.1.0
faker==19.2.0
```

```bash
# Install for different environments
pip install -r requirements/development.txt    # Dev
pip install -r requirements/production.txt     # Prod
pip install -r requirements/testing.txt        # CI/CD

# Also works with root requirements.txt
pip install -r requirements.txt
```

---

## 9.3 — `pip freeze` vs Manual

```bash
# pip freeze — captures EVERYTHING (including sub-dependencies)
pip freeze > requirements.txt
# Output includes: requests==2.28.2, certifi==2023.5.7, charset-normalizer==3.2.0...
# Too many! Sub-dependencies clutter the file

# Better approach: pip-tools
pip install pip-tools

# Create requirements.in with only DIRECT dependencies
echo "requests" > requirements.in
echo "flask" >> requirements.in
echo "sqlalchemy" >> requirements.in

# Compile to requirements.txt (resolves and pins ALL deps)
pip-compile requirements.in → requirements.txt

# Upgrade all packages
pip-compile --upgrade requirements.in

# Sync your environment exactly
pip-sync requirements.txt
```

---

<a name="section-10"></a>
# 🏗️ SECTION 10 — Project Structure Masterclass

## 10.1 — Small Project Structure

```
small_project/
├── main.py               ← Entry point
├── utils.py              ← Helper functions
├── config.py             ← Configuration
├── requirements.txt      ← Dependencies
├── README.md             ← Documentation
└── .gitignore            ← Git ignore rules
```

---

## 10.2 — Medium Project Structure

```
medium_project/
├── src/                      ← Source code
│   ├── __init__.py
│   ├── main.py               ← Entry point
│   ├── models/               ← Data models
│   │   ├── __init__.py
│   │   └── user.py
│   ├── services/             ← Business logic
│   │   ├── __init__.py
│   │   └── user_service.py
│   └── utils/                ← Utilities
│       ├── __init__.py
│       ├── validators.py
│       └── formatters.py
├── tests/                    ← Test files
│   ├── __init__.py
│   ├── test_models.py
│   └── test_services.py
├── docs/                     ← Documentation
│   └── README.md
├── requirements.txt
├── requirements-dev.txt
├── README.md
├── LICENSE
└── .gitignore
```

---

## 10.3 — Enterprise Project Structure

```
enterprise_application/
├── src/
│   └── myapp/
│       ├── __init__.py
│       ├── main.py
│       ├── config/
│       │   ├── __init__.py
│       │   ├── settings.py         ← App settings
│       │   ├── logging_config.py   ← Logging setup
│       │   └── database.py         ← DB config
│       ├── api/
│       │   ├── __init__.py
│       │   ├── v1/
│       │   │   ├── routes.py
│       │   │   └── handlers.py
│       │   └── middleware.py
│       ├── models/
│       │   ├── __init__.py
│       │   ├── user.py
│       │   ├── product.py
│       │   └── order.py
│       ├── services/
│       │   ├── __init__.py
│       │   ├── auth_service.py
│       │   ├── payment_service.py
│       │   └── notification_service.py
│       ├── repositories/
│       │   ├── __init__.py
│       │   ├── user_repo.py
│       │   └── product_repo.py
│       ├── utils/
│       │   ├── __init__.py
│       │   ├── validators.py
│       │   ├── formatters.py
│       │   ├── logger.py
│       │   └── helpers.py
│       └── exceptions/
│           ├── __init__.py
│           └── custom_exceptions.py
├── tests/
│   ├── __init__.py
│   ├── unit/
│   │   ├── test_models.py
│   │   ├── test_services.py
│   │   └── test_utils.py
│   ├── integration/
│   │   ├── test_api.py
│   │   └── test_database.py
│   └── fixtures/
│       └── sample_data.json
├── scripts/
│   ├── setup_db.py
│   ├── seed_data.py
│   └── run_migrations.py
├── docs/
│   ├── API.md
│   ├── ARCHITECTURE.md
│   ├── CONTRIBUTING.md
│   └── DEPLOYMENT.md
├── .github/
│   ├── workflows/
│   │   ├── test.yml
│   │   └── deploy.yml
│   └── PULL_REQUEST_TEMPLATE.md
├── docker/
│   ├── Dockerfile
│   └── docker-compose.yml
├── requirements/
│   ├── base.txt
│   ├── development.txt
│   └── production.txt
├── .env.example
├── .gitignore
├── Makefile
├── README.md
├── LICENSE
└── setup.py / pyproject.toml
```

---

## 10.4 — AI/ML Project Structure

```
ml_project/
├── data/
│   ├── raw/                    ← Original, unmodified data
│   ├── processed/              ← Cleaned, transformed data
│   ├── external/               ← Third-party data sources
│   └── interim/                ← Intermediate transformations
├── models/
│   ├── trained/                ← Saved model files (.pkl, .h5)
│   ├── experiments/            ← Experiment configs
│   └── deployment/             ← Production-ready models
├── notebooks/
│   ├── 01_EDA.ipynb            ← Exploratory Data Analysis
│   ├── 02_preprocessing.ipynb  ← Data preprocessing
│   ├── 03_modeling.ipynb       ← Model training
│   └── 04_evaluation.ipynb     ← Model evaluation
├── src/
│   └── mlproject/
│       ├── __init__.py
│       ├── data/
│       │   ├── make_dataset.py
│       │   └── preprocess.py
│       ├── features/
│       │   ├── build_features.py
│       │   └── feature_store.py
│       ├── models/
│       │   ├── train.py
│       │   ├── predict.py
│       │   └── evaluate.py
│       └── visualization/
│           └── plots.py
├── tests/
├── configs/
│   ├── model_config.yaml
│   └── training_config.yaml
├── scripts/
│   ├── train.sh
│   └── evaluate.sh
├── requirements.txt
├── setup.py
├── dvc.yaml                    ← Data Version Control
├── Makefile
└── README.md
```

---

## 10.5 — LLM/AI Agent Project Structure

```
llm_application/
├── src/
│   └── llmapp/
│       ├── __init__.py
│       ├── agents/
│       │   ├── __init__.py
│       │   ├── base_agent.py
│       │   ├── research_agent.py
│       │   └── coding_agent.py
│       ├── chains/
│       │   ├── __init__.py
│       │   └── rag_chain.py
│       ├── memory/
│       │   ├── __init__.py
│       │   └── conversation_memory.py
│       ├── tools/
│       │   ├── __init__.py
│       │   ├── search_tool.py
│       │   ├── calculator_tool.py
│       │   └── code_tool.py
│       ├── prompts/
│       │   ├── __init__.py
│       │   ├── system_prompts.py
│       │   └── few_shot_examples.py
│       ├── vectorstore/
│       │   ├── __init__.py
│       │   └── chroma_store.py
│       └── api/
│           ├── __init__.py
│           └── endpoints.py
├── data/
│   ├── documents/              ← RAG knowledge base
│   └── embeddings/             ← Cached embeddings
├── tests/
├── notebooks/
├── requirements.txt
├── .env.example                ← API keys template
└── README.md
```

---

<a name="section-11"></a>
# ⚙️ SECTION 11 — Python Execution Model

## 11.1 — How Python Executes Code

```
SOURCE CODE (.py)
      │
      ▼
┌─────────────────┐
│    TOKENIZER    │  → Breaks code into tokens
│   (Lexer)       │    (keywords, names, operators, literals)
└─────────────────┘
      │
      ▼
┌─────────────────┐
│    PARSER       │  → Builds Abstract Syntax Tree (AST)
│    (Syntax)     │    (tree structure of code)
└─────────────────┘
      │
      ▼
┌─────────────────┐
│    COMPILER     │  → Converts AST to bytecode
│   (Bytecode)    │    (.pyc files in __pycache__)
└─────────────────┘
      │
      ▼
┌─────────────────┐
│  PVM (Python    │  → Executes bytecode
│  Virtual        │    (CPython interpreter loop)
│  Machine)       │
└─────────────────┘
      │
      ▼
    OUTPUT
```

---

## 11.2 — Bytecode and `.pyc` Files

```python
# See bytecode for any function
import dis

def add(a, b):
    return a + b

dis.dis(add)

# Output:
#   2           0 RESUME                   0
#   3           2 LOAD_FAST                0 (a)
#               4 LOAD_FAST                1 (b)
#               6 BINARY_OP               0 (+)
#              10 RETURN_VALUE
```

```bash
# After importing a module, check __pycache__
ls __pycache__/

# Output:
# calculator.cpython-311.pyc
# string_utils.cpython-311.pyc
# ^module name  ^python version  ^bytecode

# The .pyc file is reused if .py hasn't changed
# Speeds up repeated imports significantly

# Force recompile
python -m py_compile calculator.py

# View .pyc info
python -c "import marshal, struct; f = open('__pycache__/calculator.cpython-311.pyc', 'rb'); f.read(16); code = marshal.load(f); print(code.co_consts)"
```

---

## 11.3 — Module Execution Flow

```python
# module_demo.py

print("1. Module top-level code runs on import")

x = 42
print(f"2. Variable x = {x}")

def setup():
    print("3. setup() called")

class Config:
    debug = False
    print("4. Class body runs on import")

print("5. End of module top-level")

if __name__ == "__main__":
    print("6. This only runs when executed directly")
    setup()
```

```bash
# When imported:
>>> import module_demo
1. Module top-level code runs on import
2. Variable x = 42
4. Class body runs on import
5. End of module top-level
# (6 does NOT run)

# When run directly:
$ python module_demo.py
1. Module top-level code runs on import
2. Variable x = 42
4. Class body runs on import
5. End of module top-level
6. This only runs when executed directly
3. setup() called
```

---

<a name="section-12"></a>
# 🔐 SECTION 12 — Environment Variables

## 12.1 — What are Environment Variables?

Environment variables are **key-value pairs** stored in the operating system that programs can access. They're perfect for:
- Configuration that changes between environments (dev/prod)
- Secrets (API keys, passwords) — never hardcode these!
- System paths and settings

```bash
# Setting environment variables (temporary — current session only)
export DATABASE_URL="postgresql://localhost:5432/mydb"
export SECRET_KEY="my-super-secret-key-123"
export DEBUG="True"
export PORT="8000"

# Viewing
echo $DATABASE_URL
env                             # List all environment variables
printenv DATABASE_URL           # Print specific variable
```

---

## 12.2 — Accessing Environment Variables in Python

```python
import os

# Basic access
db_url = os.environ["DATABASE_URL"]         # Raises KeyError if not found
secret = os.environ.get("SECRET_KEY")       # Returns None if not found
debug = os.environ.get("DEBUG", "False")    # Default value if not found
port = int(os.environ.get("PORT", "8000"))  # Convert to int with default

# Check if variable exists
if "API_KEY" not in os.environ:
    raise RuntimeError("API_KEY environment variable not set!")

# List all environment variables
for key, value in os.environ.items():
    print(f"{key}={value}")
```

---

## 12.3 — Using `.env` Files (Best Practice)

```bash
# .env file (NEVER commit to git!)
DATABASE_URL=postgresql://localhost:5432/myapp
SECRET_KEY=your-super-secret-key-here-change-in-production
DEBUG=True
PORT=8000
ALLOWED_HOSTS=localhost,127.0.0.1
OPENAI_API_KEY=sk-...your-key-here...
REDIS_URL=redis://localhost:6379/0
EMAIL_HOST=smtp.gmail.com
EMAIL_PORT=587
EMAIL_USER=your@email.com
EMAIL_PASSWORD=your-email-password
```

```bash
# .env.example (COMMIT THIS — shows what's needed, no real values)
DATABASE_URL=postgresql://localhost:5432/your_db_name
SECRET_KEY=your-secret-key-here
DEBUG=True
PORT=8000
OPENAI_API_KEY=your-openai-api-key
REDIS_URL=redis://localhost:6379/0
```

```python
# config.py — Using python-dotenv
from dotenv import load_dotenv
import os

# Load .env file
load_dotenv()                               # Loads from .env in current dir
load_dotenv(".env.local")                   # Custom file
load_dotenv(override=True)                  # Override existing env vars

# Now access normally
DATABASE_URL = os.getenv("DATABASE_URL")
SECRET_KEY = os.getenv("SECRET_KEY")
DEBUG = os.getenv("DEBUG", "False").lower() == "true"
PORT = int(os.getenv("PORT", "8000"))

# Settings class (professional pattern)
class Settings:
    def __init__(self):
        load_dotenv()
        self.DATABASE_URL = os.getenv("DATABASE_URL", "sqlite:///local.db")
        self.SECRET_KEY = os.getenv("SECRET_KEY", "dev-secret-change-in-prod")
        self.DEBUG = os.getenv("DEBUG", "False") == "True"
        self.PORT = int(os.getenv("PORT", "8000"))
        
        # Validate required settings
        if not self.SECRET_KEY or self.SECRET_KEY == "dev-secret-change-in-prod":
            if not self.DEBUG:
                raise ValueError("SECRET_KEY must be set in production!")
    
    def __repr__(self):
        return f"Settings(DEBUG={self.DEBUG}, PORT={self.PORT})"

settings = Settings()
```

---

## 12.4 — PYTHONPATH

```bash
# PYTHONPATH tells Python where to find modules
export PYTHONPATH=/path/to/my/project/src:/path/to/other/modules

# Now Python searches those directories
python -c "import mymodule"     # Works if mymodule is in PYTHONPATH

# Common use: running from project root
# Instead of dealing with imports, just set PYTHONPATH
cd /my/project
PYTHONPATH=src python -m myapp.main

# Or in .env
PYTHONPATH=src
```

---

<a name="section-13"></a>
# 🔄 SECTION 13 — Professional Development Workflow

## 13.1 — End-to-End Project Workflow

```bash
# ═══════════════════════════════════════════════
# STEP 1: PROJECT INITIALIZATION
# ═══════════════════════════════════════════════

mkdir my_awesome_project
cd my_awesome_project
git init
git branch -M main

# ═══════════════════════════════════════════════
# STEP 2: VIRTUAL ENVIRONMENT
# ═══════════════════════════════════════════════

python -m venv venv
source venv/bin/activate          # Linux/Mac
# venv\Scripts\activate           # Windows

# ═══════════════════════════════════════════════
# STEP 3: .GITIGNORE
# ═══════════════════════════════════════════════

cat > .gitignore << 'EOF'
# Virtual Environment
venv/
.venv/
env/

# Python
__pycache__/
*.py[cod]
*.pyc
*.pyd

# Environment files
.env
.env.local
.env.production

# IDE
.vscode/
.idea/
*.swp
*.swo

# OS
.DS_Store
Thumbs.db

# Testing
.pytest_cache/
.coverage
htmlcov/

# Distribution
dist/
build/
*.egg-info/
EOF

# ═══════════════════════════════════════════════
# STEP 4: PROJECT STRUCTURE
# ═══════════════════════════════════════════════

mkdir -p src/myproject tests docs scripts
touch src/myproject/__init__.py
touch src/myproject/main.py
touch tests/__init__.py
touch README.md
touch .env.example

# ═══════════════════════════════════════════════
# STEP 5: INSTALL DEPENDENCIES
# ═══════════════════════════════════════════════

pip install requests flask python-dotenv loguru
pip install pytest pytest-cov black flake8 --dev  # in reality, separate req file

pip freeze > requirements.txt

# ═══════════════════════════════════════════════
# STEP 6: WRITE CODE
# ═══════════════════════════════════════════════

# Write your actual application code...

# ═══════════════════════════════════════════════
# STEP 7: FORMAT & LINT
# ═══════════════════════════════════════════════

black src/                        # Auto-format code
flake8 src/                       # Lint for style errors
isort src/                        # Sort imports

# ═══════════════════════════════════════════════
# STEP 8: TEST
# ═══════════════════════════════════════════════

pytest tests/ -v                  # Run tests
pytest --cov=src tests/           # Run with coverage
pytest tests/ -v --tb=short       # Short traceback

# ═══════════════════════════════════════════════
# STEP 9: COMMIT
# ═══════════════════════════════════════════════

git add .
git commit -m "feat: initial project structure and core functionality"

# Conventional Commits format:
# feat: new feature
# fix: bug fix
# docs: documentation only
# style: formatting, no logic change
# refactor: code restructure
# test: adding tests
# chore: build process, tooling

# ═══════════════════════════════════════════════
# STEP 10: PUSH TO GITHUB
# ═══════════════════════════════════════════════

git remote add origin https://github.com/username/my_awesome_project.git
git push -u origin main

# ═══════════════════════════════════════════════
# STEP 11: VERSION RELEASE
# ═══════════════════════════════════════════════

git tag v1.0.0
git push origin v1.0.0
# Create GitHub Release with changelog
```

---

## 13.2 — Makefile for Project Automation

```makefile
# Makefile — Automate common tasks

.PHONY: install dev-install test lint format clean run

install:
	pip install -r requirements.txt

dev-install:
	pip install -r requirements/development.txt

test:
	pytest tests/ -v --cov=src --cov-report=html

lint:
	flake8 src/ tests/
	mypy src/

format:
	black src/ tests/
	isort src/ tests/

clean:
	find . -type f -name "*.pyc" -delete
	find . -type d -name "__pycache__" -delete
	find . -type d -name "*.egg-info" -exec rm -rf {} +
	rm -rf .pytest_cache .coverage htmlcov dist build

run:
	python src/myproject/main.py

setup-venv:
	python -m venv venv
	@echo "Run: source venv/bin/activate"
```

```bash
make install      # Install dependencies
make test         # Run tests with coverage
make format       # Auto-format code
make clean        # Clean build artifacts
```

---

<a name="section-14"></a>
# 🌐 SECTION 14 — Open Source Workflow

## 14.1 — Contributing to Open Source

```bash
# ═══════════════════════════════════════════════
# STEP 1: FORK THE REPOSITORY
# ═══════════════════════════════════════════════
# On GitHub: Click "Fork" button on the project page
# This creates a copy at: github.com/YOUR_USERNAME/project

# ═══════════════════════════════════════════════
# STEP 2: CLONE YOUR FORK
# ═══════════════════════════════════════════════
git clone https://github.com/YOUR_USERNAME/project.git
cd project

# Add upstream (original repo) as remote
git remote add upstream https://github.com/ORIGINAL_OWNER/project.git
git remote -v   # Verify: origin=your fork, upstream=original

# ═══════════════════════════════════════════════
# STEP 3: CREATE A BRANCH
# ═══════════════════════════════════════════════
git checkout -b feature/add-json-export
# or
git checkout -b fix/login-timeout-bug
# or
git checkout -b docs/improve-readme

# ═══════════════════════════════════════════════
# STEP 4: MAKE CHANGES
# ═══════════════════════════════════════════════
# Set up development environment
python -m venv venv
source venv/bin/activate
pip install -e ".[dev]"   # Install in editable mode with dev deps

# Write code, add tests, update docs

# ═══════════════════════════════════════════════
# STEP 5: TEST YOUR CHANGES
# ═══════════════════════════════════════════════
pytest tests/ -v
flake8 src/
black --check src/

# ═══════════════════════════════════════════════
# STEP 6: COMMIT
# ═══════════════════════════════════════════════
git add .
git commit -m "feat: add JSON export functionality to data module"

# ═══════════════════════════════════════════════
# STEP 7: SYNC WITH UPSTREAM
# ═══════════════════════════════════════════════
git fetch upstream
git rebase upstream/main   # or: git merge upstream/main

# ═══════════════════════════════════════════════
# STEP 8: PUSH YOUR BRANCH
# ═══════════════════════════════════════════════
git push origin feature/add-json-export

# ═══════════════════════════════════════════════
# STEP 9: CREATE PULL REQUEST
# ═══════════════════════════════════════════════
# On GitHub: "Compare & pull request" button appears
# Fill in: title, description, related issue number
# Add screenshots if UI changes
# Request reviewers

# ═══════════════════════════════════════════════
# STEP 10: ADDRESS REVIEW FEEDBACK
# ═══════════════════════════════════════════════
git add .
git commit -m "fix: address review feedback - handle edge case"
git push origin feature/add-json-export
# PR auto-updates

# ═══════════════════════════════════════════════
# STEP 11: MERGE (done by maintainer)
# ═══════════════════════════════════════════════
# After approval: maintainer merges your PR!
# Celebrate! 🎉 You're an open source contributor!

# Clean up
git checkout main
git pull upstream main
git branch -d feature/add-json-export
```

---

<a name="section-15"></a>
# 🐛 SECTION 15 — Debugging Modules

## 15.1 — Common Import Errors

```python
# ─────────────── ModuleNotFoundError ───────────────
# Error: No module named 'requests'
# Fix:
pip install requests

# Or in code, handle gracefully:
try:
    import requests
except ModuleNotFoundError:
    print("requests not installed. Run: pip install requests")
    import sys
    sys.exit(1)

# ─────────────── ImportError ───────────────
# Error: cannot import name 'magic_function' from 'requests'
# Fix: Check the correct function name
import requests
print(dir(requests))   # See what's actually in requests

# ─────────────── Wrong directory ───────────────
# Your module is in /home/user/mymodule.py
# But you're running from /home/user/other/
# Python can't find it!

# Fix 1: Run from correct directory
cd /home/user && python script.py

# Fix 2: Add to sys.path
import sys
sys.path.insert(0, "/home/user")
import mymodule

# Fix 3: Set PYTHONPATH
PYTHONPATH=/home/user python script.py
```

---

## 15.2 — Circular Import Problem

```python
# CIRCULAR IMPORT — The Problem

# module_a.py
from module_b import func_b    # Imports module_b

def func_a():
    return "Function A"

# module_b.py
from module_a import func_a    # Imports module_a — CIRCULAR!

def func_b():
    return func_a()

# When you run either module:
# ImportError: cannot import name 'func_a' from partially initialized module 'module_a'

# ─────────────── FIX 1: Import inside function ───────────────
# module_b.py
def func_b():
    from module_a import func_a    # Import when needed, not at top
    return func_a()

# ─────────────── FIX 2: Create third module ───────────────
# common.py — shared code
def shared_function():
    return "Shared"

# module_a.py
from common import shared_function

# module_b.py
from common import shared_function

# ─────────────── FIX 3: Restructure architecture ───────────────
# Usually circular imports signal design problems
# Refactor so dependencies flow in one direction:
# models → services → api (not the other way)
```

---

## 15.3 — Virtual Environment Debugging

```bash
# ─────────────── Wrong interpreter ───────────────
which python                    # Check which Python you're using
which pip                       # Check which pip

# If not showing venv path, venv is not activated
source venv/bin/activate        # Activate!

# ─────────────── Packages installed but not found ───────────────
# You installed with pip but module not found
# Likely: you installed in wrong environment

python -m pip install requests  # Always use: python -m pip
# This ensures you install for the CURRENT python

# ─────────────── Verify package location ───────────────
python -c "import requests; print(requests.__file__)"
# Should show path inside your venv

# ─────────────── Recreate corrupted venv ───────────────
deactivate
rm -rf venv/
python -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```

---

<a name="section-16"></a>
# ✨ SECTION 16 — Best Practices

## 16.1 — Import Organization (PEP 8)

```python
# CORRECT ORDER (PEP 8):

# 1. Standard library imports (alphabetical)
import json
import os
import sys
from collections import defaultdict
from datetime import datetime
from pathlib import Path

# 2. Third-party imports (alphabetical)
import numpy as np
import pandas as pd
import requests
from flask import Flask, jsonify
from loguru import logger

# 3. Local application imports (alphabetical)
from myproject.config import settings
from myproject.models.user import User
from myproject.utils.validators import validate_email

# Use isort to auto-organize:
# pip install isort
# isort your_file.py
```

---

## 16.2 — Module Naming Conventions

```python
# ✅ GOOD Names
import calculator              # lowercase, descriptive
import string_utils            # lowercase with underscores
import data_processor          # snake_case
from mypackage import helpers

# ❌ BAD Names
import Calculator              # PascalCase (reserved for classes)
import stringUtils             # camelCase (not Pythonic)
import su                      # Too abbreviated
import my_string_utility_helper_module  # Too long

# Package names
mypackage/      # ✅ lowercase
my_package/     # ✅ with underscore
MyPackage/      # ❌ PascalCase

# Class names in modules: PascalCase
class UserManager:    # ✅
class userManager:    # ❌

# Function/variable names in modules: snake_case
def process_data():   # ✅
def ProcessData():    # ❌
```

---

## 16.3 — `__all__` — Controlling Public API

```python
# mypackage/utils.py

# Define public API — what gets exported with: from utils import *
__all__ = [
    "clean_text",
    "count_words",
    "validate_email",
    # NOT included: _private_helper, _internal_cache
]

def clean_text(text):
    """Public function — in __all__."""
    return text.strip().lower()

def count_words(text):
    """Public function — in __all__."""
    return len(text.split())

def validate_email(email):
    """Public function — in __all__."""
    import re
    return bool(re.match(r'^[\w.-]+@[\w.-]+\.\w{2,}$', email))

def _private_helper(data):
    """Private function — NOT in __all__, prefixed with _."""
    return data

_internal_cache = {}    # Private variable — underscore prefix
```

---

## 16.4 — Professional `.gitignore`

```gitignore
# Python
__pycache__/
*.py[cod]
*$py.class
*.so
.Python
build/
develop-eggs/
dist/
downloads/
eggs/
.eggs/
lib/
lib64/
parts/
sdist/
var/
wheels/
*.egg-info/
.installed.cfg
*.egg
MANIFEST

# Virtual Environments
venv/
ENV/
env/
.venv/
.env/
env.bak/
venv.bak/

# Environment Variables
.env
.env.local
.env.production
.env.staging
*.env

# Testing
.pytest_cache/
.coverage
htmlcov/
.tox/
nosetests.xml
coverage.xml
*.cover

# IDE
.vscode/
.idea/
*.swp
*.swo
*~
.project
.pydevproject

# OS
.DS_Store
.DS_Store?
._*
.Spotlight-V100
.Trashes
ehthumbs.db
Thumbs.db

# Jupyter
.ipynb_checkpoints/
*.ipynb_checkpoints

# Distribution
*.whl

# Logs
*.log
logs/

# Data (be careful — sometimes you DO want to commit data)
data/raw/
data/processed/
*.csv
*.sqlite
*.db
```

---

<a name="section-17"></a>
# 🔨 SECTION 17 — Mini Projects (Complete Code)

## Project 1: Calculator Package

```
calculator_package/
├── __init__.py
├── basic.py
├── scientific.py
└── financial.py
```

```python
# calculator_package/__init__.py
"""
Calculator Package v1.0.0
==========================
Professional calculator with basic, scientific, and financial operations.
"""
__version__ = "1.0.0"
from .basic import add, subtract, multiply, divide
from .scientific import sqrt, power, factorial, log
from .financial import simple_interest, compound_interest, emi

# calculator_package/basic.py
def add(a, b): return a + b
def subtract(a, b): return a - b
def multiply(a, b): return a * b
def divide(a, b):
    if b == 0: raise ZeroDivisionError("Cannot divide by zero")
    return a / b
def modulo(a, b): return a % b
def integer_divide(a, b): return a // b
def absolute(a): return abs(a)

# calculator_package/scientific.py
import math
def sqrt(n):
    if n < 0: raise ValueError("Cannot compute sqrt of negative number")
    return math.sqrt(n)
def power(base, exp): return math.pow(base, exp)
def factorial(n): return math.factorial(n)
def log(x, base=math.e): return math.log(x, base)
def sin(angle_deg): return math.sin(math.radians(angle_deg))
def cos(angle_deg): return math.cos(math.radians(angle_deg))
def tan(angle_deg): return math.tan(math.radians(angle_deg))
def combinations(n, r): return math.comb(n, r)
def permutations(n, r): return math.perm(n, r)

# calculator_package/financial.py
def simple_interest(principal, rate, time):
    """SI = P × R × T / 100"""
    return (principal * rate * time) / 100

def compound_interest(principal, rate, time, n=12):
    """CI = P(1 + r/n)^(nt) - P"""
    r = rate / 100
    amount = principal * (1 + r/n) ** (n * time)
    return round(amount - principal, 2)

def emi(principal, annual_rate, months):
    """EMI = P × r × (1+r)^n / ((1+r)^n - 1)"""
    import math
    r = annual_rate / (12 * 100)
    return round(principal * r * math.pow(1+r, months) / (math.pow(1+r, months) - 1), 2)

def profit_loss(cost, selling):
    """Calculate profit/loss and percentage."""
    pl = selling - cost
    pct = (pl / cost) * 100
    return {
        "profit_loss": round(pl, 2),
        "percentage": round(pct, 2),
        "type": "Profit" if pl > 0 else "Loss" if pl < 0 else "Break Even"
    }

# Usage Demo
if __name__ == "__main__":
    import calculator_package as calc
    
    print("=== Basic Calculator ===")
    print(f"10 + 5 = {calc.add(10, 5)}")
    print(f"20 - 8 = {calc.subtract(20, 8)}")
    print(f"4 × 7 = {calc.multiply(4, 7)}")
    print(f"100 ÷ 4 = {calc.divide(100, 4)}")
    
    print("\n=== Scientific Calculator ===")
    print(f"√144 = {calc.sqrt(144)}")
    print(f"2^10 = {calc.power(2, 10)}")
    print(f"10! = {calc.factorial(10)}")
    print(f"log(1000) = {calc.log(1000, 10)}")
    
    print("\n=== Financial Calculator ===")
    print(f"SI: ₹{calc.simple_interest(100000, 8, 3)}")
    print(f"CI: ₹{calc.compound_interest(100000, 8, 3)}")
    print(f"EMI: ₹{calc.emi(500000, 8.5, 60)}/month")
```

---

## Project 2: Text Processing Package

```python
# textpro/__init__.py
"""TextPro — Professional Text Processing Toolkit"""
__version__ = "1.0.0"

# textpro/cleaner.py
import re
import string

def remove_punctuation(text):
    return text.translate(str.maketrans('', '', string.punctuation))

def remove_numbers(text):
    return re.sub(r'\d+', '', text)

def remove_extra_spaces(text):
    return re.sub(r'\s+', ' ', text).strip()

def remove_html_tags(text):
    return re.sub(r'<[^>]+>', '', text)

def clean(text, remove_punct=True, remove_nums=False, lowercase=True):
    if lowercase:
        text = text.lower()
    if remove_punct:
        text = remove_punctuation(text)
    if remove_nums:
        text = remove_numbers(text)
    return remove_extra_spaces(text)

# textpro/analyzer.py
from collections import Counter
import re

def word_count(text):
    return len(text.split())

def char_count(text, include_spaces=True):
    if include_spaces:
        return len(text)
    return len(text.replace(' ', ''))

def sentence_count(text):
    return len(re.split(r'[.!?]+', text.strip()))

def word_frequency(text, top_n=None):
    words = text.lower().split()
    freq = Counter(words)
    if top_n:
        return dict(freq.most_common(top_n))
    return dict(freq)

def average_word_length(text):
    words = text.split()
    if not words:
        return 0
    return sum(len(w) for w in words) / len(words)

def reading_time_minutes(text, wpm=200):
    return round(word_count(text) / wpm, 1)

def flesch_reading_ease(text):
    """Estimate readability score."""
    words = text.split()
    sentences = re.split(r'[.!?]+', text)
    syllables = sum(_count_syllables(w) for w in words)
    
    if not words or not sentences:
        return 0
    
    score = 206.835 - 1.015 * (len(words)/len(sentences)) - 84.6 * (syllables/len(words))
    return round(score, 2)

def _count_syllables(word):
    word = word.lower().strip(".,!?")
    if len(word) <= 3:
        return 1
    vowels = "aeiou"
    count = sum(1 for i, c in enumerate(word) if c in vowels and (i == 0 or word[i-1] not in vowels))
    if word.endswith('e'):
        count -= 1
    return max(count, 1)

# Usage
if __name__ == "__main__":
    import textpro.cleaner as cleaner
    import textpro.analyzer as analyzer
    
    text = """
    Python is a versatile programming language. It is used for web development,
    data science, artificial intelligence, and automation. Python's simple syntax
    makes it perfect for beginners!
    """
    
    cleaned = cleaner.clean(text)
    print(f"Words: {analyzer.word_count(cleaned)}")
    print(f"Characters: {analyzer.char_count(cleaned)}")
    print(f"Sentences: {analyzer.sentence_count(text)}")
    print(f"Reading time: {analyzer.reading_time_minutes(text)} minutes")
    print(f"Top words: {analyzer.word_frequency(cleaned, top_n=5)}")
    print(f"Avg word length: {analyzer.average_word_length(cleaned):.1f}")
```

---

## Project 3: Random Password Generator

```python
# passgen.py — Password Generator Module

"""
Password Generator Module
=========================
Generate secure, customizable passwords for any use case.
"""

import random
import string
import secrets    # Cryptographically secure!
import re


def generate(
    length=16,
    use_uppercase=True,
    use_lowercase=True,
    use_digits=True,
    use_symbols=True,
    exclude_chars="",
    min_uppercase=1,
    min_lowercase=1,
    min_digits=1,
    min_symbols=1
):
    """
    Generate a secure password with customizable requirements.
    
    Uses secrets module for cryptographic security.
    """
    # Build character pool
    pool = ""
    required = []
    
    if use_uppercase:
        chars = ''.join(c for c in string.ascii_uppercase if c not in exclude_chars)
        pool += chars
        required.extend(secrets.choice(chars) for _ in range(min_uppercase))
    
    if use_lowercase:
        chars = ''.join(c for c in string.ascii_lowercase if c not in exclude_chars)
        pool += chars
        required.extend(secrets.choice(chars) for _ in range(min_lowercase))
    
    if use_digits:
        chars = ''.join(c for c in string.digits if c not in exclude_chars)
        pool += chars
        required.extend(secrets.choice(chars) for _ in range(min_digits))
    
    if use_symbols:
        symbols = "!@#$%^&*()_+-=[]{}|;:,.<>?"
        chars = ''.join(c for c in symbols if c not in exclude_chars)
        pool += chars
        required.extend(secrets.choice(chars) for _ in range(min_symbols))
    
    if not pool:
        raise ValueError("At least one character type must be selected!")
    
    # Fill remaining length
    remaining = length - len(required)
    if remaining < 0:
        raise ValueError(f"Length {length} is too short for requirements")
    
    password_chars = required + [secrets.choice(pool) for _ in range(remaining)]
    
    # Shuffle to avoid required chars being in predictable positions
    secrets.SystemRandom().shuffle(password_chars)
    
    return ''.join(password_chars)


def generate_pin(digits=6):
    """Generate a numeric PIN."""
    return ''.join(secrets.choice(string.digits) for _ in range(digits))


def generate_memorable(words=3, separator="-"):
    """Generate a memorable passphrase (like 'correct-horse-battery')."""
    wordlist = [
        "apple", "brave", "cloud", "dance", "earth", "flame", "grace", "heart",
        "ivory", "jewel", "karma", "light", "magic", "noble", "ocean", "peace",
        "quest", "river", "storm", "tiger", "unity", "vapor", "water", "xenon",
        "yacht", "zebra", "amber", "blaze", "coral", "delta"
    ]
    selected = [secrets.choice(wordlist) for _ in range(words)]
    return separator.join(selected)


def check_strength(password):
    """
    Evaluate password strength.
    Returns: dict with score (0-100) and feedback
    """
    score = 0
    feedback = []
    
    # Length scoring
    if len(password) >= 8:
        score += 20
    if len(password) >= 12:
        score += 10
    if len(password) >= 16:
        score += 10
    else:
        feedback.append("Use at least 16 characters for strong security")
    
    # Character diversity
    if re.search(r'[a-z]', password):
        score += 15
    else:
        feedback.append("Add lowercase letters")
    
    if re.search(r'[A-Z]', password):
        score += 15
    else:
        feedback.append("Add uppercase letters")
    
    if re.search(r'\d', password):
        score += 15
    else:
        feedback.append("Add digits")
    
    if re.search(r'[!@#$%^&*()_+\-=\[\]{}|;:,.<>?]', password):
        score += 15
    else:
        feedback.append("Add special characters (!@#$%)")
    
    # Determine label
    if score >= 85:
        label = "🟢 Very Strong"
    elif score >= 70:
        label = "🟡 Strong"
    elif score >= 50:
        label = "🟠 Moderate"
    else:
        label = "🔴 Weak"
    
    return {
        "score": score,
        "label": label,
        "feedback": feedback
    }


def generate_bulk(count=10, **kwargs):
    """Generate multiple passwords at once."""
    return [generate(**kwargs) for _ in range(count)]


if __name__ == "__main__":
    print("=" * 50)
    print("🔐 PASSWORD GENERATOR")
    print("=" * 50)
    
    # Standard password
    pwd = generate(16)
    print(f"\n📌 Standard (16 chars): {pwd}")
    
    # No symbols (for systems that don't support them)
    pwd2 = generate(20, use_symbols=False)
    print(f"📌 No Symbols (20): {pwd2}")
    
    # Only letters and numbers
    pwd3 = generate(12, use_symbols=False)
    print(f"📌 Alphanumeric (12): {pwd3}")
    
    # PIN
    pin = generate_pin(6)
    print(f"📌 6-digit PIN: {pin}")
    
    # Memorable passphrase
    phrase = generate_memorable(4, "-")
    print(f"📌 Passphrase: {phrase}")
    
    # Check strength
    test_pwd = "Hello123!"
    strength = check_strength(test_pwd)
    print(f"\n🔍 Strength of '{test_pwd}':")
    print(f"   Score: {strength['score']}/100 — {strength['label']}")
    for tip in strength['feedback']:
        print(f"   💡 {tip}")
    
    print("\n📦 Bulk Generated (5 passwords):")
    for i, p in enumerate(generate_bulk(5, length=14), 1):
        print(f"   {i}. {p}")
```

---

## Project 4: System Information Tool

```python
# sysinfo.py — System Information Module

"""
System Information Toolkit
===========================
Comprehensive system monitoring and information gathering.
"""

import os
import sys
import platform
import datetime


def get_python_info():
    """Get Python interpreter information."""
    return {
        "version": platform.python_version(),
        "implementation": platform.python_implementation(),
        "compiler": platform.python_compiler(),
        "build": platform.python_build(),
        "executable": sys.executable,
        "path": sys.path,
        "version_info": {
            "major": sys.version_info.major,
            "minor": sys.version_info.minor,
            "micro": sys.version_info.micro,
        }
    }


def get_os_info():
    """Get operating system information."""
    uname = platform.uname()
    return {
        "system": platform.system(),
        "node": platform.node(),
        "release": platform.release(),
        "version": platform.version(),
        "machine": platform.machine(),
        "processor": platform.processor(),
        "architecture": platform.architecture()[0],
        "hostname": uname.node,
    }


def get_environment_info():
    """Get environment variables summary."""
    important_vars = ["HOME", "USER", "PATH", "PYTHONPATH", "VIRTUAL_ENV", "CONDA_DEFAULT_ENV"]
    env_info = {}
    for var in important_vars:
        value = os.environ.get(var, "Not Set")
        if var == "PATH":
            value = os.environ.get(var, "").split(os.pathsep)[:5]  # First 5 only
        env_info[var] = value
    return env_info


def get_disk_usage(path="."):
    """Get disk usage for a path."""
    try:
        stat = os.statvfs(path) if hasattr(os, 'statvfs') else None
        if stat:
            total = stat.f_blocks * stat.f_frsize
            free = stat.f_bavail * stat.f_frsize
            used = total - free
            return {
                "total_gb": round(total / (1024**3), 2),
                "used_gb": round(used / (1024**3), 2),
                "free_gb": round(free / (1024**3), 2),
                "usage_pct": round((used / total) * 100, 1) if total > 0 else 0
            }
    except Exception:
        pass
    return {"error": "Disk info unavailable on this platform"}


def get_installed_packages():
    """Get list of installed Python packages."""
    try:
        import subprocess
        result = subprocess.run(
            [sys.executable, "-m", "pip", "list", "--format=json"],
            capture_output=True, text=True
        )
        import json
        packages = json.loads(result.stdout)
        return [{"name": p["name"], "version": p["version"]} for p in packages]
    except Exception as e:
        return [{"error": str(e)}]


def get_full_report():
    """Generate complete system report."""
    return {
        "timestamp": datetime.datetime.now().isoformat(),
        "python": get_python_info(),
        "os": get_os_info(),
        "environment": get_environment_info(),
        "disk": get_disk_usage(),
    }


def print_report():
    """Pretty print the system report."""
    report = get_full_report()
    
    print("=" * 60)
    print("🖥️  SYSTEM INFORMATION REPORT")
    print(f"📅 Generated: {report['timestamp']}")
    print("=" * 60)
    
    print("\n🐍 PYTHON:")
    py = report["python"]
    print(f"   Version: {py['version']}")
    print(f"   Implementation: {py['implementation']}")
    print(f"   Executable: {py['executable']}")
    
    print("\n💻 OPERATING SYSTEM:")
    os_info = report["os"]
    print(f"   System: {os_info['system']}")
    print(f"   Node: {os_info['node']}")
    print(f"   Release: {os_info['release']}")
    print(f"   Machine: {os_info['machine']}")
    print(f"   Architecture: {os_info['architecture']}")
    
    print("\n🌍 ENVIRONMENT:")
    for key, value in report["environment"].items():
        if isinstance(value, list):
            print(f"   {key}: {value[0]}... (+ more)")
        else:
            print(f"   {key}: {value}")
    
    print("\n💾 DISK USAGE:")
    disk = report["disk"]
    if "error" not in disk:
        print(f"   Total: {disk['total_gb']} GB")
        print(f"   Used:  {disk['used_gb']} GB ({disk['usage_pct']}%)")
        print(f"   Free:  {disk['free_gb']} GB")
    
    print("\n" + "=" * 60)


if __name__ == "__main__":
    print_report()
```

---

## Project 5: JSON Utility Toolkit

```python
# jsonutil.py — JSON Utility Toolkit

"""
JSON Utility Toolkit
====================
Read, write, validate, transform, and query JSON data.
"""

import json
import os
from pathlib import Path
from datetime import datetime


def read(filepath, encoding="utf-8"):
    """Read JSON from file."""
    with open(filepath, "r", encoding=encoding) as f:
        return json.load(f)


def write(data, filepath, indent=2, ensure_ascii=False, encoding="utf-8"):
    """Write data to JSON file."""
    Path(filepath).parent.mkdir(parents=True, exist_ok=True)
    with open(filepath, "w", encoding=encoding) as f:
        json.dump(data, f, indent=indent, ensure_ascii=ensure_ascii, default=str)


def parse(json_string):
    """Parse JSON string to Python object."""
    return json.loads(json_string)


def stringify(data, indent=None, compact=False):
    """Convert Python object to JSON string."""
    if compact:
        return json.dumps(data, separators=(',', ':'))
    return json.dumps(data, indent=indent, ensure_ascii=False, default=str)


def pretty_print(data, indent=2):
    """Print JSON in human-readable format."""
    print(json.dumps(data, indent=indent, ensure_ascii=False, default=str))


