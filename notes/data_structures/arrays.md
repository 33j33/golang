
## Arrays

- https://www.golangprograms.com/go-language/arrays.html
- https://golangbot.com/arrays-and-slices/

An array is a collection of elements that belong to the same type. The length of an array is fixed and is decided at the time of initialisation.    
An array belongs to type `[n]T`. `n` denotes the number of elements in an array and `T` represents the type of each element. The number of elements `n` is also a part of the type.    
Arrays in Go are value types and not reference types. This means that when they are assigned to a new variable, a copy of the original array is assigned to the new variable. If changes are made to the new variable, it will not be reflected in the original array.

#### Declaring Arrays 

```golang
var x [5]int   // An array of 5 integers
fmt.Println(x) // [0 0 0 0 0]

var y [8]string // An array of 8 strings
fmt.Println(y)  // [         ]

var z [3]complex128 // An array of 3 complex numbers
fmt.Println(z)      // [(0+0i) (0+0i) (0+0i)]
```




