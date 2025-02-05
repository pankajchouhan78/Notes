## Python Collections

### 1. List
- A **list** is a collection object that is ordered and indexed.
- Lists are **mutable**, meaning that once they are created, you can add, remove, and modify their elements.

### 2. Tuple
- A **tuple** is a collection object that is ordered and indexed. This means we can access tuple elements by their index.
- Tuples are **immutable**, meaning once they are created, we cannot add, remove, or modify their elements.

### 3. Set
- A **set** is used to store **unique elements**.
- Sets are **unordered** and **unindexed** internally, and they are **mutable**.

### 4. Dictionary
- A **dictionary** is a collection object, mainly used to store values based on keys.
- In a dictionary, we store **unique keys**, but we can store **duplicate values**.

---

## Difference Between List and Tuple

| **Aspect**                | **List**                                                          | **Tuple**                                                     |
|---------------------------|-------------------------------------------------------------------|---------------------------------------------------------------|
| **Mutability**             | Lists are **mutable**, meaning once they are created, you can add, remove, or modify elements. You can use methods like `append()`, `remove()`, `pop()`, and assignment to modify elements. | Tuples are **immutable**, meaning once they are created, you cannot modify their elements. Once a tuple is defined, you cannot add, remove, or change its elements. |
| **Methods**                | Lists have many methods available for modification.               | Tuples have only two methods: `count()` and `index()`.          |
| **Definition**             | Lists are defined using square brackets `[]`.                     | Tuples are defined using parentheses `()`.                     |
| **Example**                | Example of a list: `my_list = [1, 2, 3, 4]`<br>`my_list[2] = 5` (This is allowed, modifying the third element) | Example of a tuple: `my_tuple = (1, 2, 3, 4)`<br>`# my_tuple[2] = 5` (This will raise a `TypeError` since tuples are immutable) |
| **Memory Usage**           | Lists consume **more memory**.                                   | Tuples consume **less memory**.                               |

---

## Difference Between List and Dictionary Comprehension

| **Aspect**              | **List Comprehension**                                            | **Dictionary Comprehension**                                   |
|-------------------------|-------------------------------------------------------------------|-----------------------------------------------------------------|
| **Purpose**              | List comprehension is used to create a new list by applying an expression to each element of an iterable. | Dictionary comprehension is used to create a new dictionary by applying an expression to each key-value pair. |
| **Example**              | Creating a list of squares of numbers from 1 to 5 using list comprehension: <br> `squares = [x**2 for x in range(1, 6)]` <br> **Output**: `[1, 4, 9, 16, 25]` | Creating a dictionary of squares of numbers from 1 to 5 using dictionary comprehension: <br> `squares_dict = {x: x**2 for x in range(1, 6)}` <br> **Output**: `{1: 1, 2: 4, 3: 9, 4: 16, 5: 25}` |

---

## Difference Between Python Arrays and Lists

| **Aspect**               | **List**                                                       | **Arrays**                                                      |
|--------------------------|----------------------------------------------------------------|-----------------------------------------------------------------|
| **Data Types**            | A List can hold elements of **different data types**, including integers, floats, and strings. | An Array can hold elements of the **same data type**.           |
| **Example**               | Example: `my_list = [1, 2, "hello", 3.14]`                    | Example: `from array import array; my_array = array('i', [1, 2, 3, 4, 5])` |
| **Import Requirement**    | Lists do not require any imports.                             | Arrays require importing the `array` module and specifying the data type (e.g., `'i'` for integers). |

---

## How to Initialize Empty List, Tuple, Dict, and Set?

| **Data Structure**    | **Initialization**       |
|-----------------------|--------------------------|
| **Empty List**        | `empty_list = []`        |
| **Empty Tuple**       | `empty_tuple = ()`       |
| **Empty Dictionary**  | `empty_dict = {}`        |
| **Empty Set**         | `empty_set = set()`      |


## what do you mean by negative indexing in python? 
In Python, negative indexing is a feature that allows you to access elements from the end of a sequence (like a list, tuple, or string) using negative numbers.
