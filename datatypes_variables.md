### Python Data Types

Python has several built-in data types to handle different kinds of data. Here’s an overview:

1. **Numeric Types**:
   - `int`: For whole numbers (e.g., 1, 25, -10).
   - `float`: For decimal numbers (e.g., 3.14, -0.001, 2.0).
   - `complex`: For complex numbers (e.g., 2 + 3j).

2. **Sequence Types**:
   - `list`: An ordered, mutable collection (e.g., `[1, 2, 3]`).
   - `tuple`: An ordered, immutable collection (e.g., `(1, 2, 3)`).
   - `range`: Represents a sequence of numbers used mainly in loops (e.g., `range(5)`).

3. **Text Type**:
   - `str`: Represents text data (e.g., `"hello"`, `'Python'`).

4. **Mapping Type**:
   - `dict`: A collection of key-value pairs (e.g., `{"name": "Alice", "age": 25}`).

5. **Set Types**:
   - `set`: An unordered collection of unique items (e.g., `{1, 2, 3}`).
   - `frozenset`: An immutable version of a set (e.g., `frozenset([1, 2, 3])`).

6. **Boolean Type**:
   - `bool`: Represents `True` or `False`.

7. **Binary Types**:
   - `bytes`: Immutable sequence of bytes (e.g., `b'hello'`).
   - `bytearray`: Mutable sequence of bytes (e.g., `bytearray([65, 66, 67])`).
   - `memoryview`: Allows viewing of the memory of other binary objects (e.g., `memoryview(b'hello')`).

8. **None Type**:
   - `None`: Represents the absence of a value or null value.

#### Dynamic Typing in Python
Python is dynamically typed, meaning that variables do not require an explicit declaration of type. The type of a variable is determined at runtime and can change during the program execution.

---

#### **Mutable vs Immutable Data Types**:

| **Mutable Data Types**                 | **Immutable Data Types**              |
|----------------------------------------|---------------------------------------|
| A mutable data type is one whose value **can be changed** after it is created. | An immutable data type is one whose value **cannot be changed** after it is created. |
| **Examples**: `list`, `set`, `dict`, `classes` | **Examples**: `int`, `float`, `str`, `tuple` |

---

In summary:
- **Mutable types** can be changed after they are created (e.g., lists, sets, dictionaries).
- **Immutable types** cannot be changed after they are created (e.g., integers, strings, tuples).
---

# Variables Related Questions and Answers

## 1. What are variables in Python?

In Python, a variable is a name of memory location that contains some information. It is used to store data that can be used and modified throughout the program. Python is dynamically typed, meaning you don't need to declare the type of the variable explicitly; it is inferred from the value assigned to it.

### Example
```python
x = 10  # x is a variable holding the integer value 10
name = "Alice"  # name is a variable holding the string value "Alice"
```

---

## 2. What are the rules for naming variables in Python?

- Variable names must start with a letter (a-z, A-Z) or an underscore (_).
- The rest of the name can include letters, numbers, and underscores.
- Python is case-sensitive, so `variable` and `Variable` are considered different.
- Reserved keywords (e.g., `class`, `def`, `if`, etc.) cannot be used as variable names.

---

## 3. Can you assign a value to a variable in Python without declaring its type?

Yes, in Python, variables are dynamically typed, so you don’t need to declare their type explicitly. When you create a variable and give it a value, the system automatically figures out what kind of thing that variable is.

### Example
```python
x = 5  # 'x' is an integer
x = "Hello"  # Now 'x' is a string
x = 3.14  # Now 'x' is a float
```

---
## 4. What happens if you try to use a variable before it’s assigned a value?

If you try to use a variable before assigning a value to it, Python will raise a `NameError`, indicating that the variable is not defined.

---

## 5. What is a variable’s scope in Python?

A variable's scope refers to the region in the program where a variable is accessible. In Python, there are four types of scopes:

- **Local scope**: Inside a function or block.
- **Enclosing scope**: In the parent function (for nested functions).
- **Global scope**: At the module level (outside all functions).
- **Built-in scope**: The scope of built-in Python functions and exceptions.

Python follows the **LEGB** (Local, Enclosing, Global, Built-in) rule to determine the order in which it looks up variable names.

### Example
```python
x = 10  # Global scope

def foo():
    x = 20  # Local scope to foo
    print(x)  # Prints 20 (local)

foo()
print(x)  # Prints 10 (global)
```

---

## Difference Between Local and Global Variables in Python

### Local Variable
- A local variable is declared inside a function and is only accessible within that function.
- Local variables are created when the function is called and destroyed when the function ends.
- They cannot be accessed outside the function.

### Global Variable
- A global variable is declared outside of any function and is accessible throughout the entire program.
- Global variables exist for the duration of the program's execution.
- They can be accessed and modified from anywhere in the program.

### Example of Local Variable:
```python
def func():
    x = 10  # Local variable
```
---
## 8. How do you check the type of a variable in Python?

You can use the built-in `type()` function to check the type of a variable.

### Example:
```python
x = 10
print(type(x))  # <class 'int'>

y = "Hello"
print(type(y))  # <class 'str'>
```
---

## 9. What happens to a variable’s memory when it is no longer needed?

Python uses automatic memory management, which includes:
- **Garbage collection**: Automatically frees memory by removing objects no longer in use.
- **Reference counting**: Tracks how many references point to an object. When the count drops to zero, the memory is deallocated.

### Example:
```python
x = [1, 2, 3]  # Reference count for the list is 1
y = x  # Reference count increases to 2
del x  # Reference count decreases to 1
del y  # Reference count drops to 0, and the list is deallocated
```

---

## 10. How can you check if a variable is None in Python?

To check if a variable is `None`, use the `is` keyword because `None` is a singleton in Python.

### Example:
```python
x = None
if x is None:
    print("x is None")
else:
    print("x is not None")
```

---

## 11. What is the purpose of the id() function in Python?

The `id()` function returns the identity (a unique memory address) of an object during its lifetime.

### Example:
```python
x = 10
y = 10
print(id(x))  # Memory address of x
print(id(y))  # Likely the same, as integers are immutable
```

---

## 12. What is the global keyword used for in Python?

The `global` keyword in Python is used inside a function to indicate that a variable refers to a variable defined in the global scope (outside the function). It allows you to access and modify the value of a global variable from within a function, rather than creating a new local variable with the same name.

### Example:
```python
x = 10  # Global variable

def modify_global():
    global x  # Refers to the global variable x
    x = 20  # Modifies the global variable

modify_global()
print(x)  # Output: 20
```




