
[Variables in Go]https://docs.microsoft.com/en-us/learn/modules/go-variables-functions-packages/1-variables

[Data Types - Overview]https://docs.microsoft.com/en-us/learn/modules/go-variables-functions-packages/2-data-types

https://go101.org/article/type-system-overview.html

In Go, you have four categories of data types:

- Basic types: numbers, strings, and booleans
- Aggregate types: arrays and structs
- Reference types: pointers, slices, maps, functions, and channels
- Interface types: interface

### Basic Types

```
bool

string

int  int8  int16  int32  int64
uint uint8 uint16 uint32 uint64 uintptr

byte // alias for uint8

rune // alias for int32
     // represents a Unicode code point

float32 float64

complex64 complex128
```
### Variable Declaration and Initialisation

```golong
var x int
fmt.Println(x) // 0
x = 5 
fmt.Println(x)
var y int = 10
fmt.Println(y) // 10
z:= 20 
fmt.Println(z) // 20
```

### Default Values (or Zero values)

 In Go, unlike in other programming languages, all data types have a default value (or zero value) when you don't initialize a variable.
 
 A list of a few default values for the types we've explored so far:

- 0 for int types (and all of its subtypes, like int64)
- +0.000000e+000 for float32 and float64 types
- false for bool types
- An empty value for string types

```golang
var defaultInt int
var defaultFloat32 float32
var defaultFloat64 float64
var defaultBool bool
var defaultString string
fmt.Println(defaultInt, defaultBool, defaultFloat32, defaultFloat64, defaultString) // 0 false 0 0 
```

### Type Assertion

![type assestion](https://user-images.githubusercontent.com/63919345/179368479-f43da135-76d8-4847-86af-9e823025bff6.png)


### Type Conversions 

https://golangdocs.com/type-casting-in-golang

In Go, casting needs to be done explicitly. Go offers some native ways for converting one data type to a different data type. For example, one way is to use the built-in function for each type, like this:
 
```golang
var integer16 int16 = 127
var integer32 int32 = 32767
fmt.Println(int32(integer16) + integer32) // 32894
```

Another approach for casting in Go is to use the `strconv` package. For example, to convert a `string` to an `int`, and vice-versa, you could use this code:

```golang
package main

import (
    "fmt"
    "strconv"
)

func main() {
    i, _ := strconv.Atoi("-42")
    s := strconv.Itoa(-42)
    fmt.Println(i, s) // -42 -42
}
```

### Type Alias Declaration

```golang
// The following new defined and source types are all
// basic types. The source types are all predeclared.
type (
	MyInt int
	Age   int
	Text  string
)

// The following new defined and source types are all
// composite types. The source types are all unnamed.
type IntPtr *int
type Book struct{author, title string; pages int}
type Convert func(in0 int, in1 bool)(out0 int, out1 string)
type StringArray [5]string
type StringSlice []string
```
```golang
/// It is also possible to define non-struct types which you can use as an alias for a built-in type declaration, 
// and you can define receiver functions on them to extend them in the same way as struct types.

type Name string
func SayHello(n Name) {
  fmt.Printf("Hello %s\n", n)
}
n := Name("Fred")
SayHello(n)
// Output: Hello Fred

// You can also define non-struct types composed of arrays and maps.

type Names []string
func SayHello(n Names) {
  for _, name := range n {
    fmt.Printf("Hello %s\n", name)
  }
}
n := Names([]string{"Fred", "Bill"})
SayHello(n)
// Output:
// Hello Fred
// Hello Bill

```

## Strings


https://golangbot.com/strings/

https://gobyexample.com/string-functions

https://pkg.go.dev/strings

https://gobyexample.com/string-formatting

https://www.golangprograms.com/golang/string-functions/

https://blog.logrocket.com/exploring-the-possibilities-of-golang-string-formatting/

#### Strings Exercises

1. Write a program which prompts the user to enter a string. The program searches through the entered string for the characters ‘i’, ‘a’, and ‘n’. The program should print “Found!” if the entered string starts with the character ‘i’, ends with the character ‘n’, and contains the character ‘a’. The program should print “Not Found!” otherwise. The program should not be case-sensitive, so it does not matter if the characters are upper-case or lower-case. Examples: The program should print “Found!” for the following example entered strings, “ian”, “Ian”, “iuiygaygn”, “I d skd a efju N”. The program should print “Not Found!” for the following strings, “ihhhhhn”, “ina”, “xian”. 
	```golang
	func findian() {
	  var str string
	  fmt.Println("Enter test string: ")
	  _, err := fmt.Scan(&str)
	  if (err != nil){
	    fmt.Println("error", err)
	  }
	  str = strings.ToLower(str)
	  found := str[0] == 'i' && str[len(str) - 1] == 'n' && strings.Contains(str, "a")
	  if (found) {
	    fmt.Println("Found")
	  } else {
	    fmt.Println("Not Found")
	  }
	}
	```
