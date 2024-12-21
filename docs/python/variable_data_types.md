---
sidebar_position: 2
---

# Variables & Data types

In python variables are containers for storing data values, and data types define the type of data that a variable can hold. Python is dynamically typed, meaning you don't need to declare the type of a variable explicitly - the type is inferred at runtime.

## 1. Declaring variables

Variables are created by assigning a value using the `=` operator.

```python
x = 10         # Integer
y = 3.14       # Float
name = "Python" # String
is_active = True # Boolean
```

## 2. Naming rules

- Variable names must start with a letter or an underscore(`_`).
- They can contain letters, numbers, and underscores but cannot start with a number.
- Python is case-sensitive (`age` and `Age` are different variables).

## 3. Data types in python

| **Data Type** | **Description**                    | **Example**                              |
| ------------- | ---------------------------------- | ---------------------------------------- |
| **int**       | Integer numbers                    | `x = 10`                                 |
| **float**     | Floating-point numbers             | `y = 3.14`                               |
| **str**       | Strings (text)                     | `name = "Python"`                        |
| **bool**      | Boolean values (`True` or `False`) | `is_active = True`                       |
| **list**      | Ordered, mutable collection        | `fruits = ["apple", "banana", "cherry"]` |
| **tuple**     | Ordered, immutable collection      | `coordinates = (10, 20)`                 |
| **dict**      | Key-value pairs (dictionary)       | `person = {"name": "John", "age": 25}`   |
| **set**       | Unordered, unique items            | `unique_numbers = {1, 2, 3}`             |
| **complex**   | Complex numbers                    | `z = 1 + 2j`                             |
| **NoneType**  | Represents `None` (no value)       | `value = None`                           |

## 4. Type casting

Typecasting in Python refers to the process of converting one data type into another. Python provides built-in functions to perform this conversion explicitly. It is useful when you need to convert data between different types to perform operations or ensure compatibility.

### Types of Typecasting

1. Implicit Typecasting

Python automatically converts one data type to another when it is safe to do so, without requiring explicit intervention.

```python
x = 10   # Integer
y = 3.14 # Float
z = x + y  # Python automatically converts `x` to float.
print(z)        # Output: 13.14
print(type(z))  # Output: <class 'float'>
```

2. Explicit Typecasting

This requires using Python's built-in functions to convert data types manually.

| **Function** | **Purpose**                                     | **Example**                                       |
| ------------ | ----------------------------------------------- | ------------------------------------------------- |
| `int()`      | Converts to an integer                          | `int("10")` → `10`                                |
| `float()`    | Converts to a floating-point number             | `float("3.14")` → `3.14`                          |
| `str()`      | Converts to a string                            | `str(10)` → `"10"`                                |
| `bool()`     | Converts to a boolean (`True`/`False`)          | `bool(0)` → `False`                               |
| `list()`     | Converts to a list                              | `list((1, 2, 3))` → `[1, 2, 3]`                   |
| `tuple()`    | Converts to a tuple                             | `tuple([1, 2, 3])` → `(1, 2, 3)`                  |
| `set()`      | Converts to a set                               | `set([1, 1, 2])` → `{1, 2}`                       |
| `dict()`     | Converts to a dictionary (from key-value pairs) | `dict([(1, "a"), (2, "b")])` → `{1: "a", 2: "b"}` |
| `complex()`  | Converts to a complex number                    | `complex(1, 2)` → `1+2j`                          |

## 5. Operators

| **Category**         | **Operator**            | **Description**                                      | **Example**                 |
|-----------------------|-------------------------|------------------------------------------------------|-----------------------------|
| **Arithmetic**       | `+`                    | Addition                                            | `a + b`                     |
|                       | `-`                    | Subtraction                                         | `a - b`                     |
|                       | `*`                    | Multiplication                                      | `a * b`                     |
|                       | `/`                    | Division                                            | `a / b`                     |
|                       | `%`                    | Modulus (remainder)                                 | `a % b`                     |
|                       | `**`                   | Exponentiation                                      | `a ** b`                    |
|                       | `//`                   | Floor division                                      | `a // b`                    |
| **Relational**       | `==`                   | Equal to                                            | `a == b`                    |
|                       | `!=`                   | Not equal to                                        | `a != b`                    |
|                       | `<`                    | Less than                                           | `a < b`                     |
|                       | `<=`                   | Less than or equal to                               | `a <= b`                    |
|                       | `>`                    | Greater than                                        | `a > b`                     |
|                       | `>=`                   | Greater than or equal to                            | `a >= b`                    |
| **Logical**          | `and`                  | Logical AND                                         | `a > 0 and b > 0`           |
|                       | `or`                   | Logical OR                                          | `a > 0 or b > 0`            |
|                       | `not`                  | Logical NOT                                         | `not a`                     |
| **Bitwise**          | `&`                    | Bitwise AND                                         | `a & b`                     |
|                       | `|`                    | Bitwise OR                                          | `a | b`                     |
|                       | `^`                    | Bitwise XOR                                         | `a ^ b`                     |
|                       | `~`                    | Bitwise NOT                                         | `~a`                        |
|                       | `<<`                   | Left shift                                          | `a << 1`                    |
|                       | `>>`                   | Right shift                                         | `a >> 1`                    |
| **Assignment**       | `=`                    | Assign                                              | `a = 10`                    |
|                       | `+=`                   | Add and assign                                      | `a += 5`                    |
|                       | `-=`                   | Subtract and assign                                 | `a -= 5`                    |
|                       | `*=`                   | Multiply and assign                                 | `a *= 5`                    |
|                       | `/=`                   | Divide and assign                                   | `a /= 5`                    |
|                       | `%=`                   | Modulus and assign                                  | `a %= 5`                    |
|                       | `**=`                  | Exponentiation and assign                           | `a **= 5`                   |
|                       | `//=`                  | Floor division and assign                           | `a //= 5`                   |
|                       | `&=`                   | Bitwise AND and assign                              | `a &= b`                    |
|                       | `|=`                   | Bitwise OR and assign                               | `a |= b`                    |
|                       | `^=`                   | Bitwise XOR and assign                              | `a ^= b`                    |
|                       | `<<=`                  | Left shift and assign                               | `a <<= 1`                   |
|                       | `>>=`                  | Right shift and assign                              | `a >>= 1`                   |
| **Membership**       | `in`                   | Returns `True` if a value is found in a sequence    | `x in [1, 2, 3]`            |
|                       | `not in`               | Returns `True` if a value is not in a sequence      | `x not in [1, 2, 3]`        |
| **Identity**         | `is`                   | Returns `True` if both variables refer to the same object | `a is b`            |
|                       | `is not`               | Returns `True` if variables refer to different objects | `a is not b`        |
| **Comparison**       | `<`                    | Less than                                           | `a < b`                     |
|                       | `<=`                   | Less than or equal to                               | `a <= b`                    |
|                       | `>`                    | Greater than                                        | `a > b`                     |
|                       | `>=`                   | Greater than or equal to                            | `a >= b`                    |
