---
sidebar_position: 10
---

# Maps

In Go `map` is built-in data structures that associate keys with values. maps are unordered collections of key-value pairs.

## 1. Declaring and Initializing a Map

You can declare a `map` using the `make()` function or map literal.

```go
package main

import "fmt"

func main() {
    // Example Using make():
    m := make(map[string]int) // Creating an empty map
    m["apple"] = 5
    fmt.Println(m) // Output: map[apple:5]

    // Example Using Map Literal:
    m := map[string]int{"apple": 5, "banana": 10}
    fmt.Println(m) // Output: map[apple:5 banana:10]
}
```

## 2. Accessing Map Elements

You access values using keys. If the key doesn't exist, it returns the zero value for the map's value type.

```go
// Example

package main

import "fmt"

func main() {
    m := map[string]int{"apple": 5, "banana": 10}
    fmt.Println(m["apple"])   // Output: 5
    fmt.Println(m["orange"])  // Output: 0 (default value for int)
}
```

## 3. Checking for Key Existence

You can check if a key exists in the map by using the second return value from the map access expression.

```go
// Example

package main

import "fmt"

func main() {
    m := map[string]int{"apple": 5, "banana": 10}
    value, exists := m["banana"]
    if exists {
        fmt.Println("banana:", value)  // Output: banana: 10
    } else {
        fmt.Println("banana not found")
    }
}
```

## 4. Copy a map

In Go, you can copy a map by creating a new map and iterating over the original to copy each key-value pair. Go doesn't have a built-in function to directly copy maps, but this manual method works effectively.

```go
// Example

package main

import "fmt"

func main() {
    // Original map
    original := map[string]int{
        "Alice": 25,
        "Bob":   30,
        "Carol": 27,
    }

    // Create a new map with the same capacity
    copyMap := make(map[string]int, len(original))

    // Copy each key-value pair
    for key, value := range original {
        copyMap[key] = value
    }

    // Print to verify
    fmt.Println("Original:", original)
    fmt.Println("Copy:", copyMap)

    // Modify copy to show they are independent
    copyMap["Alice"] = 35
    fmt.Println("After modifying copy:")
    fmt.Println("Original:", original)
    fmt.Println("Copy:", copyMap)
}
```

## 5. Deleting Elements from a Map

Use the `delete()` function to remove an entry from the map.

```go
// Example

package main

import "fmt"

func main() {
    m := map[string]int{"apple": 5, "banana": 10}
    delete(m, "banana")  // Deletes the "banana" entry
    fmt.Println(m)        // Output: map[apple:5]
}
```

## 6. Iterating Over a Map

You can use a `for` loop with the `range` keyword to iterate over a map.

```go
// Example

package main

import "fmt"

func main() {
    m := map[string]int{"apple": 5, "banana": 10, "orange": 7}
    for key, value := range m {
        fmt.Println(key, value)
    }
    // Output:
    // apple 5
    // banana 10
    // orange 7
}
```

## 7. Map with Custom Types

Maps can also be used with custom types as keys or values.

```go
// Example

package main

import "fmt"

type Person struct {
    Name string
    Age  int
}

func main() {
    m := map[string]Person{
        "john": {"John Doe", 30},
        "alice": {"Alice Smith", 25},
    }
    fmt.Println(m["john"])  // Output: {John Doe 30}
}
```

## 8. Map with Struct Keys

When using `structs` as map keys, they must be comparable (e.g., no slices or maps can be used as map keys).

```go
// Example

package main

import "fmt"

type Point struct {
    X, Y int
}

func main() {
    m := make(map[Point]string)
    p1 := Point{1, 2}
    p2 := Point{3, 4}
    m[p1] = "A"
    m[p2] = "B"
    fmt.Println(m) // Output: map[{1 2}:A {3 4}:B]
}
```

### Summary of Common Map Operations

| Operation                      | Example                                         |
| ------------------------------ | ----------------------------------------------- |
| **Declare and Initialize Map** | `m := make(map[string]int)`                     |
| **Map Literal**                | `m := map[string]int{"apple": 5, "banana": 10}` |
| **Access Elements**            | `value := m["apple"]`                           |
| **Check for Key Existence**    | `value, exists := m["banana"]`                  |
| **Delete Element**             | `delete(m, "apple")`                            |
| **Iterate Over Map**           | `for key, value := range m { ... }`             |
| **Map with Structs as Keys**   | `m := make(map[Point]string)`                   |
| **Map with Custom Types**      | `m["john"] = Person{Name: "John", Age: 30}`     |
