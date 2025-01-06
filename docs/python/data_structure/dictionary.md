# Dictionary

In Python, a dictionary (or dict) is an unordered collection of items. Each item is a key-value pair, where the key is unique and used to access the corresponding value. Dictionaries are mutable, meaning you can change their contents.

## 1. Creating a Dictionary

You can create a dictionary by placing key-value pairs inside curly braces `{}`.

```python
my_dict = {'name': 'John', 'age': 30, 'city': 'New York'}
print(my_dict)
```

## 2. Accessing Values

You can access the value of a dictionary using the key.

```python
name = my_dict['name']
print(name)  # Output: John
```

If the key does not exist, it raises a `KeyError`. To avoid this, use the get() method, which returns None or a default value if the key is not found.

## 3. Adding or Updating Items

You can add new key-value pairs or update existing ones by assigning a value to a key.

```python
my_dict['email'] = 'john@example.com'  # Add new key-value pair
my_dict['age'] = 31  # Update value of existing key

print(my_dict)
```

## 4. Removing Items

You can remove a key-value pair using `del`, `pop()`, or `popitem()`.

```python
del my_dict['city']  # Removes the 'city' key
print(my_dict)

# Using pop() to remove a key and return its value
age = my_dict.pop('age')  # Removes 'age' and returns its value
print(age)  # Output: 31
print(my_dict)

# Using popitem() to remove the last inserted item
item = my_dict.popitem()
print(item)  # Output: ('email', 'john@example.com')
print(my_dict)
```

## 5. Iterating through a Dictionary

You can loop through a dictionary using a `for` loop to access keys, values, or both.

```python
for key, value in my_dict.items():
    print(f'{key}: {value}')

# Iterating through keys only
for key in my_dict.keys():
    print(key)

# Iterating through values only
for value in my_dict.values():
    print(value)
```

## 6. Dictionary Comprehension

You can create a dictionary using dictionary comprehension, similar to list comprehensions.

```python
squares = {x: x**2 for x in range(5)}
print(squares)  # Output: {0: 0, 1: 1, 2: 4, 3: 9, 4: 16}
```

## 7. Nested Dictionaries

Dictionaries can contain other dictionaries as values, allowing you to create complex structures.

```python
student = {
    'name': 'Alice',
    'age': 22,
    'courses': {'math': 90, 'english': 85}
}

# Accessing nested dictionary values
math_score = student['courses']['math']
print(math_score)  # Output: 90
```

## 8. Copying a Dictionary

You can create a shallow copy of a dictionary using copy() or dict().

```python
new_dict = my_dict.copy()  # Creates a shallow copy
print(new_dict)
```

## 9. Merging Dictionaries

You can merge two dictionaries using the update() method or the | (union) operator in Python 3.9+.

```python
# Merging dictionaries using update()
dict1 = {'a': 1, 'b': 2}
dict2 = {'b': 3, 'c': 4}
dict1.update(dict2)  # Updates dict1 with dict2
print(dict1)  # Output: {'a': 1, 'b': 3, 'c': 4}

# Merging dictionaries using the union operator (Python 3.9+)
merged_dict = dict1 | dict2
print(merged_dict)  # Output: {'a': 1, 'b': 3, 'c': 4}
```

## 10. Default Dictionary

Using `collections.defaultdict`, you can provide a default value for non-existent keys.

```python
from collections import defaultdict

default_dict = defaultdict(int)  # Default value is 0
default_dict['a'] += 1
print(default_dict)  # Output: defaultdict(<class 'int'>, {'a': 1})
```

# Dictionary Methods

| Method               | Description                                                                 |
|----------------------|-----------------------------------------------------------------------------|
| `clear()`            | Removes all items from the dictionary.                                       |
| `copy()`             | Returns a shallow copy of the dictionary.                                    |
| `fromkeys()`         | Creates a dictionary from a sequence of keys with the same value.            |
| `get()`              | Retrieves the value for a given key. If the key is not found, returns `None` or a default value. |
| `items()`            | Returns a view object that displays a list of key-value pairs as tuples.     |
| `keys()`             | Returns a view object that displays a list of all the keys in the dictionary.|
| `pop()`              | Removes and returns the value for a specified key. Raises `KeyError` if the key doesn't exist. |
| `popitem()`          | Removes and returns the last inserted key-value pair as a tuple.            |
| `setdefault()`       | Returns the value of a key if it exists, or inserts the key with a default value and returns that value. |
| `update()`           | Updates the dictionary with elements from another dictionary or iterable of key-value pairs. |
| `values()`           | Returns a view object that displays a list of all the values in the dictionary. |
| `del` (Keyword)      | Deletes a specific key-value pair from the dictionary.                       |
| `|` (Union Operator) | Merges two dictionaries (Python 3.9+).                                       |
