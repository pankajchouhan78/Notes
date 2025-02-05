# Python Function-based Interview Questions

## What is a function in Python?

A function contains a block of code that is mainly used for code reusability. There are two types of functions:
- **Built-in functions**: These are also known as predefined functions, such as `print()`, `type()`, `input()`, etc.
- **User-defined functions**: These are functions defined by the user to perform a specific task. We define these functions with the help of the `def` keyword.

## What is the purpose of the `pass` statement in Python?

The purpose of the `pass` statement is to avoid syntax errors in situations where the interpreter expects an indented block but you don't want to execute any specific code at that point.

In Python, the pass statement is a placeholder that does nothing. It is used when a statement is syntactically required but you do not want to execute any code. It can be helpful in situations where you are writing a function or class, but you haven't implemented it yet, or when you need to create an empty loop or conditional block.
Here’s how the pass statement is typically used

```python
Example 1: Empty Function
def my_function():
    pass  # Function does nothing yet

Example 2: Empty Class
class MyClass:
    pass  # Class does nothing yet

Example 3: Empty Loop
for i in range(5):
    pass  # Do nothing for now

Example 4: Empty Conditional Block
x = 10
if x > 5:
    pass  # Do nothing when the condition is True
else:
    print("x is 5 or less")
```
### Why use pass?
Stubs for future implementation: You can use pass to indicate that a function or block is intentionally left empty for now, especially when you’re developing a program incrementally.
Syntactical placeholder: In situations like defining minimal classes, handling exceptions, or even defining an empty loop, pass allows you to keep your code syntactically correct without having to add extraneous code.
The key takeaway is that pass is simply a "no-op" (no operation) statement that does nothing when executed, but it satisfies Python's syntactical need for a statement.

## What is `return`?

The **`return`** keyword is used to return a value from a function. It allows a function to return the value that it computes or processes.

## List of Python functions:

- **Input function**: Used to take input from the user at runtime.
- **Len function**: Used to determine the length of an object like a string, list, tuple, etc.
- **Type function**: Used to identify the class type of an object. Example: `print(type(a))`
- **Id function**: Used to find out the memory address of an object. Example: `print(id(a))`
- **Eval function**: Used to evaluate an expression and return its result. `eval()` is a predefined function.
- **Zip function**: Used to combine two lists or tuples into a single object.
- **Random**: A module in Python used to generate random numbers.

## What is a recursive function?

A function that calls itself repeatedly is called a **recursive function**.

## What is the `range` function?

In Python, the **`range()`** function is used to generate a sequence of numbers.

---

# What is a Lambda Function?

A lambda function is a small, anonymous function defined using the `lambda` keyword. It can have any number of arguments but only one expression. Lambda functions are typically used for simple operations and are often used in functional programming constructs like `map()`, `filter()`, and `reduce()`.

## Syntax of Lambda Function:

```python
lambda arguments: expression

# 1. Add Two Numbers
add = lambda x, y: x + y
print(add(5, 3))  # Output: 8

# 2. Square a Number
square = lambda x: x**2
print(square(4))  # Output: 16

# 3. Find the Maximum of Two Numbers
max_num = lambda x, y: x if x > y else y
print(max_num(7, 12))  # Output: 12

# 4. Check if a Number is Even
is_even = lambda x: x % 2 == 0
print(is_even(6))  # Output: True

# 5. Reverse a String
reverse_str = lambda s: s[::-1]
print(reverse_str("hello"))  # Output: "olleh"

# 6. Multiply All Elements in a List by 2
double_elements = lambda lst: [x * 2 for x in lst]
print(double_elements([1, 2, 3, 4]))  # Output: [2, 4, 6, 8]

# 7. Sort a List of Tuples Based on the Second Element
sort_tuples = lambda lst: sorted(lst, key=lambda x: x[1])
print(sort_tuples([(1, 4), (3, 2), (2, 5)]))  # Output: [(3, 2), (1, 4), (2, 5)]

# 8. Generate a List of Squares from 1 to 5
squares = lambda n: [x**2 for x in range(1, n+1)]
print(squares(5))  # Output: [1, 4, 9, 16, 25]

# 9. Calculate the Factorial of a Number
factorial = lambda n: 1 if n == 0 else n * factorial(n - 1)
print(factorial(5))  # Output: 120

```
---
### Difference between Anonymous and Lambda Functions:

An **anonymous function** is a general term for a function that does not have a name. It is defined using the `def` keyword in Python and can contain multiple expressions or statements. These functions are useful when you need a function for a specific task without needing to define it globally.

A **lambda function** is a specific type of anonymous function in Python, defined using the `lambda` keyword. It is limited to a single expression, making it concise and often used for short operations or when passing functions as arguments to other functions like `map()`, `filter()`, or `sorted()`.

#### Key Differences:
- **Anonymous Function**: Defined using the `def` keyword, can have multiple statements and complex logic.
- **Lambda Function**: Defined using the `lambda` keyword, restricted to a single expression.

#### Example:

- **Anonymous function:**
  ```python
  def add(x, y):
      return x + y
  ```
--- 
### Difference between Parameters and Arguments:

#### Key Difference:
- **Parameters** are variables in the function definition.
- **Arguments** are the values supplied to the function when it is called.
  
| **Feature**       | **Parameters**                                             | **Arguments**                                              |
|-------------------|------------------------------------------------------------|------------------------------------------------------------|
| **Definition**    | Placeholders defined in a function's definition.           | Actual values passed to the function when called.           |
| **Where Used**    | Used when defining the function.                           | Used when calling the function.                             |
| **Example**       | In `sum(a, b) { return a + b; }`, `a` and `b` are **parameters**. | In `sum(5, 6);`, `5` and `6` are **arguments**.             |
| **Purpose**       | To specify what values the function expects.               | To provide the values for the function to work with.        |

---

### Recursion in Python

Recursion is a technique where a function calls itself to solve a problem until it reaches a base case. It’s a powerful concept but should be used carefully because excessive recursion can lead to inefficiency or stack overflow errors if the recursion limit is exceeded.

#### Types of Recursion:

1. **Direct Recursion**: When a function calls itself directly.
    ```python
    def factorial(n):
        if n == 0:
            return 1
        return n * factorial(n-1)

    print(factorial(5))  # Output: 120
    ```

2. **Indirect Recursion**: When one function calls another function, and that second function calls the first function again.
    ```python
    def function_a(n):
        if n > 0:
            print(n)
            function_b(n-1)

    def function_b(n):
        if n > 0:
            print(n)
            function_a(n-1)

    function_a(3)
    ```

3. **Tail Recursion**: This occurs when the recursive call is the last operation in the function. Although Python does not optimize for tail recursion, it can still be useful.
    ```python
    def tail_factorial(n, a=1):
        if n == 0:
            return a
        return tail_factorial(n-1, n*a)

    print(tail_factorial(5))  # Output: 120
    ```

#### Python Recursion Limits:
- Python has a default recursion limit of 1000. If the recursion exceeds this limit, a `RecursionError` is raised.
    ```python
    import sys
    print(sys.getrecursionlimit())  # Default: 1000
    sys.setrecursionlimit(2000)  # Increase the limit
    ```

---
## Recursion Examples

1. **Calculating Factorial**

    ```python
    def factorial(n):
        if n == 0:
            return 1
        return n * factorial(n-1)

    print(factorial(5))  # Output: 120
    ```

2. **Finding Fibonacci Sequence**

    ```python
    def fibonacci(n):
        if n <= 1:
            return n
        return fibonacci(n-1) + fibonacci(n-2)

    print(fibonacci(6))  # Output: 8
    ```

3. **Summing Natural Numbers**

    ```python
    def sum_natural(n):
        if n == 1:
            return 1
        return n + sum_natural(n-1)

    print(sum_natural(5))  # Output: 15
    ```

4. **Reversing a String**

    ```python
    def reverse_string(s):
        if len(s) == 0:
            return s
        return reverse_string(s[1:]) + s[0]

    print(reverse_string("hello"))  # Output: "olleh"
    ```

5. **Calculating Power of a Number**

    ```python
    def power(base, exp):
        if exp == 0:
            return 1
        return base * power(base, exp - 1)

    print(power(2, 3))  # Output: 8
    ```

6. **Finding GCD using the Euclidean Algorithm**

    ```python
    def gcd(a, b):
        if b == 0:
            return a
        return gcd(b, a % b)

    print(gcd(48, 18))  # Output: 6
    ```

7. **Summing the Digits of a Number**

    ```python
    def sum_of_digits(n):
        if n == 0:
            return 0
        return n % 10 + sum_of_digits(n // 10)

    print(sum_of_digits(1234))  # Output: 10
    ```

8. **Checking if a String is a Palindrome**

    ```python
    def is_palindrome(s):
        if len(s) <= 1:
            return True
        if s[0] != s[-1]:
            return False
        return is_palindrome(s[1:-1])

    print(is_palindrome("radar"))  # Output: True
    print(is_palindrome("hello"))  # Output: False
    ```

9. **Performing a Binary Search**

    ```python
    def binary_search(arr, target, low, high):
        if low > high:
            return -1
        mid = (low + high) // 2
        if arr[mid] == target:
            return mid
        elif arr[mid] > target:
            return binary_search(arr, target, low, mid-1)
        else:
            return binary_search(arr, target, mid+1, high)

    arr = [1, 2, 3, 4, 5, 6, 7]
    target = 5
    print(binary_search(arr, target, 0, len(arr)-1))  # Output: 4
    ```

10. **Solving the Tower of Hanoi Problem**

    ```python
    def tower_of_hanoi(n, source, target, auxiliary):
        if n == 1:
            print(f"Move disk 1 from {source} to {target}")
            return
        tower_of_hanoi(n-1, source, auxiliary, target)
        print(f"Move disk {n} from {source} to {target}")
        tower_of_hanoi(n-1, auxiliary, target, source)

    tower_of_hanoi(3, 'A', 'C', 'B')
    ```

11. **Flattening a Nested List**

    ```python
    def flatten_list(nested_list):
        flat_list = []
        for item in nested_list:
            if isinstance(item, list):
                flat_list.extend(flatten_list(item))
            else:
                flat_list.append(item)
        return flat_list

    nested = [1, [2, [3, 4], 5], 6]
    print(flatten_list(nested))  # Output: [1, 2, 3, 4, 5, 6]
    ```

12. **Generating Permutations of a String**

    ```python
    def permutations(s, step=0):
        if step == len(s):
            print("".join(s))
        for i in range(step, len(s)):
            s_copy = [char for char in s]
            s_copy[step], s_copy[i] = s_copy[i], s_copy[step]
            permutations(s_copy, step + 1)

    permutations("abc")
    ```

---

These examples showcase common recursion patterns and problems. Let me know if you'd like further explanations or modifications to any of them!


