# 🚀 Day 17 — Binary Search + Two Pointers + Sliding Window + Sorting + LeetCode & Kaggle Mastery

---

## 📋 Table of Contents

| Section | Topic | Difficulty |
|---------|-------|------------|
| 01 | Complete Revision Day01–Day16 | ⭐ |
| 02 | Problem Solving Framework | ⭐⭐ |
| 03 | Binary Search Masterclass | ⭐⭐ |
| 04 | Advanced Binary Search Patterns | ⭐⭐⭐ |
| 05 | Two Pointer Masterclass | ⭐⭐ |
| 06 | Two Pointer Patterns | ⭐⭐⭐ |
| 07 | Sliding Window Masterclass | ⭐⭐ |
| 08 | Advanced Sliding Window Patterns | ⭐⭐⭐ |
| 09 | Sorting Masterclass | ⭐⭐⭐ |
| 10 | Recursion for DSA | ⭐⭐ |
| 11 | LeetCode Mastery Framework | ⭐⭐⭐ |
| 12 | LeetCode Roadmap (230 Problems) | ⭐⭐⭐ |
| 13 | LeetCode Interview System | ⭐⭐⭐ |
| 14 | Competitive Programming Masterclass | ⭐⭐⭐ |
| 15 | Kaggle Masterclass | ⭐⭐ |
| 16 | Kaggle Profile Setup | ⭐⭐ |
| 17 | Kaggle Projects (10 Projects) | ⭐⭐⭐ |
| 18 | Mini Projects (10 Projects) | ⭐⭐⭐ |
| 19 | 20 Portfolio Projects | ⭐⭐⭐⭐ |
| 20 | Project Layout Masterclass | ⭐⭐ |
| 21 | GitHub Profile Booster Projects | ⭐⭐⭐ |
| 22 | Daily Practice System | ⭐⭐ |
| 23 | 500 Practice Questions | ⭐⭐⭐ |
| 24 | 200 Interview Questions | ⭐⭐⭐⭐ |
| 25 | Assignments + Solutions | ⭐⭐⭐ |
| 26 | Enterprise Challenge Projects | ⭐⭐⭐⭐ |
| 27 | Day17 Revision | ⭐ |
| 28 | Preparation for Day18 | ⭐⭐ |

---

# 📚 SECTION 1 — COMPLETE REVISION DAY01–DAY16

## 1.1 Python Learning Roadmap Summary

```
Day01  → Python Fundamentals    → Variables, Types, Operators
Day02  → Strings               → Methods, Formatting, Slicing
Day03  → Conditionals          → if/elif/else, Ternary
Day04  → Loops                 → for, while, break, continue
Day05  → Functions + Recursion → def, *args, **kwargs, lambda
Day06  → Lists                 → CRUD, Comprehensions, Sorting
Day07  → Tuples+Sets+Dicts     → Immutability, Hashing, Mapping
Day08  → Modules + Packages    → import, pip, virtual environments
Day09  → Exception Handling    → try/except/finally, Custom Errors
Day10  → File Handling         → open(), CSV, JSON, pathlib
Day11  → OOP Foundations       → class, __init__, inheritance
Day12  → Advanced OOP          → Abstract, Protocol, Mixins, MRO
Day13  → Advanced Python       → Generators, Decorators, Context Mgr
Day14  → Testing + CI/CD       → pytest, coverage, GitHub Actions
Day15  → Software Architecture → SOLID, Design Patterns, Capstone
Day16  → Big O + Arrays        → Complexity, Searching, Prefix Sums
Day17  → Binary Search + 2P    → THIS DOCUMENT ← You Are Here
```

---

## 1.2 Big O Cheat Sheet

| Notation | Name | Example | Growth |
|----------|------|---------|--------|
| O(1) | Constant | Array index access | Flat line |
| O(log n) | Logarithmic | Binary search | Very slow growth |
| O(n) | Linear | Linear search | Straight line |
| O(n log n) | Linearithmic | Merge sort | Slightly curved |
| O(n²) | Quadratic | Bubble sort | Steep curve |
| O(2ⁿ) | Exponential | Fibonacci naive | Explosive |
| O(n!) | Factorial | Permutations | Astronomical |

**Golden Rule:** Always aim for the lowest complexity possible.

```
Speed Comparison for n = 1,000,000:
O(1)       →        1 operation
O(log n)   →       20 operations
O(n)       →    1,000,000 operations
O(n log n) →   20,000,000 operations
O(n²)      → 1,000,000,000,000 operations ← NEVER acceptable
```

---

## 1.3 Arrays Cheat Sheet

```python
# Creation
arr = []                    # empty list
arr = [0] * n               # n zeros
arr = list(range(n))        # [0, 1, 2, ..., n-1]

# Access
arr[0]                      # first element  O(1)
arr[-1]                     # last element   O(1)
arr[i:j]                    # slice          O(j-i)

# Modification
arr.append(x)               # add to end     O(1) amortized
arr.insert(i, x)            # insert at i    O(n)
arr.pop()                   # remove last    O(1)
arr.pop(i)                  # remove at i    O(n)

# Search
x in arr                    # contains       O(n)
arr.index(x)                # find index     O(n)

# Iteration
for x in arr:               # traverse       O(n)
for i, x in enumerate(arr): # with index     O(n)

# Sorting
arr.sort()                  # in-place       O(n log n)
sorted(arr)                 # new list       O(n log n)

# 2D Arrays
matrix = [[0]*cols for _ in range(rows)]
matrix[r][c]                # access cell    O(1)
```

---

## 1.4 Prefix Sum Cheat Sheet

```python
# Build prefix sum
def build_prefix(arr):
    prefix = [0] * (len(arr) + 1)
    for i in range(len(arr)):
        prefix[i+1] = prefix[i] + arr[i]
    return prefix

# Range sum query [l, r] inclusive  O(1)
def range_sum(prefix, l, r):
    return prefix[r+1] - prefix[l]

# Use Cases:
# - Sum of any subarray in O(1)
# - Count elements satisfying condition
# - Equilibrium index
# - Subarray with target sum
```

---

## 1.5 Searching Cheat Sheet

| Algorithm | Best | Average | Worst | Space | Prerequisite |
|-----------|------|---------|-------|-------|--------------|
| Linear Search | O(1) | O(n) | O(n) | O(1) | None |
| Binary Search | O(1) | O(log n) | O(log n) | O(1) | Sorted |
| Jump Search | O(1) | O(√n) | O(√n) | O(1) | Sorted |
| Interpolation | O(1) | O(log log n) | O(n) | O(1) | Sorted+Uniform |
| Exponential | O(1) | O(log n) | O(log n) | O(1) | Sorted |

---

# 🧠 SECTION 2 — PROBLEM SOLVING FRAMEWORK

## 2.1 The 10-Step Framework Used by Top Engineers

This is how FAANG engineers approach every problem. Internalize this.

```
STEP 1: UNDERSTAND THE PROBLEM
   → Read the problem 2–3 times
   → Don't rush to code
   → Ask: What am I actually being asked?

STEP 2: IDENTIFY INPUT
   → What data comes in?
   → What are the data types?
   → What is the size range?

STEP 3: IDENTIFY OUTPUT
   → What should I return?
   → What format is expected?
   → What if no answer exists?

STEP 4: FIND CONSTRAINTS
   → n ≤ 100? → O(n²) might be fine
   → n ≤ 10⁵? → Need O(n log n)
   → n ≤ 10⁶? → Need O(n) or O(n log n)
   → n ≤ 10⁹? → Need O(log n) or O(1)

STEP 5: BRUTE FORCE FIRST
   → What's the simplest solution?
   → Don't optimize yet
   → Get it working first

STEP 6: OPTIMIZE
   → What repeated work can be eliminated?
   → Can I precompute anything?
   → Which pattern fits? (BS, 2P, SW, DP?)

STEP 7: COMPLEXITY ANALYSIS
   → Time: How many operations?
   → Space: How much memory?
   → Is this within constraints?

STEP 8: TEST EDGE CASES
   → Empty input
   → Single element
   → All same elements
   → Negative numbers
   → Maximum values

STEP 9: REFACTOR
   → Clean variable names
   → Remove redundant code
   → Add comments

STEP 10: DOCUMENT
   → Write docstring
   → Add complexity comment
   → Explain approach
```

---

## 2.2 Pattern Recognition Guide

```
Input is SORTED?                    → Try Binary Search
Need to find a PAIR/TRIPLET?       → Try Two Pointers
Need SUBARRAY/SUBSTRING optimum?   → Try Sliding Window
Need to COUNT/SUM ranges?          → Try Prefix Sum
Need MINIMUM/MAXIMUM of something? → Try Binary Search on Answer
Contains DUPLICATES pattern?       → Try Hashing
Need ORDERING relationship?        → Try Sorting first
Overlapping subproblems?           → Try Dynamic Programming (later)
Tree/Graph traversal?              → Try BFS/DFS (later)
```

---

## 2.3 Professional Problem Solving Example

**Problem:** Given sorted array, find if target exists.

```python
def solve(arr: list[int], target: int) -> bool:
    """
    Find if target exists in sorted array.
    
    Args:
        arr: Sorted array of integers
        target: Value to search for
    
    Returns:
        True if found, False otherwise
    
    Time: O(log n)   — Binary search
    Space: O(1)      — No extra space
    
    Approach:
        1. Sorted input → Binary search pattern
        2. Maintain lo, hi pointers
        3. Narrow search space each iteration
    
    Edge Cases:
        - Empty array → False
        - Target smaller than all → False  
        - Target larger than all → False
    """
    # Edge case
    if not arr:
        return False
    
    # Binary search
    lo, hi = 0, len(arr) - 1
    while lo <= hi:
        mid = lo + (hi - lo) // 2  # Avoids integer overflow
        if arr[mid] == target:
            return True
        elif arr[mid] < target:
            lo = mid + 1
        else:
            hi = mid - 1
    
    return False

# Test
arr = [1, 3, 5, 7, 9, 11, 13]
print(solve(arr, 7))    # True
print(solve(arr, 6))    # False
print(solve([], 5))     # False
```

---

# 🔍 SECTION 3 — BINARY SEARCH MASTERCLASS

## 3.1 What is Binary Search?

Binary Search is an algorithm that finds the position of a target value in a **sorted array** by repeatedly halving the search space.

> **Real World Analogy:** Imagine finding a word in a dictionary. You don't start from page 1. You open the middle, see if your word comes before or after, then repeat on the relevant half. This is exactly binary search.

---

## 3.2 Why Binary Search Works

Binary search works because of one crucial property:

> **If the array is sorted, we can eliminate HALF the remaining elements in each step.**

This gives us O(log n) — for n = 1,000,000, that's only ~20 comparisons vs 1,000,000 for linear search.

```
Array: [1, 3, 5, 7, 9, 11, 13, 15, 17, 19]
                        ↑
                    Start here (middle)
                    
If target > middle → search RIGHT half
If target < middle → search LEFT half
If target == middle → FOUND!

Each step: eliminates half the remaining elements
```

---

## 3.3 Internal Working — Step by Step

### Visualization

```
Array: [2, 5, 8, 12, 16, 23, 38, 56, 72, 91]
Index:  0  1  2   3   4   5   6   7   8   9

Target = 23

Step 1: lo=0, hi=9, mid=4, arr[4]=16
        16 < 23 → search right → lo = 5

Step 2: lo=5, hi=9, mid=7, arr[7]=56
        56 > 23 → search left → hi = 6

Step 3: lo=5, hi=6, mid=5, arr[5]=23
        23 == 23 → FOUND at index 5! ✅

Total comparisons: 3
Linear search would need: 6
```

### Dry Run Table

| Step | lo | hi | mid | arr[mid] | Decision |
|------|----|----|-----|----------|----------|
| 1 | 0 | 9 | 4 | 16 | 16 < 23, lo = 5 |
| 2 | 5 | 9 | 7 | 56 | 56 > 23, hi = 6 |
| 3 | 5 | 6 | 5 | 23 | Found! Return 5 |

---

## 3.4 Classic Binary Search Implementation

```python
def binary_search(arr: list[int], target: int) -> int:
    """
    Classic binary search on sorted array.
    
    Returns: Index of target, or -1 if not found
    Time: O(log n)
    Space: O(1)
    """
    lo, hi = 0, len(arr) - 1
    
    while lo <= hi:
        # IMPORTANT: Use lo + (hi-lo)//2 to avoid overflow
        # In Python, integers don't overflow, but good habit
        mid = lo + (hi - lo) // 2
        
        if arr[mid] == target:
            return mid
        elif arr[mid] < target:
            lo = mid + 1      # Target in right half
        else:
            hi = mid - 1      # Target in left half
    
    return -1  # Not found


def binary_search_recursive(arr: list[int], target: int, lo: int = 0, hi: int = None) -> int:
    """
    Recursive version of binary search.
    Time: O(log n)
    Space: O(log n) — call stack
    """
    if hi is None:
        hi = len(arr) - 1
    
    if lo > hi:
        return -1  # Base case: not found
    
    mid = lo + (hi - lo) // 2
    
    if arr[mid] == target:
        return mid
    elif arr[mid] < target:
        return binary_search_recursive(arr, target, mid + 1, hi)
    else:
        return binary_search_recursive(arr, target, lo, mid - 1)


# Tests
arr = [1, 3, 5, 7, 9, 11, 13, 15]
print(binary_search(arr, 7))    # 3
print(binary_search(arr, 6))    # -1
print(binary_search(arr, 1))    # 0
print(binary_search(arr, 15))   # 7
```

---

## 3.5 Complexity Analysis

| Aspect | Value | Reason |
|--------|-------|--------|
| Time — Best | O(1) | Target is at mid first try |
| Time — Average | O(log n) | Halve space each time |
| Time — Worst | O(log n) | Target not found |
| Space — Iterative | O(1) | No extra memory |
| Space — Recursive | O(log n) | Call stack depth |

**Why log n?**

```
After 1 step:  n/2 elements remain
After 2 steps: n/4 elements remain
After 3 steps: n/8 elements remain
After k steps: n/2^k elements remain

When does it stop? When n/2^k = 1
→ 2^k = n
→ k = log₂(n)

So we do at most log₂(n) steps.
```

---

## 3.6 Common Mistakes in Binary Search

```python
# MISTAKE 1: Wrong mid calculation (can cause infinite loop)
mid = (lo + hi) // 2      # OK in Python, bad in C++/Java
mid = lo + (hi - lo) // 2  # ✅ Always use this

# MISTAKE 2: Wrong loop condition
while lo < hi:    # ❌ Misses single element arrays
while lo <= hi:   # ✅ Correct

# MISTAKE 3: Wrong boundary update
lo = mid      # ❌ Can cause infinite loop
lo = mid + 1  # ✅ Correct

hi = mid      # ❌ Can cause infinite loop  
hi = mid - 1  # ✅ Correct

# MISTAKE 4: Not handling empty array
def bad_search(arr, target):
    lo, hi = 0, len(arr) - 1  # ❌ hi = -1 if empty!
    
def good_search(arr, target):
    if not arr:                # ✅ Check first
        return -1
    lo, hi = 0, len(arr) - 1
```

---

# 🔍 SECTION 4 — ADVANCED BINARY SEARCH PATTERNS

## 4.1 Pattern 1: First Occurrence

**Problem:** In a sorted array with duplicates, find the FIRST position of target.

```
Array: [1, 2, 2, 2, 3, 4, 5]
                ↑
        Target = 2, Answer = 1 (first index)
```

```python
def first_occurrence(arr: list[int], target: int) -> int:
    """
    Find first index of target in sorted array with duplicates.
    
    Strategy: When arr[mid] == target, DON'T stop.
              Record the answer and keep searching LEFT.
    
    Time: O(log n)  Space: O(1)
    """
    lo, hi = 0, len(arr) - 1
    result = -1
    
    while lo <= hi:
        mid = lo + (hi - lo) // 2
        
        if arr[mid] == target:
            result = mid      # Found one, but might be earlier
            hi = mid - 1     # Keep searching left!
        elif arr[mid] < target:
            lo = mid + 1
        else:
            hi = mid - 1
    
    return result


# Dry Run: arr=[1,2,2,2,3], target=2
# Step 1: lo=0, hi=4, mid=2, arr[2]=2 → result=2, hi=1
# Step 2: lo=0, hi=1, mid=0, arr[0]=1 → lo=1
# Step 3: lo=1, hi=1, mid=1, arr[1]=2 → result=1, hi=0
# Step 4: lo=1, hi=0 → EXIT
# Return: 1 ✅

arr = [1, 2, 2, 2, 3, 4, 5]
print(first_occurrence(arr, 2))  # 1
print(first_occurrence(arr, 1))  # 0
print(first_occurrence(arr, 5))  # 6
print(first_occurrence(arr, 6))  # -1
```

---

## 4.2 Pattern 2: Last Occurrence

```python
def last_occurrence(arr: list[int], target: int) -> int:
    """
    Find last index of target in sorted array with duplicates.
    
    Strategy: When arr[mid] == target, record and search RIGHT.
    
    Time: O(log n)  Space: O(1)
    """
    lo, hi = 0, len(arr) - 1
    result = -1
    
    while lo <= hi:
        mid = lo + (hi - lo) // 2
        
        if arr[mid] == target:
            result = mid      # Found one, but might be later
            lo = mid + 1     # Keep searching right!
        elif arr[mid] < target:
            lo = mid + 1
        else:
            hi = mid - 1
    
    return result


# Count occurrences of target
def count_occurrences(arr: list[int], target: int) -> int:
    first = first_occurrence(arr, target)
    if first == -1:
        return 0
    last = last_occurrence(arr, target)
    return last - first + 1

arr = [1, 2, 2, 2, 3, 4, 5]
print(count_occurrences(arr, 2))  # 3
print(count_occurrences(arr, 1))  # 1
print(count_occurrences(arr, 6))  # 0
```

---

## 4.3 Pattern 3: Search Insert Position (LeetCode #35)

**Problem:** Given sorted array and target, find where target would be inserted.

```python
def search_insert(arr: list[int], target: int) -> int:
    """
    LeetCode 35: Search Insert Position
    
    Returns: Index where target is, or where it would be inserted.
    
    Time: O(log n)  Space: O(1)
    """
    lo, hi = 0, len(arr) - 1
    
    while lo <= hi:
        mid = lo + (hi - lo) // 2
        
        if arr[mid] == target:
            return mid
        elif arr[mid] < target:
            lo = mid + 1
        else:
            hi = mid - 1
    
    # When loop ends, lo is the insertion point
    return lo


arr = [1, 3, 5, 6]
print(search_insert(arr, 5))  # 2
print(search_insert(arr, 2))  # 1
print(search_insert(arr, 7))  # 4
print(search_insert(arr, 0))  # 0
```

---

## 4.4 Pattern 4: Find Peak Element (LeetCode #162)

**Problem:** Peak element is greater than its neighbors. Find any peak.

```python
def find_peak_element(nums: list[int]) -> int:
    """
    LeetCode 162: Find Peak Element
    
    Key Insight: If arr[mid] < arr[mid+1], there's a peak to the RIGHT.
                 If arr[mid] > arr[mid+1], there's a peak to the LEFT (or at mid).
    
    Time: O(log n)  Space: O(1)
    """
    lo, hi = 0, len(nums) - 1
    
    while lo < hi:
        mid = lo + (hi - lo) // 2
        
        if nums[mid] < nums[mid + 1]:
            lo = mid + 1  # Peak is to the right
        else:
            hi = mid      # Peak is at mid or to the left
    
    return lo  # lo == hi at this point


nums = [1, 2, 3, 1]
print(find_peak_element(nums))  # 2 (nums[2]=3 is peak)

nums = [1, 2, 1, 3, 5, 6, 4]
print(find_peak_element(nums))  # 5 (nums[5]=6 is peak)
```

---

## 4.5 Pattern 5: Search in Rotated Sorted Array (LeetCode #33)

**Problem:** Array was sorted, then rotated. Find target.

```
Original: [1, 2, 3, 4, 5, 6, 7]
Rotated:  [4, 5, 6, 7, 1, 2, 3]
                   ↑
              Rotation point
```

```python
def search_rotated(nums: list[int], target: int) -> int:
    """
    LeetCode 33: Search in Rotated Sorted Array
    
    Key Insight: After finding mid, ONE of the two halves is always sorted.
                 Check if target is in the sorted half; if yes, search there.
    
    Time: O(log n)  Space: O(1)
    """
    lo, hi = 0, len(nums) - 1
    
    while lo <= hi:
        mid = lo + (hi - lo) // 2
        
        if nums[mid] == target:
            return mid
        
        # Left half is sorted
        if nums[lo] <= nums[mid]:
            if nums[lo] <= target < nums[mid]:
                hi = mid - 1          # Target in sorted left half
            else:
                lo = mid + 1          # Target in right half
        
        # Right half is sorted
        else:
            if nums[mid] < target <= nums[hi]:
                lo = mid + 1          # Target in sorted right half
            else:
                hi = mid - 1          # Target in left half
    
    return -1


nums = [4, 5, 6, 7, 0, 1, 2]
print(search_rotated(nums, 0))   # 4
print(search_rotated(nums, 3))   # -1
print(search_rotated(nums, 6))   # 2
```

---

## 4.6 Pattern 6: Find Minimum in Rotated Array (LeetCode #153)

```python
def find_min_rotated(nums: list[int]) -> int:
    """
    LeetCode 153: Find Minimum in Rotated Sorted Array
    
    The minimum is always at the rotation point.
    
    Key: If nums[mid] > nums[hi], minimum is in RIGHT half
         Otherwise, minimum is in LEFT half (or at mid)
    
    Time: O(log n)  Space: O(1)
    """
    lo, hi = 0, len(nums) - 1
    
    while lo < hi:
        mid = lo + (hi - lo) // 2
        
        if nums[mid] > nums[hi]:
            lo = mid + 1  # Min is in right half
        else:
            hi = mid      # Min is at mid or left of mid
    
    return nums[lo]


print(find_min_rotated([3, 4, 5, 1, 2]))  # 1
print(find_min_rotated([4, 5, 6, 7, 0, 1, 2]))  # 0
print(find_min_rotated([11, 13, 15, 17]))  # 11
```

---

## 4.7 Pattern 7: Binary Search on Answer

This is the most powerful and often overlooked binary search pattern.

**Idea:** Instead of searching in the given array, we binary search on the ANSWER space.

**Template:**
```
If we can do it with mid as the answer → try smaller (search left)
If we cannot do it with mid → need larger (search right)
```

### Example: Square Root (LeetCode #69)

```python
def my_sqrt(x: int) -> int:
    """
    LeetCode 69: Sqrt(x)
    
    Find integer square root of x (floor).
    
    Binary search on answer space: [0, x]
    
    Time: O(log x)  Space: O(1)
    """
    if x < 2:
        return x
    
    lo, hi = 1, x // 2
    
    while lo <= hi:
        mid = lo + (hi - lo) // 2
        
        if mid * mid == x:
            return mid
        elif mid * mid < x:
            lo = mid + 1    # Try larger
        else:
            hi = mid - 1    # Try smaller
    
    return hi  # hi is the floor of sqrt(x)


print(my_sqrt(4))   # 2
print(my_sqrt(8))   # 2 (floor of 2.828)
print(my_sqrt(16))  # 4
```

---

## 4.8 Pattern 8: Book Allocation Problem

**Problem:** N books, M students. Each student reads consecutive books. Minimize the maximum pages any student reads.

```python
def allocate_books(pages: list[int], m: int) -> int:
    """
    Allocate books to m students minimizing max pages.
    
    Binary search on answer:
    - Low = max(pages)   → each student gets at least the largest book
    - High = sum(pages)  → one student reads all
    - Check if mid pages is feasible with m students
    
    Time: O(n log(sum))  Space: O(1)
    """
    def is_feasible(pages, m, max_pages):
        """Can we allocate so no student reads more than max_pages?"""
        students = 1
        current = 0
        for p in pages:
            if p > max_pages:
                return False  # Single book exceeds limit
            if current + p > max_pages:
                students += 1  # New student
                current = p
            else:
                current += p
        return students <= m
    
    if not pages or m <= 0 or m > len(pages):
        return -1
    
    lo = max(pages)
    hi = sum(pages)
    result = hi
    
    while lo <= hi:
        mid = lo + (hi - lo) // 2
        
        if is_feasible(pages, m, mid):
            result = mid       # Valid! Try to minimize
            hi = mid - 1
        else:
            lo = mid + 1      # Not enough, increase
    
    return result


pages = [12, 34, 67, 90]
m = 2
print(allocate_books(pages, m))  # 113
```

---

## 4.9 Pattern 9: Aggressive Cows (Classic CP Problem)

**Problem:** Place C cows in N stalls such that minimum distance between any two cows is maximized.

```python
def aggressive_cows(stalls: list[int], c: int) -> int:
    """
    Place c cows in stalls maximizing minimum distance between cows.
    
    Binary search on minimum distance:
    - Low = 1 (minimum possible distance)
    - High = last_stall - first_stall
    - Check if distance d is achievable with c cows
    
    Time: O(n log n + n log(max_dist))
    """
    def can_place(stalls, c, min_dist):
        cows = 1
        last = stalls[0]
        for i in range(1, len(stalls)):
            if stalls[i] - last >= min_dist:
                cows += 1
                last = stalls[i]
                if cows == c:
                    return True
        return False
    
    stalls.sort()
    lo, hi = 1, stalls[-1] - stalls[0]
    result = 0
    
    while lo <= hi:
        mid = lo + (hi - lo) // 2
        
        if can_place(stalls, c, mid):
            result = mid     # Can do this distance, try larger
            lo = mid + 1
        else:
            hi = mid - 1    # Cannot, try smaller
    
    return result


stalls = [1, 2, 4, 8, 9]
c = 3
print(aggressive_cows(stalls, c))  # 3
```

---

## 4.10 Binary Search Pattern Summary

| Pattern | Key Idea | When to Use |
|---------|----------|-------------|
| Classic | Find exact value | Value in sorted array |
| First Occurrence | Find leftmost | Duplicates, first position |
| Last Occurrence | Find rightmost | Duplicates, last position |
| Insert Position | Find where it goes | Insertion queries |
| Peak Element | Find local max | Mountain-like arrays |
| Rotated Array | Identify sorted half | Rotated arrays |
| Binary Search on Answer | Search answer space | Optimization problems |
| Book Allocation | Minimize maximum | Partition problems |
| Aggressive Cows | Maximize minimum | Placement problems |

---

# 👆👆 SECTION 5 — TWO POINTER MASTERCLASS

## 5.1 What is Two Pointers?

Two Pointers is a technique that uses two indices (pointers) moving through a data structure—typically in opposite directions or at different speeds—to solve problems efficiently.

> **Real World Analogy:** Two people searching from both ends of a hallway. One starts from the left, one from the right. They move toward each other, and together they can search the whole hallway faster than one person starting from one end.

---

## 5.2 Why Two Pointers Works

```
Problem: Find two numbers that sum to target in sorted array.

Brute Force: Try every pair → O(n²)
Two Pointers: Use left/right pointers → O(n)

Why it works:
- If arr[left] + arr[right] < target → move left pointer right (need larger sum)
- If arr[left] + arr[right] > target → move right pointer left (need smaller sum)
- If equal → found the pair

Each pointer moves at most n steps → O(n) total
```

---

## 5.3 Two Pointer Types

```
TYPE 1: OPPOSITE DIRECTION
   [←  →]
   Start at ends, move toward center
   Use for: Pair sum, palindrome, container with water

TYPE 2: SAME DIRECTION (FAST & SLOW)
   [→  →→]
   Both start at beginning, different speeds
   Use for: Remove duplicates, cycle detection, linked lists

TYPE 3: SLIDING WINDOW (covered in Section 7)
   [→ window →]
   Fixed or variable size window moving forward
```

---

## 5.4 Template

```python
# Opposite Direction Template
def two_pointer_opposite(arr):
    left, right = 0, len(arr) - 1
    
    while left < right:
        # Process arr[left] and arr[right]
        
        if condition_to_move_left:
            left += 1
        elif condition_to_move_right:
            right -= 1
        else:
            # Found answer
            pass
    
    return result


# Same Direction (Fast & Slow) Template
def two_pointer_same(arr):
    slow = 0
    
    for fast in range(len(arr)):
        # Process arr[fast]
        
        if condition:
            arr[slow] = arr[fast]
            slow += 1
    
    return slow  # slow is new length
```

---

# 👆👆 SECTION 6 — TWO POINTER PATTERNS

## 6.1 Pattern 1: Two Sum (Sorted Array) (LeetCode #167)

```python
def two_sum_sorted(numbers: list[int], target: int) -> list[int]:
    """
    LeetCode 167: Two Sum II - Input Array Is Sorted
    
    Find two numbers summing to target. Return 1-indexed positions.
    
    Time: O(n)  Space: O(1)
    """
    left, right = 0, len(numbers) - 1
    
    while left < right:
        current_sum = numbers[left] + numbers[right]
        
        if current_sum == target:
            return [left + 1, right + 1]  # 1-indexed
        elif current_sum < target:
            left += 1   # Need larger sum
        else:
            right -= 1  # Need smaller sum
    
    return []  # No solution found


# Dry Run: numbers=[2,7,11,15], target=9
# left=0, right=3: 2+15=17 > 9 → right=2
# left=0, right=2: 2+11=13 > 9 → right=1  
# left=0, right=1: 2+7=9 == 9 → return [1,2] ✅

print(two_sum_sorted([2, 7, 11, 15], 9))   # [1, 2]
print(two_sum_sorted([2, 3, 4], 6))         # [1, 3]
```

---

## 6.2 Pattern 2: Remove Duplicates (LeetCode #26)

```python
def remove_duplicates(nums: list[int]) -> int:
    """
    LeetCode 26: Remove Duplicates from Sorted Array
    
    Remove duplicates in-place. Return new length.
    
    Strategy: slow pointer tracks unique elements.
              fast pointer scans the array.
    
    Time: O(n)  Space: O(1)
    """
    if not nums:
        return 0
    
    slow = 0  # Points to last unique element
    
    for fast in range(1, len(nums)):
        if nums[fast] != nums[slow]:
            slow += 1
            nums[slow] = nums[fast]  # Place next unique element
    
    return slow + 1  # Length of unique portion


# Dry Run: [1, 1, 2, 2, 3]
# slow=0, fast=1: nums[1]=1 == nums[0]=1 → skip
# slow=0, fast=2: nums[2]=2 != nums[0]=1 → slow=1, nums[1]=2
# slow=1, fast=3: nums[3]=2 == nums[1]=2 → skip
# slow=1, fast=4: nums[4]=3 != nums[1]=2 → slow=2, nums[2]=3
# Result: nums=[1,2,3,...], return 3 ✅

nums = [1, 1, 2, 2, 3]
length = remove_duplicates(nums)
print(nums[:length])  # [1, 2, 3]
print(length)         # 3
```

---

## 6.3 Pattern 3: Valid Palindrome (LeetCode #125)

```python
def is_palindrome(s: str) -> bool:
    """
    LeetCode 125: Valid Palindrome
    
    Check if string is palindrome (alphanumeric only, case-insensitive).
    
    Time: O(n)  Space: O(1)
    """
    left, right = 0, len(s) - 1
    
    while left < right:
        # Skip non-alphanumeric
        while left < right and not s[left].isalnum():
            left += 1
        while left < right and not s[right].isalnum():
            right -= 1
        
        # Compare
        if s[left].lower() != s[right].lower():
            return False
        
        left += 1
        right -= 1
    
    return True


print(is_palindrome("A man, a plan, a canal: Panama"))  # True
print(is_palindrome("race a car"))                       # False
print(is_palindrome(" "))                                # True
```

---

## 6.4 Pattern 4: Container With Most Water (LeetCode #11)

```python
def max_area(height: list[int]) -> int:
    """
    LeetCode 11: Container With Most Water
    
    Find two lines that form container holding most water.
    
    Key Insight: Area = min(h[left], h[right]) * (right - left)
    Move the SHORTER pointer (keep taller to maximize potential).
    
    Time: O(n)  Space: O(1)
    """
    left, right = 0, len(height) - 1
    max_water = 0
    
    while left < right:
        # Calculate area with current pointers
        width = right - left
        water = min(height[left], height[right]) * width
        max_water = max(max_water, water)
        
        # Move shorter pointer
        if height[left] < height[right]:
            left += 1
        else:
            right -= 1
    
    return max_water


# Dry Run: height=[1,8,6,2,5,4,8,3,7]
# left=0(h=1), right=8(h=7): area=1*8=8, move left
# left=1(h=8), right=8(h=7): area=7*7=49, move right
# left=1(h=8), right=7(h=3): area=3*6=18, move right
# ... continues ...

print(max_area([1, 8, 6, 2, 5, 4, 8, 3, 7]))  # 49
print(max_area([1, 1]))                          # 1
```

---

## 6.5 Pattern 5: Three Sum (LeetCode #15)

```python
def three_sum(nums: list[int]) -> list[list[int]]:
    """
    LeetCode 15: 3Sum
    
    Find all unique triplets that sum to zero.
    
    Strategy:
    1. Sort the array
    2. Fix one element, use two pointers for the other two
    3. Skip duplicates carefully
    
    Time: O(n²)  Space: O(1) (not counting output)
    """
    nums.sort()
    result = []
    n = len(nums)
    
    for i in range(n - 2):
        # Skip duplicates for the fixed element
        if i > 0 and nums[i] == nums[i - 1]:
            continue
        
        # Early termination: smallest three > 0
        if nums[i] > 0:
            break
        
        left, right = i + 1, n - 1
        
        while left < right:
            total = nums[i] + nums[left] + nums[right]
            
            if total == 0:
                result.append([nums[i], nums[left], nums[right]])
                # Skip duplicates
                while left < right and nums[left] == nums[left + 1]:
                    left += 1
                while left < right and nums[right] == nums[right - 1]:
                    right -= 1
                left += 1
                right -= 1
            elif total < 0:
                left += 1
            else:
                right -= 1
    
    return result


print(three_sum([-1, 0, 1, 2, -1, -4]))  # [[-1,-1,2],[-1,0,1]]
print(three_sum([0, 0, 0]))               # [[0,0,0]]
print(three_sum([1, 2, -2, -1]))          # []
```

---

## 6.6 Pattern 6: Move Zeroes (LeetCode #283)

```python
def move_zeroes(nums: list[int]) -> None:
    """
    LeetCode 283: Move Zeroes
    
    Move all zeroes to end while maintaining relative order.
    
    Strategy: slow tracks position for next non-zero element.
    
    Time: O(n)  Space: O(1)
    """
    slow = 0  # Position for next non-zero
    
    # Move all non-zeros to front
    for fast in range(len(nums)):
        if nums[fast] != 0:
            nums[slow] = nums[fast]
            slow += 1
    
    # Fill rest with zeros
    while slow < len(nums):
        nums[slow] = 0
        slow += 1


nums = [0, 1, 0, 3, 12]
move_zeroes(nums)
print(nums)  # [1, 3, 12, 0, 0]
```

---

## 6.7 Pattern 7: Fast & Slow Pointer (Cycle Detection)

```python
class ListNode:
    def __init__(self, val=0, next=None):
        self.val = val
        self.next = next


def has_cycle(head: ListNode) -> bool:
    """
    LeetCode 141: Linked List Cycle
    
    Floyd's Cycle Detection Algorithm (Tortoise and Hare).
    
    Slow moves 1 step, fast moves 2 steps.
    If cycle exists, they will eventually meet.
    
    Time: O(n)  Space: O(1)
    """
    slow = head
    fast = head
    
    while fast and fast.next:
        slow = slow.next       # Move 1 step
        fast = fast.next.next  # Move 2 steps
        
        if slow == fast:
            return True  # They met → cycle detected
    
    return False  # Fast reached end → no cycle


def find_cycle_start(head: ListNode) -> ListNode:
    """
    LeetCode 142: Linked List Cycle II
    
    Find where the cycle begins.
    
    After detection: reset one pointer to head.
    Move both one step at a time → they meet at cycle start.
    """
    slow = fast = head
    
    # Detect cycle
    while fast and fast.next:
        slow = slow.next
        fast = fast.next.next
        if slow == fast:
            break
    else:
        return None  # No cycle
    
    # Find start
    slow = head
    while slow != fast:
        slow = slow.next
        fast = fast.next
    
    return slow  # Cycle start
```

---

## 6.8 Two Pointer Summary Table

| Pattern | Pointer Direction | Key Operation | Time |
|---------|------------------|---------------|------|
| Pair Sum | Opposite | Compare sum vs target | O(n) |
| Remove Duplicates | Same direction | Track unique elements | O(n) |
| Palindrome | Opposite | Compare characters | O(n) |
| Container Water | Opposite | Maximize area | O(n) |
| Three Sum | Fixed + Opposite | Find zero sum | O(n²) |
| Move Zeroes | Same direction | Partition array | O(n) |
| Cycle Detection | Same (different speed) | Tortoise & Hare | O(n) |

---

# 🪟 SECTION 7 — SLIDING WINDOW MASTERCLASS

## 7.1 What is Sliding Window?

Sliding Window is a technique for processing a contiguous subset (window) of data. Instead of recomputing from scratch for each position, we "slide" the window by adding one element and removing one.

> **Real World Analogy:** Imagine looking through a train window. As the train moves, you see new scenery appear on the right and old scenery disappear on the left. Your "window" of view moves forward — this is exactly sliding window.

---

## 7.2 Fixed vs Variable Window

```
FIXED WINDOW (size = k):
[a, b, c | d, e, f | g, h, i]
 ↑       ↑
 left   right      Add right, remove left

VARIABLE WINDOW (size changes):
[a, b, c, d, e, f, g]
 ↑           ↑
 left        right     Expand right, shrink from left when invalid
```

---

## 7.3 Fixed Window Template

```python
def fixed_window(arr: list[int], k: int):
    """
    Fixed size sliding window template.
    Time: O(n)
    """
    n = len(arr)
    if n < k:
        return None
    
    # Build first window
    window_sum = sum(arr[:k])
    result = window_sum
    
    # Slide window
    for i in range(k, n):
        window_sum += arr[i]       # Add new element (right)
        window_sum -= arr[i - k]   # Remove old element (left)
        result = max(result, window_sum)  # Or whatever operation
    
    return result
```

---

## 7.4 Variable Window Template

```python
def variable_window(arr: list[int], target):
    """
    Variable size sliding window template.
    Time: O(n)
    """
    left = 0
    current_state = 0  # Track window state
    result = 0
    
    for right in range(len(arr)):
        # Expand window: add arr[right]
        current_state += arr[right]  # Or whatever operation
        
        # Shrink window when invalid
        while current_state > target:  # Or whatever condition
            current_state -= arr[left]
            left += 1
        
        # Update result at valid window
        result = max(result, right - left + 1)
    
    return result
```

---

# 🪟 SECTION 8 — ADVANCED SLIDING WINDOW PATTERNS

## 8.1 Pattern 1: Maximum Sum Subarray of Size K

```python
def max_sum_subarray_k(arr: list[int], k: int) -> int:
    """
    Find maximum sum subarray of exactly size k.
    
    Time: O(n)  Space: O(1)
    """
    n = len(arr)
    if n < k:
        return -1
    
    # First window
    window_sum = sum(arr[:k])
    max_sum = window_sum
    
    # Slide
    for i in range(k, n):
        window_sum += arr[i] - arr[i - k]
        max_sum = max(max_sum, window_sum)
    
    return max_sum


# Dry Run: arr=[2,1,5,1,3,2], k=3
# First window: 2+1+5=8
# i=3: 8+1-2=7
# i=4: 7+3-1=9  ← max
# i=5: 9+2-5=6
# Answer: 9 ✅

print(max_sum_subarray_k([2, 1, 5, 1, 3, 2], 3))  # 9
print(max_sum_subarray_k([2, 3, 4, 1, 5], 2))       # 7
```

---

## 8.2 Pattern 2: Longest Substring Without Repeating Characters (LeetCode #3)

```python
def length_of_longest_substring(s: str) -> int:
    """
    LeetCode 3: Longest Substring Without Repeating Characters
    
    Variable window: expand right, shrink from left when duplicate.
    
    Time: O(n)  Space: O(min(n, 26)) = O(1)
    """
    char_index = {}  # Last seen index of each character
    left = 0
    max_length = 0
    
    for right in range(len(s)):
        # If character seen in current window, shrink window
        if s[right] in char_index and char_index[s[right]] >= left:
            left = char_index[s[right]] + 1
        
        # Update last seen index
        char_index[s[right]] = right
        
        # Update max length
        max_length = max(max_length, right - left + 1)
    
    return max_length


# Dry Run: s="abcabcbb"
# r=0('a'): left=0, window="a", len=1
# r=1('b'): left=0, window="ab", len=2
# r=2('c'): left=0, window="abc", len=3 ← max
# r=3('a'): 'a' seen at 0 ≥ left(0), left=1, window="bca", len=3
# r=4('b'): 'b' seen at 1 ≥ left(1), left=2, window="cab", len=3
# ...

print(length_of_longest_substring("abcabcbb"))  # 3
print(length_of_longest_substring("bbbbb"))      # 1
print(length_of_longest_substring("pwwkew"))     # 3
```

---

## 8.3 Pattern 3: Minimum Window Substring (LeetCode #76)

```python
from collections import Counter

def min_window(s: str, t: str) -> str:
    """
    LeetCode 76: Minimum Window Substring
    
    Find smallest window in s containing all chars of t.
    
    Time: O(|s| + |t|)  Space: O(|s| + |t|)
    """
    if not t or not s:
        return ""
    
    need = Counter(t)          # Characters needed
    missing = len(t)           # Total characters still needed
    left = 0
    start, end = 0, 0
    min_len = float('inf')
    result = ""
    
    for right, char in enumerate(s):
        # Expand window
        if need[char] > 0:
            missing -= 1       # One required char satisfied
        need[char] -= 1
        
        # Window valid: contains all of t
        if missing == 0:
            # Shrink from left while still valid
            while need[s[left]] < 0:
                need[s[left]] += 1
                left += 1
            
            # Update result
            if right - left + 1 < min_len:
                min_len = right - left + 1
                result = s[left:right + 1]
            
            # Move left to try smaller window
            need[s[left]] += 1
            missing += 1
            left += 1
    
    return result


print(min_window("ADOBECODEBANC", "ABC"))  # "BANC"
print(min_window("a", "a"))                # "a"
print(min_window("a", "aa"))               # ""
```

---

## 8.4 Pattern 4: Find All Anagrams in String (LeetCode #438)

```python
def find_anagrams(s: str, p: str) -> list[int]:
    """
    LeetCode 438: Find All Anagrams in a String
    
    Find all start indices of p's anagrams in s.
    
    Fixed window of size len(p), compare frequency maps.
    
    Time: O(n)  Space: O(1) — at most 26 chars
    """
    result = []
    p_count = Counter(p)
    window = Counter(s[:len(p)])
    
    if window == p_count:
        result.append(0)
    
    for i in range(len(p), len(s)):
        # Add new character
        window[s[i]] += 1
        
        # Remove old character
        old = s[i - len(p)]
        window[old] -= 1
        if window[old] == 0:
            del window[old]
        
        # Check if anagram
        if window == p_count:
            result.append(i - len(p) + 1)
    
    return result


print(find_anagrams("cbaebabacd", "abc"))  # [0, 6]
print(find_anagrams("abab", "ab"))          # [0, 1, 2]
```

---

## 8.5 Pattern 5: Longest Substring with K Distinct Characters

```python
def longest_k_distinct(s: str, k: int) -> int:
    """
    Find length of longest substring with at most k distinct characters.
    
    Time: O(n)  Space: O(k)
    """
    if k == 0:
        return 0
    
    freq = {}
    left = 0
    max_len = 0
    
    for right in range(len(s)):
        # Add character to window
        freq[s[right]] = freq.get(s[right], 0) + 1
        
        # Shrink window if more than k distinct chars
        while len(freq) > k:
            freq[s[left]] -= 1
            if freq[s[left]] == 0:
                del freq[s[left]]
            left += 1
        
        max_len = max(max_len, right - left + 1)
    
    return max_len


print(longest_k_distinct("eceba", 2))  # 3 ("ece")
print(longest_k_distinct("aa", 1))     # 2
```

---

## 8.6 Pattern 6: Longest Repeating Character Replacement (LeetCode #424)

```python
def character_replacement(s: str, k: int) -> int:
    """
    LeetCode 424: Longest Repeating Character Replacement
    
    You can replace at most k characters to make all same.
    Find longest such substring.
    
    Key: window_size - max_freq <= k means we can make all same with k replacements
    
    Time: O(n)  Space: O(1)
    """
    count = {}
    left = 0
    max_freq = 0
    result = 0
    
    for right in range(len(s)):
        count[s[right]] = count.get(s[right], 0) + 1
        max_freq = max(max_freq, count[s[right]])
        
        # Window is invalid: need more than k replacements
        window_size = right - left + 1
        if window_size - max_freq > k:
            count[s[left]] -= 1
            left += 1
        
        result = max(result, right - left + 1)
    
    return result


print(character_replacement("ABAB", 2))   # 4
print(character_replacement("AABABBA", 1)) # 4
```

---

## 8.7 Sliding Window Summary

| Pattern | Window Type | Key Condition | Time |
|---------|-------------|---------------|------|
| Max Sum K | Fixed | None | O(n) |
| Longest No Repeat | Variable | No duplicates | O(n) |
| Min Window Substring | Variable | Contains all of t | O(n) |
| Find Anagrams | Fixed | Freq match | O(n) |
| K Distinct Chars | Variable | ≤ k distinct | O(n) |
| Char Replacement | Variable | replacements ≤ k | O(n) |

---

# 📊 SECTION 9 — SORTING MASTERCLASS

## 9.1 Why Sorting Matters

Sorting unlocks many other algorithms:
- Binary search requires sorted data
- Two pointers on sorted data
- Many greedy algorithms need sorted input
- Database query optimization

---

## 9.2 Bubble Sort

```python
def bubble_sort(arr: list[int]) -> list[int]:
    """
    Repeatedly swap adjacent elements if they're in wrong order.
    Largest elements "bubble up" to the end.
    
    Time: O(n²)  Space: O(1)  Stable: Yes
    """
    n = len(arr)
    arr = arr.copy()
    
    for i in range(n):
        swapped = False
        for j in range(0, n - i - 1):
            if arr[j] > arr[j + 1]:
                arr[j], arr[j + 1] = arr[j + 1], arr[j]
                swapped = True
        
        if not swapped:  # Optimization: already sorted
            break
    
    return arr


# Visualization:
# [64, 34, 25, 12, 22]
# Pass 1: [34, 25, 12, 22, 64]  (64 bubbles up)
# Pass 2: [25, 12, 22, 34, 64]  (34 bubbles up)
# Pass 3: [12, 22, 25, 34, 64]  (25 bubbles up)
# Pass 4: [12, 22, 25, 34, 64]  no swap → done

print(bubble_sort([64, 34, 25, 12, 22]))  # [12, 22, 25, 34, 64]
```

---

## 9.3 Selection Sort

```python
def selection_sort(arr: list[int]) -> list[int]:
    """
    Find minimum in unsorted portion, place at beginning.
    
    Time: O(n²)  Space: O(1)  Stable: No
    """
    n = len(arr)
    arr = arr.copy()
    
    for i in range(n):
        min_idx = i
        for j in range(i + 1, n):
            if arr[j] < arr[min_idx]:
                min_idx = j
        arr[i], arr[min_idx] = arr[min_idx], arr[i]
    
    return arr


print(selection_sort([64, 25, 12, 22, 11]))  # [11, 12, 22, 25, 64]
```

---

## 9.4 Insertion Sort

```python
def insertion_sort(arr: list[int]) -> list[int]:
    """
    Build sorted portion one element at a time.
    Like sorting playing cards in hand.
    
    Time: O(n²) worst, O(n) best (already sorted)
    Space: O(1)  Stable: Yes
    """
    arr = arr.copy()
    
    for i in range(1, len(arr)):
        key = arr[i]
        j = i - 1
        
        # Shift elements greater than key one position right
        while j >= 0 and arr[j] > key:
            arr[j + 1] = arr[j]
            j -= 1
        
        arr[j + 1] = key  # Place key in correct position
    
    return arr


# Visualization:
# [5, 2, 4, 6, 1]
# i=1: key=2, shift 5 → [2, 5, 4, 6, 1]
# i=2: key=4, shift 5 → [2, 4, 5, 6, 1]
# i=3: key=6, no shift → [2, 4, 5, 6, 1]
# i=4: key=1, shift all → [1, 2, 4, 5, 6]

print(insertion_sort([5, 2, 4, 6, 1]))  # [1, 2, 4, 5, 6]
```

---

## 9.5 Merge Sort

```python
def merge_sort(arr: list[int]) -> list[int]:
    """
    Divide and Conquer: split into halves, sort each, merge.
    
    Time: O(n log n)  Space: O(n)  Stable: Yes
    """
    if len(arr) <= 1:
        return arr
    
    mid = len(arr) // 2
    left = merge_sort(arr[:mid])
    right = merge_sort(arr[mid:])
    
    return merge(left, right)


def merge(left: list[int], right: list[int]) -> list[int]:
    result = []
    i = j = 0
    
    while i < len(left) and j < len(right):
        if left[i] <= right[j]:
            result.append(left[i])
            i += 1
        else:
            result.append(right[j])
            j += 1
    
    result.extend(left[i:])
    result.extend(right[j:])
    return result


# Visualization:
#           [38, 27, 43, 3, 9, 82, 10]
#          /                           \
#   [38, 27, 43]               [3, 9, 82, 10]
#    /        \                  /          \
# [38]     [27, 43]          [3, 9]      [82, 10]
#            / \              / \           / \
#          [27] [43]        [3] [9]      [82] [10]
# MERGE UP:
# [27,43]  →  [27,38,43]  →  [3,9]  →  [10,82]  →  [3,9,10,82]
# Final: [3, 9, 10, 27, 38, 43, 82]

print(merge_sort([38, 27, 43, 3, 9, 82, 10]))
# [3, 9, 10, 27, 38, 43, 82]
```

---

## 9.6 Quick Sort

```python
def quick_sort(arr: list[int], lo: int = 0, hi: int = None) -> list[int]:
    """
    Choose pivot, partition array, recurse on both sides.
    
    Time: O(n log n) avg, O(n²) worst  Space: O(log n)  Stable: No
    """
    if hi is None:
        arr = arr.copy()
        hi = len(arr) - 1
    
    if lo < hi:
        pivot_idx = partition(arr, lo, hi)
        quick_sort(arr, lo, pivot_idx - 1)
        quick_sort(arr, pivot_idx + 1, hi)
    
    return arr


def partition(arr: list[int], lo: int, hi: int) -> int:
    """
    Lomuto partition scheme.
    Pivot is last element.
    """
    pivot = arr[hi]
    i = lo - 1  # Index of smaller element
    
    for j in range(lo, hi):
        if arr[j] <= pivot:
            i += 1
            arr[i], arr[j] = arr[j], arr[i]
    
    arr[i + 1], arr[hi] = arr[hi], arr[i + 1]
    return i + 1


print(quick_sort([10, 7, 8, 9, 1, 5]))  # [1, 5, 7, 8, 9, 10]
```

---

## 9.7 Python's Built-in Sorting

```python
# Python uses Timsort (hybrid of Merge Sort + Insertion Sort)
# Time: O(n log n)  Space: O(n)  Stable: Yes

# sort() — in-place
arr = [3, 1, 4, 1, 5, 9, 2, 6]
arr.sort()              # ascending
arr.sort(reverse=True)  # descending

# sorted() — returns new list
new = sorted(arr)
new = sorted(arr, reverse=True)

# Custom key
students = [("Alice", 90), ("Bob", 75), ("Charlie", 85)]
students.sort(key=lambda x: x[1])           # Sort by grade
students.sort(key=lambda x: x[1], reverse=True)  # Descending

# Multi-key sort
data = [(1, 'b'), (2, 'a'), (1, 'a')]
data.sort(key=lambda x: (x[0], x[1]))  # Sort by first, then second

# Sort objects by attribute
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

people = [Person("Alice", 30), Person("Bob", 25)]
people.sort(key=lambda p: p.age)

# Using operator module (faster than lambda)
from operator import itemgetter, attrgetter
students.sort(key=itemgetter(1))
people.sort(key=attrgetter('age'))
```

---

## 9.8 Sorting Complexity Comparison

| Algorithm | Best | Average | Worst | Space | Stable |
|-----------|------|---------|-------|-------|--------|
| Bubble Sort | O(n) | O(n²) | O(n²) | O(1) | Yes |
| Selection Sort | O(n²) | O(n²) | O(n²) | O(1) | No |
| Insertion Sort | O(n) | O(n²) | O(n²) | O(1) | Yes |
| Merge Sort | O(n log n) | O(n log n) | O(n log n) | O(n) | Yes |
| Quick Sort | O(n log n) | O(n log n) | O(n²) | O(log n) | No |
| Heap Sort | O(n log n) | O(n log n) | O(n log n) | O(1) | No |
| Tim Sort | O(n) | O(n log n) | O(n log n) | O(n) | Yes |

**When to use which:**
- `n < 50` → Insertion Sort (fast in practice, simple)
- `n < 1000` → Any O(n log n) algorithm
- `n > 1000` → Always O(n log n) 
- Need stability → Merge Sort or Python's built-in
- Memory limited → Heap Sort
- Python code → Always use `list.sort()` or `sorted()`

---

## 9.9 Custom Sorting Problems

```python
# Sort by Absolute Value
arr = [-3, 1, -5, 2, -1]
arr.sort(key=abs)
print(arr)  # [1, -1, 2, -3, -5]

# Sort Strings by Length then Alphabetically
words = ["banana", "apple", "fig", "cherry", "date"]
words.sort(key=lambda w: (len(w), w))
print(words)  # ['fig', 'date', 'apple', 'banana', 'cherry']

# Sort Intervals by Start Time (common interview pattern)
intervals = [[3, 6], [1, 4], [2, 5], [8, 10]]
intervals.sort(key=lambda x: x[0])
print(intervals)  # [[1,4],[2,5],[3,6],[8,10]]

# Comparator-based sort (Python 3)
from functools import cmp_to_key

def compare(a, b):
    if a < b: return -1
    if a > b: return 1
    return 0

arr = [3, 1, 4, 1, 5]
arr.sort(key=cmp_to_key(compare))
```

---

# 🔄 SECTION 10 — RECURSION FOR DSA

## 10.1 Recursive Thinking Framework

```
EVERY recursive solution needs:
1. BASE CASE  → When do we stop?
2. RECURSIVE CASE → How do we reduce toward base case?
3. TRUST → Trust the recursive call will work
```

---

## 10.2 Classic Recursive Problems

```python
# FACTORIAL
def factorial(n: int) -> int:
    """
    n! = n * (n-1)!
    Base case: 0! = 1
    """
    if n <= 1:
        return 1
    return n * factorial(n - 1)


# FIBONACCI
def fibonacci(n: int) -> int:
    """
    F(n) = F(n-1) + F(n-2)
    Base cases: F(0)=0, F(1)=1
    Time: O(2^n) — terrible! Use memoization
    """
    if n <= 1:
        return n
    return fibonacci(n - 1) + fibonacci(n - 2)


# FIBONACCI WITH MEMOIZATION
def fibonacci_memo(n: int, memo: dict = {}) -> int:
    """
    Time: O(n)  Space: O(n)
    """
    if n in memo:
        return memo[n]
    if n <= 1:
        return n
    memo[n] = fibonacci_memo(n - 1, memo) + fibonacci_memo(n - 2, memo)
    return memo[n]


# POWER FUNCTION
def power(base: int, exp: int) -> int:
    """
    Fast exponentiation: O(log exp)
    """
    if exp == 0:
        return 1
    if exp % 2 == 0:
        half = power(base, exp // 2)
        return half * half
    return base * power(base, exp - 1)


# BINARY SEARCH RECURSIVELY
def binary_search_rec(arr, target, lo, hi):
    if lo > hi:
        return -1
    mid = lo + (hi - lo) // 2
    if arr[mid] == target:
        return mid
    elif arr[mid] < target:
        return binary_search_rec(arr, target, mid + 1, hi)
    else:
        return binary_search_rec(arr, target, lo, mid - 1)


print(factorial(5))          # 120
print(fibonacci_memo(10))    # 55
print(power(2, 10))          # 1024
```

---

## 10.3 Call Stack Visualization

```
factorial(4)
  └─ 4 * factorial(3)
           └─ 3 * factorial(2)
                    └─ 2 * factorial(1)
                              └─ returns 1
                    └─ 2 * 1 = 2
           └─ 3 * 2 = 6
  └─ 4 * 6 = 24

CALL STACK at deepest point:
┌─────────────────┐
│  factorial(1)   │ ← TOP (current)
├─────────────────┤
│  factorial(2)   │
├─────────────────┤
│  factorial(3)   │
├─────────────────┤
│  factorial(4)   │ ← BOTTOM (first call)
└─────────────────┘
```

---

# 🏆 SECTION 11 — LEETCODE MASTERY FRAMEWORK

## 11.1 How to Read a LeetCode Problem

```
STEP 1: Read Problem Statement
   → What are the inputs?
   → What is the expected output?
   → Read examples carefully

STEP 2: Study Examples
   → Trace through each example manually
   → Understand why each output is correct
   → Don't skip this step!

STEP 3: Read Constraints
   → These tell you expected time complexity
   → Constraints guide your algorithm choice

STEP 4: Think Before Coding
   → Spend 5-10 minutes planning
   → Write pseudocode on paper/comment
   → Think about edge cases

STEP 5: Code
   → Start with brute force if stuck
   → Refactor to optimal
   → Clean, readable code

STEP 6: Test
   → Test with provided examples
   → Test your own edge cases
   → Check empty input, single element
```

---

## 11.2 Constraint → Algorithm Mapping

```
n ≤ 10        → Any algorithm, even O(n!)
n ≤ 20        → O(2^n) acceptable (backtracking)
n ≤ 100       → O(n³) acceptable
n ≤ 1,000     → O(n²) acceptable
n ≤ 100,000   → O(n log n) required
n ≤ 1,000,000 → O(n) required
n ≤ 10^9      → O(log n) or O(1) required
```

---

## 11.3 Clean Code Template for LeetCode

```python
class Solution:
    def problemName(self, nums: list[int], target: int) -> int:
        """
        Brief description of approach.
        
        Time: O(n log n)
        Space: O(1)
        """
        # Edge cases
        if not nums:
            return -1
        
        # Main logic
        # ...
        
        return result
```

---

# 🗺️ SECTION 12 — LEETCODE ROADMAP (230 PROBLEMS)

## 12.1 Arrays — Easy (30 Problems)

| # | Problem | Pattern | Expected TC |
|---|---------|---------|-------------|
| 1 | Two Sum | Hashing | O(n) |
| 26 | Remove Duplicates from Sorted Array | Two Pointers | O(n) |
| 27 | Remove Element | Two Pointers | O(n) |
| 35 | Search Insert Position | Binary Search | O(log n) |
| 53 | Maximum Subarray | Kadane's | O(n) |
| 66 | Plus One | Array Math | O(n) |
| 88 | Merge Sorted Array | Two Pointers | O(m+n) |
| 118 | Pascal's Triangle | 2D Array | O(n²) |
| 119 | Pascal's Triangle II | Math | O(n) |
| 121 | Best Time to Buy & Sell Stock | Prefix Min | O(n) |
| 136 | Single Number | XOR | O(n) |
| 169 | Majority Element | Boyer-Moore | O(n) |
| 189 | Rotate Array | Reverse | O(n) |
| 217 | Contains Duplicate | Hashing | O(n) |
| 219 | Contains Duplicate II | Sliding Window | O(n) |
| 228 | Summary Ranges | Two Pointers | O(n) |
| 243 | Shortest Word Distance | Two Pointers | O(n) |
| 268 | Missing Number | Math/XOR | O(n) |
| 283 | Move Zeroes | Two Pointers | O(n) |
| 303 | Range Sum Query | Prefix Sum | O(1) |
| 349 | Intersection of Two Arrays | Hashing | O(n) |
| 350 | Intersection of Two Arrays II | Two Pointers | O(n log n) |
| 414 | Third Maximum Number | Sorting | O(n) |
| 485 | Max Consecutive Ones | Sliding Window | O(n) |
| 496 | Next Greater Element I | Stack | O(n) |
| 532 | K-diff Pairs in Array | Hashing | O(n) |
| 561 | Array Partition I | Sorting | O(n log n) |
| 566 | Reshape the Matrix | Array | O(m*n) |
| 581 | Shortest Unsorted Continuous Subarray | Sorting | O(n log n) |
| 605 | Can Place Flowers | Greedy | O(n) |

---

## 12.2 Binary Search — Easy to Medium (30 Problems)

| # | Problem | Difficulty | Pattern |
|---|---------|------------|---------|
| 35 | Search Insert Position | Easy | Classic BS |
| 69 | Sqrt(x) | Easy | BS on Answer |
| 74 | Search a 2D Matrix | Medium | BS on flattened |
| 153 | Find Minimum in Rotated Array | Medium | BS rotated |
| 162 | Find Peak Element | Medium | BS peak |
| 167 | Two Sum II - Input Sorted | Medium | Two Pointers |
| 278 | First Bad Version | Easy | BS first occurrence |
| 374 | Guess Number Higher or Lower | Easy | Classic BS |
| 441 | Arranging Coins | Easy | BS on Answer |
| 475 | Heaters | Medium | BS + sorting |
| 540 | Single Element in Sorted Array | Medium | BS trick |
| 704 | Binary Search | Easy | Classic BS |
| 744 | Find Smallest Letter Greater Than Target | Easy | BS |
| 852 | Peak Index in Mountain Array | Easy | BS peak |
| 875 | Koko Eating Bananas | Medium | BS on Answer |
| 1011 | Capacity To Ship Packages | Medium | BS on Answer |
| 1060 | Missing Element in Sorted Array | Medium | BS |
| 1064 | Fixed Point | Easy | BS |
| 1095 | Find in Mountain Array | Hard | Three phase BS |
| 1150 | Check If a Number Is Majority Element | Easy | BS occurrences |
| 1170 | Compare Strings | Medium | BS + frequency |
| 1201 | Ugly Number III | Hard | BS + LCM |
| 1231 | Divide Chocolate | Hard | BS on Answer |
| 1283 | Find the Smallest Divisor | Medium | BS on Answer |
| 1337 | K Weakest Rows | Easy | BS + sorting |
| 1351 | Count Negative Numbers | Easy | BS each row |
| 1385 | Find Distance Value | Easy | BS |
| 1482 | Minimum Number of Days to Make m Bouquets | Medium | BS on Answer |
| 1539 | Kth Missing Positive Number | Easy | BS |
| 1760 | Minimum Limit of Balls in a Bag | Medium | BS on Answer |

---

## 12.3 Two Pointers — Medium (25 Problems)

| # | Problem | Difficulty | Key Insight |
|---|---------|------------|-------------|
| 11 | Container With Most Water | Medium | Move shorter |
| 15 | 3Sum | Medium | Fix + 2P |
| 16 | 3Sum Closest | Medium | Fix + 2P |
| 18 | 4Sum | Medium | Fix two + 2P |
| 125 | Valid Palindrome | Easy | Skip non-alnum |
| 141 | Linked List Cycle | Easy | Fast & Slow |
| 142 | Linked List Cycle II | Medium | Floyd's algorithm |
| 167 | Two Sum II | Medium | Opposite pointers |
| 202 | Happy Number | Easy | Cycle detection |
| 234 | Palindrome Linked List | Easy | Fast & Slow + reverse |
| 287 | Find the Duplicate Number | Medium | Floyd's cycle |
| 344 | Reverse String | Easy | Swap at ends |
| 345 | Reverse Vowels of String | Easy | Skip consonants |
| 349 | Intersection of Two Arrays | Easy | Sort + 2P |
| 392 | Is Subsequence | Easy | Same direction |
| 443 | String Compression | Medium | Fast + Slow |
| 455 | Assign Cookies | Easy | Sort + 2P greedy |
| 524 | Longest Word in Dictionary | Medium | 2P matching |
| 557 | Reverse Words in String III | Easy | 2P each word |
| 680 | Valid Palindrome II | Easy | Skip one char |
| 763 | Partition Labels | Medium | Greedy + 2P |
| 844 | Backspace String Compare | Easy | Reverse iteration |
| 876 | Middle of Linked List | Easy | Fast & Slow |
| 977 | Squares of Sorted Array | Easy | Opposite + merge |
| 1099 | Two Sum Less Than K | Easy | Sort + 2P |

---

## 12.4 Sliding Window — Medium (25 Problems)

| # | Problem | Difficulty | Window Type |
|---|---------|------------|-------------|
| 3 | Longest Substring Without Repeating | Medium | Variable |
| 30 | Substring with Concatenation of All Words | Hard | Fixed |
| 76 | Minimum Window Substring | Hard | Variable |
| 187 | Repeated DNA Sequences | Medium | Fixed |
| 209 | Minimum Size Subarray Sum | Medium | Variable |
| 219 | Contains Duplicate II | Easy | Fixed |
| 239 | Sliding Window Maximum | Hard | Deque |
| 340 | Longest Substring with At Most K Distinct | Medium | Variable |
| 395 | Longest Substring with At Least K Repeating | Medium | Divide |
| 424 | Longest Repeating Character Replacement | Medium | Variable |
| 438 | Find All Anagrams in a String | Medium | Fixed |
| 480 | Sliding Window Median | Hard | Two heaps |
| 485 | Max Consecutive Ones | Easy | Variable |
| 487 | Max Consecutive Ones II | Medium | Variable |
| 567 | Permutation in String | Medium | Fixed freq |
| 632 | Smallest Range Covering Elements | Hard | Variable |
| 643 | Maximum Average Subarray I | Easy | Fixed |
| 713 | Subarray Product Less Than K | Medium | Variable |
| 718 | Maximum Length of Repeated Subarray | Medium | Fixed |
| 727 | Minimum Window Subsequence | Hard | Variable |
| 904 | Fruit Into Baskets | Medium | 2 distinct |
| 930 | Binary Subarrays With Sum | Medium | Variable |
| 992 | Subarrays with K Different Integers | Hard | Exactly K |
| 1004 | Max Consecutive Ones III | Medium | Variable |
| 1208 | Get Equal Substrings Within Budget | Medium | Variable |

---

## 12.5 Hard Problems (30 Problems)

| # | Problem | Topic | Key Technique |
|---|---------|-------|---------------|
| 4 | Median of Two Sorted Arrays | BS | Binary search on partition |
| 23 | Merge K Sorted Lists | Heap | Min heap |
| 25 | Reverse Nodes in k-Group | Linked List | Recursion |
| 30 | Substring with Concatenation | SW | Sliding window |
| 42 | Trapping Rain Water | Stack/2P | Two pointers |
| 51 | N-Queens | Backtracking | Recursion |
| 52 | N-Queens II | Backtracking | Count solutions |
| 76 | Minimum Window Substring | SW | Sliding window |
| 84 | Largest Rectangle in Histogram | Stack | Monotonic stack |
| 85 | Maximal Rectangle | Stack | Row-by-row |
| 124 | Binary Tree Maximum Path Sum | Tree | DFS |
| 128 | Longest Consecutive Sequence | Set | O(n) |
| 135 | Candy | Greedy | Two pass |
| 145 | Binary Tree Postorder | Tree | Iterative |
| 174 | Dungeon Game | DP | Reverse DP |
| 188 | Best Time to Buy Sell Stock IV | DP | State machine |
| 212 | Word Search II | Trie+DFS | Trie |
| 239 | Sliding Window Maximum | Deque | Monotonic deque |
| 269 | Alien Dictionary | Graph | Topological sort |
| 297 | Serialize/Deserialize Binary Tree | Tree | BFS/DFS |
| 315 | Count of Smaller Numbers | MergeSort | Divide conquer |
| 327 | Count of Range Sum | MergeSort | Prefix + sort |
| 354 | Russian Doll Envelopes | BS+DP | LIS variant |
| 410 | Split Array Largest Sum | BS | BS on answer |
| 460 | LFU Cache | Design | Two hash maps |
| 480 | Sliding Window Median | Heap | Two heaps |
| 632 | Smallest Range | PQ | Min heap |
| 715 | Range Module | Interval | Sorted list |
| 778 | Swim in Rising Water | BS+BFS | Binary search |
| 850 | Rectangle Area II | Sweep | Coordinate compress |

---

# 🎯 SECTION 13 — LEETCODE INTERVIEW SYSTEM

## 13.1 FAANG Interview Structure

```
TYPICAL TECHNICAL INTERVIEW (45-60 min):

00:00-05:00  Introductions & Rapport
05:00-35:00  Coding Problems (1-2 problems)
35:00-45:00  System Design (senior roles)
45:00-60:00  Questions for interviewer

CODING PROBLEM BREAKDOWN (30 min):
00:00-05:00  Read problem, clarify
05:00-10:00  Plan approach, discuss
10:00-25:00  Code solution
25:00-30:00  Test, debug, optimize
```

---

## 13.2 Communication Framework

```python
# THINK ALOUD TEMPLATE

"""
CLARIFICATION PHASE:
"Let me make sure I understand — [restate problem].
 A few questions:
 - Can the array be empty?
 - Can there be negative numbers?
 - Is there always exactly one answer?"

APPROACH PHASE:
"My first thought is [brute force]. This would be O(n²).
 But I notice [key observation], which suggests [optimal approach].
 This would be O(n log n). Does this approach make sense to you?"

CODING PHASE:
"I'll start by [edge case handling].
 Then [main logic].
 Here I'm using [data structure] because [reason]."

TESTING PHASE:
"Let me trace through the first example...
 And let me think about edge cases: empty array, single element..."

COMPLEXITY PHASE:
"Time complexity is O(n log n) because [reason].
 Space complexity is O(1) because [reason]."
"""
```

---

## 13.3 Common Mistakes in Interviews

```
1. JUMPING TO CODE TOO FAST
   → Always spend 3-5 min understanding problem

2. WRITING WRONG CODE CONFIDENTLY
   → Ask clarifying questions

3. SILENT CODING
   → Think aloud, explain your thought process

4. NOT HANDLING EDGE CASES
   → Always ask about empty input, negatives, overflow

5. OPTIMIZING TOO EARLY
   → Brute force first, then optimize

6. GIVING UP
   → "I'm not sure about the optimal, let me think..."
   → Interviewers help when asked

7. NOT TESTING
   → Always trace through your code with examples

8. BAD VARIABLE NAMES
   → i, j, k OK for loops; use descriptive names elsewhere
```

---

# 🏅 SECTION 14 — COMPETITIVE PROGRAMMING MASTERCLASS

## 14.1 Platform Overview

| Platform | Best For | Rating System | Specialty |
|----------|----------|---------------|-----------|
| Codeforces | Contest practice | Elo-based | Speed + accuracy |
| LeetCode | Job interviews | Monthly contests | Industry prep |
| AtCoder | Algorithm depth | ABC/ARC/AGC | Clean problems |
| CodeChef | Beginners to experts | Star system | Monthly long |
| HackerRank | Certifications | Score-based | HR screening |
| SPOJ | Classic problems | Submissions | Classic archive |

---

## 14.2 Codeforces Roadmap

```
RATING BRACKETS:
< 1200   → Newbie       → Solve Div3 A, B problems
1200-1400 → Pupil       → Solve Div3 A-C, Div2 A-B
1400-1600 → Specialist  → Solve Div2 A-D
1600-1900 → Expert      → Solve Div2 A-E
1900-2100 → Candidate Master → Div1 A-C
2100-2400 → Master      → Div1 A-D
2400+    → Grandmaster  → All

HOW TO IMPROVE:
1. Solve 5-10 problems at your level daily
2. Participate in contests (Div2 for beginners)
3. Upsolve: after contest, solve problems you couldn't
4. Virtual contests: simulate contest conditions
5. Editorial reading: read solutions after trying yourself
```

---

## 14.3 Contest Strategy

```
DURING A CONTEST:
1. Read ALL problems first (5-10 min)
2. Identify which problems you can solve
3. Solve easiest ones first (guaranteed points)
4. For hard problems: write brute force first
5. Don't get stuck on one problem > 30 min
6. Test before submitting (wrong answer = time penalty in CF)

AFTER CONTEST:
1. Upsolve problems you couldn't solve
2. Read editorials for all problems
3. Understand approaches you didn't know
4. Add learned patterns to your notebook
```

---

## 14.4 Competitive Programming Template

```python
import sys
from collections import defaultdict, Counter, deque
from itertools import permutations, combinations
from functools import lru_cache
from heapq import heappush, heappop
import bisect
import math

input = sys.stdin.readline  # Faster input

def solve():
    # Read input
    n = int(input())
    arr = list(map(int, input().split()))
    
    # Your solution here
    
    print(result)

# Multiple test cases
t = int(input())
for _ in range(t):
    solve()
```

---

# 📊 SECTION 15 — KAGGLE MASTERCLASS

## 15.1 What is Kaggle?

Kaggle is the world's largest data science and machine learning community platform. It offers:

- **Competitions:** Real-world ML problems with prize money
- **Datasets:** 50,000+ public datasets
- **Notebooks:** Free GPU/TPU compute (30h/week GPU)
- **Courses:** Free ML courses
- **Community:** Forums, discussions, collaboration

---

## 15.2 Why Kaggle Matters for Engineers

| Role | Kaggle Benefit |
|------|----------------|
| ML Engineer | Prove model building skills |
| AI Engineer | Showcase deep learning work |
| Data Scientist | Portfolio of real projects |
| Research Engineer | Reproducible experiments |
| Software Engineer | Demonstrate Python/data skills |

---

## 15.3 Kaggle Rank System

```
NOTEBOOKS:
  Bronze   → 1 medal
  Silver   → 5 medals (incl. 1 silver/gold)
  Gold     → 15 medals (incl. 1 gold)
  
COMPETITIONS:
  Expert   → 2 bronze medals
  Master   → 1 gold + 3 silver/gold
  Grandmaster → 5 gold medals
  
DATASETS:
  Expert   → 3 bronze medals
  
DISCUSSIONS:
  Expert   → 50 upvotes
```

---

## 15.4 Kaggle for Beginners Roadmap

```
MONTH 1: Setup & Exploration
  Week 1: Create profile, explore datasets
  Week 2: Complete Titanic tutorial
  Week 3: Submit first competition
  Week 4: First public notebook

MONTH 2: Skill Building
  Week 1: Pandas & EDA deeply
  Week 2: Feature engineering
  Week 3: Multiple ML models
  Week 4: Ensemble methods

MONTH 3: Competition Strategy
  Week 1: Pick active competition
  Week 2: Data exploration + baseline
  Week 3: Improve model
  Week 4: Team up or final submission
```

---

# 👤 SECTION 16 — KAGGLE PROFILE SETUP

## 16.1 Professional Profile Checklist

```
PROFILE ESSENTIALS:
✅ Professional username (firstname-lastname or handle)
✅ Professional photo
✅ Compelling bio (skills + goals)
✅ Location
✅ GitHub link
✅ LinkedIn link
✅ Website/Portfolio link

BIO TEMPLATE:
"Machine Learning Engineer | Python Developer | DSA Enthusiast
Passionate about building data-driven solutions.
Currently learning: [topic]. Working on: [project].
Top skills: Python, Pandas, Sklearn, TensorFlow"

```

---

## 16.2 Notebook Strategy for Medal Earning

```
BRONZE MEDAL NOTEBOOKS:
- Complete EDA of a popular dataset
- Tutorial-quality beginner guide
- Visualization showcase
- Data cleaning walkthrough

SILVER MEDAL NOTEBOOKS:
- Novel approach to competition
- Comprehensive guide (referenced widely)
- Domain-specific analysis

GOLD MEDAL NOTEBOOKS:
- Competition winning solution writeup
- State-of-the-art technique implementation
- Widely cited reference notebook

HOW TO GET UPVOTES:
1. Post during first week of dataset release
2. Create visually appealing notebooks
3. Explain concepts clearly for beginners
4. Engage with comments
5. Update notebook when upvoted
```

---

# 📁 SECTION 17 — KAGGLE PROJECTS

## Project 1: Titanic Survival Analysis

```python
"""
TITANIC SURVIVAL ANALYSIS
Objective: Predict survival on the Titanic
Dataset: titanic.csv (Kaggle classic)
Skills: EDA, Feature Engineering, Classification
Resume Value: ⭐⭐⭐⭐⭐ (Industry standard beginner project)
"""

import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
from sklearn.model_selection import train_test_split, cross_val_score
from sklearn.ensemble import RandomForestClassifier
from sklearn.preprocessing import LabelEncoder
from sklearn.metrics import accuracy_score, classification_report

# Load data
train = pd.read_csv('train.csv')
test = pd.read_csv('test.csv')

# === EXPLORATORY DATA ANALYSIS ===
print("Shape:", train.shape)
print("\nMissing Values:")
print(train.isnull().sum())
print("\nSurvival Rate:", train['Survived'].mean())

# Visualizations
fig, axes = plt.subplots(2, 3, figsize=(15, 10))

# Survival by class
train.groupby('Pclass')['Survived'].mean().plot(kind='bar', ax=axes[0,0])
axes[0,0].set_title('Survival Rate by Class')

# Survival by sex
train.groupby('Sex')['Survived'].mean().plot(kind='bar', ax=axes[0,1])
axes[0,1].set_title('Survival Rate by Sex')

# Age distribution
train['Age'].hist(bins=30, ax=axes[0,2])
axes[0,2].set_title('Age Distribution')

# Survival by embarked
train.groupby('Embarked')['Survived'].mean().plot(kind='bar', ax=axes[1,0])
axes[1,0].set_title('Survival Rate by Embarkation')

# Fare distribution
train['Fare'].hist(bins=50, ax=axes[1,1])
axes[1,1].set_title('Fare Distribution')

plt.tight_layout()
plt.savefig('eda.png')

# === FEATURE ENGINEERING ===
def preprocess(df):
    # Fill missing values
    df['Age'].fillna(df['Age'].median(), inplace=True)
    df['Embarked'].fillna(df['Embarked'].mode()[0], inplace=True)
    df['Fare'].fillna(df['Fare'].median(), inplace=True)
    
    # Create new features
    df['FamilySize'] = df['SibSp'] + df['Parch'] + 1
    df['IsAlone'] = (df['FamilySize'] == 1).astype(int)
    df['Title'] = df['Name'].str.extract(' ([A-Za-z]+)\.', expand=False)
    df['Title'] = df['Title'].replace(
        ['Lady','Countess','Capt','Col','Don','Dr','Major','Rev','Sir','Jonkheer','Dona'], 'Rare'
    )
    df['Title'] = df['Title'].replace('Mlle', 'Miss')
    df['Title'] = df['Title'].replace('Ms', 'Miss')
    df['Title'] = df['Title'].replace('Mme', 'Mrs')
    
    # Encode categoricals
    le = LabelEncoder()
    df['Sex'] = le.fit_transform(df['Sex'])
    df['Embarked'] = le.fit_transform(df['Embarked'])
    df['Title'] = le.fit_transform(df['Title'])
    
    return df

train = preprocess(train)
test = preprocess(test)

# Select features
features = ['Pclass', 'Sex', 'Age', 'SibSp', 'Parch', 'Fare', 
            'Embarked', 'FamilySize', 'IsAlone', 'Title']

X = train[features]
y = train['Survived']
X_test = test[features]

# === MODEL TRAINING ===
X_train, X_val, y_train, y_val = train_test_split(X, y, test_size=0.2, random_state=42)

model = RandomForestClassifier(n_estimators=100, random_state=42, n_jobs=-1)
model.fit(X_train, y_train)

# Evaluate
y_pred = model.predict(X_val)
print(f"\nValidation Accuracy: {accuracy_score(y_val, y_pred):.4f}")
print("\nClassification Report:")
print(classification_report(y_val, y_pred))

# Cross-validation
cv_scores = cross_val_score(model, X, y, cv=5, scoring='accuracy')
print(f"\nCV Score: {cv_scores.mean():.4f} ± {cv_scores.std():.4f}")

# Feature importance
importance = pd.DataFrame({
    'Feature': features,
    'Importance': model.feature_importances_
}).sort_values('Importance', ascending=False)
print("\nFeature Importance:")
print(importance)

# Submission
predictions = model.predict(X_test)
submission = pd.DataFrame({
    'PassengerId': test['PassengerId'],
    'Survived': predictions
})
submission.to_csv('submission.csv', index=False)
print("\nSubmission saved!")

"""
FOLDER STRUCTURE:
titanic-analysis/
├── data/
│   ├── train.csv
│   └── test.csv
├── notebooks/
│   └── titanic_eda.ipynb
├── src/
│   ├── preprocess.py
│   ├── train.py
│   └── predict.py
├── outputs/
│   ├── eda.png
│   └── submission.csv
└── README.md
"""
```

---

## Project 2: Student Performance Analysis

```python
"""
STUDENT PERFORMANCE ANALYSIS
Objective: Analyze factors affecting student grades
Dataset: student-performance.csv
Skills: Statistical Analysis, Visualization, Regression
Resume Value: ⭐⭐⭐⭐
"""

import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
from scipy import stats
from sklearn.linear_model import LinearRegression
from sklearn.preprocessing import StandardScaler
from sklearn.metrics import r2_score, mean_squared_error

# Generate sample data (or use Kaggle dataset)
np.random.seed(42)
n = 1000

df = pd.DataFrame({
    'study_hours': np.random.normal(5, 2, n).clip(0, 14),
    'sleep_hours': np.random.normal(7, 1.5, n).clip(3, 12),
    'attendance_pct': np.random.normal(80, 15, n).clip(0, 100),
    'parent_education': np.random.choice(['none', 'high_school', 'college', 'graduate'], n),
    'internet_access': np.random.choice([0, 1], n, p=[0.3, 0.7]),
    'extracurricular': np.random.choice([0, 1], n, p=[0.5, 0.5]),
    'gender': np.random.choice(['M', 'F'], n),
})

# Target: exam score
df['exam_score'] = (
    df['study_hours'] * 4 +
    df['sleep_hours'] * 2 +
    df['attendance_pct'] * 0.3 +
    df['internet_access'] * 5 +
    np.random.normal(0, 5, n)
).clip(0, 100)

print("Dataset Overview:")
print(df.describe())

# === ANALYSIS ===
print("\nCorrelation with Exam Score:")
numeric_cols = ['study_hours', 'sleep_hours', 'attendance_pct', 'internet_access']
for col in numeric_cols:
    corr, pval = stats.pearsonr(df[col], df['exam_score'])
    print(f"  {col}: r={corr:.3f}, p={pval:.4f}")

# Visualizations
fig, axes = plt.subplots(2, 2, figsize=(14, 10))

# Study hours vs score
axes[0,0].scatter(df['study_hours'], df['exam_score'], alpha=0.3)
axes[0,0].set_xlabel('Study Hours/Day')
axes[0,0].set_ylabel('Exam Score')
axes[0,0].set_title('Study Hours vs Exam Score')

# Score by gender
df.groupby('gender')['exam_score'].plot(kind='kde', ax=axes[0,1])
axes[0,1].set_title('Score Distribution by Gender')
axes[0,1].legend()

# Attendance vs score
axes[1,0].scatter(df['attendance_pct'], df['exam_score'], alpha=0.3)
axes[1,0].set_title('Attendance vs Exam Score')

# Score by parent education
df.groupby('parent_education')['exam_score'].mean().plot(kind='bar', ax=axes[1,1])
axes[1,1].set_title('Avg Score by Parent Education')
axes[1,1].tick_params(axis='x', rotation=45)

plt.tight_layout()
plt.savefig('student_analysis.png')

print("\nAnalysis saved!")
```

---

# 🛠️ SECTION 18 — MINI PROJECTS

## Project 1: Binary Search Visualizer

```python
"""
Binary Search Visualizer
Shows step-by-step binary search process
"""

def binary_search_visualizer(arr: list[int], target: int):
    """
    Visualize binary search with ASCII art.
    """
    print(f"\n{'='*60}")
    print(f"Binary Search Visualizer")
    print(f"Array: {arr}")
    print(f"Target: {target}")
    print(f"{'='*60}\n")
    
    lo, hi = 0, len(arr) - 1
    step = 0
    
    while lo <= hi:
        step += 1
        mid = lo + (hi - lo) // 2
        
        # Visualization
        print(f"Step {step}: lo={lo}, hi={hi}, mid={mid}")
        
        # Draw array
        line1 = ""
        line2 = ""
        for i, val in enumerate(arr):
            cell = f" {val:3} "
            line1 += cell
            if i == lo:
                line2 += "  L  "
            elif i == mid:
                line2 += "  M  "
            elif i == hi:
                line2 += "  H  "
            else:
                line2 += "     "
        
        print(line1)
        print(line2)
        
        if arr[mid] == target:
            print(f"\n✅ FOUND! Target {target} at index {mid}\n")
            return mid
        elif arr[mid] < target:
            print(f"  arr[{mid}]={arr[mid]} < {target} → search RIGHT half\n")
            lo = mid + 1
        else:
            print(f"  arr[{mid}]={arr[mid]} > {target} → search LEFT half\n")
            hi = mid - 1
    
    print(f"\n❌ Target {target} NOT FOUND\n")
    return -1


# Demo
arr = [2, 5, 8, 12, 16, 23, 38, 56, 72, 91]
binary_search_visualizer(arr, 23)
binary_search_visualizer(arr, 50)
```

---

## Project 2: LeetCode Progress Tracker

```python
"""
LeetCode Progress Tracker
Track your LeetCode solving progress
"""

import json
import os
from datetime import datetime, date
from collections import defaultdict

class LeetCodeTracker:
    """
    Personal LeetCode progress tracking system.
    """
    
    def __init__(self, filepath: str = "leetcode_progress.json"):
        self.filepath = filepath
        self.data = self._load()
    
    def _load(self) -> dict:
        if os.path.exists(self.filepath):
            with open(self.filepath) as f:
                return json.load(f)
        return {
            "problems": {},
            "sessions": [],
            "streak": 0,
            "last_date": None
        }
    
    def _save(self):
        with open(self.filepath, 'w') as f:
            json.dump(self.data, f, indent=2)
    
    def add_problem(self, number: int, title: str, difficulty: str,
                    pattern: str, time_minutes: int, notes: str = ""):
        """Add a solved problem."""
        problem_id = str(number)
        today = str(date.today())
        
        self.data["problems"][problem_id] = {
            "number": number,
            "title": title,
            "difficulty": difficulty,
            "pattern": pattern,
            "time_minutes": time_minutes,
            "notes": notes,
            "solved_date": today,
            "review_count": 0,
            "last_review": today
        }
        
        # Update streak
        if self.data["last_date"] != today:
            if self.data["last_date"] == str(date.today() - 
                                              __import__('datetime').timedelta(1)):
                self.data["streak"] += 1
            else:
                self.data["streak"] = 1
            self.data["last_date"] = today
        
        self._save()
        print(f"✅ Added: #{number} {title}")
    
    def get_stats(self) -> dict:
        """Get solving statistics."""
        problems = self.data["problems"]
        
        stats = {
            "total": len(problems),
            "easy": sum(1 for p in problems.values() if p["difficulty"] == "Easy"),
            "medium": sum(1 for p in problems.values() if p["difficulty"] == "Medium"),
            "hard": sum(1 for p in problems.values() if p["difficulty"] == "Hard"),
            "streak": self.data["streak"],
            "patterns": defaultdict(int)
        }
        
        for p in problems.values():
            stats["patterns"][p["pattern"]] += 1
        
        return stats
    
    def print_dashboard(self):
        """Print progress dashboard."""
        stats = self.get_stats()
        
        print("\n" + "="*50)
        print("📊 LEETCODE PROGRESS DASHBOARD")
        print("="*50)
        print(f"🔥 Current Streak: {stats['streak']} days")
        print(f"\n📈 Problems Solved:")
        print(f"   Total: {stats['total']}")
        print(f"   Easy:   {stats['easy']} 🟢")
        print(f"   Medium: {stats['medium']} 🟡")
        print(f"   Hard:   {stats['hard']} 🔴")
        print(f"\n🏷️  Patterns Mastered:")
        for pattern, count in sorted(stats["patterns"].items(), 
                                     key=lambda x: -x[1]):
            bar = "█" * min(count, 20)
            print(f"   {pattern:<20} {bar} ({count})")
        print("="*50)
    
    def get_review_list(self) -> list:
        """Get problems due for review (spaced repetition)."""
        today = date.today()
        review_days = {0: 1, 1: 3, 2: 7, 3: 14, 4: 30}
        due = []
        
        for pid, p in self.data["problems"].items():
            last = date.fromisoformat(p["last_review"])
            count = p["review_count"]
            days_needed = review_days.get(count, 60)
            
            if (today - last).days >= days_needed:
                due.append(p)
        
        return sorted(due, key=lambda x: x["number"])


# Usage
tracker = LeetCodeTracker()
tracker.add_problem(704, "Binary Search", "Easy", "Binary Search", 15)
tracker.add_problem(3, "Longest Substring Without Repeating", "Medium", "Sliding Window", 25)
tracker.add_problem(15, "3Sum", "Medium", "Two Pointers", 35)
tracker.print_dashboard()
```

---

## Project 3: Algorithm Benchmark Tool

```python
"""
Algorithm Benchmark Tool
Compare different algorithm implementations
"""

import time
import random
import sys
from typing import Callable

class Benchmark:
    """
    Benchmark multiple algorithm implementations.
    """
    
    def __init__(self, name: str):
        self.name = name
        self.results = {}
    
    def measure(self, func: Callable, *args, runs: int = 5) -> dict:
        """Measure execution time of a function."""
        times = []
        for _ in range(runs):
            start = time.perf_counter()
            result = func(*args)
            end = time.perf_counter()
            times.append(end - start)
        
        return {
            "min": min(times),
            "max": max(times),
            "avg": sum(times) / len(times),
            "result": result
        }
    
    def compare(self, algorithms: dict, *args):
        """Compare multiple algorithms on same input."""
        print(f"\n{'='*60}")
        print(f"BENCHMARK: {self.name}")
        print(f"Input size: {len(args[0]) if args else 'N/A'}")
        print(f"{'='*60}")
        
        results = {}
        for name, func in algorithms.items():
            stats = self.measure(func, *args)
            results[name] = stats
            print(f"\n{name}:")
            print(f"  Average: {stats['avg']*1000:.3f} ms")
            print(f"  Min:     {stats['min']*1000:.3f} ms")
            print(f"  Max:     {stats['max']*1000:.3f} ms")
        
        # Find winner
        winner = min(results, key=lambda k: results[k]['avg'])
        print(f"\n🏆 Winner: {winner}")
        
        return results


# Benchmark searching algorithms
def linear_search(arr, target):
    for i, x in enumerate(arr):
        if x == target:
            return i
    return -1

def binary_search(arr, target):
    lo, hi = 0, len(arr) - 1
    while lo <= hi:
        mid = (lo + hi) // 2
        if arr[mid] == target:
            return mid
        elif arr[mid] < target:
            lo = mid + 1
        else:
            hi = mid - 1
    return -1

# Run benchmark
n = 100000
arr = sorted(random.randint(0, 1000000) for _ in range(n))
target = arr[n // 2]

bench = Benchmark("Search Algorithms")
bench.compare({
    "Linear Search": linear_search,
    "Binary Search": binary_search,
    "Python bisect": lambda a, t: __import__('bisect').bisect_left(a, t)
}, arr, target)
```

---

# 💼 SECTION 19 — 20 HIGH VALUE PYTHON DEVELOPER PORTFOLIO PROJECTS

## Project 1: LeetCode Analytics Dashboard

```
PROBLEM STATEMENT:
  Developers need to track their LeetCode progress systematically,
  analyze their strengths/weaknesses, and get personalized study plans.

ARCHITECTURE:
  Data Layer    → JSON/SQLite storage
  Logic Layer   → Analytics engine, pattern detector
  UI Layer      → Rich CLI dashboard / Web dashboard

FOLDER LAYOUT:
leetcode-analytics-dashboard/
├── src/
│   ├── core/
│   │   ├── __init__.py
│   │   ├── models.py          # Problem, Session, Stats models
│   │   ├── storage.py         # Data persistence
│   │   └── analytics.py       # Stats computation
│   ├── importers/
│   │   ├── csv_importer.py    # Import from CSV
│   │   ├── leetcode_api.py    # (if API available)
│   │   └── manual_entry.py    # Manual problem entry
│   ├── analyzers/
│   │   ├── pattern_analyzer.py  # Pattern strength analysis
│   │   ├── time_analyzer.py     # Time tracking analysis
│   │   └── streak_analyzer.py   # Consistency analysis
│   ├── visualizers/
│   │   ├── charts.py           # matplotlib/rich charts
│   │   ├── heatmap.py          # GitHub-style heatmap
│   │   └── progress_bar.py     # Progress indicators
│   ├── reporters/
│   │   ├── weekly_report.py    # Weekly summary
│   │   ├── export_pdf.py       # PDF export
│   │   └── export_csv.py       # Data export
│   └── cli/
│       ├── main.py             # Entry point
│       └── commands.py         # CLI commands
├── data/
│   ├── problems.json
│   └── sessions.json
├── tests/
│   ├── test_analytics.py
│   └── test_storage.py
├── docs/
│   └── README.md
├── requirements.txt
└── setup.py

SKILLS DEMONSTRATED:
  ✅ Python OOP
  ✅ Data analysis
  ✅ CLI development
  ✅ JSON/SQLite
  ✅ Visualization

RESUME VALUE: ⭐⭐⭐⭐⭐
RECRUITER APPEAL: Shows discipline, systems thinking

MVP VERSION: CLI tracker with basic stats
PROFESSIONAL VERSION: Rich terminal UI + charts
ENTERPRISE VERSION: Web app + team features + API

FUTURE AI INTEGRATION:
  - AI generates personalized study plan
  - Problem difficulty prediction
  - Pattern recommendation engine

FUTURE SAAS POTENTIAL:
  - Team subscription for bootcamps
  - Recruiter access to candidate stats
```

---

## Project 2: Algorithm Visualizer

```
PROBLEM STATEMENT:
  Students learning DSA need visual, interactive explanations
  to understand how algorithms work step by step.

ARCHITECTURE:
  Algorithm Engine → Step-by-step state generators
  Renderer         → ASCII/HTML/Web canvas visualization
  Controller       → Speed, step controls

FOLDER LAYOUT:
algorithm-visualizer/
├── src/
│   ├── algorithms/
│   │   ├── sorting/
│   │   │   ├── bubble.py
│   │   │   ├── merge.py
│   │   │   ├── quick.py
│   │   │   └── insertion.py
│   │   ├── searching/
│   │   │   ├── binary.py
│   │   │   └── linear.py
│   │   └── patterns/
│   │       ├── two_pointer.py
│   │       └── sliding_window.py
│   ├── renderers/
│   │   ├── ascii_renderer.py
│   │   ├── html_renderer.py
│   │   └── web_renderer.py
│   └── ui/
│       └── app.py
├── static/
│   ├── css/
│   └── js/
├── templates/
└── README.md

SKILLS DEMONSTRATED:
  ✅ Algorithm implementation
  ✅ Generator functions
  ✅ Web development (Flask/FastAPI)
  ✅ JavaScript integration
  ✅ UI/UX thinking

RESUME VALUE: ⭐⭐⭐⭐⭐
RECRUITER APPEAL: Shows teaching ability + deep algo knowledge
```

---

## Project 3: DSA Learning Platform

```
PROBLEM STATEMENT:
  A structured, self-paced DSA learning platform that tracks
  concepts learned, generates quizzes, and adapts to learner level.

FOLDER LAYOUT:
dsa-learning-platform/
├── content/
│   ├── topics/
│   │   ├── arrays.md
│   │   ├── binary_search.md
│   │   └── two_pointers.md
│   └── problems/
│       ├── easy/
│       ├── medium/
│       └── hard/
├── src/
│   ├── quiz_engine.py
│   ├── progress_tracker.py
│   ├── recommendation.py
│   └── cli.py
├── tests/
└── README.md

FUTURE AI INTEGRATION:
  - GPT-powered hints
  - Auto-generate quiz questions
  - Personalized learning path
```

---

## Projects 4–20: Summary Table

| # | Project | Stack | Recruiter Value |
|---|---------|-------|-----------------|
| 4 | Competitive Programming Tracker | Python + SQLite | ⭐⭐⭐⭐ |
| 5 | Kaggle Progress Tracker | Python + Pandas | ⭐⭐⭐⭐ |
| 6 | Coding Interview Manager | Python + Flask | ⭐⭐⭐⭐⭐ |
| 7 | Algorithm Benchmark Engine | Python + matplotlib | ⭐⭐⭐⭐ |
| 8 | Problem Solving Dashboard | Python + Rich | ⭐⭐⭐⭐ |
| 9 | Developer Growth Dashboard | Python + SQLite | ⭐⭐⭐⭐ |
| 10 | Research Dataset Explorer | Python + Pandas | ⭐⭐⭐⭐ |
| 11 | Contest Performance Analyzer | Python + API | ⭐⭐⭐⭐ |
| 12 | Learning Analytics Engine | Python + ML | ⭐⭐⭐⭐⭐ |
| 13 | Algorithm Pattern Library | Python + Docs | ⭐⭐⭐⭐ |
| 14 | Search Optimization Toolkit | Python + Profiling | ⭐⭐⭐ |
| 15 | Coding Habit Tracker | Python + CLI | ⭐⭐⭐ |
| 16 | Performance Benchmark Framework | Python + pytest | ⭐⭐⭐⭐ |
| 17 | Data Structure Simulator | Python + Viz | ⭐⭐⭐⭐ |
| 18 | Analytics Reporting Engine | Python + PDF | ⭐⭐⭐⭐ |
| 19 | Interview Preparation System | Python + AI | ⭐⭐⭐⭐⭐ |
| 20 | Developer Intelligence Platform | Python + ML | ⭐⭐⭐⭐⭐ |

---

# 📁 SECTION 20 — PROJECT LAYOUT MASTERCLASS

## 20.1 Standard Python Project Structure

```
project-name/
│
├── src/                        # All source code
│   ├── __init__.py
│   ├── core/                   # Core business logic
│   │   ├── __init__.py
│   │   ├── models.py           # Data models
│   │   └── exceptions.py      # Custom exceptions
│   ├── algorithms/             # Algorithm implementations
│   │   ├── __init__.py
│   │   ├── searching.py
│   │   ├── sorting.py
│   │   └── two_pointer.py
│   ├── utils/                  # Helper utilities
│   │   ├── __init__.py
│   │   ├── validators.py
│   │   └── formatters.py
│   └── cli/                    # Command line interface
│       ├── __init__.py
│       └── main.py
│
├── tests/                      # All tests
│   ├── __init__.py
│   ├── unit/
│   │   ├── test_algorithms.py
│   │   └── test_models.py
│   ├── integration/
│   │   └── test_pipeline.py
│   └── conftest.py             # pytest fixtures
│
├── docs/                       # Documentation
│   ├── api.md                  # API reference
│   ├── getting_started.md      # Setup guide
│   └── examples/               # Code examples
│
├── notebooks/                  # Jupyter notebooks (if needed)
│   └── exploration.ipynb
│
├── data/                       # Data files
│   ├── raw/
│   └── processed/
│
├── scripts/                    # Utility scripts
│   ├── setup.sh
│   └── benchmark.py
│
├── .github/                    # GitHub configuration
│   ├── workflows/
│   │   └── ci.yml             # GitHub Actions CI
│   └── ISSUE_TEMPLATE/
│
├── README.md                   # Project overview
├── requirements.txt            # Production dependencies
├── requirements-dev.txt        # Development dependencies
├── setup.py                    # Package configuration
├── pyproject.toml              # Modern Python config
├── .gitignore                  # Git ignore rules
├── .env.example                # Environment variables template
└── LICENSE                     # License file
```

## 20.2 Professional README Template

```markdown
# Project Name

Brief, compelling one-line description.

## 🎯 Problem Solved

What problem does this solve? Why does it matter?

## ✨ Features

- Feature 1
- Feature 2
- Feature 3

## 🚀 Quick Start

```bash
git clone https://github.com/username/project
cd project
pip install -r requirements.txt
python src/cli/main.py
```

## 📸 Demo

[Screenshot or GIF here]

## 🛠️ Tech Stack

| Tool | Purpose |
|------|---------|
| Python 3.11 | Core language |
| Click | CLI framework |
| Rich | Terminal UI |

## 📊 Performance

| Operation | Time | Space |
|-----------|------|-------|
| Search | O(log n) | O(1) |

## 🤝 Contributing

See CONTRIBUTING.md

## 📄 License

MIT License
```

---

# 🌟 SECTION 21 — GITHUB PROFILE BOOSTER PROJECTS

## Why These Projects Work

```
RECRUITERS LOOK FOR:
1. Active commit history
2. Clean, documented code
3. Projects solving real problems
4. Tests and CI/CD
5. Professional README

THESE PROJECTS DEMONSTRATE:
- Algorithm knowledge (sorting, searching, patterns)
- Python proficiency (OOP, type hints, docstrings)
- Software engineering (testing, documentation, structure)
- Problem-solving mindset
- Consistency (regular commits)
```

## Top 10 GitHub Profile Projects

| # | Project | Stars Potential | Skills Shown |
|---|---------|-----------------|--------------|
| 1 | LeetCode Analytics Dashboard | ⭐⭐⭐⭐⭐ | DSA + Python + Data |
| 2 | DSA Learning Platform | ⭐⭐⭐⭐⭐ | Teaching + Full Stack |
| 3 | Kaggle Progress Tracker | ⭐⭐⭐⭐ | ML + Data Analysis |
| 4 | Algorithm Benchmark Platform | ⭐⭐⭐⭐ | CS Fundamentals |
| 5 | Coding Interview System | ⭐⭐⭐⭐⭐ | Backend + AI |
| 6 | Developer Growth Dashboard | ⭐⭐⭐⭐ | Analytics + CLI |
| 7 | Analytics Reporting Engine | ⭐⭐⭐ | Data + PDF/Export |
| 8 | Problem Solving Platform | ⭐⭐⭐⭐ | Flask + SQLite |
| 9 | Algorithm Intelligence System | ⭐⭐⭐⭐⭐ | AI + Algorithms |
| 10 | Research Dataset Explorer | ⭐⭐⭐ | Pandas + Viz |

---

# 📅 SECTION 22 — DAILY PRACTICE SYSTEM

## 22.1 The Daily 10 Problem System

```
DAILY COMMITMENT:
  3 Easy     → Build confidence, review patterns
  5 Medium   → Core skill building
  2 Hard     → Challenge and stretch

TIME ALLOCATION (per problem):
  Easy:   15-20 min
  Medium: 25-35 min
  Hard:   45-60 min

Total daily time: ~3.5-4 hours

DAILY WORKFLOW:
  06:00-06:30  Review yesterday's problems
  06:30-07:30  Solve 3 Easy problems
  07:30-09:00  Solve 3 Medium problems
  09:00-10:00  Study new concept
  10:00-11:00  Solve 2 Medium + 2 Hard
  11:00-11:30  Update progress tracker
```

---

## 22.2 Weekly Review System

```
SUNDAY REVIEW CHECKLIST:
□ Count problems solved this week
□ Review any problems you got wrong
□ Re-attempt 2-3 problems from 1 week ago
□ Identify weakest pattern (drill it next week)
□ Update GitHub with week's progress
□ Plan next week's focus topic

MONTHLY REVIEW:
□ Full stats review
□ Mock interview (1-2 problems timed)
□ Contest participation
□ Kaggle notebook submission
□ Update resume with new skills
```

---

## 22.3 Spaced Repetition for DSA

```
REVIEW SCHEDULE:
  Day 1:  Solve problem
  Day 2:  First review (1 day later)
  Day 4:  Second review (3 days later)
  Day 11: Third review (7 days later)
  Day 25: Fourth review (14 days later)
  Day 55: Fifth review (30 days later)

IMPLEMENTATION:
  Use LeetCode Tracker project (Section 18)
  Flag problems for review
  Daily: check review list first
```

---

# 📝 SECTION 23 — 500 PRACTICE QUESTIONS

## 23.1 Binary Search Questions (100 Questions)

### Easy (40 Questions)

1. What is binary search? Explain in plain English.
2. What is the prerequisite for binary search?
3. What is the time complexity of binary search?
4. What is the space complexity of iterative binary search?
5. What is the space complexity of recursive binary search?
6. Why do we use `mid = lo + (hi - lo) // 2` instead of `(lo + hi) // 2`?
7. Write binary search without looking at notes.
8. What does binary search return when element is not found?
9. How many comparisons does binary search need for n=1024?
10. Implement binary search on a list of strings.
11. What happens if the array has duplicate elements in classic binary search?
12. Explain the difference between `lo < hi` and `lo <= hi` loop conditions.
13. When should you use `lo = mid` vs `lo = mid + 1`?
14. Implement binary search that returns True/False instead of index.
15. Write binary search using recursion.
16. What is the worst case input for binary search?
17. Can binary search work on a 2D matrix? How?
18. Implement a search that counts occurrences in O(log n).
19. What is the "search space" in binary search?
20. When is binary search NOT applicable?
21. Implement lower_bound (first position ≥ target).
22. Implement upper_bound (first position > target).
23. What's the difference between lower_bound and first_occurrence?
24. Find the first and last occurrence of an element.
25. Implement search insert position.
26. Find the number of elements in range [lo, hi] in a sorted array.
27. Check if a value exists exactly k times.
28. Given sorted array, find the element closest to target.
29. Find the floor and ceiling of a target in sorted array.
30. Search in a sorted array that may have empty strings interspersed.
31. Find minimum in a sorted rotated array.
32. Find maximum in a sorted rotated array.
33. Search a target in a rotated sorted array.
34. Can a rotated array have duplicates? What changes?
35. Find the rotation count of a sorted rotated array.
36. Given bitonic (mountain) array, find the maximum.
37. Search in a bitonic array.
38. Find peak element in array.
39. What makes peak element finding a binary search problem?
40. Find the kth smallest element in sorted matrix.

### Medium (40 Questions)

41. Apply binary search on answer: square root of integer.
42. Apply binary search: find kth missing positive number.
43. Book allocation problem with 3 students, find minimum pages.
44. What is binary search on answer? Give 3 examples.
45. Median of two sorted arrays — explain the approach.
46. Find the smallest divisor that makes sum ≤ threshold.
47. Capacity to ship packages within D days.
48. Minimum days to make m bouquets.
49. Koko eating bananas — optimal eating speed.
50. What is the aggressive cows problem? Solve it.
51. Painter's partition problem.
52. Allocate minimum number of pages.
53. Split array largest sum.
54. Find kth largest element using binary search.
55. Nth root of a number using binary search.
56. Binary search in nearly sorted array.
57. Search in sorted array of unknown size.
58. Find pair with difference = d using binary search.
59. Count triplets with sum less than given value.
60. Search in row-wise and column-wise sorted 2D matrix.
61. Implement `bisect_left` from scratch.
62. Implement `bisect_right` from scratch.
63. How does Python's `bisect` module work internally?
64. Find position to insert to maintain sorted order.
65. Find element equal to its index in sorted array.
66. Find the fixed point in sorted array.
67. Given infinite sorted array, find target.
68. Find the element that appears once (others appear twice).
69. Magic index in sorted array (array[i] == i).
70. Find number of times sorted array is rotated.
71. Time complexity of searching in rotated array.
72. Can you do binary search on a linked list? Explain.
73. What data structure requires O(log n) search natively?
74. How does BST search relate to binary search?
75. Implement exponential search.
76. When is interpolation search better than binary search?
77. What is ternary search? When would you use it?
78. Find the minimum element where arr[i] >= arr[i-1]*2.
79. Find transition point in boolean array (0→1).
80. Find the missing number in a sorted array.

### Hard (20 Questions)

81. Median of two sorted arrays in O(log(m+n)).
82. Binary search with custom comparator.
83. Solve the "minimum maximum" partition problem.
84. Design a data structure with O(log n) search and insert.
85. Parallel binary search — what is it?
86. Binary search on the answer space for graph problems.
87. Find the k-th smallest prime fraction.
88. Smallest range covering elements from k lists.
89. Race condition in binary search — how to handle in distributed systems?
90. Binary search on floating point answer.
91. Implement fractional cascading.
92. Binary search with function evaluation (expensive predicate).
93. Find the celebrity problem with binary search variant.
94. Weighted binary search — explain and implement.
95. Binary search in compressed coordinate space.
96. Cutting ribbons to maximum length with k pieces.
97. Minimize the maximum distance between gas stations.
98. Find minimum speed to arrive on time.
99. Magnetic force between two balls.
100. Find the kth smallest pair distance.

---

## 23.2 Two Pointers Questions (100 Questions)

### Easy (40 Questions)

1. What is the two pointer technique?
2. When should you use two pointers?
3. What are the two types of two pointer movement?
4. Time complexity of typical two pointer solution?
5. Prerequisite for using opposite-direction two pointers?
6. Implement: check if string is palindrome using two pointers.
7. Implement: reverse an array using two pointers.
8. Implement: find pair with given sum in sorted array.
9. Implement: remove duplicates from sorted array.
10. Implement: move all zeros to the end.
11. Implement: merge two sorted arrays.
12. Implement: find intersection of two sorted arrays.
13. What is the fast-slow pointer technique?
14. What is Floyd's cycle detection algorithm?
15. Detect cycle in linked list using fast-slow pointers.
16. Find middle of linked list using fast-slow pointers.
17. Implement: check if linked list is palindrome.
18. Implement: remove nth node from end of linked list.
19. How many pointers does 3Sum use?
20. Why must we sort before using two pointers for pair sum?
21. Implement: count pairs with sum less than target.
22. Implement: sort array of 0s, 1s, 2s (Dutch National Flag).
23. Implement: maximum of min(a[i], a[j]) * (j-i).
24. Implement: squaring a sorted array in order.
25. Implement: valid palindrome ignoring non-alphanumeric.
26. Implement: reverse vowels only in string.
27. Implement: check if two strings are isomorphic using two pointers.
28. What is a subsequence? Check with two pointers.
29. Implement is_subsequence using two pointers.
30. What is the difference between two pointers and sliding window?
31. Implement: count pairs with difference = k.
32. Implement: two sum on unsorted array (use two approaches).
33. When do we use three pointers?
34. Implement: rotate sorted array to find minimum.
35. Implement: find happy number using fast-slow pointers.
36. Implement: intersection of two arrays II.
37. Implement: remove element from array in-place.
38. Implement: push zeros to front instead of back.
39. Implement: segregate even and odd numbers.
40. Implement: minimum absolute difference pairs.

### Medium (40 Questions)

41. Solve 3Sum without duplicates in O(n²).
42. Solve 3Sum closest to target.
43. Solve 4Sum in O(n³).
44. Container with most water — explain the greedy insight.
45. Why do we always move the shorter pointer in container problem?
46. Implement: trapping rain water using two pointers.
47. Implement: find all triplets that sum to zero.
48. Implement: partition array around pivot (like quicksort).
49. Fast-slow pointer: find start of cycle in linked list.
50. Prove Floyd's algorithm finds cycle start correctly.
51. Implement: find duplicate number using Floyd's algorithm.
52. Implement: longest substring with at most 2 distinct chars.
53. Implement: minimum window to sort remaining array.
54. Implement: sort colors (Dutch National Flag).
55. Implement: find pair with maximum sum ≤ target.
56. Implement: longest palindromic substring using two pointers (expand around center).
57. Implement: find three elements with maximum product.
58. Two pointer on circular array.
59. Implement: pair sum in sorted rotated array.
60. Implement: count distinct elements in window (two pointer variant).
61. Implement: maximum sum of two non-overlapping subarrays.
62. Implement: 3Sum with multiplicity (count instead of find).
63. Find all pairs with difference k in O(n log n).
64. Implement: remove duplicates allowing at most 2 occurrences.
65. Implement: next permutation using two pointers.
66. Implement: partition labels.
67. Implement: boats to save people.
68. Implement: advantage shuffle.
69. Implement: minimum number of swaps to sort array.
70. Implement: merge intervals.
71. Implement: interval list intersections.
72. Implement: find the position of largest group.
73. Implement: number of subarrays with product less than k.
74. Implement: number of subsequences that satisfy condition.
75. Implement: make array strictly increasing.
76. Implement: max area of island.
77. Implement: minimum distance between bst nodes.
78. Implement: maximum erasure value.
79. Implement: ways to split array into three parts.
80. Implement: minimum operations to make array sorted.

### Hard (20 Questions)

81. Implement: trapping rain water O(n) time O(1) space.
82. Implement: minimum window substring.
83. Implement: sliding window maximum.
84. Implement: longest substring with at most k distinct chars.
85. Implement: subarrays with k different integers.
86. Implement: count of range sum.
87. Implement: 4Sum II (count tuples).
88. Implement: shortest subarray to remove to make sorted.
89. Implement: maximum number of non-overlapping subarrays.
90. Implement: minimum swaps to make sequences increasing.
91. Generalize k-sum to k pointers.
92. Implement: pairs with smallest sum.
93. Implement: find kth smallest pair distance.
94. Implement: strange printer using two pointers.
95. Implement: minimum cost to cut a stick.
96. Implement: sliding window based DP.
97. Two pointer on matrix (sorted columns, sorted rows).
98. Implement: maximum sum of three non-overlapping subarrays.
99. Implement: longest turbulent subarray.
100. Implement: count beautiful pairs.

---

## 23.3 Sliding Window Questions (100 Questions)

### Easy (40 Questions)

1. What is a sliding window?
2. What problem does sliding window solve?
3. What is a fixed-size sliding window?
4. What is a variable-size sliding window?
5. Time complexity of sliding window?
6. Space complexity of sliding window?
7. When to use fixed vs variable window?
8. Maximum sum subarray of size k.
9. Minimum sum subarray of size k.
10. Average of all subarrays of size k.
11. Count occurrences of each character in window.
12. First window containing all distinct characters.
13. Longest subarray with sum ≤ target.
14. Shortest subarray with sum ≥ target.
15. Maximum consecutive ones.
16. Find max in every window of size k.
17. Find min in every window of size k.
18. Sliding window to check if anagram exists.
19. Count number of occurrences of anagram in string.
20. Check if string b is rotation of string a using sliding window.
21. Longest substring without repeating characters.
22. Sliding window for DNA repeated sequences.
23. Contains duplicate within k distance.
24. Subarray with equal number of 0s and 1s.
25. Implement sliding window counter using dict.
26. Implement fixed window with deque for max.
27. First negative number in every window of size k.
28. Count substrings with exactly k vowels.
29. Binary subarrays with given sum.
30. Subarray with sum divisible by k.
31. Maximum points from beginning and end (reverse of window).
32. Minimum window to cover all characters.
33. Substring with all characters of given string.
34. Longest substring with equal 0s and 1s.
35. Maximum number of vowels in substring of length k.
36. Maximum sum of 4 consecutive elements.
37. Moving average from data stream.
38. Sliding window where elements are from given set only.
39. Count subarrays where max - min ≤ limit.
40. Minimum operations to reduce array to minimum.

### Medium (40 Questions)

41. Longest substring with at most 2 distinct characters.
42. Longest substring with at most k distinct characters.
43. Permutation in string.
44. Find all anagrams in string.
45. Minimum window substring — brute force O(n²).
46. Minimum window substring — optimal O(n).
47. Longest repeating character replacement.
48. Maximum consecutive ones with at most k flips.
49. Longest subarray of 1s after deleting one element.
50. Fruit into baskets.
51. Subarrays with k different integers.
52. Subarray product less than k.
53. Minimum size subarray sum.
54. Maximum length subarray with equal sum.
55. Longest substring without 3 consecutive characters.
56. Minimum window with all characters of t.
57. Sliding window median.
58. Implement sliding window with monotonic deque.
59. Maximum of minimum for every window size.
60. Count distinct elements in every window.
61. Smallest window with all distinct characters.
62. Substring with concatenation of all words.
63. Minimize maximum distance to gas station.
64. At most k swaps to get k consecutive 1s.
65. Ways to partition array such that each part has equal sum.
66. Grumpy bookstore owner.
67. Maximize the confusion of exam.
68. K radius subarray averages.
69. Longest nice substring.
70. Count good triplets.
71. Delete characters to make fancy string.
72. Maximum average subarray II (variable k).
73. K-size subarray with maximum beauty.
74. Longest balanced substring.
75. Window with maximum elements.
76. Minimum recolors to get k consecutive black blocks.
77. Maximum number of vowels in substring of given length.
78. House robber using sliding window DP.
79. Minimum number of flips to make binary string alternating.
80. Count complete day pairs.

### Hard (20 Questions)

81. Sliding window maximum using monotonic deque.
82. Sliding window minimum.
83. Smallest range covering elements from k lists.
84. Count of subarrays with exactly k distinct integers.
85. Longest substring with at least k repeating characters.
86. Minimum window subsequence.
87. Shortest subarray with sum at least k (negative numbers allowed).
88. Maximum frequency stack — sliding window variant.
89. Minimum number of taps to water garden.
90. Constrained subset sum.
91. Maximum erasure value.
92. Cat and mouse II using sliding window.
93. Sliding window with binary search combination.
94. Maximum sum circular subarray.
95. Jump game VI using deque optimization.
96. Longest subarray with absolute diff ≤ limit.
97. Maximize score after k operations.
98. Count subarrays where max ≥ k * min.
99. Minimum adjacent swaps for k consecutive ones.
100. Get biggest three rhombus sums in grid.

---

## 23.4 Sorting Questions (100 Questions)

### Easy (40 Questions)

1. What is a stable sort?
2. What sorting algorithm does Python use internally?
3. What is Timsort?
4. What is the time complexity of Python's sort()?
5. What is the difference between sort() and sorted()?
6. How do you sort in descending order in Python?
7. How do you sort by a custom key?
8. How do you sort objects by attribute?
9. How do you sort a list of tuples by second element?
10. Sort strings by length.
11. Sort strings alphabetically (case-insensitive).
12. What is selection sort?
13. What is bubble sort?
14. What is insertion sort?
15. When is insertion sort better than merge sort?
16. What is the best case time complexity of bubble sort?
17. Implement bubble sort.
18. Implement selection sort.
19. Implement insertion sort.
20. What is the space complexity of merge sort?
21. What is the space complexity of quick sort?
22. What is the worst case of quick sort?
23. How do you avoid worst case in quick sort?
24. What is random pivot selection?
25. What is the Dutch National Flag problem?
26. Sort array of 0s, 1s, and 2s in O(n) single pass.
27. Sort by frequency.
28. Sort by absolute value.
29. Sort alternately (positive, negative).
30. Sort even numbers, then odd numbers.
31. Sort to bring all negative numbers to front.
32. Count inversions in array (related to sorting).
33. What is a comparison sort? What's the minimum complexity?
34. What is a non-comparison sort?
35. What is counting sort?
36. What is radix sort?
37. What is bucket sort?
38. Sort array with elements 0-100 efficiently.
39. Sort phone numbers (string sort).
40. Sort dates in format "DD-MM-YYYY".

### Medium (40 Questions)

41. Implement merge sort.
42. Implement quick sort with random pivot.
43. Implement quick sort with median-of-3 pivot.
44. Implement merge sort to count inversions.
45. Sort nearly sorted array (each element ≤ k positions away).
46. Find the kth smallest element using quick-select.
47. Sort characters by frequency.
48. Sort by custom multi-key (first by age, then by name).
49. Implement stable sort of objects by key.
50. Meeting rooms: sort intervals by start time.
51. Merge overlapping intervals.
52. Sort k sorted lists (merge).
53. Find the minimum number of arrows to burst balloons.
54. Largest number from array of digits.
55. Sort colors using partition.
56. Minimum number of platforms needed.
57. Activity selection (greedy with sorting).
58. Sort array and find sum of min of all subarrays.
59. Wiggle sort: arr[0] ≤ arr[1] ≥ arr[2] ≤ ...
60. Sort matrix diagonally.
61. Sort matrix each row individually.
62. Relative sort array.
63. Custom comparator for sorting fractions.
64. Sort array by parity.
65. Sort array by parity II (even in even positions).
66. Find K closest points to origin (quick-select variant).
67. Top K frequent elements.
68. Top K frequent words.
69. Sort transformed array.
70. Sort by power value.
71. Rank teams by votes.
72. Assign cookies (sort both, greedy).
73. Non-decreasing array (minimum changes).
74. Sort string characters.
75. Sort list by decrementing value.
76. Reorder data in log files.
77. Maximum gap (radix sort).
78. Sort array to maximize next permutation count.
79. Count of pairs with absolute difference ≤ k.
80. Minimum cost to hire k workers.

### Hard (20 Questions)

81. Count inversions in O(n log n) using merge sort.
82. Find the kth largest element in unsorted array in O(n) average.
83. Sort very large file that doesn't fit in memory (external sort).
84. Find minimum number of swaps to sort array.
85. Sort array in O(n) when elements are from 1 to n.
86. Reverse pairs using merge sort.
87. Count of smaller numbers after self.
88. Minimum cost to sort array with swaps.
89. Sort list in O(n log n) time (linked list).
90. Count number of range sums.
91. Find the smallest range covering k sorted lists.
92. Minimum cost to connect ropes.
93. Maximum performance of team.
94. Sort students by decreasing performance.
95. Reconstruct original permutation from sort trace.
96. Pancake sorting.
97. Minimum number of moves to sort array using only shift operations.
98. Find number of pairs with product sum.
99. Sort by factor count.
100. Sort items by groups respecting dependencies.

---

# 💬 SECTION 24 — 200 INTERVIEW QUESTIONS

## 24.1 Beginner Level (50 Questions)

### Binary Search

**Q1: Explain binary search to a non-programmer.**

*"Imagine finding a name in a phone book. Instead of starting from A and going letter by letter, you open the book in the middle. If the name comes before the middle page, you only look at the first half. You keep halving until you find the name. This is binary search — it halves the problem each step."*

**Q2: What is the difference between binary search and linear search?**

| Aspect | Linear Search | Binary Search |
|--------|---------------|---------------|
| Requirement | None | Array must be sorted |
| Best Case | O(1) | O(1) |
| Worst Case | O(n) | O(log n) |
| Space | O(1) | O(1) |

**Q3: Why does binary search require sorted data?**

*Binary search's core logic is: "if target < middle, search left half; if target > middle, search right half." This only works if we KNOW the left half has smaller elements and right half has larger — which is only true when sorted.*

**Q4: Write binary search without looking at notes.**

```python
def binary_search(arr, target):
    lo, hi = 0, len(arr) - 1
    while lo <= hi:
        mid = lo + (hi - lo) // 2
        if arr[mid] == target:
            return mid
        elif arr[mid] < target:
            lo = mid + 1
        else:
            hi = mid - 1
    return -1
```

**Q5: What happens when mid = (lo + hi) // 2 and lo + hi overflows?**

*In Python, integers don't overflow. But in Java/C++, lo + hi can exceed INT_MAX when both are large. The safe version lo + (hi - lo) // 2 avoids this. Good habit to use in all languages.*

**Q6: What is time complexity and why is binary search O(log n)?**

*Each step halves the search space. Starting with n elements: after 1 step → n/2, after 2 → n/4, ... after k → n/2^k. When n/2^k = 1, we're done. Solving: k = log₂(n). So O(log n) steps.*

**Q7: What are edge cases for binary search?**

```python
# Edge cases to check:
# 1. Empty array → return -1 immediately
# 2. Single element array → check that element
# 3. Target smaller than all elements → return -1
# 4. Target larger than all elements → return -1
# 5. Target is first element
# 6. Target is last element
# 7. Array with duplicates → returns any valid index
```

**Q8: Can binary search be used on strings?**

*Yes, if strings are sorted lexicographically. Compare strings instead of numbers: `if arr[mid] == target` uses string comparison.*

**Q9: What is the recursive vs iterative binary search?**

*Iterative uses O(1) space. Recursive uses O(log n) stack space. Prefer iterative. They have same time complexity.*

**Q10: Write first and last occurrence functions.**

```python
def first(arr, target):
    lo, hi, result = 0, len(arr)-1, -1
    while lo <= hi:
        mid = lo + (hi-lo)//2
        if arr[mid] == target:
            result = mid; hi = mid-1  # Search left
        elif arr[mid] < target:
            lo = mid + 1
        else:
            hi = mid - 1
    return result

def last(arr, target):
    lo, hi, result = 0, len(arr)-1, -1
    while lo <= hi:
        mid = lo + (hi-lo)//2
        if arr[mid] == target:
            result = mid; lo = mid+1  # Search right
        elif arr[mid] < target:
            lo = mid + 1
        else:
            hi = mid - 1
    return result
```

---

### Two Pointers

**Q11: What is the two pointer technique?**

*Two pointers is a technique where we maintain two indices into an array or string. By moving these pointers intelligently (usually inward from both ends, or both moving forward at different speeds), we can solve problems in O(n) that would otherwise be O(n²).*

**Q12: What are the two main patterns of two pointers?**

*1. Opposite direction: Start at both ends, move toward center. Used for pair sum, palindrome check, container with water.*

*2. Same direction (fast/slow): Both start at beginning. Slow tracks result position, fast scans ahead. Used for remove duplicates, move zeros, cycle detection.*

**Q13: Why can two pointers reduce O(n²) to O(n)?**

*In brute force pair-finding, we try every pair: O(n²). With two pointers on sorted array, each pointer only moves in one direction (left → right or right → left). Together they make at most n moves total → O(n).*

**Q14: What is Floyd's cycle detection?**

*Slow pointer moves 1 step, fast pointer moves 2 steps. If a cycle exists, fast will eventually lap slow and they'll meet. If no cycle, fast reaches the end.*

**Q15: Write palindrome check using two pointers.**

```python
def is_palindrome(s):
    left, right = 0, len(s) - 1
    while left < right:
        if s[left] != s[right]:
            return False
        left += 1
        right -= 1
    return True
```

---

## 24.2 Intermediate Level (50 Questions)

**Q51: Explain the book allocation problem and its binary search approach.**

*We have N books with pages[] and M students. Each student reads consecutive books. We want to minimize the maximum pages any student reads.*

*Binary search on answer: search between max(pages) and sum(pages). For each mid, check if M students can cover all books with max_pages = mid. This gives O(n log(sum)) solution.*

**Q52: What is the "binary search on answer" paradigm?**

*Instead of searching for a value in an array, we search the answer space (min to max possible answer). For each candidate answer mid, we check feasibility. If feasible, we try to optimize. This converts optimization problems into decision problems.*

*Pattern recognition: "minimize maximum" or "maximize minimum" → binary search on answer.*

**Q53: Explain 3Sum and why O(n²) is optimal.**

*Sort array. Fix one element with index i. Use two pointers (left=i+1, right=n-1) to find pair summing to -arr[i]. This is O(n²). For 3Sum, Ω(n²) is a known lower bound — we can't do better without additional constraints.*

**Q54: Why do we skip duplicates in 3Sum?**

*Without skipping: if arr[i]=arr[i-1], fixing at i gives the same triplets as fixing at i-1. Skip to avoid adding duplicates to result.*

**Q55: Explain minimum window substring approach.**

*Use two pointers (window). Expand right until window contains all chars of t. Then shrink from left until it stops containing all. Record this window. Move right and repeat. Track using frequency map and "missing" counter.*

**Q56: What is a monotonic deque? When is it used?**

*A deque where elements are maintained in monotonically increasing or decreasing order. Used in sliding window maximum: maintain indices in decreasing order of values. Front always has the maximum in the current window. Pop from front when it's outside window; pop from back when new element is larger.*

**Q57: How does Kadane's algorithm relate to sliding window?**

*Kadane's finds maximum subarray sum. It's a O(n) algorithm maintaining current sum and resetting to 0 when sum goes negative. It's like a variable sliding window where we restart when sum drops below 0.*

**Q58: Explain merge sort and why it's O(n log n).**

*Divide array into two halves → sort each half recursively → merge sorted halves. The merge step is O(n). We have log n levels of recursion. Total: O(n log n). Recurrence: T(n) = 2T(n/2) + O(n) → T(n) = O(n log n) by Master Theorem.*

**Q59: When is quick sort faster than merge sort in practice?**

*Quick sort has better cache performance (in-place, sequential access) and smaller constant factors. On random data, it's typically 2-3x faster. But worst case O(n²) with bad pivot choice.*

**Q60: What is the partition function in quick sort?**

*Rearranges array such that elements ≤ pivot are on left, elements > pivot on right. Returns pivot's final position. All elements left of pivot index are ≤ pivot; all to the right are > pivot.*

---

## 24.3 Advanced Level — FAANG (50 Questions)

**Q101: Design an O(n log n) algorithm to count inversions.**

*An inversion is a pair (i,j) where i<j but arr[i]>arr[j]. Use modified merge sort: during merge, when a right element is placed before a left element, count all remaining left elements as inversions.*

```python
def count_inversions(arr):
    if len(arr) <= 1:
        return arr, 0
    
    mid = len(arr) // 2
    left, left_inv = count_inversions(arr[:mid])
    right, right_inv = count_inversions(arr[mid:])
    
    merged, split_inv = merge_count(left, right)
    return merged, left_inv + right_inv + split_inv

def merge_count(left, right):
    result, inversions = [], 0
    i = j = 0
    while i < len(left) and j < len(right):
        if left[i] <= right[j]:
            result.append(left[i]); i += 1
        else:
            result.append(right[j]); j += 1
            inversions += len(left) - i  # All remaining left elements are > right[j]
    result.extend(left[i:])
    result.extend(right[j:])
    return result, inversions
```

**Q102: Explain the median of two sorted arrays problem.**

*Find median of two sorted arrays in O(log(m+n)). Binary search on partition: find partition point i in arr1, j in arr2 such that all elements left of partition ≤ all elements right. Check: arr1[i-1] ≤ arr2[j] and arr2[j-1] ≤ arr1[i].*

**Q103: How would you optimize LeetCode #76 (Min Window Substring) for interview?**

*1. State clearly: "I'll use variable sliding window with frequency maps." 2. Walk through the key insight: track 'missing' count to know when window is valid. 3. Two-pointer expansion + shrinking. 4. Update result only when window is minimal valid. Time: O(|s|+|t|), Space: O(|s|+|t|).*

**Q104: Design a real-time leaderboard with top-k query.**

*Use sorted set (Redis ZSET or Python's SortedList). Add/update score: O(log n). Top-k query: O(k). This is better than re-sorting O(n log n) each time.*

**Q105: How would you apply binary search in a distributed system?**

*"I'd use binary search on versioned data. For example, finding the first deployment that introduced a bug: binary search through deployment history, deploying and testing at each mid point."*

**Q106: Explain the two pointer approach for trapping rain water.**

*At each position, water level = min(max_left, max_right). Use two pointers from both ends. If left_max < right_max, we know left position's water level is left_max. Process left pointer. Otherwise process right pointer.*

```python
def trap(height):
    left, right = 0, len(height) - 1
    left_max = right_max = 0
    water = 0
    while left < right:
        if height[left] < height[right]:
            left_max = max(left_max, height[left])
            water += left_max - height[left]
            left += 1
        else:
            right_max = max(right_max, height[right])
            water += right_max - height[right]
            right -= 1
    return water
```

---

## 24.4 AI Engineer Specific (50 Questions)

**Q151: How does binary search appear in ML/AI?**

*1. Learning rate search (bisection method to find optimal lr). 2. Hyperparameter optimization. 3. Tree-based models internally use binary search. 4. Beam search in NLP uses heap which relies on ordering. 5. Finding confidence thresholds. 6. Active learning: binary search for decision boundary.*

**Q152: How does sorting relate to recommendation systems?**

*Content-based filtering: sort items by similarity score. Collaborative filtering: sort by predicted rating. Top-k recommendations: quick-select or heap for O(n log k). Real-time: maintaining sorted order with online updates.*

**Q153: Explain sliding window in the context of NLP.**

*Sliding window for: 1. N-gram language modeling (window of n tokens). 2. Attention mechanisms in early models used fixed windows. 3. Chunking long documents for LLM processing. 4. Rolling statistics in time series NLP data.*

**Q154: How would you implement binary search for finding optimal ML threshold?**

*For binary classification, find threshold t that maximizes F1 or satisfies precision≥p requirement. Sort probabilities. Binary search threshold: check precision/recall at mid threshold. Converge to optimal.*

**Q155: Describe a sliding window approach for anomaly detection.**

```python
def detect_anomalies(time_series, window_size, threshold):
    """
    Sliding window anomaly detection.
    Flag point as anomaly if it deviates > threshold * std from window mean.
    """
    anomalies = []
    from collections import deque
    window = deque()
    
    for i, val in enumerate(time_series):
        window.append(val)
        if len(window) > window_size:
            window.popleft()
        
        if len(window) == window_size:
            mean = sum(window) / window_size
            std = (sum((x-mean)**2 for x in window) / window_size) ** 0.5
            
            if abs(val - mean) > threshold * std:
                anomalies.append((i, val, mean, std))
    
    return anomalies
```

---

# 📋 SECTION 25 — ASSIGNMENTS + SOLUTIONS

## Assignment 1: Binary Search

### Problems

1. **Implement Binary Search** — Write iterative and recursive versions.
2. **Find Peak Element** — Implement O(log n) solution.
3. **Search in Rotated Array** — Handle both with and without duplicates.
4. **Book Allocation** — Minimize maximum pages with M students.
5. **Square Root** — Find floor(sqrt(x)) using binary search.

### Solutions

```python
# Assignment 1 Solutions

# 1. Binary Search (both versions above in Section 3)

# 2. Peak Element
def find_peak(nums):
    lo, hi = 0, len(nums) - 1
    while lo < hi:
        mid = (lo + hi) // 2
        if nums[mid] < nums[mid + 1]:
            lo = mid + 1
        else:
            hi = mid
    return lo

# 3. Search in Rotated Array (above in Section 4)

# 4. Book Allocation (above in Section 4)

# 5. Square Root
def sqrt(x):
    if x < 2:
        return x
    lo, hi = 1, x // 2
    while lo <= hi:
        mid = (lo + hi) // 2
        if mid * mid == x:
            return mid
        elif mid * mid < x:
            lo = mid + 1
        else:
            hi = mid - 1
    return hi

# Test all
print(find_peak([1, 2, 3, 1]))           # 2
print(sqrt(8))                            # 2
```

---

## Assignment 2: Two Pointers

### Problems

1. **3Sum** — Find all unique triplets summing to 0.
2. **Container With Most Water** — Maximize water.
3. **Cycle Detection** — Floyd's algorithm on linked list.
4. **Trapping Rain Water** — Two pointer O(1) space.
5. **Move Zeroes** — In-place, maintain order.

### Solutions

```python
# All solutions provided above in Section 6
# Key test cases:

# 3Sum
print(three_sum([-1, 0, 1, 2, -1, -4]))
# [[-1,-1,2],[-1,0,1]]

# Container
print(max_area([1,8,6,2,5,4,8,3,7]))
# 49

# Rain water
print(trap([0,1,0,2,1,0,1,3,2,1,2,1]))
# 6
```

---

## Assignment 3: Sliding Window

### Problems

1. **Longest Substring Without Repeating** — LeetCode #3.
2. **Find All Anagrams** — LeetCode #438.
3. **Min Window Substring** — LeetCode #76.
4. **Max Sum Subarray K** — Fixed window.
5. **K Distinct Characters** — Variable window.

### Solutions

```python
# All solutions above in Section 8

# Additional: Longest subarray with 1s after deleting one 0
def longest_ones(nums, k):
    """LeetCode 1004: Max Consecutive Ones III"""
    left = zeros = result = 0
    for right in range(len(nums)):
        zeros += 1 - nums[right]  # Count zeros in window
        while zeros > k:           # Too many zeros, shrink
            zeros -= 1 - nums[left]
            left += 1
        result = max(result, right - left + 1)
    return result

print(longest_ones([1,1,1,0,0,0,1,1,1,1,0], 2))  # 6
```

---

## Assignment 4: Sorting

### Problems

1. **Sort Colors** — O(n) single pass, Dutch flag.
2. **Merge Intervals** — Sort then merge.
3. **Largest Number** — Custom comparator sort.
4. **K Closest Points** — Quick-select or heap.
5. **Count Inversions** — Merge sort variant.

### Solutions

```python
# Sort Colors (Dutch National Flag)
def sort_colors(nums):
    lo, mid, hi = 0, 0, len(nums) - 1
    while mid <= hi:
        if nums[mid] == 0:
            nums[lo], nums[mid] = nums[mid], nums[lo]
            lo += 1; mid += 1
        elif nums[mid] == 1:
            mid += 1
        else:
            nums[mid], nums[hi] = nums[hi], nums[mid]
            hi -= 1

# Merge Intervals
def merge_intervals(intervals):
    intervals.sort(key=lambda x: x[0])
    merged = [intervals[0]]
    for start, end in intervals[1:]:
        if start <= merged[-1][1]:
            merged[-1][1] = max(merged[-1][1], end)
        else:
            merged.append([start, end])
    return merged

# Largest Number
from functools import cmp_to_key
def largest_number(nums):
    def compare(a, b):
        if a + b > b + a: return -1
        if a + b < b + a: return 1
        return 0
    strs = [str(n) for n in nums]
    strs.sort(key=cmp_to_key(compare))
    return str(int(''.join(strs)))

print(merge_intervals([[1,3],[2,6],[8,10],[15,18]]))
# [[1,6],[8,10],[15,18]]

print(largest_number([3,30,34,5,9]))
# "9534330"
```

---

## Assignment 5: LeetCode Challenge

Solve these 10 LeetCode problems in order:

| # | Problem | Difficulty | Pattern |
|---|---------|------------|---------|
| 704 | Binary Search | Easy | Binary Search |
| 35 | Search Insert Position | Easy | Binary Search |
| 167 | Two Sum II | Medium | Two Pointers |
| 283 | Move Zeroes | Easy | Two Pointers |
| 643 | Maximum Average Subarray | Easy | Sliding Window |
| 3 | Longest Substring No Repeat | Medium | Sliding Window |
| 88 | Merge Sorted Array | Easy | Two Pointers |
| 153 | Find Min in Rotated Array | Medium | Binary Search |
| 424 | Character Replacement | Medium | Sliding Window |
| 15 | 3Sum | Medium | Two Pointers |

---

# 🏢 SECTION 26 — ENTERPRISE CHALLENGE PROJECTS

## Project 1: DSA Learning Platform

```
VISION:
  A full-stack web platform where users learn DSA concepts,
  solve problems, track progress, and get AI-powered hints.

ARCHITECTURE:
┌─────────────────────────────────────────┐
│              FRONTEND                   │
│   React + TypeScript + TailwindCSS      │
│   Problem Viewer, Code Editor, Viz      │
└─────────────────┬───────────────────────┘
                  │ REST/WebSocket
┌─────────────────▼───────────────────────┐
│              BACKEND API                │
│   FastAPI + PostgreSQL + Redis          │
│   Auth, Problems, Progress, Hints       │
└─────────────────┬───────────────────────┘
                  │
┌─────────────────▼───────────────────────┐
│              AI SERVICE                 │
│   Claude API / GPT-4                    │
│   Hint generation, Solution review      │
└─────────────────────────────────────────┘

FOLDER LAYOUT:
dsa-platform/
├── backend/
│   ├── app/
│   │   ├── api/
│   │   │   ├── auth.py
│   │   │   ├── problems.py
│   │   │   ├── progress.py
│   │   │   └── hints.py
│   │   ├── models/
│   │   │   ├── user.py
│   │   │   ├── problem.py
│   │   │   └── submission.py
│   │   ├── services/
│   │   │   ├── ai_hints.py
│   │   │   ├── code_runner.py
│   │   │   └── analytics.py
│   │   └── main.py
│   ├── tests/
│   └── requirements.txt
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   ├── pages/
│   │   └── hooks/
│   ├── package.json
│   └── tsconfig.json
├── docker-compose.yml
├── nginx.conf
└── README.md

SCALING PLAN:
  Phase 1: 100 users     → SQLite + single server
  Phase 2: 10,000 users  → PostgreSQL + Redis cache
  Phase 3: 100,000 users → Microservices + CDN
  Phase 4: 1M+ users    → Kubernetes + global CDN

TESTING STRATEGY:
  Unit: pytest (backend), Jest (frontend)
  Integration: API tests with httpx
  E2E: Playwright
  Load: locust

DEPLOYMENT PLAN:
  Docker → GitHub Actions CI/CD → AWS ECS
  Database: RDS PostgreSQL
  Cache: ElastiCache Redis
  CDN: CloudFront

FUTURE AI INTEGRATION:
  - Personalized learning paths
  - Automatic problem generation
  - Code review and suggestions
  - Interview simulation
```

---

# 📝 SECTION 27 — DAY17 REVISION

## 27.1 One-Page Summary

```
BINARY SEARCH:
  ├── Requirement: SORTED array
  ├── Time: O(log n), Space: O(1)
  ├── Template: lo=0, hi=n-1; mid=lo+(hi-lo)//2
  ├── Decision: if arr[mid]<target: lo=mid+1 else hi=mid-1
  └── Patterns: First/Last Occ, Rotated, BS on Answer

TWO POINTERS:
  ├── Opposite: lo=0,hi=n-1 move inward → Pair sum, palindrome
  ├── Same dir: slow=0; for fast in range(n) → Remove dups, move zeros
  ├── Fast+Slow: cycle detection, find middle
  └── Time: O(n), Space: O(1)

SLIDING WINDOW:
  ├── Fixed: for i in range(k,n): add arr[i], remove arr[i-k]
  ├── Variable: expand right, shrink left when invalid
  ├── State: track using dict/counter/sum
  └── Time: O(n), Space: O(k) or O(alphabet)

SORTING:
  ├── Python: list.sort() = Timsort = O(n log n), stable
  ├── Use key= for custom sorting
  ├── Bubble/Selection/Insertion: O(n²) [for small n]
  ├── Merge: O(n log n), O(n) space, stable
  └── Quick: O(n log n) avg, O(n²) worst, O(log n) space
```

---

## 27.2 Binary Search Cheat Sheet

```python
# 1. Classic
def bs(arr, t):
    lo, hi = 0, len(arr)-1
    while lo <= hi:
        mid = lo + (hi-lo)//2
        if arr[mid]==t: return mid
        elif arr[mid]<t: lo=mid+1
        else: hi=mid-1
    return -1

# 2. First Occurrence
def first(arr, t):
    lo, hi, res = 0, len(arr)-1, -1
    while lo<=hi:
        mid = lo+(hi-lo)//2
        if arr[mid]==t: res=mid; hi=mid-1
        elif arr[mid]<t: lo=mid+1
        else: hi=mid-1
    return res

# 3. BS on Answer (minimize maximum)
def solve(data):
    def feasible(mid): ...  # Can we do it with mid?
    lo, hi = min_ans, max_ans
    res = hi
    while lo<=hi:
        mid = lo+(hi-lo)//2
        if feasible(mid): res=mid; hi=mid-1
        else: lo=mid+1
    return res
```

---

## 27.3 Two Pointer Cheat Sheet

```python
# Opposite direction
def two_pointer_op(arr, target):
    lo, hi = 0, len(arr)-1
    while lo < hi:
        s = arr[lo] + arr[hi]
        if s == target: return [lo, hi]
        elif s < target: lo += 1
        else: hi -= 1

# Same direction (fast & slow)
def two_pointer_same(arr):
    slow = 0
    for fast in range(len(arr)):
        if condition(arr[fast]):
            arr[slow] = arr[fast]
            slow += 1
    return slow

# Fast & Slow (cycle)
def has_cycle(head):
    slow = fast = head
    while fast and fast.next:
        slow = slow.next
        fast = fast.next.next
        if slow == fast: return True
    return False
```

---

## 27.4 Sliding Window Cheat Sheet

```python
# Fixed window (max sum k)
def fixed_sw(arr, k):
    win = sum(arr[:k]); res = win
    for i in range(k, len(arr)):
        win += arr[i] - arr[i-k]
        res = max(res, win)
    return res

# Variable window (longest no repeat)
def var_sw(s):
    seen = {}; lo = 0; res = 0
    for hi, c in enumerate(s):
        if c in seen and seen[c] >= lo:
            lo = seen[c] + 1
        seen[c] = hi
        res = max(res, hi-lo+1)
    return res

# Variable window (min subarray sum >= target)
def min_win(arr, target):
    lo = s = 0; res = float('inf')
    for hi in range(len(arr)):
        s += arr[hi]
        while s >= target:
            res = min(res, hi-lo+1)
            s -= arr[lo]; lo += 1
    return res if res != float('inf') else 0
```

---

## 27.5 Common Mistakes Summary

```
BINARY SEARCH:
  ❌ mid = (lo+hi)//2  →  ✅ mid = lo+(hi-lo)//2
  ❌ while lo < hi     →  ✅ while lo <= hi (usually)
  ❌ lo = mid          →  ✅ lo = mid+1
  ❌ No edge case      →  ✅ Check empty array first

TWO POINTERS:
  ❌ Using on unsorted for pair sum
  ❌ Forgetting to skip duplicates in 3Sum
  ❌ Not handling cycle detection properly
  ❌ Off-by-one on same-direction pointers

SLIDING WINDOW:
  ❌ O(n*k) recomputation instead of O(n) sliding
  ❌ Forgetting to shrink window when invalid
  ❌ Wrong window size calculation (right-left vs right-left+1)
  ❌ Not handling empty string edge case

SORTING:
  ❌ Using O(n²) when O(n log n) is needed
  ❌ Forgetting sort() modifies in-place (no return value!)
  ❌ Not considering stability requirements
  ❌ Wrong custom comparator sign
```

---

# 🔮 SECTION 28 — PREPARATION FOR DAY18

## 28.1 What's Coming: Data Structures Deep Dive

```
DAY 18 TOPICS:
  
  🔗 Linked Lists
     ├── Singly Linked List
     ├── Doubly Linked List
     ├── Circular Linked List
     ├── Implementation from scratch
     └── Classic problems (reverse, merge, detect cycle)
  
  📚 Stacks
     ├── Array-based stack
     ├── Linked list stack
     ├── Monotonic stack
     └── Problems: valid parentheses, next greater element
  
  🔄 Queues
     ├── Array queue
     ├── Circular queue
     ├── Deque (double-ended queue)
     └── Problems: BFS, sliding window max
  
  #️⃣ Hash Maps Advanced
     ├── Collision handling
     ├── Custom hash functions
     ├── LRU Cache implementation
     └── Design problems

  📊 Monotonic Stack
     ├── Increasing vs decreasing
     ├── Next greater/smaller element
     ├── Largest rectangle in histogram
     └── Trapping rain water
```

---

## 28.2 Day18 Preview: Linked List

```python
# Simple Linked List Node
class ListNode:
    def __init__(self, val=0, next=None):
        self.val = val
        self.next = next

# Build a linked list: 1 → 2 → 3 → 4 → 5
def build_list(values):
    dummy = ListNode(0)
    curr = dummy
    for val in values:
        curr.next = ListNode(val)
        curr = curr.next
    return dummy.next

# Traverse
def print_list(head):
    vals = []
    while head:
        vals.append(head.val)
        head = head.next
    print(" → ".join(map(str, vals)))

# Reverse a linked list (Day 18 core problem)
def reverse_list(head):
    prev, curr = None, head
    while curr:
        next_node = curr.next
        curr.next = prev
        prev = curr
        curr = next_node
    return prev

head = build_list([1, 2, 3, 4, 5])
print_list(head)               # 1 → 2 → 3 → 4 → 5
print_list(reverse_list(head)) # 5 → 4 → 3 → 2 → 1
```

---

## 28.3 Roadmap Visual

```
       YOU ARE HERE
           ↓
Day17: Binary Search + 2P + SW + Sorting
           ↓
Day18: Linked Lists + Stacks + Queues + Hash Maps
           ↓
Day19: Trees + Binary Search Trees + Tree Traversals
           ↓
Day20: Heaps + Priority Queues + Heap Problems
           ↓
Day21: Graphs + BFS + DFS + Topological Sort
           ↓
Day22: Dynamic Programming Part 1 (1D DP)
           ↓
Day23: Dynamic Programming Part 2 (2D DP)
           ↓
Day24: Advanced DP + Greedy Algorithms
           ↓
Day25: System Design + FAANG Interview Prep
```

---

## 28.4 Day18 Pre-Study Checklist

Before Day 18, make sure you can:

```
BINARY SEARCH:
□ Write from memory in < 3 minutes
□ Find first/last occurrence
□ Implement binary search on answer
□ Solve: Book allocation, Aggressive cows

TWO POINTERS:
□ Solve pair sum in sorted array
□ 3Sum without duplicates
□ Container with most water
□ Detect cycle in linked list

SLIDING WINDOW:
□ Max sum subarray of size k
□ Longest substring without repeating
□ Find all anagrams

SORTING:
□ Explain Timsort
□ Use custom key in sort()
□ Merge intervals
□ Sort colors (Dutch flag)
```

---

# 🏆 FINAL THOUGHTS

## Key Principles for DSA Success

```
1. CONSISTENCY > INTENSITY
   Solve 5 problems daily > solve 50 on weekends
   30 minutes daily > 5 hours once a week

2. PATTERN RECOGNITION IS THE SKILL
   You're not memorizing solutions
   You're learning to see patterns:
   Sorted + Search → Binary Search
   Subarray optimization → Sliding Window
   Pair in sorted → Two Pointers

3. UNDERSTAND > MEMORIZE
   Understanding WHY binary search works
   is more valuable than memorizing the template.
   Understanding comes from dry-runs and tracing.

4. BUILD IN PUBLIC
   Document your solutions on GitHub
   Write about what you learned
   Teach others (best way to learn)

5. COMPETE REGULARLY
   Participate in Codeforces Div3
   Join LeetCode weekly contests
   Aim for Kaggle bronze medals

6. TRACK EVERYTHING
   Progress tracker (built in Section 18)
   Weekly reviews
   Patterns mastered

7. EMBRACE THE STRUGGLE
   Stuck on a problem for 30 min? GOOD.
   That's when the real learning happens.
   After 45 min, look at hint or editorial.
   Then solve it yourself from scratch.
```

---

## Day17 Completion Checklist

```
CONCEPTS:
□ Binary Search — iterative + recursive
□ First/Last occurrence
□ Binary Search on Answer
□ Rotated Array search
□ Two Pointer — opposite direction
□ Two Pointer — same direction (fast/slow)
□ Floyd's cycle detection
□ 3Sum
□ Sliding Window — fixed
□ Sliding Window — variable
□ Minimum Window Substring
□ All sorting algorithms
□ Python sort() with custom key

PROBLEMS SOLVED:
□ 704. Binary Search
□ 35. Search Insert Position
□ 69. Sqrt(x)
□ 153. Find Min in Rotated Array
□ 33. Search in Rotated Array
□ 167. Two Sum II
□ 283. Move Zeroes
□ 15. 3Sum
□ 11. Container With Most Water
□ 141. Linked List Cycle
□ 643. Max Average Subarray I
□ 3. Longest Substring Without Repeating
□ 438. Find All Anagrams
□ 76. Min Window Substring
□ 424. Character Replacement

PROJECTS:
□ Binary Search Visualizer
□ LeetCode Progress Tracker
□ Algorithm Benchmark Tool
□ Kaggle profile created
□ GitHub portfolio project started

NEXT STEPS:
□ Register on Codeforces
□ Solve 10 problems on LeetCode this week
□ Start Titanic Kaggle notebook
□ Review Day17 on Day18 morning (10 min)
□ Begin Day18: Linked Lists
```

---
*Day17 Complete! 🎉*
---

