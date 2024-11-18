---
sidebar_position: 19
---

# Gnerics

Generics in Go, allow you to write functions and data structures that can operate on different types without sacrificing type safety. Generics make code more flexible and reusable by enabling you to define type parameters for functions, methods, and types.

## 1. Basic Syntax of Generics

A generic function or type in Go uses type parameters enclosed in square brackets ([]). You specify a type parameter by defining a name and a constraint, where the constraint defines what types are allowed. If you don't specify a constraint, any (an alias for interface{}) is used, allowing any type.

```go
package main

import "fmt"

func PrintSlice[T any](s []T) {
    for _, v := range s {
        fmt.Println(v)
    }
}

func main() {
    // Using PrintSlice with an int slice
    intSlice := []int{1, 2, 3}
    PrintSlice(intSlice)

    // Using PrintSlice with a string slice
    stringSlice := []string{"hello", "world"}
    PrintSlice(stringSlice)
}
```

## 2. Constraints

Constraints specify the types that a generic function or type can accept. Some common constraints include:

- `any`: Allows any type (alias for `interface{}`).
- `comparable`: Allows only types that can be compared with `==` and `!=`.
- `Type Lists`: You can specify specific types that are allowed.

```go
package main

import "fmt"

// Contains checks if a slice of comparable elements contains a specific value.
func Contains[T comparable](slice []T, value T) bool {
    for _, v := range slice {
        if v == value {
            return true
        }
    }
    return false
}

func main() {
    intSlice := []int{1, 2, 3, 4, 5}
    fmt.Println("Contains 3:", Contains(intSlice, 3))  // true
    fmt.Println("Contains 6:", Contains(intSlice, 6))  // false

    stringSlice := []string{"apple", "banana", "cherry"}
    fmt.Println("Contains 'banana':", Contains(stringSlice, "banana")) // true
    fmt.Println("Contains 'orange':", Contains(stringSlice, "orange")) // false
}
```

## 3. Generic Struct

```go
package main

import "fmt"

// Pair is a generic struct with two fields of any type
type Pair[T, U any] struct {
    First  T
    Second U
}

func main() {
    intStringPair := Pair[int, string]{First: 1, Second: "one"}
    fmt.Println(intStringPair)

    floatBoolPair := Pair[float64, bool]{First: 3.14, Second: true}
    fmt.Println(floatBoolPair)
}
```
