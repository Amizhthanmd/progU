---
sidebar_position: 6
---

# Iterative statement

- `for` loop: Used for iterating over a sequence (like a list, tuple, dictionary, string, or range).
- `while` loop: Repeats as long as a condition is `True`.

## 1. For Loop

The `for` loop iterates over a sequence (or other iterable objects).

```python
# Iterating over a list
numbers = [1, 2, 3, 4]
for num in numbers:
    print(num)

# Iterating over a range
for i in range(5):
    print(i)
```

## 2. while Loop

The `while` loop executes as long as a condition is True.

```python
# Printing numbers from 1 to 5
count = 1
while count <= 5:
    print(count)
    count += 1
# Output: 1 2 3 4 5
```

## 3. break, continue, and else in Loops

- `break`: Exits the loop prematurely.
- `continue`: Skips the current iteration and moves to the next.
- `else`: Executes if the loop completes without encountering a break.

```python
for num in range(10):
    if num == 5:
        break  # Exit loop when num equals 5
    print(num)

for num in range(5):
    if num == 2:
        continue  # Skip when num equals 2
    print(num)


for num in range(3):
    print(num)
else:
    print("Loop completed without a break.")

```

## 4. zip and enumerate with Iteration

```python

names = ["Alice", "Bob"]
ages = [25, 30]
for name, age in zip(names, ages):
    print(f"{name} is {age} years old.")

items = ["a", "b", "c"]
for index, item in enumerate(items):
    print(f"Index {index}: {item}")

```
