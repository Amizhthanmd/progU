---
sidebar_position: 1
---

# Introduction

## 1. History

- Go, also known as Golang, was created by Robert Griesemer, Rob Pike, and Ken Thompson at Google in 2007 and was publicly released in 2009. The primary goal was to create a language that addressed shortcomings in other programming languages, especially in terms of concurrency, simplicity, and performance.

- Go was designed with the intention to be fast, efficient, and easy to use, with a focus on simplicity and clarity. It combines the performance of low-level languages like C with the ease of use of higher-level languages like Python.

## 2. What is Golang?

- Go (often referred to as Golang) is an open-source programming language developed by Google.
- Go is statically typed and has a rich set of standard libraries, along with built-in garbage collection.
- It features a unique concurrency model using goroutines and channels, which allows efficient multi-threaded processing.
- Go is widely used in backend development, cloud services, and large-scale systems.

## 3. Installation

- Go to the official Go download page: [click here](https://go.dev/doc/install)
- Download the installer for your operating system (Windows, macOS, or Linux).

To check go version by running the following command.

```bash
go version
```

## 4. Go's basic syntax

```go
package main

import "fmt"

func main() {
    fmt.Println("Hello, World!")
}
```

- `package main`: Defines the package name. The `main` package is used for creating executable programs.
- `import "fmt"`: Imports the `fmt` package, which provides I/O functions.
- `func main()`: The entry point of a Go program. The `main` function is executed when the program runs.
- `fmt.Println()`: A function from the `fmt` package used to print text to the console.

## 5. Golang Keywords

Golang has 25 reserved keywords, which are special identifiers with predefined meanings.
| Keyword | Keyword | Keyword | Keyword | Keyword |
|------------|-------------|--------------|-----------|------------|
| break | case | chan | const | continue |
| default | defer | else | fallthrough | for |
| func | go | goto | if | import |
| interface | map | package | range | return |
| select | struct | switch | type | var |
