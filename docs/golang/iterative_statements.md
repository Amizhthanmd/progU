---
sidebar_position: 5
---

# Iterative Statements

In Go, Iterative statements allows you you repeat a set of instructions mutiple times, which is primarily achieved using `for` loop. Unlike many other programming languages, Golang only has one looping construct: `for`. It can be used in different forms to handle variety of iteration needs.

## 1. Basic for Loop

The most common form of the for loop is similar to that in other languages, where you specify initialization, a condition, and incrementation.

```go
// Example

package main

import "fmt"

func main() {
    for i := 0; i < 5; i++ {
        fmt.Println(i)
    }
}
```

- `i := 0` initializes the loop variable.
- `i < 5` is the condition that controls how long the loop will continue.
- `i++` increments i by 1 on each iteration.
- This loop will print numbers from 0 to 4.

## 2. for as a while Loop

In Golang, for can be used without any statements in the initializer and post sections, making it behave like a while loop.

```go
// Example

package main

import "fmt"

func main() {
    i := 0
    for i < 5 {
        fmt.Println(i)
        i++
    }
}
```

- This loop will run as long as `i < 5` is true.
- Here, `i` is incremented manually inside the loop.

## 3. Infinite Loop

If you omit all three components of the for loop, it creates an infinite loop. You can exit it using a break statement when a specific condition is met.

```go
// Example

package main

import "fmt"

func main() {
    i := 0
    for {
        if i >= 5 {
            break
        }
        fmt.Println(i)
        i++
    }
}
```

## 4. for Range Loop (for Iterating Over Collections)

The `for ... range` loop is used to iterate over collections like arrays, slices, maps, or strings.

```go
// Example

package main

import "fmt"

func main() {
    numbers := []int{1, 2, 3, 4, 5}

    for index, value := range numbers {
        fmt.Printf("Index: %d, Value: %d\n", index, value)
    }
}
```

## 5. Using continue and break

`continue` skips the current iteration and moves to the next one, while `break` exits the loop.

```go
// Example

package main

import "fmt"

func main() {
    for i := 0; i < 10; i++ {
        if i%2 == 0 {
            continue // Skip even numbers
        }
        if i > 7 {
            break // Stop the loop if i is greater than 7
        }
        fmt.Println(i) // This will print only odd numbers up to 7
    }
}
```

### Summary

| **Type of Loop**               | **Syntax**                                     | **Description**                                                                                                     |
| ------------------------------ | ---------------------------------------------- | ------------------------------------------------------------------------------------------------------------------- |
| Basic `for` Loop               | `for i := 0; i < 5; i++ { ... }`               | Executes a block of code a specific number of times. Used with initializer, condition, and post-statement.          |
| `for` as `while` Loop          | `for condition { ... }`                        | Repeats as long as the condition is `true`. Useful when you don’t need an initializer or post-statement.            |
| Infinite Loop                  | `for { ... }`                                  | Runs indefinitely until a `break` is used to exit the loop.                                                         |
| `for ... range` Loop           | `for index, value := range collection { ... }` | Iterates over collections (e.g., arrays, slices, maps). Returns index and value for each element in the collection. |
| `continue` and `break` Control | `continue`, `break` inside `for` loop          | `continue` skips the current iteration; `break` exits the loop entirely.                                            |
