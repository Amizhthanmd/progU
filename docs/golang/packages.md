---
sidebar_position: 6
---

# Packages

In Go, packages provide a way to organize and modularize code, making it easier to manage and reuse across different projects. The import and export rules in Go allow you to bring in external packages and control which parts of your package are accessible to other packages.

## 1. Package Basics

A Go package is a collection of related Go source files in the same directory. Each Go file starts with a package declaration, and the package name determines its visibility and purpose.

```go
package mypackage
```

## 2. Creating and Using Packages

Go has two primary types of packages:

- Executable packages: Used to create executable programs; the main file must have package `main`.
- Library packages: Collections of reusable code that can be imported by other packages.

```go
package main

import "fmt"

func main() {
    fmt.Println("Hello, Go!")
}
```

- Here, main is an executable package that runs as the main application entry point.

## 3. Exporting in Go

In Go, exported identifiers (functions, types, variables, or constants) are accessible outside the package in which they are defined. Identifiers that start with an uppercase letter are exported, making them accessible from other packages, while identifiers starting with a lowercase letter are unexported and only accessible within the same package.

```go
// Example

package mathutils

// Add is an exported function, accessible outside this package.
func Add(a, b int) int {
    return a + b
}

// subtract is unexported, accessible only within the mathutils package.
func subtract(a, b int) int {
    return a - b
}
```

- `Add` is exported and can be accessed from other packages.
- `subtract` is unexported and cannot be accessed from outside mathutils.

## 4. Importing Packages

The `import` statement is used to bring in external or standard packages, making their exported names available in the current file.

```go
import "package/path"
```

```go
// Example

package main

import (
    "fmt"
    "go-package/mathutils"  // Importing a custom package
)

func main() {
    result := mathutils.Add(3, 4)  // Calling the exported Add function
    fmt.Println("Result:", result)
}
```

## 5. Importing Custom Packages

To use a custom package, ensure it is in a location accessible to Go, typically within your GOPATH or a Go module. Once the package is in the right location, you can import it just like any standard library package.

```tree
project/
├── main.go          # The main application file
└── mathutils/       # Custom package directory
    └── math.go      # mathutils package file
```

## 6. Aliasing Imports

You can create an alias for an imported package to avoid naming conflicts or to simplify references.

```go
import alias "package/path"
```

```go
// Example

package main

import f "fmt"  // Aliasing the fmt package

func main() {
    f.Println("Hello, with alias!")
}
```

## 7. Blank Identifier Import (\_)

The blank identifier (\_) is used to import a package solely for its side effects (e.g., initializing a package without directly using its exported functions).

```go
import _ "database/sql/driver"
```

## 8. Go Modules

Go modules are the standard way of managing dependencies in modern Go projects. The module system allows you to define and version dependencies, making it easier to handle imports and packages.

### Creating a Go Module

- In your project directory, initialize a module with:

```bash
go mod init your/module/name
```

This creates a go.mod file to manage dependencies.

- When you import packages that are not part of the standard library, Go automatically adds them to your go.mod file.

- Use go get to add specific versions of packages.

```bash
// Example

go get github.com/gorilla/mux
```

## 9. Working with External Packages

To include and use third-party packages:

- Add the package to your module with go get.
- Import it using its full module path.

```go
// Example

package main

import (
    "fmt"
    "github.com/gorilla/mux"
)

func main() {
    router := mux.NewRouter()
    fmt.Println("Router created:", router)
}
```
