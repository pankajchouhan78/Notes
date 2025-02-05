# Python Operator Based Interview Questions and Answers

### Operators
Operators are symbols used to perform operations on operands. Types of operators in Python:

- **Arithmetic Operators**
- **Assignment Operators**
- **Relational and Comparison Operators**
- **Logical Operators**
- **Identity Operators** (`is` or `is not`)
- **Membership Operators** (`in` or `not in`)

---

### 1. What is the difference between the '==' operator and the 'is' operator in Python?
- The `==` operator is used to compare the values of two objects and returns a boolean value (`True` or `False`).
- The `is` operator checks whether two objects refer to the same memory location (i.e., whether they are the same object).

---

### 2. What is the purpose of the '//' operator in Python?
- The `//` operator is the **floor division** operator. It performs division and returns the largest integer that is less than or equal to the result of the division.

---

### 3. What is the purpose of the 'in' operator in Python?
- The `in` operator is used to check if a value exists in a sequence (such as a string, list, or tuple). It returns `True` if the value is present, and `False` otherwise.

---

### 4. How does the 'and' operator work in Python?
- The `and` operator is a logical operator that returns `True` when both conditions are `True`. Otherwise, it returns `False`.

---

### 5. Explain the use of the 'not' operator in Python.
- The `not` operator is a logical operator. It inverts the result of the condition:
  - If the condition is `True`, it returns `False`.
  - If the condition is `False`, it returns `True`.

---

### 6. What is the purpose of the '%' operator in Python?
- The `%` operator is the **modulo** operator. It returns the remainder of the division between two numbers.

---

### 7. How does the 'or' operator work in Python?
- The `or` operator is a logical operator that returns `True` when either one or both conditions are `True`. Otherwise, it returns `False`.

---

### 8. What is the difference between the '+' operator and the '+= 'operator in Python?
- The `+` operator is used to add two numbers or concatenate two strings.
- The `+=` operator is an **assignment** operator that adds the right operand to the left operand and assigns the result to the left operand.

---

### 9. Explain the 'is not' operator in Python.
- The `is not` operator checks whether two objects do not refer to the same memory location. It returns `True` if the objects are different and `False` if they are the same.

---

### 10. Ternary Operator in Python.
- In Python, the ternary operator is a shorthand for writing conditional expressions in a single line.
- It allows you to decide between two expressions based on a condition.

#### Syntax: - value_if_true if condition else value_if_false

### Example Using Ternary Operator:
```python
x = 10
result = "x is greater than 5" if x > 5 else "x is less than or equal to 5"
print(result)  # Output: "x is greater than 5"
```

### This is equivalent to:
```python
x = 10
if x > 5:
    result = "x is greater than 5"
else:
    result = "x is less than or equal to 5"
print(result)  # Output: "x is greater than 5"
```

 # Bitwise Operators in Python

Python mein bitwise operators numbers ke binary representation par kaam karte hain. Yeh operators har bit ko individually manipulate karte hain.

## List of Bitwise Operators:

### 1. `&` (Bitwise AND)
**Explanation:** Yeh operator do numbers ke corresponding bits ko compare karta hai aur tab `1` return karta hai jab dono bits `1` hon, otherwise `0` return karta hai.

**Example:**
```python
5 & 3  # 0101 & 0011 = 0001 (result 1 hai)
```

### 2. `|` (Bitwise OR)
**Explanation:** Yeh operator do numbers ke corresponding bits ko compare karta hai aur tab `1` return karta hai agar kisi bhi ek bit ka value `1` ho.

**Example:**
```python
5 | 3  # 0101 | 0011 = 0111 (result 7 hai)
```

### 3. `^` (Bitwise XOR)
**Explanation:** Yeh operator do numbers ke corresponding bits ko compare karta hai aur tab `1` return karta hai agar dono bits alag hon, otherwise `0` return karta hai.

**Example:**
```python
5 ^ 3  # 0101 ^ 0011 = 0110 (result 6 hai)
```

### 4. `~` (Bitwise NOT)
**Explanation:** Yeh operator ek number ke saare bits ko invert kar deta hai (isey one’s complement bhi keh sakte hain).

**Example:**
```python
~5  # 5 ke bits ko invert kar ke result -6 milta hai
```

### 5. `<<` (Left Shift)
**Explanation:** Yeh operator number ke bits ko left shift karta hai. Har shift se number `2` se multiply ho jata hai.

**Example:**
```python
5 << 2  # 0101 << 2 = 10100 (result 20 hai)
```

### 6. `>>` (Right Shift)
**Explanation:** Yeh operator number ke bits ko right shift karta hai. Har shift se number `2` se divide ho jata hai.

**Example:**
```python
5 >> 2  # 0101 >> 2 = 0001 (result 1 hai)
```

## Bitwise Assignment Operators (Shorthand Notations):

### 7. `&=` (Bitwise AND Assignment)
```python
x = 5
x &= 3  # x = x & 3, result 1 ho jayega
```

### 8. `|=` (Bitwise OR Assignment)
```python
x = 5
x |= 3  # x = x | 3, result 7 ho jayega
```

### 9. `^=` (Bitwise XOR Assignment)
```python
x = 5
x ^= 3  # x = x ^ 3, result 6 ho jayega
```

### 10. `<<=` (Left Shift Assignment)
```python
x = 5
x <<= 2  # x = x << 2, result 20 ho jayega
```

### 11. `>>=` (Right Shift Assignment)
```python
x = 5
x >>= 2  # x = x >> 2, result 1 ho jayega
```

## XOR (Exclusive OR) Operator in Python
Python mein XOR ek logical operator hai jo do boolean values ke beech comparison karta hai. XOR tab `True` hota hai jab dono values alag-alag hoti hain, aur `False` tab hota hai jab dono values same hoti hain.

| A      | B      | A ^ B  |
|--------|--------|--------|
| True   | True   | False  |
| True   | False  | True   |
| False  | True   | True   |
| False  | False  | False  |

### Example:
```python
a = 5   # 0101 in binary
b = 3   # 0011 in binary

result = a ^ b   # 0110 in binary, which is 6 in decimal
print(result)    # Output: 6
```

Yahaan pe `5` (0101) aur `3` (0011) ko XOR kiya gaya hai, aur result `6` (0110) milta hai.
