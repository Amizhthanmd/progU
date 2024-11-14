---
sidebar_position: 17
---

# Defer

In Go, `defer` keyword is used to delay the execution of the function or statement until the surrounding function returns. `defer` is often used for resources cleanup, such as file closing, releasing locks, or disconnecting from database. Defered function are executed in Last in first out(LIFO) order, meaning the last defered function will run first.

```go
// Example

package main

import "fmt"

func main() {
    fmt.Println("Start")

    defer fmt.Println("Deferred 1")
    defer fmt.Println("Deferred 2")
    defer fmt.Println("Deferred 3")

    fmt.Println("End")
}
```

```go
// Example file handling

package main

import (
    "fmt"
    "os"
)

func readFile(filename string) {
    file, err := os.Open(filename)
    if err != nil {
        fmt.Println("Error opening file:", err)
        return
    }
    defer file.Close() // Ensures the file is closed when the function returns

    fmt.Println("Reading file:", filename)
}

func main() {
    readFile("example.txt")
}
```
