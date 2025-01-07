---
sidebar_position: 1
---

# Class

A `class` in Python is a blueprint or template for creating objects. It defines properties (attributes) and behaviors (methods) that the objects created from the class can have.

- Classes are created using the `class` keyword.
- Attributes are variables that belong to the class.
- Methods are functions defined inside a class to describe its behaviors.

## Object

An object is an instance of a class. It represents a concrete entity created from the class blueprint. Objects can access the class's attributes and methods.

- You can create multiple objects from a single class.
- Each object has its own data (attributes), but it shares the class's methods.

```python
# Define a class
class Car:
    # Constructor method to initialize attributes
    def __init__(self, brand, model, year):
        self.brand = brand  # Attribute
        self.model = model  # Attribute
        self.year = year    # Attribute

    # Method to display car details
    def display_info(self):
        print(f"{self.year} {self.brand} {self.model}")

    # Method to start the car
    def start(self):
        print(f"The {self.brand} {self.model} is starting.")

# Create objects (instances) of the Car class
car1 = Car("Toyota", "Corolla", 2020)
car2 = Car("Honda", "Civic", 2018)

# Access attributes and methods using objects
car1.display_info()  # Output: 2020 Toyota Corolla
car1.start()         # Output: The Toyota Corolla is starting.

car2.display_info()  # Output: 2018 Honda Civic
car2.start()         # Output: The Honda Civic is starting.
```

## Constructor

A constructor is a special method in Python that is automatically called when an object of a class is created. It is primarily used to initialize the attributes (variables) of the class.
In Python, the constructor method is defined using the `__init__` method.

- It is invoked automatically when an object is instantiated.
- Used to initialize the attributes of the class.
- A class does not need to have a constructor, but if initialization is required, it's helpful.

## Self

In Python, self is a reference to the current instance of the class. It is used within class methods to access attributes and methods of the object that is being created or manipulated.

- It must be the first parameter of instance methods in a class.
- While calling a method, Python automatically passes the current object as the first argument.
- `self` allows you to access attributes and methods of the same object.
- `self` is not a reserved keyword; you can use any other name, but conventionally, `self` is used for readability and consistency.

## Destructor

A destructor is a special method in Python that is automatically called when an object is destroyed. Its primary purpose is to clean up resources (e.g., closing files, releasing memory) before the object is removed from memory.

In Python, the destructor method is defined using the `__del__` method.

- It is called automatically when an object is no longer needed.
- Used for cleanup tasks such as closing files, database connections, or releasing resources.

```python
class FileHandler:
    def __init__(self, filename):
        self.file = open(filename, 'w')  # Open a file for writing
        print(f"File '{filename}' opened.")

    def write_data(self, data):
        self.file.write(data)
        print(f"Data written to file.")

    def __del__(self):
        self.file.close()  # Close the file when the object is destroyed
        print("File closed and resources released.")

# Create an object
handler = FileHandler("example.txt")
handler.write_data("Hello, World!")

# The destructor is called automatically when the object is deleted or goes out of scope
del handler  # Manually delete the object (optional)
# Output:
# File 'example.txt' opened.
# Data written to file.
# File closed and resources released.
```
