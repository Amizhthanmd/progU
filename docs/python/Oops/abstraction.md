---
sidebar_position: 5
---

# Abstraction

Abstraction is one of the core concepts of Object-Oriented Programming (OOP) in Python. It refers to the process of hiding the complex implementation details and exposing only the essential features or functionalities of an object. Abstraction helps in reducing complexity and improving the maintainability of the code.

In Python, abstraction is achieved using abstract classes and interfaces. The `abc` module (Abstract Base Class) in Python provides the tools to create abstract classes.

## Key Concepts of Abstraction in Python:

### 1. Abstract Class:

- A class that cannot be instantiated directly.
- It serves as a blueprint for other classes.
- It can contain both abstract methods (methods without implementation) and concrete methods (methods with implementation).

### 2. Abstract Method:

- A method that is declared but does not have any implementation.
- Subclasses of the abstract class must provide an implementation for the abstract methods.

### 3. Concrete Class:

- A class that inherits from an abstract class and provides implementations for all the abstract methods.

```python
from abc import ABC, abstractmethod

# Abstract Class
class Animal(ABC):
    # Abstract Method
    @abstractmethod
    def sound(self):
        pass

    # Concrete Method
    def sleep(self):
        print("This animal is sleeping")

# Concrete Class
class Dog(Animal):
    def sound(self):
        print("Dog barks")

class Cat(Animal):
    def sound(self):
        print("Cat meows")

# Usage
dog = Dog()
dog.sound()  # Output: Dog barks
dog.sleep()  # Output: This animal is sleeping

cat = Cat()
cat.sound()  # Output: Cat meows
cat.sleep()  # Output: This animal is sleeping

# Cannot instantiate an abstract class
# animal = Animal()  # This will raise an error
```
