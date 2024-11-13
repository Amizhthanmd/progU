---
sidebar_position: 15
---

# Channels

- In Go, channels are a core feature used for communication between goroutines, allowing them to synchronize by sending and receiving data. Channels are typed, meaning `chan int` can only carry `int` values. They act as conduits for data, enabling goroutines to pass information back and forth efficiently.
- Channels enable safe data exchange without requiring explicit locking mechanisms.
- Unbuffered channels synchronize the sender and receiver, while buffered channels allow queued communication.
- Closing a channel signals that no more data will be sent, allowing for controlled termination of communication.

## 1. Basic Channel Operations

- Declaring and Creating a Channel: Channels are created using the make function. The type of the data that a channel carries is specified.

```go
ch := make(chan int)  // Creates an unbuffered channel of type int
```

- Sending Data to a Channel: Use the `<-` operator to send data into a channel.

```go
ch <- 42  // Send the integer 42 into the channel
```

- Receiving Data from a Channel: The `<-` operator is also used to receive data from a channel.

```go
value := <-ch  // Receive data from the channel and store it in value
```

- Closing a Channel: Once no more data will be sent on a channel, it should be closed using `close(ch)`. This is essential in some cases to avoid deadlock, especially when the channel is used in loops.

```go
close(ch)
```

## 2. Unbuffered Channels

An unbuffered channel blocks the sender until the receiver is ready and vice versa. This synchronization behavior makes unbuffered channels useful for coordinating actions between goroutines.

```go
// Example

package main

import (
    "fmt"
    "time"
)

func worker(ch chan string) {
    time.Sleep(2 * time.Second)
    ch <- "Data processed"
}

func main() {
    ch := make(chan string)
    go worker(ch)

    // Receiving data will wait for the worker goroutine to send it
    result := <-ch
    fmt.Println(result)
}
```

- Here, main waits until the worker sends "Data processed" into the channel.

## 3. Buffered Channels

A buffered channel has a capacity that allows it to store a certain number of values before blocking the sender. This can be useful when you want to send multiple values to a channel without an immediate receiver.

```go
// Example

package main

import (
	"fmt"
	"sync"
)

func main() {
	var wg sync.WaitGroup
	ch := make(chan int, 3) // Create a buffered channel with capacity 3
	wg.Add(1)
	go SendValue(ch, &wg)
	for i := 1; i <= 2; i++ {
		fmt.Println("received :", <-ch)
	}
	wg.Wait()

}

func SendValue(ch chan int, wg *sync.WaitGroup) {
	defer wg.Done()
	for i := 1; i <= 5; i++ {
		ch <- i
		fmt.Println("sent :", i)
	}
	close(ch)

}
```

## 4. Using `select` with Channels

The `select` statement allows you to wait on multiple channel operations, choosing whichever one is ready to proceed. If multiple cases are ready, one is chosen at random.

```go
// Example

package main

import (
	"fmt"
	"time"
)

func sendDataToCh1(ch chan string) {
	time.Sleep(5 * time.Second)
	ch <- "Data from ch1"
}

func sendDataToCh2(ch chan string) {
	time.Sleep(8 * time.Second)
	ch <- "Data from ch2"
}

func sendDataToCh3(ch chan string) {
	time.Sleep(12 * time.Second)
	ch <- "Data from ch3"
}

func main() {
	// Creating channels
	ch1 := make(chan string)
	ch2 := make(chan string)
	ch3 := make(chan string)

	// Starting goroutines
	go sendDataToCh1(ch1)
	go sendDataToCh2(ch2)
	go sendDataToCh3(ch3)

	// Using select to receive from multiple channels
	for i := 0; i < 3; i++ {
		select {
		case msg1 := <-ch1:
			fmt.Println("Received from ch1:", msg1)
		case msg2 := <-ch2:
			fmt.Println("Received from ch2:", msg2)
		case msg3 := <-ch3:
			fmt.Println("Received from ch3:", msg3)

		}
	}
	fmt.Println("All operations are complete.")
}
```

## 5. Channel Directions

In Go, channels can be directional, meaning they can be restricted to only sending or receiving data. You can specify this by using the `<-chan` syntax (receive-only) and `chan<-` syntax (send-only) when declaring function parameters or variables.

### 1. Receive-only Channel (`<-chan`):

- A channel is declared as receive-only by specifying `<-chan` before the channel name. This means the channel can only be used to receive data, not to send it.
- It is useful when you want to restrict a function to only receiving data from a channel.

### 2. Send-only Channel (`chan<-`):

- A channel is declared as send-only by specifying `chan<-` before the channel name. This means the channel can only be used to send data, not to receive it.
- It is useful when you want to restrict a function to only sending data to a channel.

```go
// Example

package main

import (
	"fmt"
	"sync"
)

func main() {
	var wg sync.WaitGroup
	ch := make(chan string)
	wg.Add(2)
	go SendMessage(ch, &wg)
	go ReceivedMessage(ch, &wg)
	wg.Wait()
}

func ReceivedMessage(ch <-chan string, wg *sync.WaitGroup) {
	defer wg.Done()
	fmt.Println("Message received :", <-ch)
}

func SendMessage(ch chan<- string, wg *sync.WaitGroup) {
	defer wg.Done()
	ch <- "From send channel"
}
```
