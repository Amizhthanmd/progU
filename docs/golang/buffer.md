---
sidebar_position: 20
---

# Buffer

In Go, buffer is a region of memory used to temporarily store data while it's being transfered between two places, such as between a file and memory or between a network connection and application. Buffers are particularly useful in scenarios where you need to build up or process data incrementally. Go provides buffering utilities, most notably in the `bytes` and `bufio` packages.

## 1. Buffering with bytes.Buffer

The bytes.Buffer type in Go's bytes package is a dynamic buffer for efficiently building and manipulating byte slices.

```go
package main

import (
	"bytes"
	"fmt"
)

func main() {
	var buf bytes.Buffer

	buf.WriteString("Hello")
	buf.WriteString(" World!")
	fmt.Println(buf.String()) // Output : Hello World!
}
```

## 2. Buffering with bufio.Writer

The `bufio` package provides buffering for `io.Writer` and `io.Reader` interfaces. This is particularly useful when working with files or network I/O to reduce the number of I/O operations, which can improve performance.

```go
package main

import (
	"bufio"
	"fmt"
	"os"
)

func main() {
	// Create a file
	file, err := os.Create("example.txt")
	if err != nil {
		fmt.Println("Error creating file:", err)
		return
	}
	defer file.Close()

	// Create a buffered writer
	writer := bufio.NewWriter(file)

	// Write data to buffer (not directly to the file)
	writer.WriteString("Buffered writing to a file1.\n")
	writer.WriteString("Buffered writing to a file2.\n")

	// Flush the buffer to write data to the file
	writer.Flush()
}
```
