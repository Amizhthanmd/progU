# QnA

## 1. What is Golang?

Golang (or) Go is an open-source programming language developed by google. Go is statically types and has a rich set of standard libraries, along with built-in garbage collection. It features a unique concurrency model using goroutines and channels, which allows efficient multi-threaded proccesses. Go widely used in backend development, cloud service and large scale systems.

## 2. What are the basic data types available in Golang?

- Boolean: `bool`
- Numeric:
  - Integers: `int8`, `int16`, `int32`, `int64`, `uint8`, `uint16`, `uint32`, `uint64`, `int`, `uint`
  - Floating-point: `float32`, `float64`
  - Complex numbers: `complex64`, `complex128`
- Text: `string`, `rune` (alias for `int32` for representing Unicode code points)

## 3. What is the difference between int and int32 in Golang?

`int` is a platform-dependent integer type, this meaning it could be 32 bits or 64 bits depending on the underlying architecture(32 or 64 bit). `int32` however is explicitly a 32-bit integer on any platform.

## 4. Explain the use of rune in Golang.

A `rune` is an alias for `int32` and is used to represent a unicode code point in golang.
it allows for characters from various languages, special symbols, and emoji to be handled properly.

## 5. What is the difference between an array and a slice in Golang?

- Array: An array is a fixed size, ordered collection of elements of the same type.
- Slice: An slice is a dynamically sized, ordered collection of elements of the same type. slice are not fixed in size and can grow or shrink as needed.

## 6. What is the capacity of a slice in Golang, and how does it work?

The capacity of the slice is total space allocated for the slice, starting from its first element. It may be greater than the length and determines how much the slice can grow before needing to reallocate memory. Capacity grows as elements are appended.

## 7. What is interface?

In Go, Interface is a type that specifies a set of method signatures. It allows different types to satisfy the same interface by implementing those methods, providing a way to achieve polymorphism and flexible , reusable code.

## 8. What is struct?

In Go, Struct is a composite data type that groups together field with different data types. It's used to represent data structures with named fields, similar to classes in other languages (but without methods).

## 9. What is maps?

In Go, map is a built-in data type that associates key with value. maps are unordered collections of key-value pairs.

## 10. What is the purpose of the break statement in Golang?

The `break` statement is used to terminate the execution of the nearest enclosing loop and the controll is transfered to the code following the loop.

## 11. How does the continue statement work in Golang?

The `continue` statement skips the remaining code inside the loop for the current iteration and moves to the next iteration of the loop.

## 12. What is go routines?

A Go routine is a lightweight thread managed by the Go runtime. Go routines allows concurrent execution of functions in golang. they are cheaper than traditional threads, making it possible to run thousands of go routines concurrently within a single program.

## 13. What is a channel?

A channel is a built-in data type used for communication between go routines. Channels allows go routine to send and receive data, making it easier to synchronize concurrent operations. Channels are type, meaning they carry a specific type of data.

## 14. What is a buffered channel in Golang?

A buffered channel is a channel with predefined capacity. It allows sending and receiving without blocking as long as the buffer is not full. When the buffer is full, the sending Go routine will block untill the space is available. You create a buffered channel by passing the buffer size to the `make` function.

## 15. What is the purpose of the select statement

The `select` statement is used to wait on multiple channel operations. It allows a Go routine to wait for multiple channels to become ready for sending or receviving data, and it executes the case that is ready first. If no channels are ready, select will block until one is ready.

## 16. What is the difference between a "send-only" and a "receive-only" channel in Golang?

- Send-only channel: `chan<-` is used to restrict a channel to only sending data.
- Receive-only channel: `<-chan` is used to restrict a channel to only receiving data.

## 17. What is context in go?

In Go, `context` is a standard package used to manage deadlines, cancelation signals and request-scoped value across the API boundaries and goroutines. It helps coordinate operations, improve resource management and propagate signals like timeouts and cancelations.

## 18. What is init?

In Go, `init` is a special function that initializes a package by setting up a state or running the code before the program's execution starts. It is executed automatically once per package, after all imports are resolved but before the `main` function runs.

## 19. Error handling in go

In Go, errors are handled using the `error` type. when a function encounters an error. it can return an error indicating the problem. The calling code can then check if the error is nil. if not, it handles the error appropriately.

## 20. What is pointer?

In Go, pointer is a variable that stores the memory address of another variable, allowing indirect access and modification of its value. It is declared using the `*` operator and is useful for efficient data manipulation and avoiding copies.

## 21. What is panic & recover?

In Go, `panic` is used to terminate the normal execution of a program when an unexpected condition occurs, often due to critical error. `recover` is a built-in function that can catch and handle a panic, allowing the program to recover and continue execution, typically used inside the `defer` block.

## 22. What is defer?

In Go, `defer` is used to schedule a function to be executed after the surrounding function completes. ensuring cleanup tasks are performed. Defered function are executed in LIFO(Last in first out) order, even if the function returns early or panic occurs.

## 23. What is select in go?

In Go, `select` statement allows a goroutine to wait on multiple channel operations, choosing the first available channel to receive from or send to, which is crucial for concurrent programming and managing communication between goroutines.

## 24. What is GOROOT?

`GOROOT` is the environment variable in Go that specifies the root directory of the Go installation, where standard library packages, core tools, and runtime are located.

## 25. What is GOPATH?

`GOPATH` is the environment variable in the Go that defines the workspace directory where Go projects, source code, dependencies and compiled packages are stored.

