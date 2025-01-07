---
sidebar_position: 2
---

# Inheritance

Inheritance in Python is a fundamental object-oriented programming concept where one class (called a child class or subclass) inherits attributes and methods from another class (called a parent class or base class). This allows the child class to reuse, extend, or modify the functionality of the parent class.

- Parent Class or Base Class: The class whose properties and methods are inherited.
- Child Class or Sub Class: The class that inherits the properties and methods of the parent class.
- A child class can override or extend the methods and attributes of the parent class.

## 1. Single Inheritance

A single child class inherits from one parent class.

```python
class Animal:
    def speak(self):
        print("Animal speaks")

class Dog(Animal):
    def bark(self):
        print("Dog barks")

# Using the classes
dog = Dog()
dog.speak()  # Inherited method
dog.bark()   # Child class method`
```

## 2. Method Overriding

The child class redefines a method of the parent class.

```python
class Animal:
    def speak(self):
        print("Animal speaks in general")

class Cat(Animal):
    def speak(self):
        print("Cat meows")

cat = Cat()
cat.speak()  # Overrides the parent method
```

## 3. Multiple Inheritance

A child class inherits from more than one parent class.

```python
class Flyable:
    def fly(self):
        print("This can fly")

class Swimmable:
    def swim(self):
        print("This can swim")

class Duck(Flyable, Swimmable):
    pass

# Using the classes
duck = Duck()
duck.fly()   # Inherited from Flyable
duck.swim()  # Inherited from Swimmable
```

## 4. Multilevel Inheritance

A child class inherits from another child class.

```python
class Animal:
    def eat(self):
        print("Animal eats")

class Mammal(Animal):
    def walk(self):
        print("Mammal walks")

class Dog(Mammal):
    def bark(self):
        print("Dog barks")

# Using the classes
dog = Dog()
dog.eat()   # Inherited from Animal
dog.walk()  # Inherited from Mammal
dog.bark()  # Defined in Dog

```

## 5. Hierarchical Inheritance

Multiple child classes inherit from the same parent class.

```python
class Animal:
    def eat(self):
        print("Animal eats")

class Bird(Animal):
    def fly(self):
        print("Bird flies")

class Fish(Animal):
    def swim(self):
        print("Fish swims")

# Using the classes
bird = Bird()
fish = Fish()

bird.eat()  # Inherited from Animal
bird.fly()  # Defined in Bird

fish.eat()  # Inherited from Animal
fish.swim()  # Defined in Fish
```

## Super()

In Python, the super() function is used to call methods from a parent class (superclass) in the context of a child class (subclass).
It allows you to call methods or access properties of the parent class without explicitly naming the parent class.
This is particularly useful when dealing with inheritance, especially in cases where multiple classes are involved,
or when you want to extend the functionality of a method in the child class while still retaining the behavior of the parent class.

```python
class Parent:
    def greet(self):
        print("Hello from Parent")

class Child(Parent):
    def greet(self):
        print("Hello from Child")
        super().greet()  # Calling the parent method using super()

child = Child()
child.greet()
```

```python
class A:
    def __init__(self, name):
        self.name = name
        print(f"A initialized with {self.name}")

class B:
    def __init__(self, age):
        self.age = age
        print(f"B initialized with age {self.age}")

class C(A, B):
    def __init__(self, name, age):
        super().__init__(name)  # Calls A's __init__
        super().__init__(age)   # Calls B's __init__

obj = C("Amizhthan", 25)
```
