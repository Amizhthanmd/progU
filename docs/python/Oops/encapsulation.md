# Encapsulation

Encapsulation is a fundamental concept in object-oriented programming (OOP) that restricts access to certain parts of an object's data and methods. It enables better control over how the internal state of an object is modified, ensuring data security and preventing unintended interference.

- Defining public, protected, and private members.
- Using getter and setter methods for controlled access to private attributes.

## Types of Members in Encapsulation

- Public Members:
  - Accessible from anywhere, both inside and outside the class.
  - Declared normally (e.g., `self.attribute`).
- Protected Members:
  - Indicated by a single underscore (`_attribute`).
  - Treated as internal but accessible from subclasses.
- Private Members:
  - Indicated by a double underscore (`__attribute`).
  - Not directly accessible outside the class, providing a stronger restriction.

## 1. Public Members

```python
class Person:
    def __init__(self, name):
        self.name = name # Public attribute

    def display_name(self): # Public method
        print(f"My name is {self.name}")

person = Person("Amizhthan")
person.display_name() # Accessible
print(person.name) # Accessible
```

## 2. Protected Members

```python
class Person:
    def __init__(self, name):
        self._name = name  # Protected attribute

    def display_name(self):
        print(f"My name is {self._name}")

class Employee(Person):
    def __init__(self, name, emp_id):
        super().__init__(name)
        self.emp_id = emp_id

    def _display_employee(self): # Protected method
        print(f"Employee: {self._name}, ID: {self.emp_id}")

# Creating an object
employee = Employee("Amizhthan", 101)
employee._display_employee()  # Accessible but treated as internal
print(employee._name)        # Accessible but treated as internal
```

## 3. Private Members

```python
class Person:
    def __init__(self, name, city):
        self.__name = name  # Private attribute

    def display_name(self):
        print(f"My name is {self.__name}")

    def __display_city(self):
        print(f"My city is {self.__name}")

# Creating an object
person = Person("Amizhthan", "Cuddalore")
person.display_name()
print(person.__name)  # AttributeError: 'Person' object has no attribute '__name'
print(person.__display_city()) # AttributeError: 'Person' object has no attribute '__display_city'
```

## 4. Using Getter and Setter Methods

```python
class Person:
    def __init__(self, name):
        self.__name = name  # Private attribute

    # Getter method
    def get_name(self):
        return self.__name

    # Setter method
    def set_name(self, name):
        self.__name = name

# Creating an object
person = Person("Amizhthan")
print(person.get_name())  # Accessing private attribute using getter

person.set_name("John")  # Modifying private attribute using setter
print(person.get_name())
```

## 5. Name Mangling for Private Members

Python uses name mangling to make private attributes less accessible. The attribute name is changed internally to `_ClassName__AttributeName`.

```python
class Person:
    def __init__(self, name):
        self.__name = name  # Private attribute

    def display_name(self):
        print(f"My name is {self.__name}")

# Accessing the private attribute using name mangling
person = Person("Amizhthan")
print(person._Person__name)  # Access private attribute
```
