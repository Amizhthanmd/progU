# Exceptions

The `try`, `except`, and `finally` keywords are used in Python for exception handling. Together, they allow you to manage errors gracefully and ensure that cleanup or finalization code is executed no matter what happens in the `try` block.

## 1. try Block

The `try` block contains code that might raise an exception. If an exception occurs, the remaining code in the `try` block is skipped, and the program jumps to the appropriate except block.

## 2. except Block

The `except` block catches specific exceptions raised in the `try` block. You can handle multiple exception types or use a generic exception handler.

## 3. finally Block

The `finally` block contains code that will always execute, regardless of whether an exception occurred in the `try` block or not. It's typically used for cleanup actions like closing files, releasing resources, or resetting states.

```python
try:
    num = int(input("Enter a number: "))
    result = 10 / num
    print(f"Result: {result}")
except ValueError:
    print("Invalid input! Please enter a number.")
except ZeroDivisionError:
    print("Cannot divide by zero!")
finally:
    print("Execution complete.")
```
