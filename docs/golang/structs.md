---
sidebar_position: 10
---

# Structs

In Go, Structs are a way to group the related data together into a single entity. They are similar to classes in other programming languages, but in Go does not have classes; instead, structs are used to define the complex types that can have multiple fields with different data types.

## 1. Defining a Struct

To define a struct, use the `type` keyword followed by the struct name and the fields.

```go
// Example

package main

import "fmt"

type Person struct {
    Name string
    Age  int
}

func main() {
    // Creating an instance of the struct
    p := Person{"John", 30}
    fmt.Println(p)  // Output: {John 30}

    // Accessing struct fields
    fmt.Println(p.Name)  // Output: John
    fmt.Println(p.Age)   // Output: 30
}
```

## 2. Anonymous Structs

You can create structs without explicitly naming them. These are known as anonymous structs.

```go
// Example

package main

import "fmt"

func main() {
    p := struct {
        Name string
        Age  int
    }{"John", 30}
    fmt.Println(p)  // Output: {John 30}
}
```

## 3. Structs with Methods

You can define methods on structs, which allows you to associate behavior with your structs.

```go
// Example

package main

import "fmt"

type Person struct {
    Name string
    Age  int
}

// Method with a pointer receiver
func (p *Person) Greet() {
    fmt.Println("Hello, my name is", p.Name)
}

func main() {
    p := Person{"John", 30}
    p.Greet()  // Output: Hello, my name is John
}
```

## 4. Nested Structs

Structs can contain other structs as fields, which is useful for modeling complex relationships.

```go
// Example

package main

import "fmt"

type Address struct {
    Street, City, State string
}

type Person struct {
    Name    string
    Age     int
    Address Address
}

func main() {
    p := Person{
        Name: "John",
        Age:  30,
        Address: Address{
            Street: "123 Elm St",
            City:   "Somewhere",
            State:  "NY",
        },
    }
    fmt.Println(p)  // Output: {John 30 {123 Elm St Somewhere NY}}
}
```

## 5. Struct Tags

Struct fields can have tags that help in processing them, such as for JSON marshaling or database mapping.

```go
// Example

package main

import "fmt"

type Person struct {
    Name string `json:"name"`
    Age  int    `json:"age"`
}

func main() {
    p := Person{"John", 30}
    fmt.Println(p)  // Output: {John 30}
}
```

## 6. Zero Values for Structs

A struct that is declared but not initialized has its fields set to their zero values (e.g., 0 for int, "" for string).

```go
// Example

package main

import "fmt"

type Person struct {
    Name string
    Age  int
}

func main() {
    var p Person  // Zero value
    fmt.Println(p) // Output: { 0}
}
```
