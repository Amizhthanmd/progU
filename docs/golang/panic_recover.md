---
sidebar_position: 18
---

# Panic & Recover

In Go, `panic` and `recover` are used for error handling in situations when an error is severe enough that program cannot continue as normal. They are typically used for handling unexpected or critical errors rather than routine error handling, which should use error values.

- **Panic**:

  - `panic` is a built-in function that stops the normal flow of the program and begins to unwind the stack, executing any defered function along the way.
  - When a `panic` occurs, the program will terminate after running all defered calls unless the panic is recoverd.

- **Recover**:

  - `recover` is a built-in function that allows the program to recover from panic and continue executing.
  - It is only useful within the defered function, where it can catch a panic and prevent the program from crashing.

```go
// Example

package main

import "fmt"

func main() {
	CausePanic(5)
	fmt.Println("Program exited.")
}

func CausePanic(a int) {
	defer RecoveryFunc()
	for i := 0; i <= a; i++ {
		fmt.Println(i)
		if i == 2 {
			panic("reached 2")
		}
	}
}

func RecoveryFunc() {
	fmt.Println("called recovery")
	if r := recover(); r != nil {
		fmt.Println("Recovered from panic : ", r)
	}
}
```
