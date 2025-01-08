---
sidebar_position: 1
---

# List

Python lists are a versatile and commonly used data structure that can hold an ordered collection of items (of any data type)

## 1. Creating a List

A list is created by placing items inside square brackets `[]`, separated by commas.

```python
# Empty list
empty_list = []

# List with integers
numbers = [1, 2, 3, 4, 5]

# List with strings
fruits = ["apple", "banana", "cherry"]

# Mixed data types
mixed = [1, "hello", 3.14, True]

# Nested list
nested = [[1, 2], [3, 4], [5, 6]]
```

## 2. Accessing List Elements

- Use indexing to access elements (starting at 0).
- Use negative indexing for elements from the end (-1).

```python
fruits = ["apple", "banana", "cherry"]

print(fruits[0])   # Output: apple
print(fruits[-1])  # Output: cherry
print(fruits[1])   # Output: banana
```

## 3. Modifying a List

Lists are mutable, so you can change elements.

```python
fruits = ["apple", "banana", "cherry"]

# Change an item
fruits[1] = "blueberry"
print(fruits)  # Output: ['apple', 'blueberry', 'cherry']

# Add a new item (append)
fruits.append("date")
print(fruits)  # Output: ['apple', 'blueberry', 'cherry', 'date']

# Insert at a specific index
fruits.insert(1, "mango")
print(fruits)  # Output: ['apple', 'mango', 'blueberry', 'cherry', 'date']
```

## 4. Removing Elements

Use remove(), pop(), or del to remove elements.

```python
fruits = ["apple", "banana", "cherry", "date"]

# Remove by value
fruits.remove("banana")
print(fruits)  # Output: ['apple', 'cherry', 'date']

# Remove by index
fruits.pop(1)
print(fruits)  # Output: ['apple', 'date']

# Remove the last item
fruits.pop()
print(fruits)  # Output: ['apple']

# Delete a specific index
del fruits[0]
print(fruits)  # Output: []

# Clear the list
fruits = ["apple", "banana", "cherry"]
fruits.clear()
print(fruits)  # Output: []
```

## 5. Iterating Through a List

You can loop through a list using a for loop.

```python
fruits = ["apple", "banana", "cherry"]

for fruit in fruits:
    print(fruit) # Prints only value


for i, fruit in enumerate(fruits):
    print(i, fruit) # Prints with index

```

## 6. List Operations

```python
list1 = [1, 2]
list2 = [3, 4]
combined = list1 + list2
print(combined)  # Output: [1, 2, 3, 4]

list1 = [1, 2]
print(list1 * 3)  # Output: [1, 2, 1, 2, 1, 2]

fruits = ["apple", "banana", "cherry"]
print("apple" in fruits)  # Output: True
print("date" in fruits)   # Output: False

```

## 7. Slicing Lists

Retrieve a subset of elements using slicing.

```python
fruits = ["apple", "banana", "cherry", "date"]

print(fruits[1:3])  # Output: ['banana', 'cherry']
print(fruits[:2])   # Output: ['apple', 'banana']
print(fruits[2:])   # Output: ['cherry', 'date']
print(fruits[-2:])  # Output: ['cherry', 'date']
```

## 8. List Methods

# List Methods in Python

| **Method**         | **Description**                                           |
| ------------------ | --------------------------------------------------------- |
| `append(x)`        | Adds an element to the end of the list.                   |
| `extend(iterable)` | Adds all elements of an iterable to the end of the list.  |
| `insert(i, x)`     | Inserts an element at a specific position.                |
| `remove(x)`        | Removes the first occurrence of the element.              |
| `pop([i])`         | Removes and returns an element by index (default last).   |
| `clear()`          | Removes all elements from the list.                       |
| `index(x)`         | Returns the index of the first occurrence of the element. |
| `count(x)`         | Returns the number of occurrences of the element.         |
| `sort()`           | Sorts the list in ascending order (or with a key).        |
| `reverse()`        | Reverses the list in place.                               |
| `copy()`           | Returns a shallow copy of the list.                       |

## 9. List Comprehension

```python
# Squares of numbers
squares = [x ** 2 for x in range(5)]
print(squares)  # Output: [0, 1, 4, 9, 16]

# Filter even numbers
evens = [x for x in range(10) if x % 2 == 0]
print(evens)  # Output: [0, 2, 4, 6, 8]
```

## 10. Nested Lists

```python
matrix = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]

print(matrix[1][2])  # Output: 6

for row in matrix:
    for item in row:
        print(item, end=" ")

```
