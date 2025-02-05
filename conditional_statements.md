# Conditional Statements in Python

## What is Indentation?
Indentation is an important feature of Python. It is used to define the body of a block such as loops, functions, and conditional statements. **Indentation** refers to the spaces or tabs at the beginning of a line of code, which indicate the structure and grouping of the code.

For example, when using **if statements, loops, or defining functions**, Python requires proper indentation to understand which lines of code belong to a specific block.

## Why is Indentation Important?
- **Organizes the code**: It tells Python which lines of code should run together as a group.  
- **Prevents errors**: If indentation is missing or incorrect, Python will raise an `IndentationError`.  

## Rules of Indentation:
1. **Use spaces, not tabs**: Python prefers using spaces. It’s common to use **4 spaces** for each level of indentation.  
2. **Consistency is key**: All lines inside a block must be indented **the same way**.  

## Example of Correct Indentation:
```python
def greet(name):
    print("Hello, " + name + "!")  # Proper indentation

if True:
    print("This is inside the if block")  # Indented correctly
print("This is outside the if block")  # Not indented, so it runs separately
```

In Python, conditional statements are used to execute different blocks of code based on whether a given condition is true or false. The main conditional statements in Python are:
1. if statement
The if statement allows you to test a condition, If the condition is True, the code block under the if statement is executed. If it's False, that block is skipped.
2. else statement
The else statement is used to define an alternative block of code that will execute if the condition in the if statement is False.
3. elif statement
The elif (short for "else if") statement allows you to check multiple conditions. If the first if condition is False, the elif condition is checked. You can have multiple elif statements, and Python will execute the first one whose condition is True.
4. Nested if statements
You can also nest if, elif, and else statements inside one another.
Boolean expressions in conditions:
Conditions are typically evaluated using comparison operators, like:
== (equal to)
!= (not equal to)
> (greater than)
< (less than)
>= (greater than or equal to)
<= (less than or equal to)
You can also use logical operators:
and (both conditions must be true)
or (at least one condition must be true)
not (inverts the condition)


