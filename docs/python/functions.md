---
sidebar_position: 7
---

# Functions

In Python, a function is a block of reusable code that performs a specific task. Functions help to organize code, make it more readable, and allow you to avoid repetition. Functions can accept inputs (parameters) and can return outputs.

A function is defined using the `def` keyword, followed by the function name and parentheses. Parameters (if any) are passed inside the parentheses. The code inside the function is indented.

## Basic Function

```python
def add_numbers(a, b):
    return a + b

# Calling the function
result = add_numbers(5, 3)
print(result)  # Output: 8
```

## Function Without Parameters

```python
def greet():
    print("Hello, world!")

# Calling the function
greet()  # Output: Hello, world!
```

## Function With Default Parameters

```python
def greet(name="Guest"):
    print(f"Hello, {name}!")

# Calling the function with and without an argument
greet("Alice")  # Output: Hello, Alice!
greet()         # Output: Hello, Guest!
```

## Function Returning Multiple Values

```python
def calculate_area_and_perimeter(length, width):
    area = length * width
    perimeter = 2 * (length + width)
    return area, perimeter

# Calling the function
area, perimeter = calculate_area_and_perimeter(5, 3)
print("Area:", area)         # Output: Area: 15
print("Perimeter:", perimeter)  # Output: Perimeter: 16
```

## Lambda Functions (Anonymous Functions)

Python also supports lambda functions, which are small anonymous functions defined using the `lambda` keyword:

```python
# Lambda function to add two numbers
add = lambda a, b: a + b

# Calling the lambda function
print(add(5, 3))  # Output: 8

```

## Function with Variable Number of Arguments

You can define functions that accept a variable number of arguments using \*args for non-keyword arguments or \*\*kwargs for keyword arguments:

```python
# Function using *args
def sum_numbers(*args):
    return sum(args)

print(sum_numbers(1, 2, 3))  # Output: 6
print(sum_numbers(4, 5, 6, 7))  # Output: 22

# Function using **kwargs
def print_info(**kwargs):
    for key, value in kwargs.items():
        print(f"{key}: {value}")

print_info(name="Alice", age=25)
# Output:
# name: Alice
# age: 25
```

## The pass Statement

function definitions cannot be empty, but if you for some reason have a function definition with no content, put in the pass statement to avoid getting an error.

```python
def myfunction():
  pass
```

## Positional-Only Arguments

In Python, positional-only arguments are function parameters that can only be provided by their position in the function call, not by their name. This feature is useful when you want to enforce that certain arguments must be passed in order and cannot be referenced by their keyword.

### Basic Positional-Only Arguments

```python
def greet(name, /, message):
    print(f"{message}, {name}!")

# Valid calls
greet("Alice", message="Hello")  # Output: Hello, Alice!

#Invalid calls
greet(name="Alice", message="Hello")
```

### Mixing Positional-Only and Regular Arguments

You can mix positional-only arguments, regular positional/keyword arguments, and keyword-only arguments using / and \*.

```python
def func(a, /, b, *, c):
    print(a, b, c)

# Valid calls
func(1, 2, c=3)  # Output: 1 2 3

# Invalid calls
# func(a=1, b=2, c=3)  # Raises TypeError: a is positional-only
# func(1, 2, 3)        # Raises TypeError: c must be a keyword argument
```

## map() Function:

The `map()` function applies a given function to each item of an iterable (such as a list or a tuple) and returns a map object (which is an iterator) that yields the results.

```python
numbers = [1, 2, 3, 4]
squared_numbers = map(lambda x: x ** 2, numbers)
print(list(squared_numbers))  # Output: [1, 4, 9, 16]
```

## filter() Function:

The `filter()` function constructs an iterator from elements of an iterable for which a function returns True.

```python
numbers = [1, 2, 3, 4, 5, 6]
even_numbers = filter(lambda x: x % 2 == 0, numbers)
print(list(even_numbers))  # Output: [2, 4, 6]
```
