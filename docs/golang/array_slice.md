---
sidebar_position: 9
---

# Arrays & Slices

In Go, arrays and slices are two types of data structures used to store collections of elements. While they may look similar, they have key differences in usage, flexibility, and behavior.

## 1. Arrays in Go

In Go, an array is a fixed-size, ordered collection of elements of the same type. The size of an array is specified at the time of declaration and cannot be changed later. Go's arrays are less commonly used directly because of their fixed size.

```go
// Syntax

var arrayName [size]Type
```

```go
// Example
package main

import "fmt"

func main() {
    var numbers [5]int             // An array of 5 integers, initialized to zero values
    numbers[0] = 1                  // Assigning values to array elements
    fmt.Println(numbers)            // Output: [1 0 0 0 0]

    primes := [4]int{2, 3, 5, 7}    // Array initialization with values
    fmt.Println(primes)             // Output: [2 3 5 7]
}
```

**Properties**:

- Fixed size (cannot grow or shrink).
- Elements can be accessed by index (e.g., array[0]).

### Size Inference for Arrays

The [...] syntax infers the array size based on the number of elements you provide:

```go
// Example

package main

import "fmt"

func main() {
	// Array size is inferred to be 3 based on the number of elements
	arr := [...]string{"apple", "banana", "cherry"}

	fmt.Println(arr) // Output: [apple banana cherry]

	fmt.Println(len(arr)) // Output: 3
}
```

## 2. Slices in Go

- In Go, a slice is a dynamically sized, flexible view into the elements of an array. unlike arrays , slices do not have fixed length , and their size can grow or shrink as needed.
- Slice provides more flexibility than arrays.

```go
// Syntax

var sliceName []Type
```

```go
// Example

package main

import "fmt"

func main() {
    primes := []int{2, 3, 5, 7, 11, 13} // A slice with initial values
    fmt.Println(primes)                 // Output: [2 3 5 7 11 13]

    numbers := make([]int, 3)           // Creates a slice with length 3 (zero values)
    fmt.Println(numbers)                // Output: [0 0 0]

    numbers = append(numbers, 4, 5)     // Appending elements to a slice
    fmt.Println(numbers)                // Output: [0 0 0 4 5]
}
```

**Properties**:

- Dynamic size (can grow or shrink).
- Backed by an underlying array.
- Slices have a length and a capacity:
  - **Length**: Number of elements in the slice (len(slice)).
  - **Capacity**: Number of elements in the underlying array starting from the slice’s first element (cap(slice)).
- Can be sliced further from an existing slice or array, using slice[start:end].

### Slicing an Array or Slice

Slices are often derived from an array or another slice by slicing:

```go
// Example

package main

import "fmt"

func main() {
    arr := [5]int{1, 2, 3, 4, 5} // An array of 5 integers
    slice := arr[1:4]            // Slicing the array from index 1 to 3 (4 is excluded)
    fmt.Println(slice)           // Output: [2 3 4]

    slice2 := []int{1, 2, 3, 4, 5}
    fmt.Println(slice2[:3])  // Output: [1 2 3]
    fmt.Println(slice2[2:])  // Output: [3 4 5]
}
```

### Appending to a Slice

You can use the `append()` function to add elements to a slice. It returns a new slice with the added elements.

```go
// Example

package main

import "fmt"

func main() {
    slice := []int{1, 2, 3}
    slice = append(slice, 4, 5, 6) // Appending multiple elements
    fmt.Println(slice)             // Output: [1 2 3 4 5 6]

    slice1 := []int{1, 2, 3}
    slice2 := []int{4, 5, 6}
    slice1 = append(slice1, slice2...) // Appending all elements of slice2
    fmt.Println(slice1)                // Output: [1 2 3 4 5 6]
}
```

### Copying a Slice

You can copy elements from one slice to another using the built-in `copy()` function. The function copies elements from one slice into another slice, up to the length of the smaller slice.

```go
// Example

package main

import "fmt"

func main() {
    source := []int{1, 2, 3}
    destination := make([]int, len(source)) // Make a slice of same length
    copy(destination, source)               // Copy source to destination
    fmt.Println(destination)                 // Output: [1 2 3]
}
```

### Deleting Elements from a Slice

You can delete elements from a slice using a combination of slicing and the `append()` function. There is no built-in `delete` function for slices.

```go
// Example

package main

import "fmt"

func main() {
    slice := []int{1, 2, 3, 4, 5}
    removeIndex := 2
    slice = append(slice[:removeIndex], slice[removeIndex+1:]...)
    fmt.Println(slice)  // Output: [1 2 4 5]
}
```

### Summary of Common Slice Operations

| Operation                   | Example                                             |
| --------------------------- | --------------------------------------------------- |
| **Declare and Initialize**  | `slice := []int{1, 2, 3}`                           |
| **Create with `make()`**    | `slice := make([]int, 5)`                           |
| **Access Elements**         | `value := slice[0]`                                 |
| **Modify Elements**         | `slice[1] = 10`                                     |
| **Slice a Slice**           | `subSlice := slice[1:3]`                            |
| **Append to Slice**         | `slice = append(slice, 4, 5)`                       |
| **Copy a Slice**            | `copy(dest, source)`                                |
| **Get Length and Capacity** | `len(slice), cap(slice)`                            |
| **Multi-dimensional Slice** | `matrix := [][]int{{1, 2}, {3, 4}}`                 |
| **Delete Elements**         | `slice = append(slice[:index], slice[index+1:]...)` |
| **Resize a Slice**          | `slice = slice[:newLength]`                         |
| **Check Empty Slice**       | `len(slice) == 0`                                   |
