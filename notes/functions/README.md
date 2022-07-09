# Functions

https://www.callicoder.com/golang-functions/ 

https://docs.microsoft.com/en-us/learn/modules/go-variables-functions-packages/3-functions?ns-enrollment-type=LearningPath&ns-enrollment-id=learn.languages.go-first-steps

https://gobyexample.com/variadic-functions

https://www.digitalocean.com/community/tutorials/how-to-use-variadic-functions-in-go

## Anonymous Functions

- https://golangdocs.com/anonymous-functions-in-golang

```golang
func() {
 fmt.Println("I am in anonymous function")
}()

func(x int) {
 fmt.Printf("%d is passed to this anonymous function\n", x)
}(42)

h := func(){
 fmt.Println("Function assgined to variable")
}
h()
```

## Methods (Functions tied to a type)

- https://docs.microsoft.com/en-us/learn/modules/go-methods-interfaces/1-methods
- https://go.dev/tour/methods/1

A method in Go is a special type of function with a simple difference: you have to include an extra parameter before the function name. This additional parameter is known as the *receiver*. Methods are useful when you want to group functions and tie them to a custom type. This approach in Go is similar to creating a class in other programming languages, because it allows you to implement certain features from the object-oriented programming (OOP) model, such as embedding, overloading, and encapsulation.

A method with a receiver can only be defined the package whose type is defined in the same package as method.

```golang
func (receiver type) MethodName(parameters) (returnTypes) {
  // method functionality
}
```

There are two types of receivers, *value receivers*, and *pointer receivers*.

Methods with a value receiver operate on a copy of the value passed to it, meaning that any modification done to the receiver inside the method is not visible to the caller whereas methods with pointer receiver operate on the same variable as passed to it. 

```golang
type Person struct {
  firstName string
  lastName string
  number int
}

func (p Person) getPersonInfo() string {
  return fmt.Sprintf("Name: %v %v, Number: %v", p.firstName, p.lastName, p.number)
}

func (p *Person) changeNumber(newNumber int) {
  p.number = newNumber
}

func main(){
  john := Person{"John", "Doe", 1234567890}
  fmt.Println(john.getPersonInfo())
  john.changeNumber(431239801)
  fmt.Println("After Number Change")
  fmt.Println(john.getPersonInfo())
  
  // OUTPUT
  // Name: John Doe, Number: 1234567890
  // After Number Change
  // Name: John Doe, Number: 431239801
 }
```

Go interprets *`(&x).MethodName`* and *`(*x).MethodName`* as *`x.MethodName`*

![plain functions](https://user-images.githubusercontent.com/63919345/176523016-04e5d056-53a0-47c2-b6aa-8a05c0e727d5.png)
![methods](https://user-images.githubusercontent.com/63919345/176520735-d659167b-5894-4ed7-a5cd-3b65c5b056c3.png)
![methods for non struct type](https://user-images.githubusercontent.com/63919345/176521189-467821e8-ab7e-4674-96ca-ca9b76cad409.png)
![pointer receivers](https://user-images.githubusercontent.com/63919345/176522100-5c9dfaa9-752a-40c9-960d-fc7912f3df7f.png)


## Interfaces

- https://go.dev/tour/methods/9
- https://gobyexample.com/interfaces
- https://golangbot.com/interfaces-part-1/
- https://golangbot.com/interfaces-part-2/

An interface type is effectively a set of method signatures. Any type that defines those methods "implements" the interface implicitly. There is no implements keyword in Go. Here is what an interface definition might look like:

```golang
type InterfaceName interface {
    MethodOne() MethodOneReturnType
    MethodTwo(paramOne ParamOneType, paramTwo ParamTwoType) MethodTwoReturnType 
    ...
}
```

For example, here is the built-in error interface:

```golang
type error interface {
    Error() string
}
```

This means that any type which implements an `Error()` method which returns a string implements the error interface. This allows a function with return type error to return values of different types as long as all of them satisfy the error interface.

There is one very special interface type in Go: the **empty** interface type that contains zero methods. The empty interface type is written like this: `interface{}`. Since it has no methods, every type implements the empty interface type. This is helpful for defining a function that can generically accept any value. In that case, the function parameter uses the empty interface type.

![interface implemented implicitly](https://user-images.githubusercontent.com/63919345/177055785-b42c63b8-7002-4bf9-a302-ad8d091d883d.png)

![empty interface](https://user-images.githubusercontent.com/63919345/177054854-7d07d5f5-bbc1-44f7-b5f6-b63017ec29a1.png)


## Builtin Functions

- https://pkg.go.dev/builtin
- https://dave.cheney.net/2014/08/17/go-has-both-make-and-new-functions-what-gives

- `func new(Type) *Type`

### `new`

*`func new(Type) *Type`*

The new built-in function allocates memory. The first argument is a type, not a value, and the value returned is a pointer to a newly allocated zero value of that type. 
