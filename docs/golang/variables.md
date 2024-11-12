---
sidebar_position: 3
---

# Variables

In Go, variable declaration is straightforward but follows specific rules for type assignment and initialization

## 1. Basic Variable Declaration

You can declare a variable with the `var` keyword, followed by the variable name, its type, and an optional initial value.

```go
var <name> <type> = <value>
```

```go
// Example
var age int = 25
var name string = "Alice"
```

If you don't provide an initial value, the variable will be initialized with the zero value for its type. For example, an `int` will default to 0, a `string` will default to "" (empty string), and a `bool` will default to false.

```go
var age int // age is automatically set to 0
var isActive bool // isActive is automatically set to false
```

## 2. Short Declaration (Type Inference)

Go allows you to declare variables without explicitly specifying their type using the := operator. The type is inferred from the initial value.

```go
<name> := <value>
```

```go
// Example
age := 30
name := "Bob"
```

This shorthand form can only be used inside functions, not at the package level.

## 3. Multiple Variable Declaration

You can declare multiple variables in one line, separated by commas. This can be done with the `var` keyword or the shorthand `:=`.

```go
var x, y, z int = 1, 2, 3
a, b := 10, 20
```

## 4. Constant Declaration

Go also supports constant declarations using the `const` keyword. Constants are immutable and must be initialized with a value at the time of declaration.

```go
const <name> <type> = <value>
```

```go
const pi float64 = 3.14159
```
