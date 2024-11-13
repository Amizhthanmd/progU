---
sidebar_position: 14
---

# Go routines

In Go, goroutines are lightweight, independent threads of execution. They enable concurrent programming, allowing you to perform tasks simultaneously without blocking other operations.
Goroutines are managed by Go runtime rather than the operating system, making them more efficient than traditional threads.

- **Lightweight**: Go routines are much lighter than as threads, using only a small amount of memory and dynamically growing their stack size.
- **Independent execution**: Each Go routines executes independently, the go scheduler manages their execution efficiently.
- **No explicit stopping**: Go routines stop automatically when they finish their work or when the main function exits.

## Basic Usage of Goroutines

To create a goroutine, you simply prepend the `go` keyword before a function call. The function will then run concurrently with other goroutines in your program.

```go
// Example

package main

import (
	"fmt"
	"time"
)

func main() {
	go Add(10, 20)
	time.Sleep(1 * time.Second)
}

func Add(a, b int) {
	fmt.Println(a + b) // Output: 30
}
```

- The `main` function starts by calling go Add(10, 20).
- Prefixing Add(10, 20) with go tells Go to start a new goroutine. This means Add will run concurrently, allowing the main function to continue running without waiting for Add to finish.
- The `Add` function takes two integers, a and b, adds them together, and prints the result.
- Since goroutines run concurrently, if we didn’t include time.Sleep(1 \* time.Second) in main, the main function might finish and exit before the Add goroutine has a chance to print 30.
- The `time.Sleep` call pauses the main function for 1 second, giving the Add goroutine enough time to complete and print 30.

## Waiting for Goroutines to Finish

Goroutines run independently, so you may need to coordinate their completion. The `sync.WaitGroup` can help here.

```go
// Example

package main

import (
	"fmt"
	"sync"
)

func main() {
	var wg sync.WaitGroup
	wg.Add(2)
	go Add(10, 20, &wg)
	go Sub(5, 2, &wg)
	wg.Wait()
}

func Add(a, b int, wg *sync.WaitGroup) {
	defer wg.Done()
	fmt.Println(a + b)
}

func Sub(a, b int, wg *sync.WaitGroup) {
	defer wg.Done()
	fmt.Println(a - b)
}
```

- We use `wg.Add(2)` before goroutine starts and `wg.Done()` when each goroutine completes.
- `wg.Wait()` blocks the main goroutine until all others finish.

## Communication Between Goroutines

Goroutines can communicate and synchronize using `channels`, which are typed conduits for data.

```go
// Example

package main

import (
	"fmt"
)

func main() {
	ch := make(chan int)
	go Add(10, 20, ch)
	result := <-ch
	fmt.Println("Result :", result)

}

func Add(a, b int, ch chan int) {
	ch <- a + b
}
```

- `ch := make(chan int)` creates a channel of type int.
- `ch <-` sends data to the channel, and `<- ch` receives it.
