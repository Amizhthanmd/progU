---
sidebar_position: 5
---

# Functions

A function is a block of code that performs a specific task. It’s a reusable unit of code that can be called from other parts of your program. Functions help you organize your code, make it more modular, and improve readability.

## 1. Basic Function Definition

A function in Go is defined using the `func` keyword followed by the function name, a set of parameters (optional), the return type (optional), and a block of code.

```go
// Syntax

func functionName(parameter1 type1, parameter2 type2) returnType {
    // Code block
}
```

```go
// Example

package main

import "fmt"

func greet(name string) {
    fmt.Println("Hello, " + name)
}

func main() {
    greet("Donald")
}
```

- The function `greet` takes one argument name of type string and does not return anything.
- It is called in the main function.

## 2. Function with Return Value

Functions can also return a value. The return type must be specified after the parameters.

```go
// Example

package main

import "fmt"

func add(a int, b int) int {
    return a + b
}

func main() {
    result := add(5, 3)
    fmt.Println("Sum:", result)
}
```

- The `add` function returns an `int`, which is the sum of the two input integers.
- The result is stored in the `result` variable and printed.

## 3. Multiple Return Values

Go allows a function to return multiple values. This is useful when you want to return more than one result.

```go
// Syntax

func functionName(parameter1 type1) (returnType1, returnType2) {
    // Code block
    return value1, value2
}
```

```go
// Example

package main

import "fmt"

func divide(a, b int) (int, int) {
    quotient := a / b
    remainder := a % b
    return quotient, remainder
}

func main() {
    q, r := divide(10, 3)
    fmt.Println("Quotient:", q, "Remainder:", r)
}
```

- The `divide` function returns both the quotient and remainder of two integers.

## 4. Named Return Values

In Go, you can also name the return values in the function signature. Named return values can make the code more readable and can be returned without explicitly using the return statement.

```go
// Syntax

func functionName(parameter1 type1) (resultType) {
    resultType = value
    return
}
```

```go
// Example

package main

import "fmt"

func swap(a, b int) (x, y int) {
    x = b
    y = a
    return
}

func main() {
    a, b := swap(5, 10)
    fmt.Println("a:", a, "b:", b)
}
```

The function `swap` returns two values `(x and y)`, which are automatically named and returned without an explicit `return x, y` statement.

## 5. Variadic Functions

A variadic function is a function that can accept a variable number of arguments. This is useful when you don't know how many arguments will be passed to the function.

```go
// Syntax

func functionName(parameter1 type1, params ...type2) {
    // Code block
}
```

- The `...` syntax is used to specify a variadic parameter.

```go
// Example

package main

import "fmt"

func sum(numbers ...int) int {
    total := 0
    for _, number := range numbers {
        total += number
    }
    return total
}

func main() {
    fmt.Println(sum(1, 2, 3, 4, 5))  // Output: 15
    fmt.Println(sum(10, 20))         // Output: 30
}
```

- The `sum` function takes a variable number of `int` arguments and returns their sum.

## 6. Anonymous Functions (Lambda Functions)

In Go, functions can be defined without names, called anonymous functions. These are often used for short-lived operations.

```go
// Syntax

func() {
    // Code block
}
```

```go
// Example

package main

import "fmt"

func main() {
    // Define and call an anonymous function
    func() {
        fmt.Println("This is an anonymous function")
    }()
}
```

- The anonymous function is defined and called immediately.

## 7. Function as First-Class Citizens

In Go, functions are first-class citizens, which means you can assign them to variables, pass them as arguments, and return them from other functions.

```go
// Example (function as arguments)

package main

import "fmt"

func applyOperation(a, b int, operation func(int, int) int) int {
    return operation(a, b)
}

func add(a, b int) int {
    return a + b
}

func main() {
    result := applyOperation
    fmt.Println("Result:", result(5, 3, add)) // Output: 8
}
```

- The`applyOperation` function accepts a function (operation) as an argument, which is then invoked within it.

## 8. Function Closures

A closure is a function that references variables from its surrounding lexical scope.

```go
// Example

package main

import "fmt"

func makeCounter() func() int {
    count := 0
    return func() int {
        count++
        return count
    }
}

func main() {
    counter := makeCounter()
    fmt.Println(counter()) // Output: 1
    fmt.Println(counter()) // Output: 2
    fmt.Println(counter()) // Output: 3
}
```
