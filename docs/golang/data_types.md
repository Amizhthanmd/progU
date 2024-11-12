---
sidebar_position: 2
---

# Data Types

In Go, data types define the type of value a variable can hold. Go has a rich set of built-in data types, and they can be categorized as basic types, composite types, pointer types, and interface types.

## 1. Basic Data Types

Go supports several basic types that are similar to those in other languages like C or Java.

- **Numeric Types**
  - **Integers**: Used to represent whole numbers.
    - `int` — Signed integer (platform-dependent size, 32 or 64 bits).
    - `int8` — Signed 8-bit integer (-128 to 127).
    - `int16` — Signed 16-bit integer (-32,768 to 32,767).
    - `int32` — Signed 32-bit integer (-2,147,483,648 to 2,147,483,647).
    - `int64` — Signed 64-bit integer.
    - `uint` — Unsigned integer (platform-dependent size).
    - `uint8` — Unsigned 8-bit integer (0 to 255), also called `byte`.
    - `uint16` — Unsigned 16-bit integer (0 to 65,535).
    - `uint32` — Unsigned 32-bit integer (0 to 4,294,967,295).
    - `uint64` — Unsigned 64-bit integer.
- **Floating Point Types**
  - `float32` — 32-bit floating-point number (up to ~7 decimal digits).
  - `float64` — 64-bit floating-point number (up to ~15 decimal digits).
- **Complex Types**
  - `complex64` — Complex number with float32 real and imaginary parts
  - `complex128` — Complex number with float64 real and imaginary parts.
- **Boolean Type**
  - `bool` — Represents a truth value: `true` or `false`.
- **String Type**
  - `string` — Represents a sequence of characters (text). Strings are immutable in Go, meaning once a string is created, it cannot be modified.

### Summary of Data Types in Go

| **Category**        | **Type**                                      | **Description**                                                     |
| ------------------- | --------------------------------------------- | ------------------------------------------------------------------- |
| **Numeric Types**   | `int`, `int8`, `int16`, `int32`, `int64`      | Signed integers                                                     |
|                     | `uint`, `uint8`, `uint16`, `uint32`, `uint64` | Unsigned integers                                                   |
|                     | `float32`, `float64`                          | Floating-point numbers                                              |
|                     | `complex64`, `complex128`                     | Complex numbers (real + imaginary part)                             |
| **Boolean**         | `bool`                                        | Represents `true` or `false`                                        |
| **Text**            | `string`                                      | Sequence of characters                                              |
| **Composite Types** | `array`                                       | Fixed-size collection of elements of the same type                  |
|                     | `slice`                                       | Dynamic-size, flexible view into an array                           |
|                     | `map`                                         | Collection of key-value pairs (hash table-like structure)           |
|                     | `struct`                                      | Collection of fields of different types (used to represent objects) |
| **Pointer**         | `*T`                                          | Pointer to a value of type `T`                                      |
| **Interface**       | `interface{}`                                 | Defines a set of methods; supports polymorphism                     |
| **Custom Types**    | `type`                                        | Used to define new types from existing types                        |
