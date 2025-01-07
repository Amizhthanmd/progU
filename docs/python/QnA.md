---
sidebar_position: 10
---

# QnA

## 1. What is python?

Python is a high level, interpreted programming language known for its simplicity and readability. Its key features includes dynamic typing, automatic memory management, extensive standard library, and supports multiple programming paradigms like procedural , object oriented, and functional programming.

## 2. What is interpreted?

An interpreter is a program that directly executes code line by line without converting it to machine language first. It enables dynamic execution and immediate error detection during runtime.

## 3. What are Python's conditional statements?

Python's conditional statements are used to execute code blocks based on whether a condition is true or false.

## 4. Break, Continue, Pass statements.

- `break:` The `break` statement is used to exit a loop immediately, stopping all further iterations.
- `continue:` The `continue` statement skips the current iteration of the loop and moves to the next iteration.
- `pass:` The `pass` statement is a null operation used as a placeholder where code is syntactically required but no action is needed. It's often used in empty functions, classes, or conditional blocks to avoid syntax errors.

## 5. How do you define a function in Python?

In Python, a function is defined using the `def` keyword, followed by the function name, parentheses `()` for parameters, and a colon `:`. The function body is indented and can include a return statement to send back a value.

## 6. What are `*args` and `**kwargs` in Python?

In Python, `*args` and `**kwargs` are used to handle variable numbers of arguments passed to a function.

- `*args:` This allows you to pass a variable number of positional arguments (arguments that are not named) to a function. It collects these arguments into a tuple.
- `**kwargs:` This allows you to pass a variable number of keyword arguments (arguments that are passed by name) to a function. It collects these arguments into a dictionary where the keys are the argument names and the values are the corresponding values passed.

## 7. What are exceptions in Python?

Exceptions in Python are runtime errors that disrupt the normal flow of a program. They are handled using `try`, `except` blocks to gracefully manage errors and prevent crashes.

In Python, exceptions can be handled using try, except, and finally blocks:

- The `try` block contains the code that might raise an exception.
- The `except` block catches and handles the exception if one occurs.
- The `finally` block contains code that will run no matter what, whether an exception occurs or not.

## 8. What is the purpose of the raise keyword?

The `raise` keyword in Python is used to explicitly trigger an exception. It allows you to raise custom exceptions or re-raise an existing exception within the `except` block, enabling better control over error handling.

## 9. What is list in python?

A list is a data structure in Python that is ordered, mutable, and can hold elements of different data types. Duplicates are allowed. It is defined using square brackets, e.g., `[1, 2, 3]`.

## 10. What is tuple in python?

A tuple is a data structure in Python that is ordered and immutable. Once created, its values cannot be changed. It can hold elements of different data types and allows duplicates. It is defined using parentheses, e.g., `(1, 2, 3)`.

## 11. What is set in python?

A set is a data structure in Python that is unordered, mutable, and contains unique elements. It does not allow duplicates and supports mathematical set operations like union and intersection. It is defined using curly braces, e.g., `{1, 2, 3}`.

## 12. What is dictionary in python?

A dictionary is a data structure in Python that is unordered, mutable, and contains key-value pairs. Each key is unique, and values can be of any data type. It is defined using curly braces, e.g., `{'key': 'value'}`.

## 13. What is the difference between global and local scope?

- A variable created inside a function belongs to the local scope of that function, and can only be used inside that function.
- A variable created in the main body of the Python code is a global variable and belongs to the global scope. Global variables are available from within any scope, global and local.

## 14. What is an iterator in Python?

- An iterator is an object that contains a countable number of values.
- An iterator is an object that can be iterated upon, meaning that you can traverse through all the values.
- Technically, in Python, an iterator is an object which implements the iterator protocol, which consist of the methods `__iter__()` and `__next__()`.

## 15. What is the `__init__()` function in Python?

- The `__init__()` function in Python is a special method (also known as a constructor) that is automatically called when a new object of a class is created. It is used to initialize the attributes of the object.

## 16. what is lambda functions in Python?

A lambda function in Python is a small, anonymous function defined using the lambda keyword. It is also referred to as an inline function because it is typically used in situations where defining a full function is unnecessary.

## 17. What are classes and objects in Python?

In Python, classes and objects are fundamental concepts of Object-Oriented Programming (OOP):

- A `class` is a blueprint or template for creating objects.
- It defines the properties (attributes) and behaviors (methods) that the objects created from the class will have.
- An `object` is an instance of a class.
- It is created using the class constructor and has access to the attributes and methods defined in the class.

## 18. What is the difference between instance variables and class variables?

- `Instance variables` are variables that are specific to an instance of a class. They are defined inside the `__init__` method and are accessed through the object.
- `Class variables` are variables that are shared across all instances of a class. They are defined outside of any method, typically at the class level.

## 19. What is object oriented programming in python?

Object-oriented programming (OOP) in Python is a programming paradigm that uses objects and classes to structure code. It focuses on creating reusable and modular code by encapsulating data (attributes) and behavior (methods) within objects. Key concepts include inheritance, encapsulation, polymorphism, and abstraction.

## 20. What is encapsulation in python?

Encapsulation is the practice of Bundling data (attributes) and methods that operate on the data into a single unit (class), restricting direct access to some components to ensure data integrity.

## 21. What is inheritance in python?

Inheritance allows one class (child) to inherit attributes and methods from another class (parent), enabling code reuse and the creation of hierarchical relationships. The child class can also override or extend the behavior of the parent class.

## 22. What is polymorphism in python?

Polymorphism enables methods or operations to behave differently based on the object or data type, allowing a single interface to work with different implementations. This can be achieved through method overriding, overloading, or using interfaces.

## 23. What is abstraction in python?

Abstraction focuses on exposing only essential features and hiding the internal implementation details of an object. This is achieved using abstract classes and methods, allowing users to interact with the object at a higher level without knowing its complexities.
