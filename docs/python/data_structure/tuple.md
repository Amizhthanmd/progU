---
sidebar_position: 2
---

# Tuple

A tuple in Python is an immutable and ordered collection of items. It is similar to a list, but tuples cannot be modified after creation. Here's a detailed explanation with examples:

## 1. Creating a Tuple

Tuples are created using parentheses `()` or simply by separating items with commas.

```python
# Empty tuple
empty_tuple = ()

# Tuple with integers
numbers = (1, 2, 3)

# Tuple with mixed data types
mixed = (1, "hello", 3.14)

# Tuple without parentheses (comma-separated values)
implicit_tuple = 1, 2, 3

# Nested tuple
nested = ((1, 2), (3, 4), (5, 6))

print(numbers)       # Output: (1, 2, 3)
print(implicit_tuple)  # Output: (1, 2, 3)
```

## 2. Accessing Tuple Elements

- Use indexing to access elements (starting at 0).
- Use negative indexing for elements from the end (-1).

```python
fruits = ("apple", "banana", "cherry")

print(fruits[0])   # Output: apple
print(fruits[-1])  # Output: cherry
```

## 3. Tuple Immutability

Tuples cannot be modified after creation.

```python
fruits = ("apple", "banana", "cherry")

# This will raise an error
# fruits[1] = "mango"
# TypeError: 'tuple' object does not support item assignment
```

## 4. Tuple Operations

```python
tuple1 = (1, 2)
tuple2 = (3, 4)
combined = tuple1 + tuple2
print(combined)  # Output: (1, 2, 3, 4)

tuple1 = (1, 2)
print(tuple1 * 3)  # Output: (1, 2, 1, 2, 1, 2)

fruits = ("apple", "banana", "cherry")
print("apple" in fruits)  # Output: True
print("date" in fruits)   # Output: False
```

## 5. Iterating Through a Tuple

```python
fruits = ("apple", "banana", "cherry")

for fruit in fruits:
    print(fruit)

```

## 6. Tuple Methods

```python
numbers = (1, 2, 3, 2, 4)

# Count occurrences of 2
print(numbers.count(2))  # Output: 2

# Find the index of 3
print(numbers.index(3))  # Output: 2
```

## 7. Slicing Tuples

Retrieve a subset of elements using slicing.

```python
fruits = ("apple", "banana", "cherry", "date")

print(fruits[1:3])  # Output: ('banana', 'cherry')
print(fruits[:2])   # Output: ('apple', 'banana')
print(fruits[2:])   # Output: ('cherry', 'date')
print(fruits[-2:])  # Output: ('cherry', 'date')
```

## 8. Tuple Packing and Unpacking

- Packing:
  Packing is assigning multiple values to a single tuple.

```python
packed = 1, 2, 3
print(packed)  # Output: (1, 2, 3)

```

- Unpacking:
  Unpacking assigns tuple values to variables.

```python
numbers = (1, 2, 3)
a, b, c = numbers
print(a)  # Output: 1
print(b)  # Output: 2
print(c)  # Output: 3
```

## 9. Nested Tuples

Tuples can contain other tuples.

```python
nested = ((1, 2), (3, 4), (5, 6))

# Accessing nested elements
print(nested[0])    # Output: (1, 2)
print(nested[0][1]) # Output: 2
```

## 10. Immutable But Contain Mutable Elements

A tuple itself cannot be modified, but it can contain mutable elements (like lists).

```python
mixed = (1, [2, 3], "hello")

# Modify the list inside the tuple
mixed[1][0] = 99
print(mixed)  # Output: (1, [99, 3], 'hello')
```

## 11. Single-Element Tuples

To create a single-element tuple, include a trailing comma.

```python
single = (5,)  # This is a tuple
not_a_tuple = (5)  # This is an integer

print(type(single))      # Output: <class 'tuple'>
print(type(not_a_tuple)) # Output: <class 'int'>
```
