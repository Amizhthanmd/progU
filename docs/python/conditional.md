---
sidebar_position: 5
---

# Conditional Statements

Conditional statements in python are used to execute code blocks based on whether a condition evaluates to `True` or `False`. They include `if`, `if-else` and `if-elif-else` statements.

## 1. if Statement

Executes a block of code if the condition evaluates to `True`.

```python
x = 10
if x > 5:
    print("x is greater than 5")
```

## 2. if-else Statement

Executes one block of code if the condition is `True` and another block if it is `False`.

```python
x = 3
if x > 5:
    print("x is greater than 5")
else:
    print("x is 5 or less")
```

## 3. if-elif-else Statement

Used to check multiple conditions. Executes the first block where the condition evaluates to `True`.

```python
x = 20
if x < 10:
    print("x is less than 10")
elif x == 20:
    print("x is 20")
else:
    print("x is greater than 10 and not 20")
```

## 4. Nested if Statements

You can place an `if` statement inside another `if` statement.

```python
x = 15
if x > 10:
    if x < 20:
        print("x is between 10 and 20")
```

## 5. Using Logical Operators in Conditions

You can combine multiple conditions using logical operators like `and`, `or`, and `not`.

```python
x = 10
if x > 5 and x < 20:
    print("x is between 5 and 20")

if not (x < 5):
    print("x is not less than 5")
```

## 6. Ternary Conditional Operator

A shorthand way to write an `if-else` statement.

```python
x = 10
result = "Greater than 5" if x > 5 else "5 or less"
print(result)  # Output: Greater than 5
```

## 7. Match case

The match-case statement in Python (introduced in Python 3.10) provides a way to perform pattern matching, similar to switch-case statements in other languages. It allows matching variables or expressions against one or more patterns and executing code blocks based on the match.

```python
value = 2

match value:
    case 1:
        print("Value is 1")
    case 2 | 3:
        print("Value is 2 or 3")
    case _:
        print("Value is something else")
```
