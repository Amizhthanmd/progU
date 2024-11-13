---
sidebar_position: 16
---

# Mutex

In Go, a mutex (mutual exclusion) is a synchronization primitive used to protect shared resources from being accessed concurrently by multiple goroutines. A mutex ensures that one go routine can access a critical section of code at a time, which is crucial for preventing race conditions when multiple goroutines are reading or modifying shared data.

Go provides the `sync.Mutex` type in the `sync` package, which offers two main methods for locking and unlocking the mutex:

- `Lock()` - Acquires the lock.
- `Unlock()` - Releases the lock.

**1. Locking and Unlocking**:

- When a goroutine locks a mutex, other goroutines that try to lock the same mutex will block until the first goroutine unlocks it.
- Once the mutex is unlocked, another waiting goroutine can acquire the lock and proceed.

**2. Race Conditions**:

- Without mutexes, multiple goroutines could concurrently access and modify shared data, causing unpredictable behavior (a race condition). A mutex ensures that only one goroutine at a time can modify the data, preventing such conditions.

**3. Deadlock**:

-A deadlock occurs when two or more goroutines are each waiting for the other to release a lock, leading to a situation where no goroutine can proceed. It is important to avoid situations where multiple goroutines are blocked forever.

```go
// Example

package main

import (
	"fmt"
	"sync"
)

func main() {

	var wg sync.WaitGroup
	var mu sync.Mutex
	counter := 0

	for i := 1; i <= 500; i++ {
		wg.Add(1)
		go func() {
			defer wg.Done()
			mu.Lock()
			fmt.Println("mutex locked.")
			counter++
			mu.Unlock()
			fmt.Println("mutex unlocked.")
		}()
	}

	wg.Wait()
	fmt.Println(counter)
}
```

## 2. Read-Write Mutex

`sync.RWMutex` (Read-Write Mutex) in Go is a synchronization primitive that allows multiple goroutines to read from a shared resource concurrently, but only one goroutine can write to the shared resource at a time. This is useful in scenarios where reads are frequent but writes are infrequent, allowing for better concurrency and performance than using a sync.Mutex alone.

- **Read Lock (`RLock`)**: Allows multiple goroutines to acquire a lock for reading concurrently. Multiple read operations can occur at the same time as long as no write operation is in progress.
- **Write Lock (`Lock`)**: Allows only one goroutine to acquire a lock for writing. No other goroutines (reading or writing) can access the resource while the write lock is held.

### Methods:

- `RLock()` - Acquires a read lock (multiple goroutines can acquire this at the same time).
- `RUnlock()` - Releases the read lock.
- `Lock()` - Acquires a write lock (only one goroutine can acquire this at a time).
- `Unlock()` - Releases the write lock.

```go
// Example

package main

import (
	"fmt"
	"sync"
)

var mu sync.RWMutex

var count int = 0

func main() {
	var wg sync.WaitGroup

	for i := 1; i <= 10; i++ {
		wg.Add(1)
		go Write(&wg)
	}

	for i := 1; i <= 5; i++ {
		wg.Add(1)
		go Read(&wg)
	}
	wg.Wait()
}

func Write(wg *sync.WaitGroup) {
	defer wg.Done()
	mu.Lock()
	defer mu.Unlock()
	count++
}

func Read(wg *sync.WaitGroup) {
	defer wg.Done()
	mu.RLock()
	defer mu.RUnlock()
	fmt.Println("Count: ", count)
}
```
