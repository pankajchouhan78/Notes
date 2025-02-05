
## What is an Error in Python?
An error in Python is something that goes wrong in the program and stops it from working properly. It can happen because of mistakes in writing the code or unexpected inputs.

### Types of Errors in Python:
```
# Syntax Errors: These occur when the Python parser detects an invalid syntax.
print("Hello World)  # Missing closing quote

# Indentation Errors: These occur when the indentation of the code is incorrect.
if True:
print("Hello")  # Missing indentation

# Name Errors: These occur when you try to use a variable or function name that hasn’t been defined.
print(x)  # x is not defined


# Type Errors: These occur when an operation or function is applied to an object of an inappropriate type.
print("Hello" + 5)  # Cannot add string and integer

# Value Errors: These occur when a function receives an argument of the right type but an inappropriate value.
int("abc")  # Cannot convert a string to an integer

# Index Errors: These occur when you try to access an element at an index that is out of range for a list or string.
my_list = [1, 2, 3]
print(my_list[5])  # Index out of range

# Key Errors: These occur when trying to access a dictionary key that doesn’t exist.
my_dict = {"a": 1}
print(my_dict["b"])  # Key 'b' does not exist

# Attribute Errors: These occur when you try to access an attribute of an object that doesn’t exist.
x = 10
x.append(5)  # int object has no attribute 'append'

# ZeroDivisionError: This occurs when dividing a number by zero.
print(10 / 0)  # Division by zero

```
---

## What is an Exception in Python?
An exception is an error that occurs during the execution of a program and disrupts its normal flow. Unlike syntax errors, exceptions are errors detected during runtime.
### Common Exceptions in Python:
- **ArithmeticError:** Errors like division by zero.
- **FileNotFoundError:** When a file operation (like open) fails because the file does not exist.
- **ImportError:** Raised when an import statement fails to find the module.
- **IndexError:** When accessing a list or tuple out of range.
- **KeyError:** When trying to access a dictionary key that does not exist.

# Difference Between Error and Exception

| **Aspect**            | **Error**                                                                 | **Exception**                                                            |
|-----------------------|---------------------------------------------------------------------------|---------------------------------------------------------------------------|
| **Definition**         | An error is a problem in the program's syntax or logic that prevents it from running. | An exception is a runtime event that disrupts the normal flow of a program. |
| **Can Be Handled?**    | Errors cannot be handled using code.                                      | Exceptions can be handled using `try` and `except` blocks.                |
| **Examples**           | Syntax errors, indentation errors, etc.                                   | `ZeroDivisionError`, `IndexError`, `KeyError`, etc.                       |


## What is exception handling in python?
## How Exception Handled In Python?

In Python, we use try-except blocks to handle errors.
Try: contains the code that might cause issues, and 
Except: specifies what to do if there's a problem. 
Else is for code that runs if everything's fine, and 
finally is for code that always runs."
```
try:
    # Code that may raise an exception
    result = 10 / 0  # This will raise a ZeroDivisionError
except ZeroDivisionError as e:
    # Handle the specific exception
    print(f"Error: {e}")
except Exception as e:
    # Handle other exceptions
    print(f"An error occurred: {e}")
else:
    # Code to execute if no exception occurs
    print("No errors occurred.")
finally:
    # Code that will be executed no matter what
    print("This will always execute.")

# ------------------------------------------------------------------

program:
num1 = 10
num2 = 0

try:
    result = num1/num2
    print(result)
except ZeroDivisionError:
    print("You can't divide by zero!")
print("rest of code")

# ------------------------------------------------------------------

multiple exception handle:
num1 = 10
num2 = 0

try:
    result = num1/num2
    print(result)
    print(re) # name error
except ZeroDivisionError:
    print("You can't divide by zero!")
except NameError:
    print("The variable 're' is not defined.")
    
print("rest of code")

# ------------------------------------------------------------------

num1 = 10
num2 = 0
try:
    result = num1/num2
    print(result)
    print(re) # name error
except (ZeroDivisionError, NameError) as obj:
    print(obj)
else:
    print("not exception")   
finally:
    print("rest of code")
```
---

## how to raise exception:
- **user-defined exception:** aise exceptions hote h jo programmers create karte h.
- **raise keyword:** aise keyword h jiski help se app koi bhi exception ko call kar sakte hai. On particular condition.
```
try:
    age = int(input("enter your age "))
    if age <= 0:
        raise ValueError
    print("your age is ", age)
except ValueError:
    print("please enter valid age")
print("rest of code")

# --------------------------------------------------------------

try:
    age = int(input("enter your age "))
    if age <= 0:
        raise ValueError("Invalid age")
    print("your age is ", age)
except ValueError as e:
    print(e)
print("rest of code")
```

 ## Write a python program for five division exception?
```
class FiveDivisionError(Exception):
    pass
try:
    num1=10
    num2=5
    if num2 == 5:
        raise FiveDivisionError("can-not divide by 5")
    print("division: ",num1/num2)
except FiveDivisionError as e:
    print(e)
print("rest of code")

class FiveDivisionError(Exception):
    def __init__(self):
        print("The number is not divisible by 5")

# --------------------------------------------------------------

try:
    num1=10
    num2=5
    if num2 == 5:
        raise FiveDivisionError
    print("division: ",num1/num2)
except FiveDivisionError as e:
    print(e)
print("rest of code")

# --------------------------------------------------------------

# exception handling with file handling:
try:
    f = open("data.txt", mode='r')
    f.write("hello word") # file is not writeable
except Exception as e:
    print(e)
else:
    f.close()
finally:
    print("rest of code")
```


