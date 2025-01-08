# Programming Principles

Programming principles are guidelines that help developers write clean, maintainable, and efficient code.

## DRY (Don't Repeat Yourself)

Avoid duplication in code by abstracting common functionality into reusable components.

```python
# Without DRY
length1 = 5
width1 = 10
area1 = length1 * width1  # Repeated logic
print(f"Area of rectangle 1: {area1}")

length2 = 7
width2 = 3
area2 = length2 * width2  # Repeated logic
print(f"Area of rectangle 2: {area2}")
# ----------------------------------
# With DRY
def calculate_area(length, width):
    return length * width

# Reusing the function
length1, width1 = 5, 10
area1 = calculate_area(length1, width1)
print(f"Area of rectangle 1: {area1}")

length2, width2 = 7, 3
area2 = calculate_area(length2, width2)
print(f"Area of rectangle 2: {area2}")
```

## KISS (Keep It Simple, Stupid)

Strive for simplicity in design and implementation. Simple code is easier to understand and maintain.

```python
# Without KISS
def is_even(number):
    if number % 2 == 0:
        return True
    else:
        return False

# Usage
print(is_even(4))  # Output: True
print(is_even(5))  # Output: False
# ----------------------------------
# With KISS
def is_even(number):
    return number % 2 == 0

# Usage
print(is_even(4))  # Output: True
print(is_even(5))  # Output: False
```

## YAGNI (You Aren't Gonna Need It)

Don't add functionality until it is necessary. Avoid over-engineering and adding features that may never be used.

```python
# Without YAGNI
class User:
    def __init__(self, username, password):
        self.username = username
        self.password = password

    def login(self, entered_password):
        return self.password == entered_password

    # Unnecessary method added "just in case"
    def change_password(self, new_password):
        self.password = new_password

# Usage
user = User("admin", "password123")
print(user.login("password123"))  # Output: True
# -----------------------------------------------
# With YAGNI
class User:
    def __init__(self, username, password):
        self.username = username
        self.password = password

    def login(self, entered_password):
        return self.password == entered_password

# Usage
user = User("admin", "password123")
print(user.login("password123"))  # Output: True
```

## SOLID principles

The SOLID principles are a set of five design principles that help developers create robust, maintainable, and scalable software.

- `SRP`: A class should have only one responsibility.
- `OCP`: Classes should be open for extension but closed for modification.
- `LSP`: Subclasses should be substitutable for their base classes.
- `ISP`: Create small, specific interfaces instead of large, general ones.
- `DIP`: Depend on abstractions, not concrete implementations.

### 1. Single Responsibility Principle (SRP)

A class should have only one reason to change, meaning it should have only one job or responsibility.

```python
# Without SRP
class Report:
    def __init__(self, data):
        self.data = data

    def generate_report(self):
        print(f"Generating report with data: {self.data}")

    def save_report(self, filename):
        with open(filename, "w") as file:
            file.write(self.data)
# -----------------------------------------------------------
# With SRP
class Report:
    def __init__(self, data):
        self.data = data

    def generate_report(self):
        print(f"Generating report with data: {self.data}")

class ReportSaver:
    @staticmethod
    def save_report(data, filename):
        with open(filename, "w") as file:
            file.write(data)

# Usage
report = Report("Some report data")
report.generate_report()
ReportSaver.save_report(report.data, "report.txt")
```

### 2. Open/Closed Principle (OCP)

Software entities (classes, modules, functions) should be open for extension but closed for modification.

```python
# Without OCP
class Discount:
    def __init__(self, customer_type):
        self.customer_type = customer_type

    def apply_discount(self, price):
        if self.customer_type == "regular":
            return price * 0.9
        elif self.customer_type == "premium":
            return price * 0.8

# With OCP
from abc import ABC, abstractmethod

class Discount(ABC):
    @abstractmethod
    def apply_discount(self, price):
        pass

class RegularDiscount(Discount):
    def apply_discount(self, price):
        return price * 0.9

class PremiumDiscount(Discount):
    def apply_discount(self, price):
        return price * 0.8

# Usage
regular_discount = RegularDiscount()
premium_discount = PremiumDiscount()

print(regular_discount.apply_discount(100))  # Output: 90.0
print(premium_discount.apply_discount(100))  # Output: 80.0
```

### 3. Liskov Substitution Principle (LSP)

Objects of a superclass should be replaceable with objects of a subclass without affecting the correctness of the program.

```python
# Without LSP
class Bird:
    def fly(self):
        pass

class Ostrich(Bird):
    def fly(self):
        raise NotImplementedError("Ostriches can't fly")
# ------------------------------------------------------
# With LSP
class Bird:
    pass

class FlyingBird(Bird):
    def fly(self):
        print("Flying")

class Ostrich(Bird):
    pass

# Usage
flying_bird = FlyingBird()
flying_bird.fly()  # Output: Flying

ostrich = Ostrich()
# No fly method for Ostrich, which is correct
```

### 4. Interface Segregation Principle (ISP)

Clients should not be forced to depend on interfaces they do not use. Create smaller, more specific interfaces.

```python
# Without ISP
class Printer:
    def print(self, document):
        pass

    def scan(self, document):
        pass

    def fax(self, document):
        pass
# -------------------------------
# With ISP
class Printer:
    def print(self, document):
        pass

class Scanner:
    def scan(self, document):
        pass

class FaxMachine:
    def fax(self, document):
        pass

# Usage
class MultiFunctionDevice(Printer, Scanner, FaxMachine):
    def print(self, document):
        print("Printing document")

    def scan(self, document):
        print("Scanning document")

    def fax(self, document):
        print("Faxing document")

mfd = MultiFunctionDevice()
mfd.print("doc")  # Output: Printing document
mfd.scan("doc")   # Output: Scanning document
mfd.fax("doc")    # Output: Faxing document
```

### 5. Dependency Inversion Principle (DIP)

High-level modules should not depend on low-level modules. Both should depend on abstractions.

```python
# Without DIP
class LightBulb:
    def turn_on(self):
        print("LightBulb: On")

    def turn_off(self):
        print("LightBulb: Off")

class Switch:
    def __init__(self):
        self.bulb = LightBulb()

    def operate(self):
        self.bulb.turn_on()
# -------------------------------------
# With DIP
from abc import ABC, abstractmethod

class Switchable(ABC):
    @abstractmethod
    def turn_on(self):
        pass

    @abstractmethod
    def turn_off(self):
        pass

class LightBulb(Switchable):
    def turn_on(self):
        print("LightBulb: On")

    def turn_off(self):
        print("LightBulb: Off")

class Fan(Switchable):
    def turn_on(self):
        print("Fan: On")

    def turn_off(self):
        print("Fan: Off")

class Switch:
    def __init__(self, device: Switchable):
        self.device = device

    def operate(self):
        self.device.turn_on()

# Usage
bulb = LightBulb()
switch = Switch(bulb)
switch.operate()  # Output: LightBulb: On

fan = Fan()
switch = Switch(fan)
switch.operate()  # Output: Fan: On
```
