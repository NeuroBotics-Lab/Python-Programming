# 🐍 Python Mastery — Day 01: The Foundation
### *From Zero to Python Hero — Industry-Grade Learning Document*

> **Author:** Python Mastery Series | **Level:** Absolute Beginner → Intermediate  
> **Goal:** Build an unbreakable Python foundation for Software Engineering, DSA, AI/ML, and LLM Engineering  
> **Estimated Time:** 8–12 Hours (Read + Practice)

---

```
██████╗ ██╗   ██╗████████╗██╗  ██╗ ██████╗ ███╗   ██╗
██╔══██╗╚██╗ ██╔╝╚══██╔══╝██║  ██║██╔═══██╗████╗  ██║
██████╔╝ ╚████╔╝    ██║   ███████║██║   ██║██╔██╗ ██║
██╔═══╝   ╚██╔╝     ██║   ██╔══██║██║   ██║██║╚██╗██║
██║        ██║      ██║   ██║  ██║╚██████╔╝██║ ╚████║
╚═╝        ╚═╝      ╚═╝   ╚═╝  ╚═╝ ╚═════╝ ╚═╝  ╚═══╝
                    DAY 01 — THE FOUNDATION
```

---

## 📋 Table of Contents

| # | Section | Topics |
|---|---------|--------|
| 01 | [Introduction to Programming](#section-1) | What is Code, Binary, Compiler vs Interpreter |
| 02 | [Introduction to Python](#section-2) | History, Ecosystem, Use Cases |
| 03 | [First Python Program](#section-3) | Hello World, print() deep dive |
| 04 | [Python Execution Flow](#section-4) | Interpreter → Bytecode → PVM |
| 05 | [Comments](#section-5) | Single-line, Multi-line |
| 06 | [Variables](#section-6) | Memory, Dynamic Typing, Naming |
| 07 | [Data Types](#section-7) | int, float, complex, str, bool, NoneType |
| 08 | [Type Checking](#section-8) | type(), id() |
| 09 | [Input and Output](#section-9) | input(), print() |
| 10 | [Type Casting](#section-10) | int(), float(), str(), bool() |
| 11 | [Operators](#section-11) | All 7 operator categories |
| 12 | [Strings Deep Dive](#section-12) | Indexing, Slicing, 30+ Methods |
| 13 | [Python Memory Model](#section-13) | Objects, References, GC |
| 14 | [Debugging Basics](#section-14) | Syntax, Runtime, Logical Errors |
| 15 | [Best Practices](#section-15) | PEP 8, Clean Code |
| 16 | [Common Beginner Mistakes](#section-16) | Top 15 Pitfalls |
| 17 | [100 Practice Questions](#section-17) | Easy / Medium / Advanced |
| 18 | [50 Interview Questions](#section-18) | With Answers |
| 19 | [Assignments](#section-19) | 3 Assignments + Solutions |
| 20 | [Mini Projects](#section-20) | 5 Complete Projects |
| 21 | [Revision Notes](#section-21) | Cheat Sheet + Mind Map |
| 22 | [Day 02 Roadmap](#section-22) | What's Next |

---

<a name="section-1"></a>
## 🖥️ Section 1 — Introduction to Programming

### 1.1 What is Programming?

**Definition:**  
Programming is the act of giving a computer a set of precise, step-by-step instructions to solve a problem or perform a task.

**Real World Analogy:**  
Imagine you want to teach someone to make tea. You would say:
1. Boil water
2. Add tea leaves
3. Wait 3 minutes
4. Add sugar
5. Pour into cup

This is a **program** — a set of ordered instructions. Computers work the same way, except they need instructions in a language they understand.

> 💡 **Key Insight:** Computers are dumb but extremely fast. They do exactly what you tell them — nothing more, nothing less. Your job as a programmer is to write perfect instructions.

---

### 1.2 What is a Program?

A **program** is a collection of instructions stored in a file that a computer can execute to perform a specific task.

| Term | Meaning | Example |
|------|---------|---------|
| Program | Set of instructions | WhatsApp app |
| Source Code | Human-readable instructions | `print("Hello")` |
| Executable | Machine-ready program | `.exe`, `.out` file |
| Script | Small program file | `hello.py` |

---

### 1.3 What is Software vs Hardware?

```
┌─────────────────────────────────────────────┐
│                  COMPUTER                   │
│                                             │
│  ┌──────────────┐    ┌──────────────────┐   │
│  │   HARDWARE   │    │     SOFTWARE     │   │
│  │              │    │                  │   │
│  │  CPU         │◄───│  Operating System│   │
│  │  RAM         │    │  Applications    │   │
│  │  Hard Drive  │    │  Python Programs │   │
│  │  Keyboard    │    │  Games, Apps     │   │
│  └──────────────┘    └──────────────────┘   │
└─────────────────────────────────────────────┘
```

- **Hardware** = Physical parts you can touch (CPU, RAM, screen)
- **Software** = Programs and instructions (Windows, Python, Chrome)

---

### 1.4 How Computers Understand Instructions — Binary Basics

Computers are made of billions of tiny switches called **transistors**. Each switch is either:
- **ON** = `1`
- **OFF** = `0`

This is called **Binary** (Base-2 number system).

```
Everything in a computer is ultimately 0s and 1s:

Letter 'A'  →  01000001
Number 65   →  01000001
Color Red   →  11111111 00000000 00000000
```

**Binary to Decimal:**

| Binary | Decimal |
|--------|---------|
| 0001   | 1       |
| 0010   | 2       |
| 0100   | 4       |
| 1000   | 8       |
| 1010   | 10      |
| 1111   | 15      |

> 🧠 **Memory Trick:** Binary is like a row of light switches. Each switch doubles the value: 1, 2, 4, 8, 16, 32, 64, 128...

---

### 1.5 Compiler vs Interpreter

| Feature | Compiler | Interpreter |
|---------|----------|-------------|
| Translates | Entire program at once | Line by line |
| Speed | Faster execution | Slower execution |
| Error reporting | After full compilation | Stops at first error |
| Output | Executable file | Direct output |
| Languages | C, C++, Go | Python, JavaScript, Ruby |
| Example | `gcc hello.c -o hello` | `python hello.py` |

```
COMPILER FLOW:
Source Code → Compiler → Machine Code (.exe) → CPU → Output

INTERPRETER FLOW:
Source Code → Interpreter → [translates line by line] → CPU → Output
```

> **Python uses an Interpreter** — this is why Python is beginner-friendly. Errors are shown immediately, line by line.

---

### 1.6 Why Python Was Created

- **Year:** 1991
- **Creator:** Guido van Rossum (Netherlands)
- **Problem it solved:** Existing languages (C, C++) were complex and hard to read
- **Goal:** Create a language that reads like English, is easy to learn, yet powerful

> 💬 Guido van Rossum wanted a language that was fun and productive — hence the name "Python" (inspired by the British comedy group *Monty Python's Flying Circus*, NOT the snake!).

---

<a name="section-2"></a>
## 🐍 Section 2 — Introduction to Python

### 2.1 What is Python?

Python is a **high-level, interpreted, general-purpose programming language** that emphasizes code readability and simplicity.

| Property | Detail |
|----------|--------|
| Type | Interpreted, Dynamically Typed |
| Paradigm | OOP, Functional, Procedural |
| Created | 1991 |
| Creator | Guido van Rossum |
| Current Version | Python 3.12+ |
| License | Open Source (PSF License) |
| Website | python.org |

---

### 2.2 History of Python

```
Timeline:
──────────────────────────────────────────────────────────
1989 │ Guido van Rossum begins Python over Christmas holidays
1991 │ Python 0.9.0 released (first public version)
1994 │ Python 1.0 — lambda, map, filter added
2000 │ Python 2.0 — list comprehensions, garbage collection
2008 │ Python 3.0 — major overhaul, broke backward compatibility
2020 │ Python 2 officially retired
2024 │ Python 3.12+ — current stable, fastest Python ever
──────────────────────────────────────────────────────────
```

---

### 2.3 Why Python is Popular

```
Python Popularity Factors:

  ┌─────────────────────────────────────────┐
  │  1. Simple, English-like syntax         │
  │  2. Huge standard library               │
  │  3. Massive ecosystem (PyPI: 500k+ pkgs)│
  │  4. Dominant in AI/ML/Data Science      │
  │  5. Active community (millions of devs) │
  │  6. Cross-platform (Win/Mac/Linux)      │
  │  7. Free and Open Source                │
  │  8. Versatile — web, scripts, AI, games │
  └─────────────────────────────────────────┘
```

**TIOBE Index:** Python has been the #1 programming language globally since 2022.

---

### 2.4 Python Use Cases — The Full Ecosystem

| Domain | Tools/Libraries | Companies Using |
|--------|----------------|-----------------|
| **Web Development** | Django, Flask, FastAPI | Instagram, Pinterest |
| **Data Science** | Pandas, NumPy, Matplotlib | Google, Netflix |
| **Machine Learning** | scikit-learn, XGBoost | Spotify, Uber |
| **Deep Learning** | PyTorch, TensorFlow, JAX | OpenAI, Meta, Google |
| **LLM Engineering** | LangChain, LlamaIndex, HuggingFace | Anthropic, OpenAI |
| **Automation** | Selenium, PyAutoGUI, Playwright | Any company |
| **Cybersecurity** | Scapy, Impacket, pwntools | Security firms |
| **DevOps** | Ansible, Fabric, boto3 | AWS, Azure |
| **Game Development** | Pygame, Pyglet | Indie studios |
| **Desktop Apps** | Tkinter, PyQt, Kivy | Enterprises |

---

### 2.5 Python Roadmap Overview

```
PYTHON LEARNING ROADMAP:

Day 01  → Fundamentals (Variables, Types, Operators, Strings)
Day 02  → Control Flow (if/else, loops)
Day 03  → Functions (def, args, kwargs, recursion)
Day 04  → Data Structures (List, Tuple, Set, Dict)
Day 05  → File I/O + Error Handling
Day 06  → OOP (Classes, Objects, Inheritance)
Day 07  → Modules, Packages, Virtual Environments
Day 08  → Advanced Python (Generators, Decorators, Context Managers)
Day 09  → DSA in Python (Sorting, Searching, Linked Lists)
Day 10+ → NumPy, Pandas, PyTorch, LLM Engineering...
```

---

<a name="section-3"></a>
## 💻 Section 3 — Your First Python Program

### 3.1 Hello World

```python
print("Hello, World!")
```

**Output:**
```
Hello, World!
```

Simple. Powerful. Let's break it down completely.

---

### 3.2 Anatomy of `print("Hello, World!")`

```
print ( "Hello, World!" )
  │     │               │
  │     │               └── Closing parenthesis
  │     │
  │     └── String argument inside quotes
  │
  └── Built-in function name
```

| Part | Name | Purpose |
|------|------|---------|
| `print` | Function name | Tells Python to display output |
| `()` | Parentheses | Contains what to display |
| `"Hello, World!"` | String literal | The text to display |
| `""` | Double quotes | Marks the start/end of text |

---

### 3.3 What is a String?

A **string** is any text surrounded by quotes. Python accepts three forms:

```python
print("Hello")        # Double quotes
print('Hello')        # Single quotes
print("""Hello""")    # Triple double quotes
print('''Hello''')    # Triple single quotes
```

All four lines produce the same output: `Hello`

---

### 3.4 print() — More Than Basics

```python
# Print multiple items
print("Name:", "Alice", "Age:", 20)
# Output: Name: Alice Age: 20

# Custom separator
print("A", "B", "C", sep="-")
# Output: A-B-C

# Custom end (default is newline \n)
print("Hello", end=" ")
print("World")
# Output: Hello World

# Print empty line
print()

# Print numbers
print(42)
print(3.14)
print(True)
```

> 💡 **Fun Fact:** `print()` is actually a function. On Day 03 (Functions), you'll learn to build your own functions just like `print`.

---

<a name="section-4"></a>
## ⚙️ Section 4 — Python Execution Flow

### 4.1 How Python Runs Your Code

```
YOUR CODE (hello.py)
        │
        ▼
┌───────────────────┐
│   Python Source   │  ← What you write (human-readable)
│  print("Hello")   │
└───────────────────┘
        │
        ▼
┌───────────────────┐
│  Python Interpreter│  ← Reads and parses your code
│    (CPython)      │
└───────────────────┘
        │
        ▼
┌───────────────────┐
│    Bytecode       │  ← Intermediate representation
│   (.pyc file)     │     stored in __pycache__
└───────────────────┘
        │
        ▼
┌───────────────────┐
│  Python Virtual   │  ← Executes bytecode instructions
│  Machine (PVM)    │
└───────────────────┘
        │
        ▼
    OUTPUT
  "Hello, World!"
```

### 4.2 Key Terms

| Term | Meaning |
|------|---------|
| **CPython** | The standard Python interpreter written in C |
| **Bytecode** | Low-level, platform-independent instructions |
| **PVM** | Python Virtual Machine — executes bytecode |
| **`__pycache__`** | Folder where Python stores compiled `.pyc` files |
| **REPL** | Read-Eval-Print Loop — interactive Python shell |

### 4.3 CPython vs Other Implementations

| Implementation | Language | Speed | Use Case |
|---------------|----------|-------|---------|
| CPython | C | Standard | Default, most compatible |
| PyPy | Python/C | 5-10x faster | Performance-critical code |
| Jython | Java | Standard | JVM integration |
| MicroPython | C | Lightweight | Embedded/IoT devices |

---

<a name="section-5"></a>
## 💬 Section 5 — Comments

### 5.1 What is a Comment?

A **comment** is text in your code that Python completely ignores. It exists only for humans to read.

> 🧠 **Memory Trick:** Comments are like sticky notes on your code. The computer ignores them, but they help you (and others) remember what the code does.

---

### 5.2 Single-Line Comments

```python
# This is a single-line comment
print("Hello")  # This prints Hello to the screen

# Variable storing user's name
name = "Alice"
```

The `#` symbol tells Python: "ignore everything after me on this line."

---

### 5.3 Multi-Line Comments

Python has no official multi-line comment syntax, but programmers use triple quotes:

```python
"""
This is a multi-line comment.
It can span many lines.
Python treats this as a string but doesn't assign it to anything.
"""

'''
This also works as a multi-line comment.
Single or double triple-quotes.
'''

print("Code continues here")
```

> ⚠️ **Note:** Triple-quoted strings at the start of a function/class become **docstrings** (documentation strings). We'll cover those on Day 03.

---

### 5.4 Why Comments Matter

```python
# BAD CODE — no comments:
x = 86400
y = x * 7
z = y * 52

# GOOD CODE — with comments:
SECONDS_IN_DAY = 86400          # 60 sec * 60 min * 24 hours
SECONDS_IN_WEEK = SECONDS_IN_DAY * 7    # 7 days
SECONDS_IN_YEAR = SECONDS_IN_WEEK * 52  # approx 52 weeks
```

> 💡 **Best Practice:** Write comments that explain WHY, not WHAT. The code itself shows what — the comment should explain the reasoning.

---

<a name="section-6"></a>
## 📦 Section 6 — Variables

### 6.1 What is a Variable?

A **variable** is a named container in memory that stores a value.

**Real World Analogy:**  
A variable is like a labeled box:
```
  ┌─────────┐
  │  "Alice" │  ←── value stored inside
  └─────────┘
       │
     name       ←── the label (variable name)
```

When you write `name = "Alice"`, Python:
1. Creates a box in memory
2. Stores the value `"Alice"` in it
3. Attaches the label `name` to it

---

### 6.2 Creating Variables

```python
# Syntax: variable_name = value
name = "Alice"
age = 25
height = 5.7
is_student = True
score = None

# Multiple assignment on one line
x, y, z = 1, 2, 3

# Assign same value to multiple variables
a = b = c = 0

# Print variables
print(name)      # Alice
print(age)       # 25
print(height)    # 5.7
```

---

### 6.3 Dynamic Typing — Python's Superpower

In Python, variables don't have fixed types. You can reassign to a different type:

```python
x = 10          # x is an integer
print(type(x))  # <class 'int'>

x = "Hello"     # Now x is a string
print(type(x))  # <class 'str'>

x = 3.14        # Now x is a float
print(type(x))  # <class 'float'>
```

> ⚠️ **Warning:** This freedom can cause bugs. Be mindful of what type your variable holds at each point.

---

### 6.4 Variable Naming Rules

| Rule | Valid | Invalid |
|------|-------|---------|
| Must start with letter or `_` | `name`, `_age` | `1name`, `@score` |
| Can contain letters, digits, `_` | `user_1`, `my_var` | `user-1`, `my var` |
| Case-sensitive | `Name` ≠ `name` ≠ `NAME` | — |
| No reserved keywords | `my_class` | `class`, `for`, `if` |

---

### 6.5 Python Reserved Keywords (35 total)

```python
import keyword
print(keyword.kwlist)

# Output:
['False', 'None', 'True', 'and', 'as', 'assert', 'async', 'await',
 'break', 'class', 'continue', 'def', 'del', 'elif', 'else', 'except',
 'finally', 'for', 'from', 'global', 'if', 'import', 'in', 'is',
 'lambda', 'nonlocal', 'not', 'or', 'pass', 'raise', 'return',
 'try', 'while', 'with', 'yield']
```

---

### 6.6 Naming Conventions

| Convention | Style | Use Case | Example |
|------------|-------|----------|---------|
| `snake_case` | lowercase + underscores | Variables, functions | `user_name`, `get_data()` |
| `camelCase` | second word capitalized | Not used in Python | `userName` (JavaScript style) |
| `PascalCase` | every word capitalized | Classes | `StudentInfo`, `MyClass` |
| `UPPER_CASE` | all caps + underscores | Constants | `MAX_SIZE`, `PI` |
| `_private` | leading underscore | Private variables | `_internal_count` |
| `__dunder__` | double underscores | Python special methods | `__init__`, `__str__` |

---

<a name="section-7"></a>
## 🔢 Section 7 — Data Types

### 7.1 Overview

```
Python Built-in Data Types:

┌──────────────────────────────────────────────────┐
│                  DATA TYPES                      │
├──────────┬──────────┬────────────┬───────────────┤
│ Numeric  │  Text    │  Boolean   │  None         │
├──────────┼──────────┼────────────┼───────────────┤
│  int     │  str     │  bool      │  NoneType     │
│  float   │          │  True/False│  None         │
│  complex │          │            │               │
└──────────┴──────────┴────────────┴───────────────┘
```

---

### 7.2 int — Integer

```python
# Definition: Whole numbers, positive or negative, no decimal
age = 25
temperature = -10
population = 1_400_000_000   # Underscores for readability
zero = 0

# Integer bases
decimal = 255         # base 10 (default)
binary  = 0b11111111  # base 2  (prefix 0b)
octal   = 0o377       # base 8  (prefix 0o)
hexadec = 0xFF        # base 16 (prefix 0x)

print(decimal)    # 255
print(binary)     # 255
print(octal)      # 255
print(hexadec)    # 255

# Size: Python integers have UNLIMITED precision
big = 10 ** 100   # Googol — Python handles this!
print(big)
```

| Property | Detail |
|----------|--------|
| Type | `int` |
| Size | Unlimited (arbitrary precision) |
| Immutable | Yes |
| Memory | ~28 bytes for small ints |

---

### 7.3 float — Floating Point Number

```python
# Definition: Numbers with decimal points
pi = 3.14159265358979
temperature = -273.15
price = 99.99

# Scientific notation
avogadro = 6.022e23     # 6.022 × 10²³
planck = 6.626e-34      # 6.626 × 10⁻³⁴

print(avogadro)   # 6.022e+23
print(planck)     # 6.626e-34

# Float precision issue (important!)
print(0.1 + 0.2)  # 0.30000000000000004  ← NOT 0.3!
```

> ⚠️ **Warning:** Floats are stored in binary and have precision limits. For financial calculations, use the `decimal` module instead of `float`.

---

### 7.4 complex — Complex Numbers

```python
# Definition: Numbers with real + imaginary parts
# Format: real + imaginaryj  (Python uses 'j' not 'i')
z1 = 3 + 4j
z2 = complex(2, -5)    # 2 - 5j
z3 = 5j                # Pure imaginary

print(z1)              # (3+4j)
print(z1.real)         # 3.0
print(z1.imag)         # 4.0
print(abs(z1))         # 5.0  (magnitude = sqrt(3²+4²))

# Operations
print(z1 + z2)         # (5-1j)
print(z1 * z2)         # (26-7j)
```

> 💡 **Use Case:** Complex numbers are used in signal processing, electrical engineering, and quantum computing simulations.

---

### 7.5 str — String

```python
# Definition: Sequence of characters (text)
name = "Alice"
message = 'Hello, World!'
multiline = """Line 1
Line 2
Line 3"""

# Strings are immutable
greeting = "Hello"
# greeting[0] = "J"  # ← This will CRASH! Strings can't be modified in place
```

*Deep covered in Section 12.*

---

### 7.6 bool — Boolean

```python
# Definition: Only two possible values: True or False
is_raining = True
is_logged_in = False

# Booleans are subclass of int!
print(True + True)     # 2
print(True * 10)       # 10
print(False + 5)       # 5
print(int(True))       # 1
print(int(False))      # 0

# Truthy and Falsy values
# These evaluate as False:
print(bool(0))         # False
print(bool(""))        # False
print(bool([]))        # False
print(bool(None))      # False

# These evaluate as True:
print(bool(1))         # True
print(bool("hello"))   # True
print(bool([1, 2]))    # True
```

| Falsy Values | Truthy Values |
|-------------|--------------|
| `0`, `0.0`, `0j` | Any non-zero number |
| `""` (empty string) | Any non-empty string |
| `[]`, `()`, `{}` | Any non-empty collection |
| `None` | Any object |
| `False` | `True` |

---

### 7.7 NoneType — The Absence of Value

```python
# Definition: Represents the absence of a value
result = None
user_input = None

print(result)          # None
print(type(result))    # <class 'NoneType'>
print(result is None)  # True  ← Always use 'is' to check for None
print(result == None)  # True  ← Works but not recommended style

# Common use: function that doesn't return anything
def greet():
    print("Hello")

x = greet()   # prints Hello
print(x)      # None  ← functions without return give None
```

> 🧠 **Memory Trick:** Think of `None` like a blank form — it exists, but it has no value filled in.

---

### 7.8 Data Types Quick Reference

| Type | Example | `type()` | Mutable |
|------|---------|----------|---------|
| `int` | `42` | `<class 'int'>` | No |
| `float` | `3.14` | `<class 'float'>` | No |
| `complex` | `3+4j` | `<class 'complex'>` | No |
| `str` | `"hello"` | `<class 'str'>` | No |
| `bool` | `True` | `<class 'bool'>` | No |
| `NoneType` | `None` | `<class 'NoneType'>` | No |

---

<a name="section-8"></a>
## 🔍 Section 8 — Type Checking

### 8.1 `type()` Function

```python
# Syntax: type(object)
# Returns: The type/class of the object

x = 42
y = 3.14
z = "Hello"
a = True
b = None

print(type(x))   # <class 'int'>
print(type(y))   # <class 'float'>
print(type(z))   # <class 'str'>
print(type(a))   # <class 'bool'>
print(type(b))   # <class 'NoneType'>

# Using type() in conditions
if type(x) == int:
    print("x is an integer")

# Better: use isinstance()
if isinstance(x, int):
    print("x is an integer")   # More Pythonic!

# isinstance() also checks parent classes
print(isinstance(True, int))   # True! (bool is subclass of int)
```

---

### 8.2 `id()` Function — Memory Address

```python
# id() returns the memory address (unique identity) of an object
x = 42
y = 42

print(id(x))    # e.g., 140234567890
print(id(y))    # Same as x! Python caches small integers

a = "hello"
b = "hello"
print(id(a) == id(b))   # True — string interning!

# Large integers get different addresses
p = 1000
q = 1000
print(id(p) == id(q))   # May be False
```

### 8.3 Python's Integer Cache (Important!)

Python pre-creates integer objects for `-5` to `256` for performance:

```python
a = 100
b = 100
print(a is b)    # True  (same object, cached)

x = 1000
y = 1000
print(x is y)   # False (not cached, new objects)
```

> ⚠️ **Warning:** Never use `is` to compare values — use `==`. Use `is` only to compare identity (same object) or check for `None`.

---

<a name="section-9"></a>
## 📥📤 Section 9 — Input and Output

### 9.1 `input()` — Getting User Input

```python
# Syntax: variable = input("prompt message")
name = input("Enter your name: ")
print("Hello,", name)
```

**Important:** `input()` ALWAYS returns a **string**, even if the user types a number!

```python
num = input("Enter a number: ")
print(type(num))     # <class 'str'> ← always string!
print(num + 5)       # ❌ TypeError: can't add string and int
print(int(num) + 5)  # ✅ Convert first, then add
```

---

### 9.2 `print()` — Advanced Output

```python
# Basic print
print("Hello, World!")

# Print multiple values
print("Name:", "Alice", "Age:", 25)
# Output: Name: Alice Age: 25

# Custom separator (default is space)
print("2024", "06", "15", sep="-")
# Output: 2024-06-15

# Custom end (default is newline)
print("Loading", end="")
print("...", end="")
print(" Done!")
# Output: Loading... Done!

# Print with format
name = "Bob"
age = 30
print(f"Name: {name}, Age: {age}")        # f-string
print("Name: {}, Age: {}".format(name, age))  # .format()
print("Name: %s, Age: %d" % (name, age))      # % formatting (old style)
```

---

### 9.3 Formatted Output Comparison

| Method | Syntax | Python Version |
|--------|--------|---------------|
| % formatting | `"Hello %s" % name` | Python 2+ (legacy) |
| `.format()` | `"Hello {}".format(name)` | Python 3.0+ |
| f-strings | `f"Hello {name}"` | Python 3.6+ ⭐ |
| Template strings | `Template("Hello $name")` | Rare |

> 💡 **Best Practice:** Always use **f-strings** in modern Python (3.6+). They are the fastest and most readable.

---

<a name="section-10"></a>
## 🔄 Section 10 — Type Casting

### 10.1 What is Type Casting?

**Type Casting** (also called Type Conversion) is the process of converting a value from one data type to another.

```
"25"  →  int("25")  →  25
25    →  str(25)    →  "25"
25    →  float(25)  →  25.0
1     →  bool(1)    →  True
```

---

### 10.2 Explicit Type Casting

```python
# int() — convert to integer
print(int("42"))        # 42
print(int(3.99))        # 3  ← truncates, doesn't round
print(int(True))        # 1
print(int(False))       # 0
# print(int("3.14"))    # ❌ ValueError: invalid literal

# float() — convert to float
print(float("3.14"))    # 3.14
print(float(42))        # 42.0
print(float("inf"))     # inf
print(float(True))      # 1.0

# str() — convert to string
print(str(42))          # "42"
print(str(3.14))        # "3.14"
print(str(True))        # "True"
print(str(None))        # "None"

# bool() — convert to boolean
print(bool(0))          # False
print(bool(1))          # True
print(bool(""))         # False
print(bool("hello"))    # True
print(bool(None))       # False
```

---

### 10.3 Implicit Type Casting (Coercion)

Python automatically converts types in some operations:

```python
x = 5      # int
y = 2.0    # float

result = x + y
print(result)        # 7.0   ← int automatically became float
print(type(result))  # <class 'float'>

# Python promotes: int → float → complex
a = 3
b = 3 + 0j
print(a + b)         # (6+0j)  ← int promoted to complex
```

---

### 10.4 Type Conversion Table

| From \ To | `int` | `float` | `str` | `bool` |
|-----------|-------|---------|-------|--------|
| `int` | — | `float(n)` | `str(n)` | `bool(n)` |
| `float` | `int(f)` truncates | — | `str(f)` | `bool(f)` |
| `str` | `int(s)` if numeric | `float(s)` if numeric | — | `bool(s)` |
| `bool` | `int(b)` → 0 or 1 | `float(b)` | `str(b)` | — |

---

### 10.5 Common Input Pattern

```python
# Classic pattern: get numeric input from user
age = int(input("Enter your age: "))
height = float(input("Enter your height in meters: "))
name = input("Enter your name: ")   # already string, no conversion needed

print(f"Name: {name}, Age: {age}, Height: {height}m")
```

---

<a name="section-11"></a>
## ⚡ Section 11 — Operators

### 11.1 Arithmetic Operators

| Operator | Name | Example | Result |
|----------|------|---------|--------|
| `+` | Addition | `5 + 3` | `8` |
| `-` | Subtraction | `5 - 3` | `2` |
| `*` | Multiplication | `5 * 3` | `15` |
| `/` | Division | `7 / 2` | `3.5` (always float) |
| `//` | Floor Division | `7 // 2` | `3` (truncates) |
| `%` | Modulus | `7 % 2` | `1` (remainder) |
| `**` | Exponentiation | `2 ** 10` | `1024` |

```python
a, b = 17, 5

print(a + b)    # 22
print(a - b)    # 12
print(a * b)    # 85
print(a / b)    # 3.4
print(a // b)   # 3
print(a % b)    # 2
print(a ** b)   # 1419857  (17⁵)

# Real world usage:
total_seconds = 3723
hours = total_seconds // 3600      # 1
remaining = total_seconds % 3600
minutes = remaining // 60          # 2
seconds = remaining % 60           # 3
print(f"{hours}h {minutes}m {seconds}s")  # 1h 2m 3s
```

> 🧠 **Memory Trick for `//` and `%`:** Floor division gives the **quotient**, modulus gives the **remainder**. Like long division in school!

---

### 11.2 Comparison Operators

```python
# Return True or False
a, b = 10, 20

print(a == b)   # False  (equal)
print(a != b)   # True   (not equal)
print(a > b)    # False  (greater than)
print(a < b)    # True   (less than)
print(a >= b)   # False  (greater than or equal)
print(a <= b)   # True   (less than or equal)

# Works on strings too (alphabetical comparison)
print("apple" < "banana")   # True
print("z" > "a")            # True
```

| Operator | Meaning |
|----------|---------|
| `==` | Equal to |
| `!=` | Not equal to |
| `>` | Greater than |
| `<` | Less than |
| `>=` | Greater than or equal to |
| `<=` | Less than or equal to |

> ⚠️ **Common Mistake:** `=` is assignment. `==` is comparison. Beginners often confuse them!

---

### 11.3 Logical Operators

```python
# and — both must be True
print(True and True)    # True
print(True and False)   # False
print(False and True)   # False

# or — at least one must be True
print(True or False)    # True
print(False or False)   # False

# not — reverses the boolean
print(not True)         # False
print(not False)        # True

# Real world example:
age = 20
has_id = True
can_enter = age >= 18 and has_id
print(can_enter)        # True
```

**Truth Tables:**

| A | B | A and B | A or B | not A |
|---|---|---------|--------|-------|
| T | T | T | T | F |
| T | F | F | T | F |
| F | T | F | T | T |
| F | F | F | F | T |

**Short-circuit evaluation:**
```python
# 'and' stops at first False
x = 0
result = x and (10 / x)    # Won't crash! Stops at x (False)
print(result)               # 0

# 'or' stops at first True
y = 5
result = y or (10 / 0)      # Won't crash! Stops at y (True)
print(result)               # 5
```

---

### 11.4 Assignment Operators

```python
x = 10          # basic assignment

x += 5          # x = x + 5   → 15
x -= 3          # x = x - 3   → 12
x *= 2          # x = x * 2   → 24
x /= 4          # x = x / 4   → 6.0
x //= 2         # x = x // 2  → 3.0
x **= 3         # x = x ** 3  → 27.0
x %= 5          # x = x % 5   → 2.0

# Walrus operator := (Python 3.8+)
# Assigns and returns in one expression
import random
while (n := random.randint(1, 10)) != 5:
    print(f"Got {n}, trying again...")
print(f"Finally got {n}!")
```

---

### 11.5 Membership Operators

```python
fruits = ["apple", "banana", "cherry"]

print("apple" in fruits)        # True
print("mango" in fruits)        # False
print("mango" not in fruits)    # True

# Works with strings too!
text = "Hello, World!"
print("Hello" in text)          # True
print("Python" not in text)     # True

# Works with dictionaries (checks keys)
person = {"name": "Alice", "age": 25}
print("name" in person)         # True
print("email" in person)        # False
```

---

### 11.6 Identity Operators

```python
# 'is' checks if two variables point to the SAME object in memory
# '==' checks if two variables have the SAME value

a = [1, 2, 3]
b = [1, 2, 3]
c = a

print(a == b)   # True  (same values)
print(a is b)   # False (different objects in memory)
print(a is c)   # True  (c points to same object as a)

# Correct use of 'is': check for None
x = None
print(x is None)     # True  ← Correct
print(x == None)     # True  ← Works but not recommended
```

---

### 11.7 Bitwise Operators

Bitwise operators work on the binary representation of integers:

```python
a = 12   # binary: 1100
b = 10   # binary: 1010

print(a & b)    # 8   → AND:  1000
print(a | b)    # 14  → OR:   1110
print(a ^ b)    # 6   → XOR:  0110
print(~a)       # -13 → NOT:  -(a+1)
print(a << 2)   # 48  → Left shift  (multiply by 2²)
print(a >> 1)   # 6   → Right shift (divide by 2¹)
```

| Operator | Name | Operation |
|----------|------|-----------|
| `&` | AND | Both bits must be 1 |
| `\|` | OR | At least one bit is 1 |
| `^` | XOR | Bits must be different |
| `~` | NOT | Flips all bits |
| `<<` | Left shift | Multiply by power of 2 |
| `>>` | Right shift | Divide by power of 2 |

> 💡 **Use Case:** Bitwise operations are used in cryptography, image processing, permissions systems (Linux file permissions), and performance-critical code.

---

### 11.8 Operator Precedence (PEMDAS Extended)

```
Highest Priority → Lowest Priority:

1. ()             Parentheses
2. **             Exponentiation (right to left)
3. +x, -x, ~x    Unary operators
4. *, /, //, %   Multiplication, Division
5. +, -           Addition, Subtraction
6. <<, >>         Bitwise shifts
7. &              Bitwise AND
8. ^              Bitwise XOR
9. |              Bitwise OR
10. ==, !=, >, <, >=, <=, is, is not, in, not in   Comparisons
11. not           Logical NOT
12. and           Logical AND
13. or            Logical OR
14. :=            Walrus operator
```

```python
# Example:
result = 2 + 3 * 4 ** 2 - 1
# Step 1: 4 ** 2 = 16
# Step 2: 3 * 16 = 48
# Step 3: 2 + 48 = 50
# Step 4: 50 - 1 = 49
print(result)   # 49

# When in doubt, use parentheses!
result = (2 + 3) * (4 ** 2) - 1
print(result)   # 79
```

---

<a name="section-12"></a>
## 🔤 Section 12 — Strings: Deep Dive

### 12.1 String Creation

```python
s1 = "Hello"                  # double quotes
s2 = 'World'                  # single quotes
s3 = """Multi
line"""                       # triple double quotes
s4 = '''Another
multi-line'''                 # triple single quotes
s5 = str(42)                  # from int
s6 = f"Value is {42 * 2}"     # f-string
```

---

### 12.2 String Indexing

Strings are **sequences** — each character has a numbered position (index).

```
String:  H  e  l  l  o  ,     W  o  r  l  d  !
Index:   0  1  2  3  4  5  6  7  8  9 10 11 12
Neg:   -13-12-11-10 -9 -8 -7 -6 -5 -4 -3 -2 -1
```

```python
s = "Hello, World!"

# Positive indexing (left to right, starts at 0)
print(s[0])     # H
print(s[7])     # W
print(s[12])    # !

# Negative indexing (right to left, starts at -1)
print(s[-1])    # !
print(s[-6])    # W
print(s[-13])   # H
```

---

### 12.3 String Slicing

```python
# Syntax: string[start:stop:step]
# start: inclusive, stop: exclusive

s = "Hello, World!"

print(s[0:5])    # Hello   (chars 0,1,2,3,4)
print(s[7:12])   # World   (chars 7,8,9,10,11)
print(s[:5])     # Hello   (from start to 5)
print(s[7:])     # World!  (from 7 to end)
print(s[:])      # Hello, World!  (entire string)
print(s[::2])    # Hlo ol!  (every 2nd char)
print(s[::-1])   # !dlroW ,olleH  (reversed!)
print(s[0:12:3]) # H,Wr  (every 3rd char from 0 to 12)
```

> 🧠 **Memory Trick for slicing:** Think of indices as being between characters, not on them:
> ```
> | H | e | l | l | o |
> 0   1   2   3   4   5
> ```
> `s[1:4]` picks chars between positions 1 and 4 → `ell`

---

### 12.4 String Immutability

```python
s = "Hello"

# s[0] = "J"  ← ❌ TypeError: 'str' object does not support item assignment

# To "modify", create a new string:
s = "J" + s[1:]   # Concatenate
print(s)           # Jello
```

---

### 12.5 Escape Characters

| Escape | Meaning | Example | Output |
|--------|---------|---------|--------|
| `\n` | Newline | `"Line1\nLine2"` | Two lines |
| `\t` | Tab | `"A\tB"` | `A    B` |
| `\\` | Backslash | `"C:\\Users"` | `C:\Users` |
| `\'` | Single quote | `'It\'s'` | `It's` |
| `\"` | Double quote | `"Say \"Hi\""` | `Say "Hi"` |
| `\r` | Carriage return | `"Hello\rWorld"` | Overwrites |
| `\0` | Null character | — | Empty char |

```python
# Raw strings ignore escape sequences
path = r"C:\Users\Alice\Documents"
print(path)   # C:\Users\Alice\Documents  ← backslashes preserved

# Without r:
# path = "C:\Users\Alice\Documents"  ← \U is not a valid escape!
```

---

### 12.6 f-Strings (Formatted String Literals)

```python
name = "Alice"
age = 25
gpa = 3.891

# Basic interpolation
print(f"Name: {name}, Age: {age}")

# Expressions inside f-strings
print(f"Birth year: {2024 - age}")
print(f"GPA rounded: {gpa:.2f}")   # 3.89

# Width and alignment
print(f"{'Left':<10}|{'Center':^10}|{'Right':>10}")
# Output: Left      |  Center  |     Right

# Number formatting
big_num = 1_234_567
print(f"{big_num:,}")    # 1,234,567
print(f"{0.005:.2%}")    # 0.50%
print(f"{255:#010b}")    # 0b11111111
```

---

### 12.7 String Methods — Complete Reference

#### Case Methods

```python
s = "hello WORLD"

print(s.upper())        # HELLO WORLD
print(s.lower())        # hello world
print(s.title())        # Hello World
print(s.capitalize())   # Hello world
print(s.swapcase())     # HELLO world
```

#### Search and Replace

```python
s = "Hello, Hello, Python!"

print(s.find("Hello"))          # 0  (first occurrence index)
print(s.find("Java"))           # -1 (not found)
print(s.rfind("Hello"))         # 7  (last occurrence)
print(s.index("Python"))        # 14 (like find but raises ValueError if not found)
print(s.count("Hello"))         # 2
print(s.replace("Hello", "Hi")) # Hi, Hi, Python!
print(s.replace("Hello", "Hi", 1))  # Hi, Hello, Python! (replace once)
```

#### Split and Join

```python
# split() — string to list
text = "apple,banana,cherry"
fruits = text.split(",")
print(fruits)        # ['apple', 'banana', 'cherry']

text2 = "Hello World Python"
words = text2.split()   # split on any whitespace
print(words)         # ['Hello', 'World', 'Python']

# split with maxsplit
parts = "a:b:c:d".split(":", 2)
print(parts)         # ['a', 'b', 'c:d']

# join() — list to string
fruits = ["apple", "banana", "cherry"]
print(", ".join(fruits))    # apple, banana, cherry
print(" | ".join(fruits))   # apple | banana | cherry
print("".join(["H","i"]))   # Hi
```

#### Strip Methods

```python
s = "   Hello, World!   "

print(s.strip())     # "Hello, World!"  (both sides)
print(s.lstrip())    # "Hello, World!   " (left only)
print(s.rstrip())    # "   Hello, World!" (right only)

# Strip specific characters
s2 = "***Python***"
print(s2.strip("*"))    # Python
```

#### Check Methods (return bool)

```python
print("abc123".isalnum())    # True  (letters + digits only)
print("abc".isalpha())       # True  (letters only)
print("123".isdigit())       # True  (digits only)
print("   ".isspace())       # True  (whitespace only)
print("Hello World".istitle())  # True  (title case)
print("HELLO".isupper())     # True
print("hello".islower())     # True
print("123.45".isnumeric())  # False (decimal not numeric)
```

#### Alignment Methods

```python
s = "Python"

print(s.center(20))         # "       Python       "
print(s.center(20, "-"))    # "-------Python-------"
print(s.ljust(20, "."))     # "Python.............."
print(s.rjust(20, "."))     # "..............Python"
print("42".zfill(6))        # "000042"  (zero-padded)
```

#### Start/End Check

```python
s = "Hello, Python World!"

print(s.startswith("Hello"))    # True
print(s.startswith("World"))    # False
print(s.endswith("World!"))     # True
print(s.endswith("Python"))     # False

# Check multiple options with tuple
print(s.startswith(("Hello", "Hi")))  # True
```

#### Partition Methods

```python
s = "user@email.com"

left, sep, right = s.partition("@")
print(left)    # user
print(sep)     # @
print(right)   # email.com

# rpartition — splits at LAST occurrence
path = "/home/user/documents/file.txt"
left, sep, right = path.rpartition("/")
print(right)   # file.txt
```

#### Translation

```python
# maketrans() + translate() — character-level substitution
table = str.maketrans("aeiou", "AEIOU")
print("hello world".translate(table))   # hEllO wOrld

# Remove characters
table2 = str.maketrans("", "", "aeiou")
print("hello world".translate(table2))  # hll wrld (vowels removed)
```

#### Other Useful Methods

```python
# expandtabs() — replace \t with spaces
print("Name:\tAlice".expandtabs(8))    # Name:   Alice

# encode() — convert to bytes
text = "Hello"
encoded = text.encode("utf-8")
print(encoded)        # b'Hello'
print(type(encoded))  # <class 'bytes'>

# decode back to string
print(encoded.decode("utf-8"))    # Hello
```

---

### 12.8 String Methods Quick Reference Table

| Method | Returns | Purpose |
|--------|---------|---------|
| `upper()` | str | All uppercase |
| `lower()` | str | All lowercase |
| `title()` | str | Title case |
| `capitalize()` | str | First letter upper |
| `swapcase()` | str | Swap cases |
| `strip()` | str | Remove whitespace/chars from both ends |
| `lstrip()` | str | Remove from left |
| `rstrip()` | str | Remove from right |
| `replace(old,new)` | str | Replace substring |
| `split(sep)` | list | Split into list |
| `join(iterable)` | str | Join list into string |
| `find(sub)` | int | First index of sub (-1 if not found) |
| `index(sub)` | int | First index (raises ValueError) |
| `count(sub)` | int | Count occurrences |
| `startswith(pre)` | bool | Starts with prefix? |
| `endswith(suf)` | bool | Ends with suffix? |
| `isalpha()` | bool | Only letters? |
| `isdigit()` | bool | Only digits? |
| `isalnum()` | bool | Letters + digits? |
| `isspace()` | bool | Only whitespace? |
| `islower()` | bool | All lowercase? |
| `isupper()` | bool | All uppercase? |
| `center(w)` | str | Center in width |
| `ljust(w)` | str | Left align |
| `rjust(w)` | str | Right align |
| `zfill(w)` | str | Zero-pad |
| `partition(sep)` | tuple | Split at first sep |
| `rpartition(sep)` | tuple | Split at last sep |
| `encode(enc)` | bytes | Encode to bytes |

---

<a name="section-13"></a>
## 🧠 Section 13 — Python Memory Model

### 13.1 Everything is an Object

In Python, **everything is an object**. Every number, string, list — all objects in memory.

```python
x = 42
# Python creates an object:
# ┌─────────────┐
# │  Type: int  │
# │  Value: 42  │
# │  RefCount:1 │
# └─────────────┘
#       ↑
#       │
#       x  (variable is just a reference/label)
```

---

### 13.2 Variables are References (Not Boxes)

```python
a = [1, 2, 3]
b = a        # b now POINTS TO the same list!

b.append(4)
print(a)     # [1, 2, 3, 4]  ← a changed too!
print(b)     # [1, 2, 3, 4]

# Memory:
# a ────┐
#       ├──► [1, 2, 3, 4]  (one object in memory)
# b ────┘
```

To create an independent copy:
```python
a = [1, 2, 3]
b = a.copy()   # or b = a[:]  or b = list(a)

b.append(4)
print(a)   # [1, 2, 3]   ← unchanged
print(b)   # [1, 2, 3, 4]
```

---

### 13.3 Mutable vs Immutable Objects

| Immutable (cannot change) | Mutable (can change) |
|--------------------------|----------------------|
| `int`, `float`, `complex` | `list` |
| `str` | `dict` |
| `bool` | `set` |
| `tuple` | — |
| `frozenset` | — |

```python
# Immutable: "changes" create new objects
x = 5
print(id(x))    # some address, e.g., 140234
x += 1          # x now points to a NEW object (6)
print(id(x))    # different address!

# Mutable: changes modify in place
my_list = [1, 2, 3]
print(id(my_list))    # some address
my_list.append(4)     # modifies the same object
print(id(my_list))    # SAME address!
```

---

### 13.4 Garbage Collection

Python automatically frees memory that's no longer referenced:

```python
x = "Hello"     # object created, refcount = 1
y = x           # refcount = 2
del x           # refcount = 1
del y           # refcount = 0 → GARBAGE COLLECTED (memory freed)
```

Python uses **reference counting** + **cyclic garbage collector** for memory management. You rarely need to worry about memory in Python.

---

<a name="section-14"></a>
## 🐛 Section 14 — Debugging Basics

### 14.1 Types of Errors

```
ERROR TYPES:
┌──────────────────────────────────────────────────────┐
│  1. Syntax Error    → Code violates grammar rules    │
│  2. Runtime Error  → Code crashes during execution  │
│  3. Logical Error  → Code runs but gives wrong answer│
└──────────────────────────────────────────────────────┘
```

---

### 14.2 Syntax Errors

```python
# Error 1: Missing parenthesis
print("Hello"
# SyntaxError: unexpected EOF while parsing

# Error 2: Missing colon
if x > 5
    print(x)
# SyntaxError: expected ':'

# Error 3: Wrong indentation
def greet():
print("Hello")
# IndentationError: expected an indented block
```

---

### 14.3 Runtime Errors

```python
# NameError — variable not defined
print(undefined_variable)
# NameError: name 'undefined_variable' is not defined

# TypeError — wrong type operation
print("5" + 5)
# TypeError: can only concatenate str (not "int") to str

# ZeroDivisionError
print(10 / 0)
# ZeroDivisionError: division by zero

# IndexError
lst = [1, 2, 3]
print(lst[10])
# IndexError: list index out of range

# ValueError
int("hello")
# ValueError: invalid literal for int() with base 10: 'hello'
```

---

### 14.4 Logical Errors

```python
# Code runs fine but gives wrong answer
def average(a, b):
    return a + b / 2   # BUG: should be (a + b) / 2

print(average(10, 20))   # Returns 20.0, not 15.0!

# Fix:
def average(a, b):
    return (a + b) / 2

print(average(10, 20))   # 15.0 ✓
```

> 💡 **Debugging Strategy (5-Step):**
> 1. Read the error message carefully
> 2. Find the line number mentioned
> 3. Add `print()` statements to trace values
> 4. Check logic with simple test cases
> 5. Use Python's built-in `pdb` debugger for complex bugs

---

<a name="section-15"></a>
## ✨ Section 15 — Best Practices (PEP 8)

### 15.1 What is PEP 8?

**PEP 8** is Python's official style guide. Following it makes your code readable and professional.

---

### 15.2 Key PEP 8 Rules

```python
# ✅ GOOD: Spaces around operators
x = 10 + 5
y = x * 2

# ❌ BAD:
x=10+5
y=x*2

# ✅ GOOD: Blank lines between functions
def add(a, b):
    return a + b


def subtract(a, b):    # 2 blank lines before top-level functions
    return a - b

# ✅ GOOD: 79 characters max per line
# For long lines, use backslash or parentheses to continue
result = (first_value
          + second_value
          + third_value)

# ✅ GOOD: Imports at the top, one per line
import os
import sys
from math import sqrt

# ❌ BAD:
import os, sys

# ✅ GOOD: 4 spaces for indentation (NEVER tabs)
if True:
    print("Hello")

# ✅ GOOD: Descriptive names
user_age = 25
total_price = 99.99
is_logged_in = False

# ❌ BAD: Single letters (except in short loops/math)
a = 25
tp = 99.99
il = False
```

---

### 15.3 PEP 8 Quick Reference

| Rule | Standard |
|------|---------|
| Indentation | 4 spaces |
| Max line length | 79 characters |
| Blank lines between functions | 2 |
| Blank lines inside class | 1 |
| Imports | Top of file, alphabetical |
| Variable names | `snake_case` |
| Class names | `PascalCase` |
| Constants | `UPPER_CASE` |
| Spaces around `=` in assignments | Yes |
| Spaces around `=` in function args | No |

---

<a name="section-16"></a>
## ⚠️ Section 16 — Common Beginner Mistakes

```python
# MISTAKE 1: Using = instead of == in comparisons
x = 5
if x = 10:           # ❌ SyntaxError
    print("ten")
if x == 10:          # ✅ Correct
    print("ten")

# MISTAKE 2: Forgetting that input() returns string
age = input("Age: ")
if age > 18:         # ❌ TypeError: '>' not supported between str and int
    print("Adult")
age = int(input("Age: "))  # ✅ Convert first
if age > 18:
    print("Adult")

# MISTAKE 3: Modifying a string "in place"
name = "Alice"
name[0] = "J"        # ❌ TypeError: str is immutable
name = "J" + name[1:]  # ✅ Create new string

# MISTAKE 4: Wrong indentation
def greet():
print("Hello")       # ❌ IndentationError
def greet():
    print("Hello")   # ✅ 4 spaces

# MISTAKE 5: Integer division confusion
result = 7 / 2
print(result)        # 3.5 — Python 3 always returns float
# Use // for integer division:
result = 7 // 2
print(result)        # 3

# MISTAKE 6: Comparing with is instead of ==
x = 1000
y = 1000
print(x is y)        # ❌ May be False (implementation-dependent)
print(x == y)        # ✅ Always True

# MISTAKE 7: Forgetting that print() needs parentheses
print "Hello"        # ❌ SyntaxError in Python 3 (Python 2 syntax)
print("Hello")       # ✅

# MISTAKE 8: Case sensitivity
Name = "Alice"
print(name)          # ❌ NameError: name 'name' is not defined
print(Name)          # ✅

# MISTAKE 9: Using Python keywords as variables
list = [1, 2, 3]     # ❌ Shadows built-in 'list'
my_list = [1, 2, 3]  # ✅

# MISTAKE 10: Float precision
print(0.1 + 0.2 == 0.3)   # ❌ False! (float precision)
print(abs(0.1 + 0.2 - 0.3) < 1e-9)  # ✅ Correct comparison
```

---

<a name="section-17"></a>
## 📝 Section 17 — 100 Practice Questions

### 🟢 Easy (40 Questions)

**Variables and Data Types:**
1. Create a variable `name` with your name and print it.
2. Create variables for your age, height, and a boolean `is_student`.
3. What is the output of `type(3.14)`?
4. What is the output of `type(True)`?
5. Create a variable with value `None` and print its type.
6. Assign the values 10, 20, 30 to variables x, y, z in one line.
7. What happens when you do `x = y = z = 0`?
8. Print `"My name is Alice and I am 25 years old"` using variables.
9. Which is valid: `1variable = 5` or `variable1 = 5`?
10. What naming convention is used for constants in Python?

**Operations:**
11. Calculate the area of a rectangle with length 12 and width 7.
12. Calculate 2 raised to the power of 8.
13. Find the remainder when 100 is divided by 7.
14. What is `10 // 3`? What is `10 / 3`? What's the difference?
15. Calculate the average of 85, 90, 78, 92.
16. Convert 100 degrees Celsius to Fahrenheit (formula: F = C × 9/5 + 32).
17. Calculate the simple interest: P=1000, R=5, T=3 (SI = P×R×T/100).
18. What is `True + True + True`?
19. What is `not (5 > 3)`?
20. What is `5 == 5 and 3 > 2`?

**Strings:**
21. Create a string "Hello, Python!" and find its length using `len()`.
22. Extract the first character of the string "Programming".
23. Extract the last character of "Python" using negative indexing.
24. Reverse the string "Hello" using slicing.
25. Convert "python" to uppercase.
26. Convert "HELLO WORLD" to title case.
27. Count how many times 'l' appears in "Hello, World!".
28. Replace "World" with "Python" in "Hello, World!".
29. Split "apple,orange,banana" by comma.
30. Join ["Hello", "World"] with a space.

**Input/Output:**
31. Write a program that asks for user's name and greets them.
32. Write a program that takes two numbers and prints their sum.
33. Print numbers 1 to 5 on the same line separated by spaces.
34. Print "Name: Alice" right-aligned in a field of width 20.
35. Format the number 3.14159 to 2 decimal places.

**Type Casting:**
36. Convert the string "42" to an integer.
37. Convert the integer 100 to a float.
38. Convert the float 9.99 to integer (what happens to .99?).
39. What does `bool("")` return?
40. What does `bool(0.001)` return?

---

### 🟡 Medium (40 Questions)

41. Write a program that calculates the BMI (weight / height²).
42. Check if a number is even using the modulus operator.
43. Swap two variables without using a third variable.
44. Given `name = "  Alice  "`, remove whitespace and print uppercase.
45. Extract domain from `"user@example.com"` using `split()`.
46. Check if a string is a palindrome using slicing.
47. Count vowels in a string using `count()` for each vowel.
48. Format a receipt: item name left-aligned, price right-aligned, total 30 chars wide.
49. Convert temperature program: ask user, convert C↔F based on input.
50. Write a simple calculator taking two numbers and an operator (+,-,*,/).

**Memory and Types:**
51. What is the difference between `is` and `==`? Give an example.
52. Create two strings with same content. Are they `is` equal? Are they `==` equal?
53. What does `id()` return? How does it relate to memory?
54. Demonstrate Python integer caching with numbers 100 and 1000.
55. Why is `bool` a subclass of `int` in Python?

**String Operations:**
56. Given a full name "John Michael Smith", extract first and last name.
57. Check if a password is strong: at least 8 chars, has digit, has letter.
58. Count words in a sentence using `split()`.
59. Create a Caesar cipher: shift each letter by 1 position.
60. Format a table with 3 columns: Name, Age, Score.

**Operators:**
61. Use bitwise operators to check if a number is even (hint: `n & 1`).
62. Use left shift to multiply 5 by 8 (hint: `5 << 3`).
63. What is `255 & 0xF0`? What does this do?
64. Calculate compound interest: A = P(1 + r/n)^(nt).
65. Write expression to check if a number is between 1 and 100 (inclusive).

**Debugging:**
66. Fix: `nme = input(Enter name: )`
67. Fix: `print(10 / 0)`
68. Fix: `age = input("Age: "); print(age + 1)`
69. Find the logical error: `area = length + width` (should be area of rectangle)
70. Fix: `print("Result: " + 42)`

**Advanced Easy:**
71. What is the output? `print(type(type(42)))`
72. What is the output? `print("Hello" * 3)`
73. What is the output? `print(10 ** 0)`
74. What is the output? `print("" or "default")`
75. What is the output? `print(None or "fallback")`
76. Create an f-string that shows: `"Pi is approximately 3.14"` from `pi = 3.14159`.
77. What does `\n` do in a string? Give an example.
78. What is a raw string? When do you use it?
79. Explain string interning with an example.
80. What is the difference between `find()` and `index()`?

---

### 🔴 Advanced (20 Questions)

81. Implement a string encode/decode using `maketrans()` and `translate()`.
82. Given a list of names `["alice", "bob", "charlie"]`, join them formatted as "Alice, Bob, and Charlie".
83. Write a program that validates a simple email format (has @ and a dot after @).
84. Implement `center()` manually using string concatenation.
85. Calculate the sum of digits of a number using string conversion.
86. Given a paragraph, find the 3 most common characters.
87. Explain and demonstrate the difference between mutable and immutable with memory addresses.
88. Why does `0.1 + 0.2 != 0.3`? How do you fix it?
89. Implement a function to check if a string is an anagram of another.
90. Demonstrate operator short-circuiting with side effects.
91. What is the output of `print(0.1 + 0.2 + 0.3 == 0.6)`? Why?
92. Explain Python's LEGB scope rule with examples.
93. What is the GIL (Global Interpreter Lock)?
94. How does Python garbage collect reference cycles?
95. Demonstrate implicit type promotion from int → float → complex.
96. Write a program converting any number to binary, octal, and hex.
97. Explain why `bool` inheriting from `int` is useful in practice.
98. Build a simple progress bar using `print()` with `end='\r'`.
99. What is string interning and how can you force it with `sys.intern()`?
100. Explain CPython's memory allocator and why Python uses memory pools.

---

<a name="section-18"></a>
## 🎯 Section 18 — 50 Interview Questions & Answers

**Q1. What is Python? List its key features.**  
> Python is a high-level, interpreted, dynamically-typed, general-purpose language. Key features: simple syntax, large standard library, dynamic typing, automatic memory management, object-oriented, supports multiple paradigms.

**Q2. What is the difference between Python 2 and Python 3?**  
> Python 3 is the current standard. Key differences: `print` is a function in 3, integer division `/` always returns float in 3, strings are Unicode by default in 3, `range()` returns iterator not list, `input()` always returns str.

**Q3. What are Python's built-in data types?**  
> Numeric: `int`, `float`, `complex`. Sequence: `str`, `list`, `tuple`. Mapping: `dict`. Set: `set`, `frozenset`. Boolean: `bool`. None: `NoneType`.

**Q4. What is dynamic typing?**  
> Variables don't have fixed types. The type is associated with the value, not the variable. You can reassign a variable to a value of a different type at any time.

**Q5. What is the difference between `is` and `==`?**  
> `==` compares values (equality). `is` compares identity (same object in memory). `[1,2] == [1,2]` is True but `[1,2] is [1,2]` is False.

**Q6. What is `None` in Python?**  
> `None` is a singleton object of type `NoneType` representing the absence of a value. It's Python's equivalent of null. Always check with `is None`, not `== None`.

**Q7. What is the difference between `/` and `//`?**  
> `/` always returns a float (true division). `//` returns an integer (floor division), truncating the decimal. `7/2 = 3.5`, `7//2 = 3`.

**Q8. How does Python manage memory?**  
> Python uses reference counting for garbage collection. When an object's reference count reaches 0, it's freed. Python also has a cyclic garbage collector to handle reference cycles.

**Q9. What are mutable and immutable types?**  
> Immutable: can't be changed after creation (`int`, `float`, `str`, `tuple`). Mutable: can be modified in place (`list`, `dict`, `set`). When you "modify" an immutable, Python creates a new object.

**Q10. What is string immutability? Why does it matter?**  
> Strings cannot be changed after creation. `s[0] = 'x'` raises TypeError. This allows strings to be hashable (used as dict keys), safely shared, and enables string interning optimization.

**Q11. What are f-strings? When were they introduced?**  
> f-strings (formatted string literals) allow embedding expressions in strings. Introduced in Python 3.6. `f"Hello {name}"` is the modern, preferred way to format strings.

**Q12. What is the difference between `find()` and `index()`?**  
> `find()` returns -1 if substring not found. `index()` raises `ValueError` if not found. Prefer `find()` when you want to check existence, `index()` when you expect the string to exist.

**Q13. What is the `%` operator used for?**  
> Modulus — returns the remainder of division. `17 % 5 = 2`. Also used to check if a number is even (`n % 2 == 0`) or divisible by something.

**Q14. Explain Python's integer caching.**  
> CPython caches integers from -5 to 256. These are pre-created at startup, so `a = 100; b = 100; a is b` is True. For integers outside this range, new objects are created.

**Q15. What are escape sequences? Give 5 examples.**  
> Special character combinations starting with `\`: `\n` (newline), `\t` (tab), `\\` (backslash), `\'` (single quote), `\"` (double quote), `\r` (carriage return).

**Q16. What is the `type()` function?**  
> Returns the class/type of an object. `type(42)` returns `<class 'int'>`. Can also be used to create new types (metaclass usage).

**Q17. What is the difference between `type()` and `isinstance()`?**  
> `type(x) == int` checks exact type. `isinstance(x, int)` also returns True for subclasses. For example, `isinstance(True, int)` is True since `bool` is a subclass of `int`.

**Q18. Why does `input()` always return a string?**  
> `input()` reads raw text from keyboard. Text is always a string. Python doesn't guess the intended type — the programmer must explicitly convert with `int()`, `float()`, etc.

**Q19. What is truthiness in Python?**  
> Every object has a boolean value. Falsy: `0`, `0.0`, `""`, `[]`, `{}`, `None`, `False`. Everything else is truthy. This allows `if my_list:` instead of `if len(my_list) > 0:`.

**Q20. What is `**` used for?**  
> Exponentiation: `2 ** 10 = 1024`. Also used in function definitions as `**kwargs` for variable keyword arguments (covered on Day 03).

**Q21. What is PEP 8?**  
> Python Enhancement Proposal 8 — the official style guide for Python code, covering naming conventions, indentation (4 spaces), line length (79 chars), import ordering, spacing rules.

**Q22. What are Python keywords? Give 5 examples.**  
> Reserved words with special meaning that can't be used as variable names: `if`, `else`, `for`, `while`, `def`, `class`, `import`, `return`, `True`, `False`, `None`.

**Q23. What is the `id()` function?**  
> Returns the memory address (unique identifier) of an object. The id is unique and constant during the object's lifetime. CPython implements it as the memory address.

**Q24. What is implicit type conversion?**  
> Python automatically converts types in mixed-type operations. `int + float → float`, `int + complex → complex`. Python promotes to the "wider" type to prevent data loss.

**Q25. What is the difference between `//` for positive and negative numbers?**  
> Floor division always rounds DOWN (toward negative infinity). `7 // 2 = 3` but `-7 // 2 = -4` (not -3). Contrast with truncation which rounds toward zero.

**Q26. How do you check if a string is a palindrome?**  
> `s == s[::-1]` — compare string with its reverse. For case-insensitive: `s.lower() == s.lower()[::-1]`.

**Q27. What does `strip()` do? Name its variants.**  
> Removes leading and trailing whitespace (or specified chars) from a string. `lstrip()` removes from left only, `rstrip()` from right only.

**Q28. What is string slicing? Give the syntax.**  
> `string[start:stop:step]` — extracts a substring. `start` is inclusive, `stop` is exclusive. Negative indices count from end. Omitting start/stop defaults to 0/len.

**Q29. What is the walrus operator `:=`?**  
> Assignment expression operator (Python 3.8+). Assigns and returns a value in a single expression. Useful in while loops and comprehensions: `while (n := int(input())) != 0:`.

**Q30. Explain short-circuit evaluation.**  
> `and` stops at first False. `or` stops at first True. Remaining operands are not evaluated. Used for safe evaluation: `if x != 0 and y/x > 1:` — won't divide by zero.

**Q31. What is string interning?**  
> Python reuses string objects for short strings (identifiers, string literals). Two variables with the same string literal may point to the same object. Can be forced with `sys.intern()`.

**Q32. What are bitwise operators? When are they used?**  
> Operate on binary representations: `&` (AND), `|` (OR), `^` (XOR), `~` (NOT), `<<` (left shift), `>>` (right shift). Used in cryptography, image processing, permissions, flags.

**Q33. What is the `in` operator?**  
> Membership operator — checks if a value exists in a sequence/collection. Returns `True` or `False`. Works with strings, lists, tuples, sets, dicts (checks keys).

**Q34. What are the augmented assignment operators?**  
> `+=`, `-=`, `*=`, `/=`, `//=`, `%=`, `**=` — perform operation and assign in one step. `x += 5` is equivalent to `x = x + 5`.

**Q35. Why is `float` precision limited?**  
> Floats use IEEE 754 double precision (64-bit) binary representation. Numbers like 0.1 can't be represented exactly in binary, causing small rounding errors. Use `decimal` module for exact calculations.

**Q36. What are raw strings?**  
> Strings prefixed with `r` where backslashes are treated literally, not as escape sequences. `r"C:\Users\file"` keeps the backslashes. Common for regex patterns and file paths.

**Q37. What is `None` vs `False` vs `0`?**  
> All are falsy but different. `None` = absence of value, `False` = boolean false, `0` = integer zero. `None is not False`, `False == 0` (True, because bool is int subclass).

**Q38. How do you convert a number to binary/hex/octal as string?**  
> `bin(255)` → `'0b11111111'`, `hex(255)` → `'0xff'`, `oct(255)` → `'0o377'`. Without prefix: `format(255, 'b')` → `'11111111'`.

**Q39. What does `str.split()` return when called with no arguments?**  
> Splits on any whitespace (spaces, tabs, newlines) and removes empty strings. `"  hello   world  ".split()` → `['hello', 'world']`.

**Q40. What is the difference between `str.replace()` and `str.translate()`?**  
> `replace()` replaces substring occurrences. `translate()` does character-level substitution using a mapping table (faster for many single-char replacements).

**Q41. What is a SyntaxError vs a RuntimeError vs a LogicError?**  
> SyntaxError: code violates grammar rules (detected before running). RuntimeError: error during execution (division by zero, wrong type). LogicError: code runs but gives wrong output (hardest to find).

**Q42. What is CPython?**  
> The standard, reference implementation of Python written in C. When you install Python from python.org, you get CPython. Other implementations: PyPy (faster), Jython (JVM), MicroPython (IoT).

**Q43. What are Python's comparison chaining capabilities?**  
> Python allows `1 < x < 10` which is equivalent to `1 < x and x < 10`. Not valid in most other languages.

**Q44. What does `print(*args, sep=' ', end='\n', file=sys.stdout)` mean?**  
> `*args` = multiple values. `sep` = separator between values (default space). `end` = what to print at end (default newline). `file` = where to print (default stdout).

**Q45. What is the REPL?**  
> Read-Eval-Print Loop — the interactive Python shell. Start with `python` or `python3`. Type expressions, press Enter, see result immediately. Great for testing snippets.

**Q46. What does `__pycache__` contain?**  
> Compiled Python bytecode files (`.pyc`) cached for faster subsequent imports. Python automatically creates and updates these. Safe to delete — Python recreates them.

**Q47. What is the difference between `%s` and `%d` in string formatting?**  
> `%s` formats as string (calls `str()`). `%d` formats as integer. Old-style formatting: `"Name: %s, Age: %d" % ("Alice", 25)`. Prefer f-strings in modern Python.

**Q48. Can Python integers overflow?**  
> No! Python integers have arbitrary precision. They can grow as large as your memory allows. This is unlike C/Java where int overflows to negative.

**Q49. What is operator overloading?**  
> Using the same operator for different types. `+` adds numbers but concatenates strings. `*` multiplies numbers but repeats strings: `"ha" * 3 = "hahaha"`.

**Q50. What is the difference between a keyword argument and a positional argument?**  
> Positional: `print("hello", "world")` — order matters. Keyword: `print("hello", end=" ")` — specified by name. In Day 03 (Functions), this concept is explored deeply.

---

<a name="section-19"></a>
## 📋 Section 19 — Assignments

### Assignment 1 — Personal Profile Card

**Task:** Create a program that collects user information and displays a formatted profile card.

**Requirements:**
- Collect: name, age, city, occupation
- Display in a formatted card with borders
- Show uppercase name, calculate birth year, show city in title case

```python
# ============================================
# Assignment 1: Personal Profile Card
# ============================================

# Collect information
print("=" * 45)
print("       PERSONAL PROFILE GENERATOR")
print("=" * 45)

name = input("Enter your full name: ")
age = int(input("Enter your age: "))
city = input("Enter your city: ")
occupation = input("Enter your occupation: ")

birth_year = 2024 - age

# Display formatted card
print()
print("╔" + "═" * 43 + "╗")
print("║" + " PROFILE CARD ".center(43) + "║")
print("╠" + "═" * 43 + "╣")
print("║" + f"  Name       : {name.title():<28}" + "║")
print("║" + f"  Age        : {age:<28}" + "║")
print("║" + f"  Born       : {birth_year:<28}" + "║")
print("║" + f"  City       : {city.title():<28}" + "║")
print("║" + f"  Occupation : {occupation.title():<28}" + "║")
print("╚" + "═" * 43 + "╝")
```

**Sample Output:**
```
╔═══════════════════════════════════════════╗
║             PROFILE CARD                 ║
╠═══════════════════════════════════════════╣
║  Name       : Alice Johnson              ║
║  Age        : 22                         ║
║  Born       : 2002                       ║
║  City       : Mumbai                     ║
║  Occupation : Software Engineer          ║
╚═══════════════════════════════════════════╝
```

---

### Assignment 2 — String Analyzer

**Task:** Build a comprehensive string analysis tool.

```python
# ============================================
# Assignment 2: String Analyzer
# ============================================

text = input("Enter a sentence to analyze:\n> ")

# Analysis
word_count = len(text.split())
char_count = len(text)
char_no_spaces = len(text.replace(" ", ""))
vowels = sum(text.lower().count(v) for v in "aeiou")
consonants = sum(text.lower().count(c) for c in "bcdfghjklmnpqrstvwxyz")
upper_count = sum(1 for c in text if c.isupper())
lower_count = sum(1 for c in text if c.islower())
digit_count = sum(1 for c in text if c.isdigit())

print("\n" + "=" * 45)
print("          STRING ANALYSIS REPORT")
print("=" * 45)
print(f"  Original     : {text[:30]}{'...' if len(text) > 30 else ''}")
print(f"  Uppercase    : {text.upper()[:30]}")
print(f"  Reversed     : {text[::-1][:30]}")
print("-" * 45)
print(f"  Total chars  : {char_count}")
print(f"  No spaces    : {char_no_spaces}")
print(f"  Words        : {word_count}")
print(f"  Vowels       : {vowels}")
print(f"  Consonants   : {consonants}")
print(f"  Uppercase    : {upper_count}")
print(f"  Lowercase    : {lower_count}")
print(f"  Digits       : {digit_count}")
print("-" * 45)
print(f"  Is Palindrome: {'Yes' if text.lower() == text.lower()[::-1] else 'No'}")
print("=" * 45)
```

---

### Assignment 3 — Unit Converter

**Task:** Build a multi-unit conversion tool.

```python
# ============================================
# Assignment 3: Unit Converter
# ============================================

print("╔══════════════════════════════╗")
print("║       UNIT CONVERTER         ║")
print("╠══════════════════════════════╣")
print("║  1. Length  (km ↔ miles)     ║")
print("║  2. Weight  (kg ↔ lbs)       ║")
print("║  3. Temp    (°C ↔ °F)        ║")
print("║  4. Speed   (km/h ↔ mph)     ║")
print("╚══════════════════════════════╝")

choice = input("\nEnter choice (1-4): ")
value = float(input("Enter value to convert: "))

if choice == "1":
    print(f"\n{value} km = {value * 0.621371:.4f} miles")
    print(f"{value} miles = {value * 1.60934:.4f} km")
elif choice == "2":
    print(f"\n{value} kg = {value * 2.20462:.4f} lbs")
    print(f"{value} lbs = {value * 0.453592:.4f} kg")
elif choice == "3":
    celsius_to_f = value * 9/5 + 32
    f_to_celsius = (value - 32) * 5/9
    print(f"\n{value}°C = {celsius_to_f:.2f}°F")
    print(f"{value}°F = {f_to_celsius:.2f}°C")
elif choice == "4":
    print(f"\n{value} km/h = {value * 0.621371:.4f} mph")
    print(f"{value} mph = {value * 1.60934:.4f} km/h")
else:
    print("Invalid choice!")
```

---

<a name="section-20"></a>
## 🚀 Section 20 — Mini Projects

### Project 1 — Basic Calculator

```python
# ============================================
# PROJECT 1: Basic Calculator
# Author: Python Day 01
# ============================================

def calculator():
    print("╔═══════════════════════════╗")
    print("║   🧮 PYTHON CALCULATOR    ║")
    print("╠═══════════════════════════╣")
    print("║  +  Addition              ║")
    print("║  -  Subtraction           ║")
    print("║  *  Multiplication        ║")
    print("║  /  Division              ║")
    print("║  // Floor Division        ║")
    print("║  %  Modulus               ║")
    print("║  ** Exponentiation        ║")
    print("╚═══════════════════════════╝")

    num1 = float(input("\nEnter first number: "))
    operator = input("Enter operator (+, -, *, /, //, %, **): ")
    num2 = float(input("Enter second number: "))

    print("\n" + "─" * 35)

    if operator == "+":
        result = num1 + num2
        print(f"  {num1} + {num2} = {result}")
    elif operator == "-":
        result = num1 - num2
        print(f"  {num1} - {num2} = {result}")
    elif operator == "*":
        result = num1 * num2
        print(f"  {num1} × {num2} = {result}")
    elif operator == "/":
        if num2 == 0:
            print("  ❌ Error: Cannot divide by zero!")
            return
        result = num1 / num2
        print(f"  {num1} ÷ {num2} = {result:.6f}")
    elif operator == "//":
        if num2 == 0:
            print("  ❌ Error: Cannot divide by zero!")
            return
        result = num1 // num2
        print(f"  {num1} // {num2} = {result}")
    elif operator == "%":
        result = num1 % num2
        print(f"  {num1} % {num2} = {result}")
    elif operator == "**":
        result = num1 ** num2
        print(f"  {num1} ^ {num2} = {result}")
    else:
        print("  ❌ Invalid operator!")
        return

    print("─" * 35)

calculator()
```

---

### Project 2 — Student Information System

```python
# ============================================
# PROJECT 2: Student Information System
# Author: Python Day 01
# ============================================

print("=" * 50)
print("       STUDENT INFORMATION SYSTEM")
print("=" * 50)

# Collect student data
name = input("Student Name: ")
roll = input("Roll Number: ")
branch = input("Branch/Department: ")
semester = int(input("Current Semester (1-8): "))
cgpa = float(input("CGPA (0.0 - 10.0): "))

# Marks for 5 subjects
print("\nEnter marks for 5 subjects (out of 100):")
m1 = float(input("  Subject 1 - Mathematics: "))
m2 = float(input("  Subject 2 - Physics: "))
m3 = float(input("  Subject 3 - Chemistry: "))
m4 = float(input("  Subject 4 - Programming: "))
m5 = float(input("  Subject 5 - English: "))

# Calculate
total = m1 + m2 + m3 + m4 + m5
average = total / 5
percentage = (total / 500) * 100

# Grade calculation
if percentage >= 90:
    grade = "A+ (Outstanding)"
    status = "PASS ✓"
elif percentage >= 80:
    grade = "A  (Excellent)"
    status = "PASS ✓"
elif percentage >= 70:
    grade = "B  (Very Good)"
    status = "PASS ✓"
elif percentage >= 60:
    grade = "C  (Good)"
    status = "PASS ✓"
elif percentage >= 50:
    grade = "D  (Average)"
    status = "PASS ✓"
else:
    grade = "F  (Fail)"
    status = "FAIL ✗"

# Display report card
print("\n" + "═" * 52)
print("              REPORT CARD")
print("═" * 52)
print(f"  Name       : {name.title()}")
print(f"  Roll No    : {roll.upper()}")
print(f"  Branch     : {branch.upper()}")
print(f"  Semester   : {semester}")
print(f"  CGPA       : {cgpa:.2f}")
print("─" * 52)
print(f"  {'Subject':<20} {'Marks':>10} {'Status':>10}")
print("─" * 52)

subjects = [
    ("Mathematics", m1), ("Physics", m2), ("Chemistry", m3),
    ("Programming", m4), ("English", m5)
]

for subject, marks in subjects:
    sub_status = "Pass" if marks >= 40 else "Fail"
    print(f"  {subject:<20} {marks:>10.1f} {sub_status:>10}")

print("─" * 52)
print(f"  {'Total':<20} {total:>10.1f}")
print(f"  {'Average':<20} {average:>10.2f}")
print(f"  {'Percentage':<20} {percentage:>9.2f}%")
print(f"  {'Grade':<20} {grade:>20}")
print(f"  {'Result':<20} {status:>20}")
print("═" * 52)
```

---

### Project 3 — Age Calculator

```python
# ============================================
# PROJECT 3: Age Calculator
# Author: Python Day 01
# ============================================

print("╔══════════════════════════════╗")
print("║      🎂 AGE CALCULATOR        ║")
print("╚══════════════════════════════╝\n")

# Get birth info
birth_year = int(input("Enter birth year (e.g., 2000): "))
birth_month = int(input("Enter birth month (1-12): "))
birth_day = int(input("Enter birth day (1-31): "))

# Current date (hardcoded for Day 01 — we'll use datetime module later)
current_year = 2024
current_month = 6
current_day = 15

# Calculate age
age_years = current_year - birth_year
age_months = current_month - birth_month
age_days = current_day - birth_day

if age_days < 0:
    age_months -= 1
    age_days += 30    # Approximation

if age_months < 0:
    age_years -= 1
    age_months += 12

# Total calculations
total_months = age_years * 12 + age_months
total_days = age_years * 365 + total_months * 30 + age_days  # approximate
total_hours = total_days * 24
total_minutes = total_hours * 60

# Zodiac sign
zodiac_signs = [
    (1, 20, "Aquarius ♒"), (2, 19, "Pisces ♓"), (3, 21, "Aries ♈"),
    (4, 20, "Taurus ♉"), (5, 21, "Gemini ♊"), (6, 21, "Cancer ♋"),
    (7, 23, "Leo ♌"), (8, 23, "Virgo ♍"), (9, 23, "Libra ♎"),
    (10, 23, "Scorpio ♏"), (11, 22, "Sagittarius ♐"), (12, 22, "Capricorn ♑")
]

zodiac = "Capricorn ♑"  # default
for month, day_limit, sign in zodiac_signs:
    if birth_month == month and birth_day >= day_limit:
        zodiac = sign
        break
    elif birth_month == month + 1 and birth_day < day_limit:
        zodiac = sign
        break

print("\n" + "═" * 45)
print("           AGE ANALYSIS REPORT")
print("═" * 45)
print(f"  Date of Birth : {birth_day:02d}/{birth_month:02d}/{birth_year}")
print(f"  As of Date    : {current_day:02d}/{current_month:02d}/{current_year}")
print("─" * 45)
print(f"  Age           : {age_years} years, {age_months} months, {age_days} days")
print(f"  Total Months  : {total_months:,}")
print(f"  Total Days    : {total_days:,}")
print(f"  Total Hours   : {total_hours:,}")
print(f"  Total Minutes : {total_minutes:,}")
print("─" * 45)
print(f"  Zodiac Sign   : {zodiac}")
print(f"  Generation    : ", end="")

if birth_year >= 2013:
    print("Gen Alpha (2013+)")
elif birth_year >= 1997:
    print("Gen Z (1997–2012)")
elif birth_year >= 1981:
    print("Millennial (1981–1996)")
elif birth_year >= 1965:
    print("Gen X (1965–1980)")
else:
    print("Baby Boomer or earlier")

print("═" * 45)
```

---

### Project 4 — String Analyzer Pro

```python
# ============================================
# PROJECT 4: String Analyzer Pro
# Author: Python Day 01
# ============================================

def analyze_string(text):
    """Complete string analysis function."""
    print("\n" + "═" * 55)
    print("              STRING ANALYSIS PRO")
    print("═" * 55)
    print(f"  Input: \"{text[:40]}{'...' if len(text) > 40 else ''}\"")
    print("─" * 55)

    # Transformations
    print("  TRANSFORMATIONS:")
    print(f"    Uppercase  : {text.upper()[:40]}")
    print(f"    Lowercase  : {text.lower()[:40]}")
    print(f"    Title Case : {text.title()[:40]}")
    print(f"    Reversed   : {text[::-1][:40]}")
    print(f"    Stripped   : {text.strip()[:40]}")

    print("─" * 55)

    # Statistics
    words = text.split()
    chars = len(text)
    chars_no_space = len(text.replace(" ", ""))
    vowels = sum(text.lower().count(v) for v in "aeiou")
    consonants = sum(text.lower().count(c) for c in "bcdfghjklmnpqrstvwxyz")
    digits = sum(1 for c in text if c.isdigit())
    spaces = text.count(" ")
    sentences = text.count(".") + text.count("!") + text.count("?")

    print("  STATISTICS:")
    print(f"    Characters (total)    : {chars}")
    print(f"    Characters (no space) : {chars_no_space}")
    print(f"    Words                 : {len(words)}")
    print(f"    Sentences (approx)    : {max(sentences, 1)}")
    print(f"    Vowels                : {vowels}")
    print(f"    Consonants            : {consonants}")
    print(f"    Digits                : {digits}")
    print(f"    Spaces                : {spaces}")

    print("─" * 55)

    # Checks
    print("  CHECKS:")
    print(f"    Is palindrome  : {'Yes' if text.lower().replace(' ','') == text.lower().replace(' ','')[::-1] else 'No'}")
    print(f"    Starts with cap: {'Yes' if text and text[0].isupper() else 'No'}")
    print(f"    Contains digits: {'Yes' if any(c.isdigit() for c in text) else 'No'}")
    print(f"    Is title case  : {'Yes' if text == text.title() else 'No'}")
    print(f"    All uppercase  : {'Yes' if text.isupper() else 'No'}")

    print("═" * 55)

# Run
text_input = input("Enter text to analyze:\n> ")
analyze_string(text_input)
```

---

### Project 5 — Number Analyzer

```python
# ============================================
# PROJECT 5: Number Analyzer
# Author: Python Day 01
# ============================================

def analyze_number(n):
    """Complete number analysis."""
    print("\n" + "═" * 45)
    print(f"       NUMBER ANALYSIS: {n}")
    print("═" * 45)

    # Basic properties
    print("  PROPERTIES:")
    print(f"    Value      : {n}")
    print(f"    Type       : {type(n).__name__}")
    print(f"    Absolute   : {abs(n)}")

    if isinstance(n, (int, float)):
        print(f"    Square     : {n ** 2}")
        print(f"    Square Root: {n ** 0.5:.4f}" if n >= 0 else "    Square Root: Not real")
        print(f"    Reciprocal : {1/n:.6f}" if n != 0 else "    Reciprocal : Undefined")

    if isinstance(n, int):
        print("─" * 45)
        print("  INTEGER CHECKS:")
        print(f"    Even/Odd   : {'Even' if n % 2 == 0 else 'Odd'}")
        print(f"    Positive   : {'Yes' if n > 0 else 'No' if n < 0 else 'Zero'}")

        # Prime check
        is_prime = n > 1 and all(n % i != 0 for i in range(2, int(n**0.5) + 1))
        print(f"    Prime      : {'Yes' if is_prime else 'No'}")

        # Perfect square
        sqrt = int(n ** 0.5)
        print(f"    Perfect Sq : {'Yes' if n >= 0 and sqrt * sqrt == n else 'No'}")

        # Divisors
        if 0 < n <= 1000:
            divisors = [i for i in range(1, n + 1) if n % i == 0]
            print(f"    Divisors   : {divisors[:10]}{'...' if len(divisors) > 10 else ''}")
            print(f"    # Divisors : {len(divisors)}")

        print("─" * 45)
        print("  REPRESENTATIONS:")
        print(f"    Decimal    : {n}")
        print(f"    Binary     : {bin(n)}")
        print(f"    Octal      : {oct(n)}")
        print(f"    Hexadecimal: {hex(n)}")

    print("═" * 45)

# Run
user_input = input("Enter a number to analyze: ")

# Try integer first, then float
try:
    num = int(user_input)
except ValueError:
    try:
        num = float(user_input)
    except ValueError:
        print("❌ Invalid number input!")
        exit()

analyze_number(num)
```

---

<a name="section-21"></a>
## 📖 Section 21 — Day 01 Revision Notes

### 21.1 One-Page Cheat Sheet

```
╔══════════════════════════════════════════════════════════╗
║              PYTHON DAY 01 — CHEAT SHEET                 ║
╠══════════════════════════════════════════════════════════╣
║  VARIABLES                                               ║
║  x = 10         # int                                   ║
║  y = 3.14       # float                                 ║
║  z = "hello"    # str                                   ║
║  b = True       # bool                                  ║
║  n = None       # NoneType                              ║
╠══════════════════════════════════════════════════════════╣
║  TYPE FUNCTIONS                                          ║
║  type(x)        # check type                            ║
║  id(x)          # memory address                        ║
║  isinstance(x, int)  # type check with inheritance      ║
╠══════════════════════════════════════════════════════════╣
║  CASTING                                                 ║
║  int("42")  float("3.14")  str(42)  bool(1)             ║
╠══════════════════════════════════════════════════════════╣
║  ARITHMETIC: + - * / // % **                            ║
║  COMPARISON: == != > < >= <=                             ║
║  LOGICAL:    and  or  not                                ║
║  ASSIGNMENT: = += -= *= /= //= %= **=                   ║
║  MEMBERSHIP: in  not in                                  ║
║  IDENTITY:   is  is not                                  ║
║  BITWISE:    & | ^ ~ << >>                               ║
╠══════════════════════════════════════════════════════════╣
║  I/O                                                     ║
║  name = input("Enter: ")   # always str                 ║
║  print(f"Hello {name}")    # f-string output            ║
╠══════════════════════════════════════════════════════════╣
║  STRING SLICING                                          ║
║  s[0]    first char     s[-1]   last char               ║
║  s[1:4]  slice          s[::-1] reverse                 ║
╠══════════════════════════════════════════════════════════╣
║  KEY STRING METHODS                                      ║
║  .upper() .lower() .title() .strip() .split() .join()   ║
║  .replace() .find() .count() .startswith() .endswith()  ║
╠══════════════════════════════════════════════════════════╣
║  COMMENTS                                                ║
║  # single line          """multi line"""                ║
╠══════════════════════════════════════════════════════════╣
║  NAMING                                                  ║
║  snake_case → variables   PascalCase → classes          ║
║  UPPER_CASE → constants   _private → internal           ║
╚══════════════════════════════════════════════════════════╝
```

---

### 21.2 Mind Map

```
                    PYTHON DAY 01
                         │
        ┌────────────────┼────────────────┐
        │                │                │
   FUNDAMENTALS      DATA TYPES       OPERATIONS
        │                │                │
   ┌────┴────┐      ┌────┴────┐      ┌────┴────┐
 Variables  I/O    int float  │   Arithmetic  Logic
   Rules   input   str bool  str  Comparison  Bitwise
  Naming  print() NoneType    │   Assignment  Member
                           complex  Identity
        │                │                │
   STRINGS           MEMORY           DEBUGGING
        │                │                │
  Indexing          Objects          Syntax
  Slicing          Mutable/         Runtime
  Methods          Immutable        Logical
  f-strings      References
  Escape          GarbageGC
```

---

### 21.3 Quick Revision Table

| Concept | Key Point | Example |
|---------|-----------|---------|
| Variable | Named reference to object | `x = 42` |
| int | Whole number, unlimited size | `age = 25` |
| float | Decimal, IEEE 754 | `pi = 3.14` |
| str | Immutable sequence of chars | `"Hello"` |
| bool | Subclass of int | `True == 1` |
| None | Absence of value | `x = None` |
| `type()` | Returns class of object | `type(42)` → `int` |
| `id()` | Returns memory address | `id(x)` |
| `input()` | Always returns str | Convert with `int()` |
| `print()` | Display output | `print(f"{x}")` |
| `/` | True division (float) | `7/2 = 3.5` |
| `//` | Floor division (int) | `7//2 = 3` |
| `%` | Modulus (remainder) | `7%2 = 1` |
| `**` | Exponentiation | `2**8 = 256` |
| `is` | Identity check | Use for None only |
| `==` | Value comparison | Use for values |
| `in` | Membership test | `"a" in "cat"` |
| Slicing | `s[start:stop:step]` | `s[::-1]` reverse |
| f-string | Embed expressions | `f"{name.upper()}"` |
| PEP 8 | 4 spaces, snake_case | Style guide |

---

<a name="section-22"></a>
## 🗺️ Section 22 — Day 02 Roadmap

### What's Coming Tomorrow

```
DAY 02 — CONTROL FLOW: MAKING DECISIONS

─────────────────────────────────────────────────────────

  Today (Day 01):          Tomorrow (Day 02):
  ─────────────────        ─────────────────────
  Variables ✓              if statement
  Data Types ✓             if-else
  Operators ✓              if-elif-else
  Strings ✓                Nested if
                           match-case (Python 3.10+)
                           Ternary expressions
                           Chained comparisons
                           Control flow patterns

─────────────────────────────────────────────────────────
```

### Day 02 Preview

```python
# COMING TOMORROW: if-else

age = int(input("Enter age: "))

if age >= 18:
    print("Adult — can vote!")
elif age >= 13:
    print("Teenager")
else:
    print("Child")

# match-case (Python 3.10+)
command = input("Enter command: ")
match command:
    case "quit":
        print("Exiting...")
    case "help":
        print("Available commands...")
    case _:
        print("Unknown command")
```

### Complete 30-Day Roadmap

```
Week 1 — Python Foundations:
  Day 01 ✓ Variables, Types, Operators, Strings
  Day 02   Control Flow (if/elif/else)
  Day 03   Loops (for, while, break, continue)
  Day 04   Functions (def, args, kwargs, return)
  Day 05   Data Structures — Lists
  Day 06   Data Structures — Tuples, Sets
  Day 07   Data Structures — Dictionaries

Week 2 — Intermediate Python:
  Day 08   File I/O (read, write, append)
  Day 09   Exception Handling (try/except)
  Day 10   OOP — Classes and Objects
  Day 11   OOP — Inheritance, Polymorphism
  Day 12   Modules and Packages
  Day 13   Comprehensions (list, dict, set)
  Day 14   Lambda, Map, Filter, Reduce

Week 3 — Advanced Python:
  Day 15   Decorators and Closures
  Day 16   Generators and Iterators
  Day 17   Context Managers (with)
  Day 18   Regular Expressions (re module)
  Day 19   Multithreading basics
  Day 20   Database — SQLite3
  Day 21   API calls — requests library

Week 4 — Applied Python:
  Day 22   NumPy fundamentals
  Day 23   Pandas fundamentals
  Day 24   Matplotlib / Seaborn
  Day 25   scikit-learn basics
  Day 26   PyTorch introduction
  Day 27   FastAPI — building APIs
  Day 28   LangChain basics
  Day 29   Capstone Project
  Day 30   Review + Next Steps
```

---

## 🎯 Day 01 Completion Checklist

Before moving to Day 02, verify:

- [ ] I understand what programming is and why Python was created
- [ ] I can run a Python program and understand the execution flow
- [ ] I can create variables and know the 6 basic data types
- [ ] I can use `type()` and `id()` functions
- [ ] I can get input from user and display formatted output
- [ ] I understand all 7 types of operators
- [ ] I can index, slice, and use string methods confidently
- [ ] I understand mutable vs immutable concepts
- [ ] I can identify and fix syntax, runtime, and logical errors
- [ ] I follow PEP 8 naming conventions
- [ ] I completed at least 30 practice questions
- [ ] I built at least 2 mini projects

---

## 📚 Recommended Resources

| Resource | Type | Link |
|----------|------|------|
| Official Python Docs | Documentation | docs.python.org |
| Python Tutorial | Official Tutorial | docs.python.org/3/tutorial |
| Real Python | Articles + Courses | realpython.com |
| Python Visualizer | Visual debugger | pythontutor.com |
| PEP 8 Style Guide | Standards | pep8.org |
| Exercism Python | Practice | exercism.org/tracks/python |
| LeetCode | DSA Practice | leetcode.com |

---

```
"The best way to learn Python is to write Python.
 Close this document, open your editor, and START CODING."

                              — Python Day 01 Complete ✓
                              — Day 02 Awaits You! 🚀
```

---

*Python Mastery Series | Day 01 of 30 | Version 1.0*  
*Generated for: LLM Engineering & AI Research Track*

---
