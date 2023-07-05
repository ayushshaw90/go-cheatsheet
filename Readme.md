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

### Compilation and formatting
We have a file named test_code.go

To run a go program
```shell
go run test_code.go
```

To compile a go program
```shell
go build test_code.go
```
We get, a test_code file which can be executed using the command:
```shell
./test_code
```

To format a go program:
```shell
go fmt test_code.go
```
---
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

	- unsigned :
		- `uint8` : unsigned 8 bit integer
		- `uint16` : unsigned 16 bit integer
		- `uint32` : unsigned 32 bit integer
		- `uint64` : unsigned 64 bit integer
	- signed :
		- `int8` : signed 8 bit integer
		- `int16` : signed 16 bit integer
		- `int32` : signed 32 bit integer
		- `int64` : signed 64 bit integer

- Floating types :
	- `float32`, `float64` : 32 and 64 bit IEEE-754 floating point numbers
	- `complex64`, `complex128` : floating complex numbers with real and imaginary parts each of 32bit and 64bit respectively
- Boolean type: 
	- `bool`: can be `true` or `false`
- String type:
	- `string` : a sequence of characters
---
### Example 1

```go
package main

import "fmt"

func main() {
	var a int8 // an unsigned integer variable of 8 bits
	a = 127
	c := -128 // also an integer
	fmt.Println(a, c) // 127 -128
	var b float32 = -255.12 // a float variable of 32 bits
	fmt.Println(b)
}
```
### Example 2
```go
package main

import "fmt"

func main() {
	var fname, lname string // string variable
	fname = "Ayush"
	lname = "Shaw"
	fmt.Println("Name : ", fname, lname) // Name :  Ayush Shaw
}
```

- To declare a new variable, we use var keyword, and specify the data type.
- If we assign a value to a variable while declaring it, we can omit the datatype (it is inferred).
- To declare a variable and assign its value simultaneously, we can use `:= `

### Example 3
```go
package main

import "fmt"

func main() {
	var fruit1 string // string variable
	fruit1, fruit2 := "Mango", "Apple" 
	
	// fruit1 is already declared but the compiler does not throw an error because,
	// fruit2 is a newly declared variable.
	// if we have at least 1 newly declared variable in the left side of :=, the compiler won't throw error
	
	fmt.Println("Favourite fruits :", fruit1, fruit2) // Favourite fruits : Mango Apple
	
	fruit1, fruit2 = "Orange", "Pineapple"
	// we can assign values to multiple variables simultaneously. 
	// here, we use '=' as both the variables fruit1 and fruit2 have already been declared
	fmt.Println("Favourite fruits :", fruit1, fruit2) // Favourite fruits : Orange Pineapple
}
```
- We can declare and assign multiple variables by separating them with `,`
- We use `:=` to declare a variable and initialize it with a value

### Example 4
```go
package main

import "fmt"

func main() {
	var is_studying bool // boolean variable
	fmt.Println(is_studying) // uninitialized variables have default zero value
	// for bool, default value is false
	// for int, it is 0
	// for float64, it is 0.0
	// for string, it is ""
}
```
- Every uninitialized variable has a default zero value
----
## Type conversions
A value can be converted from one data type to other using functions like `int()`, `float64()` etc.
```go
package main

import (
	"fmt"
	"reflect"
)

func main() {
	var num float64 = 23.23 //float value
	y := int(num) // y = 23 (int value)
	fmt.Println(y)
	fmt.Println(reflect.TypeOf(y)) // using reflect package, we can print the data type of a variable
	z := float64(y) // z = 23 but it's data type is float64
	fmt.Println(z)
	fmt.Println(reflect.TypeOf(z))
	// output: 
	// 23
	// int
	// 23
	// float64
}
```
---
## Constants
Constants in go can be declared with the syntax: `const var_name var_type = value`

### Example 1
```go
package main

import "fmt"

func main() {
	const PI float64 = 3.142
	radius := 10.0
	area := PI * radius * radius
	fmt.Printf("Area = %f\n", area) // Area = 314.200000
}
```
