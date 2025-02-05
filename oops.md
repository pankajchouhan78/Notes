# Object-Oriented Programming (OOP)

Object-oriented programming (OOP) is a programming paradigm. A programming paradigm is a way to arrange a program. Python supports multiple paradigms:

- Procedural-oriented paradigms
- Functional-oriented paradigms
- Object-oriented paradigms

## Procedural-Oriented Paradigms
In procedural-oriented paradigms, we arrange the program in procedures or line by line.

## Functional-Oriented Paradigms
In functional-oriented paradigms, we arrange the Python program in small pieces so we can reuse the code again and again. In functional-oriented paradigms, we reuse the code but can’t solve real-world problems effectively. As a solution, we use the object-oriented paradigm.

## Program
A program can be thought of as a collection of procedures.

## Procedures
A series of instructions to accomplish a task.

## Function
A function is a piece of code.

## What is Object-Oriented Programming?
Object-oriented programming is not a programming language. It’s just a way to arrange a Python program by creating classes and objects.

## Why Object-Oriented Programming?
To solve real-world problems effectively.

## What is OOP?
OOP stands for Object-Oriented Programming, which is a programming paradigm. A programming paradigm is a way to arrange a program by creating classes and objects.

## Why is Python an Object-Oriented Language?
Python is object-oriented because it allows you to store data and methods in a single unit called an object. In Python, everything is treated as an object—be it classes, functions, modules, or data types.

Example of error:
```python
l = [1, 2, 3, 5]
l.upper()  # Error
```

---

## Features of OOP

### Inheritance
Inheritance allows one class to inherit the properties and behaviors (methods) from another class, facilitating code reuse and the creation of hierarchical relationships between classes.

### Encapsulation
Encapsulation is the concept of binding data and methods into a single unit, known as a class. It ensures data security by restricting direct access to some of the object's components and providing controlled access via methods (getters and setters).

### Abstraction
Abstraction involves providing only the necessary details to the user while hiding the complex implementation. This allows the user to interact with objects at a high level without needing to understand their internal workings.

### Polymorphism
Polymorphism allows objects of different classes to be treated as objects of a common superclass. It enables methods to be redefined or overloaded to behave differently based on the object calling them.

## How does OOP differ from procedural programming?

Object-Oriented Programming (OOP) focuses on organizing data and behavior into objects, which model real-world entities. It emphasizes reusability, modularity, and abstraction.

In contrast, procedural programming organizes the program as a sequence of steps or functions that act on data. It typically focuses on performing operations on data, without organizing it into objects.
---

## What is a Class?

A class is a collection of objects. It defines the structure and behavior of objects. Every class has two primary properties:

- **Attributes**: These are variables defined inside the class, which represent the state of an object.
- **Methods**: These are functions defined inside the class, which represent the behavior of an object.

Technically, a class is a user-defined data type.

### Types of Classes

1. **User-defined class**: A class that is created by the programmer to define custom objects and behavior.
2. **Built-in class**: These are predefined classes in Python, such as:
   - `int` (integer)
   - `float` (floating-point number)
   - `str` (string)
   - `list` (list)
   - `tuple` (tuple)
   - `dict` (dictionary)
   - `set` (set)

# Creating Classes and Objects in Python

### Class Naming Convention
- Class names should be written in **Pascal Case** (also known as **Camel Case**), where each word starts with an uppercase letter.
  - **Example**: `CartItem`

### Method Naming Convention
- Method names should be written in **snake_case**, where all words are lowercase and separated by underscores.
  - **Example**: `cart_item`

### Defining a Class
A class in Python is defined using the `class` keyword followed by the class name and a colon. Attributes (variables) and methods (functions) are defined within the class.

```python
class CartItem:
    # Attributes
    def __init__(self, name, price, quantity):
        self.name = name
        self.price = price
        self.quantity = quantity

    # Method
    def total_price(self):
        return self.price * self.quantity
```

## What is an Object?

An object is an instance of a class, representing a real-world entity. It encapsulates data and the methods that operate on that data. In Object-Oriented Programming (OOP), objects are used to model real-life entities such as trees, persons, or mobile phones.

In Python, everything is treated as an object, including classes, functions, modules, and data types. This means that objects can have attributes (data) and methods (functions) associated with them.

### Example:

```python
class Person:
    def __init__(self, name, age):
        self.name = name  # Attribute
        self.age = age    # Attribute

    def greet(self):
        print(f"Hello, my name is {self.name} and I am {self.age} years old.")  # Method

# Creating an object of the Person class
person1 = Person("Alice", 30)
person1.greet()  # Output: Hello, my name is Alice and I am 30 years old.
```
## What is an Instance Variable?
An **instance variable** is a variable whose value is unique to each instance (object) of a class. Each object created from the class has its own copy of the instance variables. These variables are typically defined within the `__init__` method of the class.

- **Example**: 
  - An instance variable will have a different value for each object.
  
```python
class CartItem:
    def __init__(self, name, price, quantity):
        self.name = name  # instance variable
        self.price = price  # instance variable
        self.quantity = quantity  # instance variable

item1 = CartItem("Apple", 1.0, 5)
item2 = CartItem("Banana", 0.5, 10)

print(item1.name)  # Output: Apple
print(item2.name)  # Output: Banana
```

# Class Variable in Python

A **class variable** is a variable that is shared by all instances (objects) of a class. Its value remains the same across all objects of that class. Class variables are defined within the class but outside of any instance methods.

### Key Points:
- The value of a class variable is **the same for all objects**.
- It is defined inside the class, but outside the `__init__` method.
- You can access the class variable using either the class name or an instance of the class.

### Example:

```python
class CartItem:
    tax_rate = 0.05  # class variable

    def __init__(self, name, price, quantity):
        self.name = name
        self.price = price
        self.quantity = quantity

item1 = CartItem("Apple", 1.0, 5)
item2 = CartItem("Banana", 0.5, 10)

print(item1.tax_rate)  # Output: 0.05
print(item2.tax_rate)  # Output: 0.05
print(CartItem.tax_rate)  # Output: 0.05 (Accessed using the class name)
```

---

# Inheritance in Python
**Inheritance: ** Deriving a new class from existing class so that new class inherit all member (atteributes and methods) of existing class is called inheritance.
Inheritance is mainly used for code reuseablity.

### Types of Inheritance:
1. **Single Inheritance**
2. **Multilevel Inheritance**
3. **Hierarchical Inheritance**
4. **Multiple Inheritance**
5. **Hybrid Inheritance**

---

### 1. **Single Inheritance**
In **single inheritance**, there are only two classes: a parent class and a child class. The child class inherits all members (attributes and methods) from the parent class.

**Example:**

```python
class Parent:
    def greet(self):
        print("Hello from Parent")

class Child(Parent):
    pass

child = Child()
child.greet()  # Output: Hello from Parent
```

### 2. **Multilevel Inheritance**
In **multilevel inheritance**, the parent class is inherited by a child class, and that child class is further inherited by another class, forming a chain of inheritance. This allows for a hierarchy where each class in the chain inherits from the one before it.

### Example:
```python
class Grandparent:
    def greet(self):
        print("Hello from Grandparent")

class Parent(Grandparent):
    pass

class Child(Parent):
    pass

# Creating an object of the Child class
child = Child()
child.greet()  # Output: Hello from Grandparent
```

### 3. **Hierarchical Inheritance**
In **hierarchical inheritance**, a single parent class is inherited by two or more child classes. This allows multiple classes to share the same parent class and reuse its methods and attributes.

### Example:
```python
class Parent:
    def greet(self):
        print("Hello from Parent")

class Child1(Parent):
    pass

class Child2(Parent):
    pass

# Creating objects of Child1 and Child2
child1 = Child1()
child2 = Child2()

child1.greet()  # Output: Hello from Parent
child2.greet()  # Output: Hello from Parent
```

### 4. **Multiple Inheritance**
In **multiple inheritance**, a single child class inherits from two or more parent classes. This allows the child class to inherit attributes and methods from multiple parent classes.

### Example:
```python
class Parent1:
    def greet(self):
        print("Hello from Parent1")

class Parent2:
    def say_goodbye(self):
        print("Goodbye from Parent2")

class Child(Parent1, Parent2):
    pass

# Creating an object of the Child class
child = Child()
child.greet()         # Output: Hello from Parent1
child.say_goodbye()   # Output: Goodbye from Parent2
```

### 5. **Hybrid Inheritance**
**Hybrid inheritance** is a combination of two or more types of inheritance. In Python, it typically involves combining **hierarchical inheritance** and **multiple inheritance**. This allows a class to inherit from multiple parent classes, as well as share a common parent with other classes.

### Example:
```python
class Parent:
    def greet(self):
        print("Hello from Parent")

class Parent2:
    def say_goodbye(self):
        print("Goodbye from Parent2")

class Child1(Parent):
    pass

class Child2(Parent2):
    pass

class HybridChild(Child1, Child2):
    pass

# Creating an object of the HybridChild class
hybrid_child = HybridChild()
hybrid_child.greet()        # Output: Hello from Parent
hybrid_child.say_goodbye()  # Output: Goodbye from Parent2
```
### Difference Between Multilevel and Multiple Inheritance

| **Aspect**              | **Multilevel Inheritance**                                           | **Multiple Inheritance**                                           |
|-------------------------|----------------------------------------------------------------------|--------------------------------------------------------------------|
| **Definition**          | In multilevel inheritance, a parent class is inherited by a child class, and that child class is further inherited by a new class, forming a chain. | In multiple inheritance, a single child class inherits from two or more parent classes. |
| **Class Hierarchy**     | There is a chain of inheritance, where one class inherits from another class, and that class inherits from another, and so on. | A child class inherits from two or more independent parent classes. |
| **Example**             | Class A → Class B → Class C                                          | Class A, Class B → Class C                                        |
| **Relationship**        | It forms a linear chain of inheritance.                             | It forms a relationship where one class inherits from multiple parent classes. |
| **Usage**               | Used when you want to create a hierarchy with multiple levels of inheritance. | Used when a class needs to inherit features from multiple parent classes. |

---

### Example of Multilevel Inheritance:
```python
class Grandparent:
    def greet(self):
        print("Hello from Grandparent")

class Parent(Grandparent):
    pass

class Child(Parent):
    pass

child = Child()
child.greet()  # Output: Hello from Grandparent
```

### Aggregation in OOP

**Aggregation** is a concept in object-oriented programming where one class has a reference to another class's objects. It allows a class to access the data or behavior of another class without using inheritance. Aggregation represents a **has-a** relationship between classes, where one class contains or is associated with objects of another class.

Aggregation is **not** a form of inheritance, but it allows one class to use functionality from another class by holding an instance of that class.

### Key Points:
- Aggregation is a **has-a** relationship.
- It allows a class to use the features of another class without inheriting from it.
- The object of the referenced class can exist independently of the class that aggregates it.
- It is different from **composition**, where the lifetime of the contained object is controlled by the container object.

### Example of Aggregation:

```python
class Engine:
    def start(self):
        print("Engine started")

class Car:
    def __init__(self, engine):
        self.engine = engine  # Car "has-a" Engine

    def drive(self):
        self.engine.start()  # Accessing Engine method
        print("Car is driving")

# Creating an object of Engine
engine = Engine()

# Creating an object of Car and passing Engine to it
car = Car(engine)
car.drive()  # Output: Engine started \n Car is driving

# ----------------------------------------------------------

Class dummy:
    Def display(self):
         Print(“display”)
Class demo:
    d1 = dummy()
    Def show(self):
         Print(“show”)
         Self.d1.display()
d = demo()
d.show()
d.d1.display()

```

### The `__init__` Keyword in Python

The `__init__` method in Python is a special method used for initializing newly created objects of a class. It is commonly known as the **constructor**. The constructor is automatically called when an object is created, and it is used to set up initial values for the object's attributes or perform any necessary setup.

### Key Points:
- `__init__` is called automatically when an object of a class is created.
- It is used to **initialize** the object’s attributes.
- The `self` parameter refers to the current instance of the class, which allows the object to access its own attributes and methods.

### Example of `__init__` Method:

```python
class Car:
    def __init__(self, brand, model, year):
        self.brand = brand  # Instance variable
        self.model = model  # Instance variable
        self.year = year    # Instance variable

    def display_info(self):
        print(f"{self.year} {self.brand} {self.model}")

# Creating an object of the Car class
my_car = Car("Toyota", "Corolla", 2020)
my_car.display_info()  # Output: 2020 Toyota Corolla
```


### The `self` Keyword in Python

The `self` keyword in Python is used to refer to the current instance (object) of a class. It is used within instance methods to access or modify the object's attributes and call other methods within the class. When you define methods inside a class, you need to include `self` as the first parameter to bind the method to the instance of the class.

Self is a key word which is mainly used to point current class instants. With this keyword, we can access the attributes and methods of the class in python. it binds the attributes with the given arguments.

### Key Points:
- `self` refers to the current instance of the class.
- It allows access to the instance’s attributes and methods.
- `self` is automatically passed by Python when you call a method on an object.

### Example of `self` Keyword:

```python

In other word self is a variable which contain the memory address of current object.
class test:
    a=5 # class variable
    b=3
    def __init__(self, a):
        self.a = a # here a is instance varible or object
        
t = test(6) # here automatically __init__() method call hogi. then a ko value six assign hoga and self ko address t variable 
print(t.a)


# -------------------------------------------------

class Test:
    a = 5  # Class variable
    b = 3  # Class variable

    def __init__(self, a):
        self.a = a  # Instance variable, binds the argument to the object

# Creating an object of the Test class
t = Test(6)  # The __init__() method is automatically called
print(t.a)    # Output: 6
```

### Constructor in Python
Constructor is special method in python classes. Constructor is unique function that gets called automatically when an object is created of a class.

A **constructor** is a special method in Python classes. It is used to initialize the object's attributes and set up necessary values when an object of a class is created. The constructor is automatically called when an object is instantiated. It is a unique method that has the same name as the class and is used to initialize the object's state.

In Python, the constructor is defined by the `__init__` method. This method is called automatically when an object is created.

### Types of Constructors:

1. **Non-Parameterized Constructor**: A constructor that does not accept any arguments other than `self` is known as a non-parameterized constructor.
   
2. **Parameterized Constructor**: A constructor that accepts parameters other than `self` is known as a parameterized constructor. It allows initializing the object with values provided during instantiation.

3. **Default Constructor**: If no constructor is defined in the class, Python automatically creates a default constructor that does not perform any specific initialization.

### Example of Constructors:
```python
# Non parameterized constructor:
class Fruits:
    def __init__(self):
        print ("non-parameterized constructor")
        self.foverite = "Orange"
f = Fruits ()
print (f.foverite) # Orange

# ---------------------------------------------------

# Parameterized constructor
class Emp:
    def __init__ (self, name, sal):
        self.name = name
        self.sal = sal
e = Emp ("panakj", 100000)
print ('name is:',e.name)
print ('sal is:',e.sal)
print(e.__dict__) # it will print content of objects in dictionary.

# ---------------------------------------------------

# Default constructor:
class Student:
    pass

s = Student () # object ko create karne ke liye constructor ki jarrurat hoti hai without constructor hum object nahi bana sakte hai.
print(s.__dict__) # Output {} beacuse default constructor empty hota hai.

```

### Constructor Overloading in Python

**Constructor Overloading** refers to defining multiple constructors with the same name but different parameters. However, Python does not support **constructor overloading** in the same way as some other languages like Java or C++. If you define multiple `__init__` methods with the same name in a class, the last one will overwrite the previous ones.

Here’s an example of what **constructor overloading** might look like in other languages:

```python
class Calculator:
    def __init__(self, a):
        print('Cube is:', a**3)

    def __init__(self, a, b):
        print("Addition is:", a + b)

# Uncommenting the below line will raise an error because the second constructor will overwrite the first one.
# c = Calculator(10)  # Error

c = Calculator(10, 20)  # Output: Addition is: 30
```
### Achieving Constructor Overloading using `*args` and `**kwargs` in Python

In Python, we can achieve constructor overloading by using `*args` (non-keyword arguments) and `**kwargs` (keyword arguments). This allows us to pass a variable number of arguments to the constructor and handle different cases within the same constructor.

#### Example:

```python
class Calculator:
    def __init__(self, *args):
        if len(args) == 1:
            print('Cube is:', args[0]**3)
        elif len(args) == 2:
            print("Addition is:", args[0] + args[1])
        else:
            print("Invalid number of arguments")

# Creating objects with different numbers of arguments
c1 = Calculator(10)         # Output: Cube is: 1000
c2 = Calculator(10, 20)     # Output: Addition is: 30
c3 = Calculator(10, 20, 30) # Output: Invalid number of arguments
```

### Understanding `*args` and `**kwargs` in Python

`*args` and `**kwargs` are special keywords in Python that allow functions to accept variable-length arguments. They make functions flexible when we don’t know exactly how many arguments will be passed to them.

### Difference between `*args` and `**kwargs`

| **Feature**               | **`*args`**                               | **`**kwargs`**                            |
|---------------------------|-------------------------------------------|-------------------------------------------|
| **What it does**           | Allows you to pass multiple values (non-keyword) to a function. | Allows you to pass multiple key-value pairs to a function. |
| **How to use**             | Use `*args` in the function definition. | Use `**kwargs` in the function definition. |
| **What it stores**         | A list of values (like a tuple).         | A dictionary with key-value pairs.        |
| **Example**                | `def add(*args):`                         | `def show_info(**kwargs):`                |
| **Accessing the values**   | You access values using their position (index). | You access values using their names (keys). |
| **When to use**            | When you don't know how many values will be passed. | When you don’t know how many key-value pairs will be passed. |

#### Example with `*args`:
```python
def add(*args):
    return sum(args)

result = add(10, 20, 30)  # Output: 60
```
#### Example with `*kargs`:
```python
def show_info(**kwargs):
    for key, value in kwargs.items():
        print(f"{key}: {value}")

result = show_info(name="John", age=30)  
# Output:
# name: John
# age: 30
```

Automatic Memory Management: Python is dynamically-typed language, means we don’t need to declare type of variable python interpretor automatically detect variable class type.
Garbage Collection: Python me automatic garbage collection hoti hai. Iska matlab hai ki jab kisi object ka reference count zero ho jata hai, to Python ka garbage collector us memory ko free kar deta hai.
Reference Counting: Python me har ek object ke sath ek reference count hota hai jo batata hai ki kitne references us object ko point kar rahe hain. Jab reference count zero ho jata hai, to memory release ho jati hai.

---

# Python: Interpreted or Compiled?

Python is primarily an interpreted language, but it actually uses a combination of both compilation and interpretation processes. Here’s a breakdown of how Python works behind the scenes:

## Source Code to Bytecode (Compilation Phase)
When you run a Python script, the Python interpreter first compiles the source code (`.py` files) into an intermediate form known as **bytecode**. This bytecode is platform-independent and is stored in `.pyc` files, typically found in the `__pycache__` directory. This compilation step happens automatically and is different from languages like C/C++, where you explicitly compile the code before running it.

## Execution by Python Virtual Machine (PVM)
Once the source code is compiled into bytecode, the **Python Virtual Machine (PVM)** steps in. The PVM acts as an interpreter that reads the bytecode and executes it line by line. The PVM is the heart of the Python runtime, and it handles all aspects of executing the bytecode, including memory management, variable scope, and handling dynamic types.

Unlike traditional compilers that directly convert source code into machine code (which the CPU can run), Python compiles the code into bytecode, which is not directly executable by the CPU.

The bytecode is interpreted by the PVM, making Python a highly portable language, meaning the same bytecode can run on different platforms (Windows, Linux, etc.) without modification.

---

## Python Interpreter aur Compiler ke Beech Ka Antar

Python mainly ek interpreted language hai, lekin actually yeh dono, compilation aur interpretation ka combination use karta hai. Iska process kuch detail mein aise hai:

### Source Code se Bytecode (Compilation Phase)
Jab aap Python ka koi script run karte ho, toh Python interpreter pehle us source code ko ek intermediate form mein convert karta hai, jise **bytecode** kehte hain. Yeh bytecode platform-independent hota hai aur `.pyc` files mein store hota hai, jo `__pycache__` folder mein milta hai. Yeh compilation step automatically hota hai, alag se compile karne ki zarurat nahi hoti jaise C ya C++ mein hoti hai.

### Python Virtual Machine (PVM) dwara Execution
Jab source code bytecode mein convert ho jata hai, tab **Python Virtual Machine (PVM)** use karta hai. PVM ek interpreter ki tarah bytecode ko line-by-line padhta hai aur execute karta hai. PVM Python ka main part hota hai jo memory management, variable scope, aur dynamic types ko handle karta hai.

Traditional compilers jaise C/C++ mein source code ko directly machine code mein convert kiya jata hai, jo CPU run kar sakta hai, lekin Python pehle bytecode banata hai jo CPU directly nahi samajh sakta.

Fir bytecode ko PVM interpret karta hai, jiski wajah se Python ek portable language hai, matlab ek hi bytecode different platforms (Windows, Linux, etc.) par bina change ke chal sakta hai.

---

# Python: Interpreted or Compiled?

Python is primarily an interpreted language, but it actually uses a combination of both compilation and interpretation processes. Here’s a breakdown of how Python works behind the scenes:

## Source Code to Bytecode (Compilation Phase)
When you run a Python script, the Python interpreter first compiles the source code (`.py` files) into an intermediate form known as **bytecode**. This bytecode is platform-independent and is stored in `.pyc` files, typically found in the `__pycache__` directory. This compilation step happens automatically and is different from languages like C/C++, where you explicitly compile the code before running it.

## Execution by Python Virtual Machine (PVM)
Once the source code is compiled into bytecode, the **Python Virtual Machine (PVM)** steps in. The PVM acts as an interpreter that reads the bytecode and executes it line by line. The PVM is the heart of the Python runtime, and it handles all aspects of executing the bytecode, including memory management, variable scope, and handling dynamic types.

Unlike traditional compilers that directly convert source code into machine code (which the CPU can run), Python compiles the code into bytecode, which is not directly executable by the CPU.

The bytecode is interpreted by the PVM, making Python a highly portable language, meaning the same bytecode can run on different platforms (Windows, Linux, etc.) without modification.

---

## Python Interpreter aur Compiler ke Beech Ka Antar

Python mainly ek interpreted language hai, lekin actually yeh dono, compilation aur interpretation ka combination use karta hai. Iska process kuch detail mein aise hai:

### Source Code se Bytecode (Compilation Phase)
Jab aap Python ka koi script run karte ho, toh Python interpreter pehle us source code ko ek intermediate form mein convert karta hai, jise **bytecode** kehte hain. Yeh bytecode platform-independent hota hai aur `.pyc` files mein store hota hai, jo `__pycache__` folder mein milta hai. Yeh compilation step automatically hota hai, alag se compile karne ki zarurat nahi hoti jaise C ya C++ mein hoti hai.

### Python Virtual Machine (PVM) dwara Execution
Jab source code bytecode mein convert ho jata hai, tab **Python Virtual Machine (PVM)** use karta hai. PVM ek interpreter ki tarah bytecode ko line-by-line padhta hai aur execute karta hai. PVM Python ka main part hota hai jo memory management, variable scope, aur dynamic types ko handle karta hai.

Traditional compilers jaise C/C++ mein source code ko directly machine code mein convert kiya jata hai, jo CPU run kar sakta hai, lekin Python pehle bytecode banata hai jo CPU directly nahi samajh sakta.

Fir bytecode ko PVM interpret karta hai, jiski wajah se Python ek portable language hai, matlab ek hi bytecode different platforms (Windows, Linux, etc.) par bina change ke chal sakta hai.

---

# Polymorphism in Python

Polymorphism means "having many forms." In Python, if a variable, object, or method performs different behaviors according to the situation, it is called polymorphism.

## Types of Polymorphism in Python:
1. **Compile-time polymorphism (Static Binding)**
2. **Runtime polymorphism (Dynamic Binding)**

### Compile-time Polymorphism (Method Overloading)
Python does not support traditional method overloading like other languages (e.g., Java or C++). However, we can achieve similar behavior using default arguments or variable-length arguments.

Example:
```python
class Addition:
    def add(self, x, y, z=0):
        return x + y + z

obj = Addition()
print(obj.add(5, 10))  # Output: 15
print(obj.add(5, 10, 20))  # Output: 35
```

### Runtime Polymorphism (Method Overriding)
Method overriding occurs when a subclass provides a specific implementation of a method already defined in its superclass.

Example:
```python
class Animal:
    def speak(self):
        pass

class Dog(Animal):
    def speak(self):
        print("Woof")

class Cat(Animal):
    def speak(self):
        print("Meow")

d = Dog()
c = Cat()

d.speak()  # Output: Woof
c.speak()  # Output: Meow
```

### Real-life Example of Polymorphism
A simple and short real-life example of polymorphism is a **remote control**. A remote control can be used to operate various electronic devices like televisions, DVD players, and sound systems.

- **Base class** – `RemoteControl`: The base class `RemoteControl` defines common methods like `power_on()`, `power_off()`, and `change_volume()`.
- **Derived classes** – `TVRemote`, `DVDRemote`, `SoundSystemRemote`: These subclasses override the common methods to function specifically for their respective devices.

Example:
```python
class RemoteControl:
    def power_on(self):
        pass
    
    def power_off(self):
        pass

class TVRemote(RemoteControl):
    def power_on(self):
        print("Turning on the TV")
    
    def power_off(self):
        print("Turning off the TV")

class DVDRemote(RemoteControl):
    def power_on(self):
        print("Turning on the DVD Player")
    
    def power_off(self):
        print("Turning off the DVD Player")

tv = TVRemote()
dvd = DVDRemote()

tv.power_on()  # Output: Turning on the TV
dvd.power_on()  # Output: Turning on the DVD Player
```

# What is Operator Overloading & Dunder Methods

**Operator Overloading** ka matlab hota hai ki aap ek operator ko multiple behaviors assign kar sakte hain, depending on the operands.

## Dunder Methods (Double Under Methods)

Dunder Methods, jise **magic methods** bhi kaha jata hai, wo methods hote hain jo humare object banane par automatically call ho jati hain. Python mein yeh special methods hoti hain jo double underscores se shuru hoti hain (e.g., `__add__`, `__str__`, `__init__`, etc.).

### `__init__`: Constructor Method
Yeh method object ko initialize karne ke liye use hoti hai.

### `__str__`: Magic Function
Yeh automatically call hota hai jab hum apne class object ko `print()` function ke andar likhte hain.

```python
class Example:
    def __str__(self):
        return "hello world"

e = Example()
print(e)  # Output: hello world
```

### `__add__`: Addition operator (+) ke liye custom behavior define karta hai.
```python
Edit
class Vector:
    def __init__(self, x, y):
        self.x = x
        self.y = y
        
    def __add__(self, other):
        return Vector(self.x + other.x, self.y + other.y)
        
    def __str__(self):
        return f"Vector({self.x}, {self.y})"

v1 = Vector(2, 3)
v2 = Vector(4, 5)
v3 = v1 + v2
print(v3)  # Output: Vector(6, 8)
```
### Other Operator Overloading Methods:
Similar dunder methods exist for other operators:

- Subtraction: __sub__
- Multiplication: __mul__
- Division: __truediv__
---

# Super Function in Python

**Super function:**  
`super` is a special function in Python. With the help of the `super` function, we can access the properties of the parent class from the child class. This makes inheritance more manageable.

## Example

```python
class Parent:
    def show(self):
        print("show from parent")

class Child(Parent):
    def show(self):
        super().show()
        print("show from child")

c = Child()
c.show()  # Output:
         # show from parent
         # show from child
```

---

## What is method overloading and method overriding?
**Method overloading:** Method overloading refers to having multiple methods with the same name but different parameters. Python does not directly support method overloading, but we can achieve it by using default parameters or variable-length argument lists.

---
**Method overriding:** Method overriding occurs when a child class provides a specific implementation of a method that is already defined in its parent class. This allows the child class to change or extend the behavior of the inherited method

```python
# for method overloading
class calculator:
    def add(self,a,b=0):
        return a+b

c=calculator ()
print ("add:", c.add (15)) 
print ("add:", c.add (15+15)) 
--------------------------------------------------
# for method overriding
class vehicle:
    def speed(self):
        pass


class bike(vehicle):
    def speed(self):
        return "100km/hr"
    
class car(vehicle):
    def speed(self):
        return "150km/hr"


b= bike ()
c= car ()


print ("speed of bike is : ",b.speed())
print ("speed of car is : ",c.speed())
```
---

# Encapsulation in Python

## What is Encapsulation?

**Encapsulation** is the concept of binding the data (attributes) and methods (functions) into a single unit, which is typically a class in Python. The goal is to restrict the access to certain components and prevent the modification of internal data from outside the class. 

In simpler terms, encapsulation allows us to combine the properties and methods related to a class into a single entity. It also enables restricting access to those properties or methods to control how the data is accessed or modified.

---

## Example: Problem Domain

In the following example, the name of the employee is directly accessible, but we want to restrict access to it outside the class. We can achieve this through encapsulation.

### Code Example (Without Encapsulation)

```python
class Emp:
    def __init__(self, nam):
        self.name = "Pankaj"  # Name is set directly

    def display(self):
        print(self.name)

e = Emp()
e.display()  # Output: Pankaj
print(e.name)  # Output: Pankaj (Accessing the name directly)
```

## Achieving Encapsulation
Encapsulation can be achieved by declaring the data members and methods of the class as private. Private members are typically indicated by prefixing them with an underscore (_) or a double underscore (__) to make it harder to access them directly from outside the class.

Code Example (With Encapsulation)
```python

class Emp:
    def __init__(self, nam):
        self.__name = "Pankaj"  # Private attribute

    def display(self):
        print(self.__name)

e = Emp()
e.display()  # Output: Pankaj
# print(e.__name)  # This will raise an AttributeError: 'Emp' object has no attribute '__name'
In this case, __name is a private attribute, and it cannot be accessed directly from outside the class. This ensures that the internal state of the object is protected and can only be modified or accessed through defined methods, promoting data safety and integrity.

```
---

# Access Modifiers in Python

In Python, there are three main types of access modifiers that control the visibility and accessibility of class attributes and methods:

- **Public**: Accessible anywhere using the object reference. By default, all attributes and methods in a Python class are public.
- **Private**: Accessible only within the class. We cannot access private members from outside the class.
- **Protected**: Accessible within the class and its subclasses.

---

## Example: Access Modifiers

### Code Example

```python
class Example:
    a = 10  # Public attribute
    __b = 20  # Private attribute
    _c = 30  # Protected attribute

e = Example()

# Public attribute can be accessed directly
print(e.a)  # Output: 10

# Private attribute cannot be accessed directly, will raise an AttributeError
# print(e.__b)  # Uncommenting this will raise: AttributeError: 'Example' object has no attribute '_Example__b'

# Protected attribute can be accessed directly, but it's meant to be used within the class or subclass
print(e._c)  # Output: 30

# Accessing private attribute by name mangling (not recommended, just for demonstration)
print(e._Example__b)  # Output: 20 (This works due to Python's name mangling)
```

---

# Data Abstraction in Python

**Data Abstraction** is the concept of providing only the essential details to the user and hiding the internal implementation complexities. In Python, this is achieved using **Abstract Classes** and **Abstract Methods**.

## Abstract Classes and Methods

- **Abstract Class**: A class that cannot be instantiated on its own and serves as a blueprint for other classes. It can contain both abstract methods (methods without implementation) and concrete methods (methods with implementation).

- **Abstract Method**: A method that is declared but contains no implementation. Subclasses of the abstract class are required to implement these abstract methods.

## Implementing Data Abstraction

To implement data abstraction in Python, we use the `abc` (Abstract Base Class) module, which provides the infrastructure for defining abstract base classes.

### Example: Abstract Class with Abstract Method

```python
from abc import ABC, abstractmethod

class Bank(ABC):
    def database(self):
        print("Connected to database")

    @abstractmethod
    def security(self):
        pass

# b = Bank()  # This will raise an error: Can't instantiate abstract class Bank with abstract method security
```

In this example, Bank is an abstract class with an abstract method security. Attempting to instantiate Bank directly will raise an error because it contains an abstract method without implementation.

Implementing Abstract Methods in Subclasses
Subclasses of an abstract class must implement all abstract methods to be instantiated.

```python
class User(Bank):
    def user_login(self):
        print("User login")

    def security(self):
        print("Security measures implemented")

u = User()
u.database()  # Output: Connected to database
u.user_login()  # Output: User login
u.security()  # Output: Security measures implemented
```
Here, User is a subclass of Bank that provides implementations for the abstract method security and adds a new method user_login. Now, we can create an instance of User and access its methods.

Preventing Instantiation of Abstract Classes
To prevent the creation of objects from a class that should not be instantiated, we can define an abstract method without implementation.

### Problem Domain
```python
class Computer:
    def process(self):
        pass

c = Computer()  # This will raise an error: Can't instantiate abstract class Computer with abstract method process
```
In this case, Computer is an abstract class with an abstract method process. Attempting to create an instance of Computer directly will raise an error because it contains an abstract method without implementation.

```python
from abc import ABC, abstractmethod

class Computer(ABC):
    @abstractmethod
    def process(self):
        pass

# c = Computer()  # This will raise an error: Can't instantiate abstract class Computer with abstract method process
```
By importing ABC and using the @abstractmethod decorator, we define Computer as an abstract class with an abstract method process. This ensures that Computer cannot be instantiated directly, enforcing that any subclass must implement the process method.

### Conclusion
Data abstraction in Python allows us to define abstract classes and methods, providing a clear blueprint for subclasses and ensuring that certain methods are implemented in derived classes. This approach enhances code modularity and maintainability.

---

# What is Decorator? Explain With Example.
A Decorator is a special function that takes another function as an argument, add some kind of functionalities and then returns another function.
Decorators ka upayog humare functions ko modify karne ke liye hota hai bina unke core logic ko directly change kiye.

Hum decorators ka use karke ek specific functionality ko alag-alag functions mein baar-baar use kar sakte hain, isse hamara code maintainable hota hai.

### Let’s see an example of decorator:
```python
def my_decorator(func):
    def wrapper():
        print("something happens before the function is called")
        func()
        print("something happens after the function is called")
    return wrapper  # we should return the wrapper function

# Applying the decorator using @
@my_decorator
def say_hello():
    print("hello everyone")

# Calling the decorated function
say_hello()
# output:
# something happens before function is called
# hello everyone
# something happens after function is called
```

- In this example, humne ek decorator my_decorator define kiya hai, jo ek function func ko ek argument ke roop mein leta hai. 
- Decorator ke andar humne ek nested function wrapper define kiya hai, jo original func ko call karne se pehle aur baad mein some extra behavior ko add karta hai. 
- func parameter: Ye parameter woh function hai jisko hum modify kar rahe hain. Yahan, func mein add function aayega.
- wrapper ka kaam hai say_hello function ko chalane se pehle aur baad mein kuch extra kaam karna.
- @my_decorator line: Is line se say_hello function ko @my_decorator decorator se modify kiya gaya hai. Iska matlab hai ab jab bhi say_hello function ko call karenge, toh pehle my_decorator ka code chalega.

```python
# Another example of decorator:
def log_function_call(func):
    def wrapper(*args, **kwargs):
        print(f"Calling function {func.__name__} with args {args} and kwargs {kwargs}")
        result = func(*args, **kwargs)
        print(f"{func.__name__} returned {result}")
        return result
    return wrapper

@log_function_call
def add(a, b, c=2):
    return a + b

result = add(2, 3)

# output:
Calling function add with args (2, 3) and kwargs {}
add returned 5
```
Imagine aapko har ek function ka execution time measure karna hai. Instead of manually adding time measurement code to each function, aap ek decorator ka use kar sakte hain:

```python
import time

# Decorator definition
def performance_decorator(func):
    def wrapper(*args, **kwargs):
        start_time = time.time()
        result = func(*args, **kwargs)
        end_time = time.time()
        print(f"Function {func.__name__} took {end_time - start_time} seconds to execute.")
        return result
    return wrapper

# Using the decorator
@performance_decorator
def slow_function():
    time.sleep(2)
    print("Function executed.")

@performance_decorator
def fast_function():
    print("Function executed quickly.")

# Calling the decorated functions
slow_function()
fast_function()
```
---

# Generators and Iterators in Python

In Python, both **iterators** and **generators** are used to iterate over sequences, but they differ in their implementation and use cases.

## Iterators

**Definition:**  
An **iterator** is an object that allows traversing through a sequence of data without storing the entire sequence in memory. It implements two essential methods:

- `__iter__()`: Returns the iterator object itself.
- `__next__()`: Returns the next item in the sequence.

**Example: Custom Iterator**

```python
class MyIterator:
    def __init__(self, start, end):
        self.current = start
        self.end = end

    def __iter__(self):
        return self

    def __next__(self):
        if self.current >= self.end:
            raise StopIteration
        self.current += 1
        return self.current - 1

for number in MyIterator(1, 5):
    print(number)
```

## Generators:

A generator is a special type of iterator defined using a function with the yield keyword. Generators are more concise and memory-efficient than custom iterators, as they yield items one at a time and only when required.

### Example: Generator Function

```python
def my_generator(start, end):
    current = start
    while current < end:
        yield current
        current += 1

for number in my_generator(1, 5):
    print(number)
```


### Key Differences Between Iterators and Generators

**Iterator**: Requires defining a class with __iter__() and __next__() methods.
**Generator**: Defined using a function with the yield keyword.
#### Memory Efficiency:

**Iterator**: Can be memory-intensive if the sequence is large, as it may store the entire sequence in memory.
**Generator**: More memory-efficient, as it yields one item at a time and doesn't store the entire sequence.
Use Cases:

#### Iterator: Suitable for custom iteration logic where more control is needed.
**Generator**: Ideal for simple iteration patterns, especially when dealing with large datasets or streams.
**Example**: Using Generators for Large Data Processing
Generators are particularly useful when working with large datasets, as they allow processing data without loading the entire dataset into memory.

### Example: Processing Large File Line by Line

```python
def process_large_file(file_path):
    with open(file_path, 'r') as file:
        for line in file:
            yield line.strip()

for line in process_large_file('large_file.txt'):
    # Process each line
    print(line)
```
In this example, process_large_file is a generator that reads and processes a large file line by line, ensuring that only one line is in memory at a time.

---

# Custom Iterators in Python

In Python, you can create custom iterators by defining a class that implements the `__iter__()` and `__next__()` methods. This allows you to define how iteration over instances of your class should behave.

## Implementing a Custom Iterator

Here's an example of a custom iterator that generates a sequence of numbers from 0 to 10:

```python
class MakeSeries:
    def __init__(self):
        self.a = 0

    def __iter__(self):
        self.a = 0
        return self

    def __next__(self):
        if self.a > 10:
            raise StopIteration
        self.a += 1
        return self.a

# Usage
m = MakeSeries()
it = iter(m)
print(next(it))  # Output: 1
print(next(it))  # Output: 2
# ...
# After 10 iterations, StopIteration will be raised
```


## Generator ka upayog karke pehle 10 Fibonacci numbers print karne ke liye
```python
def fibonacci_generator(n):
    a, b = 0, 1
    count = 0
    while count < n:
        yield a
        a, b = b, a + b
        count += 1


fib_gen = fibonacci_generator(10)
for num in fib_gen:
    print(num)


# Output:
# 0 1 1 2 3 5 8 13 21 34
```

Is udaharan mein, humne ek generator function `fibonacci_generator` define kiya hai. Ye generator `n` tak ke Fibonacci sequence ko calculate aur yield karta hai. Ye ek saath saare numbers return nahi karta, balki `yield` keyword ka upayog karke har ek number ko ek ek karke produce karta hai.

Jab hum `fibonacci_generator(10)` ko call karke generator object `fib_gen` banate hain, to ye turant poora Fibonacci sequence calculate nahi karta hai. Balki, ye ek iterator object create karta hai jo hum `for` loop ki madad se iterate karte hain. `for` loop har iteration ke liye generator ka `__next__()` method implicit roop se call karta hai, jisse generator function wahan se chhod diya jata hai aur agla Fibonacci number yield kiya jata hai jab tak count `n` tak pahunchta hai.

Generators bade datasets ya infinite sequences ke saath kaam karne ke liye faydemand hote hain kyun ki ve sirf jarurat padne par hi values ko generate karte hain aur memory ko bachate hain.


## What is the usage of yield keyword in Python?
The yield keyword is used in Python to define generators. Generators are a special type of function that allow the programmer to return values one at a time, rather than returning all values at once. This can be useful when working with large data sets, as it allows the programmer to process the data one piece at a time, rather than having to load the entire data set into memory at once.

---

Map, Filter, and Reduce Functions in Python

In Python, the map, filter, and reduce functions are powerful tools that facilitate functional programming paradigms. They allow for concise and efficient processing of iterables.

## Map Function

The map function applies a specified function to each item in an iterable (such as a list, tuple, or string) and returns a new iterator with the results.
```python

map(function, iterable)
Example: Doubling Numbers in a List

# Function to double a number
def double(x):
    return x * 2

numbers = [1, 2, 3, 4, 5]
doubled_numbers = map(double, numbers)

# Convert the map object to a list
doubled_numbers_list = list(doubled_numbers)
print(doubled_numbers_list)  # Output: [2, 4, 6, 8, 10]
Using Lambda Functions with Map

numbers = [1, 2, 3, 4, 5]
doubled_numbers = list(map(lambda x: x * 2, numbers))
print(doubled_numbers)  # Output: [2, 4, 6, 8, 10]
```

### Example of map function:
```python
# 1. Doubling numbers in a list:
numbers = [1, 2, 3, 4, 5]
doubled_numbers = list(map(lambda x: x * 2, numbers))
print(doubled_numbers)

# 2. Converting a list of names to uppercase:
names = ["Alice", "Bob", "Charlie"]
uppercase_names = list(map(str.upper, names))
print(uppercase_names)

# 3. Calculating the square of numbers in a list:
numbers = [1, 2, 3, 4, 5]
squared_numbers = list(map(lambda x: x**2, numbers))
print(squared_numbers)

# 4. Mapping strings to their lengths:
words = ["apple", "banana", "cherry"]
word_lengths = list(map(len, words))
print(word_lengths)

# 5. Converting Fahrenheit temperatures to Celsius:
fahrenheit_temperatures = [32, 68, 95, 104]
celsius_temperatures = list(map(lambda f: (f - 32) * 5/9, fahrenheit_temperatures))
print(celsius_temperatures)
```
---

## Filter Function:
The filter function is another built-in function in Python that operates on iterables. It filters elements from an iterable based on a function that returns either True or False for each element. The filter function returns an iterator containing the elements for which the function returns True.
Syntax:
Filter (function, iterable)

### Example:
# Function to check if a number is even
```python
def is_even (x):
    return x % 2 == 0

numbers = [1, 2, 3, 4, 5, 6, 7, 8]
even_numbers = filter (is_even, numbers)

# Convert the filter object to a list
even_numbers_list = list(even_numbers)

print(even_numbers_list)
```

Is code me `filter` function `is_even` function ko `numbers` list ke har element par apply karta hai aur un elements ko filter karke ek filter object return karta hai. Fir, hum `list()` function ka use karke filter object ko list me convert kar lete hain.

### Examples of filter function:
```python
# 1. Filtering even numbers from a list:
numbers = [1, 2, 3, 4, 5, 6, 7, 8]
even_numbers = list (filter (lambda x: x % 2 == 0, numbers))
print(even_numbers)

# 2. Filtering words with more than 5 characters from a list:
words = ["apple", "banana", "cherry", "date", "fig"]
long_words = list(filter(lambda word: len(word) > 5, words))
print(long_words)

# 3. Filtering positive numbers from a list:
numbers = [-2, 0, 5, -8, 10, -3]
positive_numbers = list(filter(lambda x: x > 0, numbers))
print(positive_numbers)

# 4. Filtering students who passed an exam (grades >= 50):
grades = [85, 42, 67, 58, 90]
passed_students = list(filter(lambda grade: grade >= 50, grades))
print(passed_students)

# 5. Filtering names starting with 'A' from a list:
names = ["Alice", "Bob", "Anna", "Alex", "Charlie"]
a_names = list(filter(lambda name: name.startswith('A'), names))
print(a_names)

```
---
## Reduce Function:

The reduce function is another built-in function in Python, but it is not available directly in the global namespace. You need to import it from the functools module. The purpose of reduce is to apply a binary function cumulatively to the items of an iterable, from left to right, reducing the iterable to a single accumulated result.

### Binary function: a function that takes two arguments.
```python
from functools import reduce
reduce (function, iterable)

Example:
from functools import reduce
# Function to add two numbers
def add (x, y):
    return x + y

numbers = [1, 2, 3, 4, 5]
result = reduce (add, numbers)
print(result)
```

Is code me `reduce` function `add` function ko `numbers` list ke elements par apply karta hai aur unhe combine karke ek single result generate karta hai.

### Examples of `reduce` function:
```python
# 1. Calculating the sum of numbers in a list:
numbers = [1, 2, 3, 4, 5]
sum_result = reduce (lambda x, y: x + y, numbers)
print(sum_result)

# 2. Finding the maximum value in a list:
numbers = [43, 12, 67, 89, 54]
max_value = reduce (lambda x, y: x if x > y else y, numbers)
print(max_value)

# 3. Concatenating strings in a list:
words = ["Hello", ", ", "world", "!"]
sentence = reduce (lambda x, y: x + y, words)
print(sentence)

# 4. Calculating the product of numbers in a list:
numbers = [2, 3, 4, 5]
product_result = reduce (lambda x, y: x * y, numbers)
print(product_result)

# 5. Calculating the factorial of a number using `reduce`:
def factorial (x, y):
    return x * y

n = 5
factorial_result = reduce (factorial, range (1, n+1))
print(factorial_result)

```





