---
sidebar_position: 4
---

# Conditional statements

In Go, conditional statements allow you to execute blocks of code based on certain conditions. The common conditional statements in Go are if, else, else if, and switch.

- The `if` statement evaluates a condition and executes a block of code if the condition is true.
- If there are multiple conditions can use `else if` block.
- `else` block executes code when if condition is false.
- The `switch` statement in go is alternative to `if-else` chain and is commonly used when you have muliple conditions to evaluate
- The `fallthrough` is used within the switch statement to explicitly allow the execution to continue into the next case regardless of the condition of that case.

## 1. if Statement

The `if` statement is used to execute a block of code if a condition evaluates to true.

```go
// Syntax

if condition {
    // Code to be executed if condition is true
}
```

```go
// Example

package main

import "fmt"

func main() {
    age := 18

    if age >= 18 {
        fmt.Println("You are an adult.")
    }
}
```

## 2. if-else Statement

The `if-else` statement executes one block of code if the condition is true and another block if the condition is false.

```go
// Syntax

if condition {
    // Code to be executed if condition is true
} else {
    // Code to be executed if condition is false
}
```

```go
// Example

package main

import "fmt"

func main() {
    age := 16

    if age >= 18 {
        fmt.Println("You are an adult.")
    } else {
        fmt.Println("You are a minor.")
    }
}
```

## 3. if-else if-else Statement

You can chain multiple conditions using `else if` and provide different blocks of code for each condition.

```go
// Syntax

if condition1 {
    // Code to be executed if condition1 is true
} else if condition2 {
    // Code to be executed if condition2 is true
} else {
    // Code to be executed if all conditions are false
}
```

```go
// Example

package main

import "fmt"

func main() {
    age := 20

    if age < 18 {
        fmt.Println("You are a minor.")
    } else if age >= 18 && age < 60 {
        fmt.Println("You are an adult.")
    } else {
        fmt.Println("You are a senior citizen.")
    }
}
```

## 4. switch Statement

The switch statement is used to execute one out of several possible blocks of code based on the value of an expression. It is often more readable than multiple if-else statements.

```go
// Syntax

switch expression {
case value1:
    // Code to be executed if expression equals value1
case value2:
    // Code to be executed if expression equals value2
default:
    // Code to be executed if expression doesn't match any case
}
```

```go
// Example

package main

import "fmt"

func main() {
    day := 3

    switch day {
    case 1:
        fmt.Println("Monday")
    case 2:
        fmt.Println("Tuesday")
    case 3:
        fmt.Println("Wednesday")
    default:
        fmt.Println("Invalid day")
    }
}
```

## 5. switch with Multiple Conditions

```go
// Example

package main

import "fmt"

func main() {
    number := 15

    switch {
    case number%2 == 0:
        fmt.Println("Even number")
    case number%2 != 0:
        fmt.Println("Odd number")
    default:
        fmt.Println("Not a number")
    }
}
```

## 6. switch with Fallthrough

In Go, switch statements do not automatically "fall through" to the next case unless you explicitly use the fallthrough keyword.

```go
// Example

package main

import "fmt"

func main() {
    day := 2

    switch day {
    case 1:
        fmt.Println("Monday")
    case 2:
        fmt.Println("Tuesday")
        fallthrough
    case 3:
        fmt.Println("Wednesday")
    default:
        fmt.Println("Invalid day")
    }
}
```

## 7. if with Initialization

Go allows you to initialize variables inside an if statement, which makes the code more concise.

```go
// Example

package main

import "fmt"

func main() {
    if number := 5; number > 0 {
        fmt.Println("Positive number")
    }
    // fmt.Println(number) // Error: 'number' is not accessible here
}
```
