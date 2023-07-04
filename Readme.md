# Go Cheatsheet

## Features

- Fast compilation
- Garbage collection
- Good support for multicore processors
- Easy to learn

----------
### Sample code

```go
package main // Every go program begins with a package clause
import "fmt" // Import the packages which are used in the program
func main() { // Execution of program starts here
    fmt.Println("Hello, world!") // fmt.Println is used to print the output to the console
}
```
-----------

## Declaring variables

```go
package main

func main() {
	var x int = 51 // declare a variable by specifying its data type
	x = 5
	y := "Hello World" // Here, the variable's data type is inferred according to the value
	// var var_name data_type = <value>
	// var_name := value
}
```
-----------
### Data Types 

- Integer types : 
<br>
`uint8`, `uint16`, `uint32`, `uint64` 
<br>
unsigned integers of 8, 16, 32 and 64 bits size respectively
<br>
