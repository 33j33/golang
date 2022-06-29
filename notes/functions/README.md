### Functions

https://www.callicoder.com/golang-functions/ 

https://docs.microsoft.com/en-us/learn/modules/go-variables-functions-packages/3-functions?ns-enrollment-type=LearningPath&ns-enrollment-id=learn.languages.go-first-steps

https://gobyexample.com/variadic-functions

https://www.digitalocean.com/community/tutorials/how-to-use-variadic-functions-in-go

### Methods (Functions tied to a type)

A method in Go is a special type of function with a simple difference: you have to include an extra parameter before the function name. This additional parameter is known as the *receiver*. Methods are useful when you want to group functions and tie them to a custom type. This approach in Go is similar to creating a class in other programming languages, because it allows you to implement certain features from the object-oriented programming (OOP) model, such as embedding, overloading, and encapsulation.

A method with a receiver can only be defined the package whose type is defined in the same package as method.

```
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


