---
sidebar_position: 7
---

# Type Casting

In Go, type conversion, type inference, and type assertion are three distinct concepts. Here’s a breakdown of each:

## 1. Type Conversion

Type conversion in Go is the process of explicitly converting a value from one data type to another compatible type. This is required because Go doesn’t support implicit type conversion between different types (e.g., between int and float64).

```go
// Syntax

var a int = 10
var b float64 = float64(a) // Explicitly converting 'int' to 'float64'
```

```go
// Example

package main

import "fmt"

func main() {
    var x int = 5
    var y float64 = float64(x) // converting int to float64
    fmt.Println(y)             // Output: 5.0
}
```

## 2. Type Inference

Type inference is the process by which Go automatically determines the type of a variable based on the value assigned to it. This is useful when declaring variables without explicitly specifying a type.

```go
// Syntax

a := 10 // Go infers 'a' to be of type 'int' because 10 is an integer
```

```go
// Example

package main

import "fmt"

func main() {
    message := "Hello, Go!" // Type inferred as 'string'
    fmt.Println(message)
}
```

- In this example, message is automatically inferred to be of type string without explicitly specifying it.

## 3. Type Assertion

Type assertion is a way to retrieve the underlying concrete value of an interface. In Go, an interface can hold values of any type that implements the interface. Type assertion allows you to check if an interface holds a specific type and access its value if it does.

```go
// Syntax

var i interface{} = "hello"
s := i.(string)  // Asserts that i is of type string
```

**Safe Type Assertion**: Type assertion can return two values: the value itself and a boolean indicating if the assertion succeeded, which prevents a panic if the assertion fails.

```go
var i interface{} = "hello"
s, ok := i.(string)  // Asserts that i is a string
if ok {
    fmt.Println("String value:", s)
} else {
    fmt.Println("Not a string")
}
```

```go
// Example

package main

import "fmt"

func main() {
    var data interface{} = 42

    // Type assertion with one return value (panics if assertion fails)
    num := data.(int)
    fmt.Println("Value:", num) // Output: Value: 42

    // Type assertion with two return values (safe assertion)
    str, ok := data.(string)
    if ok {
        fmt.Println("String value:", str)
    } else {
        fmt.Println("data is not a string") // Output if 'data' isn't a string
    }
}
```

### Summary of Differences

| Feature             | Purpose                                                               | Example                                    |
| ------------------- | --------------------------------------------------------------------- | ------------------------------------------ |
| **Type Conversion** | Converts a value to a different but compatible type                   | `float64(a)` to convert `int` to `float64` |
| **Type Inference**  | Allows Go to automatically infer the type based on the assigned value | `a := 10` (inferred as `int`)              |
| **Type Assertion**  | Retrieves the concrete type from an `interface{}`                     | `s := i.(string)`                          |
