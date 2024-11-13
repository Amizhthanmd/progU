---
sidebar_position: 12
---

# Interfaces

In Go, interfaces define a set of method signatures (behavior) without specifying how these methods are implemented. A type implements an interface simply by defining all the methods declared by that interface, without needing explicit declaration. Interfaces allow for flexible and extensible code, making it easy to create functions that operate on any type that fulfills a specific contract.

## 1. Defining an Interface

An interface in Go is created by specifying the `interface` keyword followed by a set of method signatures.

```go
// Example

package main

import "fmt"

// Define an interface
type Shape interface {
    Area() float64
    Perimeter() float64
}
```

- Here, the Shape interface requires any type implementing it to have Area() and Perimeter() methods.

## 2. Implementing an Interface

In Go, any type that defines the methods required by an interface is said to "satisfy" that interface.

```go
// Example

package main

import (
    "fmt"
    "math"
)

// Define an interface
type Shape interface {
    Area() float64
    Perimeter() float64
}

// Define a struct Circle
type Circle struct {
    Radius float64
}

// Define a struct Rectangle
type Rectangle struct {
    Width, Height float64
}

// Implement Area and Perimeter for Circle
func (c Circle) Area() float64 {
    return math.Pi * c.Radius * c.Radius
}

func (c Circle) Perimeter() float64 {
    return 2 * math.Pi * c.Radius
}

// Implement Area and Perimeter for Rectangle
func (r Rectangle) Area() float64 {
    return r.Width * r.Height
}

func (r Rectangle) Perimeter() float64 {
    return 2 * (r.Width + r.Height)
}

func main() {
    var s Shape

    s = Circle{Radius: 5}
    fmt.Printf("Circle Area: %.2f, Perimeter: %.2f\n", s.Area(), s.Perimeter())

    s = Rectangle{Width: 4, Height: 5}
    fmt.Printf("Rectangle Area: %.2f, Perimeter: %.2f\n", s.Area(), s.Perimeter())
}
```

- Circle and Rectangle implement the Shape interface by providing definitions for Area and Perimeter.
- The variable s of type Shape can hold either a Circle or a Rectangle, demonstrating the flexibility of interfaces.

## 3. Empty Interface (interface{})

The empty interface, interface{}, has no methods and can hold any type. It’s commonly used when the type isn’t known in advance.

```go
// Example

package main

import "fmt"

func PrintAnything(val interface{}) {
    fmt.Println("Value:", val)
}

func main() {
    PrintAnything(42)
    PrintAnything("Hello, Go!")
    PrintAnything(3.14)
}
```

- Here, PrintAnything accepts any type as an argument due to the empty interface interface{}.

## 4. Type Assertion

Type assertion is used to retrieve the underlying value of an interface variable.

```go
// Example

package main

import "fmt"

func main() {
    var val interface{} = "hello"

    // Type assertion to get the underlying string value
    str, ok := val.(string)
    if ok {
        fmt.Println("String value:", str)
    } else {
        fmt.Println("Type assertion failed.")
    }
}
```

- Here, val.(string) asserts that val holds a string. If it’s true, the assertion succeeds; otherwise, ok is false.

## 5. Type Switch

A type switch is a way to handle different types stored in an interface variable.

```go
// Example

package main

import "fmt"

func DescribeType(val interface{}) {
    switch v := val.(type) {
    case int:
        fmt.Println("Integer:", v)
    case string:
        fmt.Println("String:", v)
    case float64:
        fmt.Println("Float64:", v)
    default:
        fmt.Println("Unknown type")
    }
}

func main() {
    DescribeType(42)
    DescribeType("Golang")
    DescribeType(3.14)
}

```

## 6. Interfaces with Pointer Receivers

When a method has a pointer receiver, only pointer instances of the type satisfy the interface.

```go
// Example

package main

import "fmt"

type Printer interface {
    Print()
}

type Document struct {
    Content string
}

// Print method with pointer receiver
func (d *Document) Print() {
    fmt.Println("Printing content:", d.Content)
}

func main() {
    doc := &Document{Content: "Hello, Go!"}
    var p Printer = doc
    p.Print()
}
```

### Summary of Common Interface Operations

| **Operation**                      | **Example**                              | **Description**                                                                                           |
| ---------------------------------- | ---------------------------------------- | --------------------------------------------------------------------------------------------------------- |
| **Define an Interface**            | `type Shape interface { ... }`           | Declares an interface with method signatures.                                                             |
| **Implement an Interface**         | `func (c Circle) Area() float64 { ... }` | A type satisfies an interface by implementing all of its methods.                                         |
| **Empty Interface**                | `interface{}`                            | Holds any type, useful for variables of unknown or mixed types.                                           |
| **Type Assertion**                 | `str, ok := val.(string)`                | Extracts the underlying value of an interface, with `ok` to check if the assertion succeeded.             |
| **Type Switch**                    | `switch v := val.(type) { ... }`         | Determines the type of value in an interface variable, allowing different cases for each underlying type. |
| **Pointer Receiver Interface**     | `func (d *Document) Print() { ... }`     | Only pointer instances implement the interface if methods have pointer receivers.                         |
| **Assign Interface to Variable**   | `var s Shape = Circle{Radius: 5}`        | Stores any type implementing the interface in a variable of that interface type.                          |
| **Pass Interface to Function**     | `func Describe(s Shape) { ... }`         | Accepts any type implementing the specified interface as a function argument.                             |
| **Return Interface from Function** | `func GetShape() Shape { ... }`          | Returns any type implementing the specified interface from a function.                                    |
