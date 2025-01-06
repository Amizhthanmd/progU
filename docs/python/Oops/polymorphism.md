# Polymorphism

Polymorphism is a core concept in object-oriented programming (OOP) that allows objects of different classes to be treated as objects of a common super-class. In Python, polymorphism allows methods in different classes to have the same name but potentially different implementations.

## Types of Polymorphism

- Method Overriding (Runtime Polymorphism):

  - Subclasses provide a specific implementation of a method defined in the parent class.
  - The behavior of the method is determined at runtime based on the object type.

- Method Overloading (Compile-Time Polymorphism):

  - Python does not support method overloading directly like some other languages (e.g., Java or C++). However, it can be achieved by using default arguments or variable-length arguments.

- Duck Typing:
  - If an object implements the required method, it can be used, regardless of its actual class.
  - This aligns with Python's dynamic typing.

## 1. Method Overriding

```python
class Animal:
    def speak(self):
        print("Animal speaks")

class Dog(Animal):
    def speak(self):
        print("Dog barks")

class Cat(Animal):
    def speak(self):
        print("Cat meows")

# Polymorphic behavior
animals = [Dog(), Cat(), Animal()]

for animal in animals:
    animal.speak()  # Calls the specific implementation based on the object type
```

## 2. Duck Typing

```python
class Dog:
    def speak(self):
        return "Bark"

class Cat:
    def speak(self):
        return "Meow"

class Bird:
    def speak(self):
        return "Chirp"

def animal_sound(animal):
    print(animal.speak())

# Objects of different types passed to the same function
dog = Dog()
cat = Cat()
bird = Bird()

animal_sound(dog)
animal_sound(cat)
animal_sound(bird)
```

## 3. Polymorphism with Class Methods

```python
class Shape:
    def area(self):
        pass

class Circle(Shape):
    def __init__(self, radius):
        self.radius = radius

    def area(self):
        return 3.14 * self.radius ** 2

class Rectangle(Shape):
    def __init__(self, width, height):
        self.width = width
        self.height = height

    def area(self):
        return self.width * self.height

shapes = [Circle(5), Rectangle(4, 6)]

for shape in shapes:
    print("Area:", shape.area())
```

