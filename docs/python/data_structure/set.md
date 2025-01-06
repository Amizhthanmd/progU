# Set

A set in Python is an unordered collection of unique elements. Sets are useful when you want to store values without duplicates, and they provide efficient operations like membership testing, union, intersection, and difference.

## 1. Creating a Set

```python
# Using curly braces to create a set
my_set = {1, 2, 3, 4}
print(my_set)  # Output: {1, 2, 3, 4}

# Using the set() constructor
my_set = set([1, 2, 3, 4])
print(my_set)  # Output: {1, 2, 3, 4}
```

## 2. Adding Elements to a Set

You can add elements to a set using the add() method.

```python
my_set = {1, 2, 3}
my_set.add(4)
print(my_set)  # Output: {1, 2, 3, 4}

# Adding duplicate item (it won't be added)
my_set.add(2)
print(my_set)  # Output: {1, 2, 3, 4}  # No duplicate added
```

## 3. Removing Elements from a Set

```python
my_set = {1, 2, 3, 4}

# Using remove() - raises KeyError if element is not found
my_set.remove(2)
print(my_set)  # Output: {1, 3, 4}

# Using discard() - doesn't raise error if element is not found
my_set.discard(5)
print(my_set)  # Output: {1, 3, 4}  # No error, element 5 is not found

# Using pop() - removes and returns an arbitrary element
removed_item = my_set.pop()
print(removed_item)  # Output: 1 (or another arbitrary element)
print(my_set)  # Output: {3, 4}
```

## 4. Set Operations

### 1. Union (|)

The union of two sets returns a set that contains all the elements from both sets (removes duplicates).

```python
set1 = {1, 2, 3}
set2 = {3, 4, 5}
union_set = set1 | set2
print(union_set)  # Output: {1, 2, 3, 4, 5}
```

### 2. Intersection (&)

The intersection of two sets returns a set containing only the elements that are present in both sets.

```python
set1 = {1, 2, 3}
set2 = {3, 4, 5}
intersection_set = set1 & set2
print(intersection_set)  # Output: {3}
```

### 3. Difference (-)

The difference of two sets returns a set containing the elements that are in the first set but not in the second.

```python
set1 = {1, 2, 3}
set2 = {3, 4, 5}
difference_set = set1 - set2
print(difference_set)  # Output: {1, 2}
```

### 4. Symmetric Difference (^)

The symmetric difference returns a set containing elements that are in either of the sets, but not in both.

```python
set1 = {1, 2, 3}
set2 = {3, 4, 5}
symmetric_diff_set = set1 ^ set2
print(symmetric_diff_set)  # Output: {1, 2, 4, 5}
```

### 5. Subset (`<=`)

A set is a subset of another if all elements of the first set are contained in the second.

```python
set1 = {1, 2, 3}
set2 = {1, 2, 3, 4, 5}
print(set1 <= set2)  # Output: True  (set1 is a subset of set2)
```

### 6. Superset (`>=`)

A set is a superset of another if all elements of the second set are contained in the first.

```python
set1 = {1, 2, 3, 4, 5}
set2 = {3, 4}
print(set1 >= set2) # Output: True (set1 is a superset of set2)
```

### 7. Disjoint (isdisjoint())

Returns `True` if two sets have no elements in common.

```python
set1 = {1, 2, 3}
set2 = {4, 5, 6}
print(set1.isdisjoint(set2))  # Output: True  (sets are disjoint)

set3 = {3, 6, 7}
print(set1.isdisjoint(set3))  # Output: False (sets have common elements)
```

## 5. Set Comprehension

```python
# Creating a set of squares
squares = {x**2 for x in range(5)}
print(squares)  # Output: {0, 1, 4, 9, 16}
```

## 6. Checking Membership

```python
my_set = {1, 2, 3, 4}
print(2 in my_set)  # Output: True
print(5 in my_set)  # Output: False
```

# Set Summary

| Feature/Method          | Description                                                             |
|-------------------------|-------------------------------------------------------------------------|
| **Definition**           | An unordered collection of unique elements.                             |
| **Creating a Set**       | `my_set = {1, 2, 3}` or `my_set = set([1, 2, 3])`.                      |
| **Add Elements**         | `add()` - Adds a single element to the set.                             |
| **Remove Elements**      | `remove()` - Removes a specified element (raises KeyError if not found).|
|                         | `discard()` - Removes an element (doesn't raise error if not found).    |
|                         | `pop()` - Removes and returns an arbitrary element.                     |
| **Clear All Elements**   | `clear()` - Removes all elements from the set.                          |
| **Set Operations**       | `|` (Union) - Combines two sets.                                        |
|                         | `&` (Intersection) - Elements common in both sets.                      |
|                         | `-` (Difference) - Elements in the first set but not in the second.    |
|                         | `^` (Symmetric Difference) - Elements in either set but not both.      |
| **Subset & Superset**    | `<=` (Subset) - Check if one set is a subset of another.               |
|                         | `>=` (Superset) - Check if one set is a superset of another.           |
| **Disjoint Sets**        | `isdisjoint()` - Returns True if sets have no common elements.         |
| **Comprehensions**       | `{x**2 for x in range(5)}` - Set comprehension.                         |
| **Membership Test**      | `in` - Check if an element exists in a set.                             |
| **Length of Set**        | `len()` - Returns the number of elements in the set.                    |
| **Immutable Elements**   | Sets can only contain immutable elements (e.g., numbers, strings, tuples).|
| **Unordered**            | Elements are stored in no particular order.                             |
