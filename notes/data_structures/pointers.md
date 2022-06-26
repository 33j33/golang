

```golang
var creature string = "shark"
var pointer *string = &creature

fmt.Println("creature =", creature)
fmt.Println("pointer =", pointer)

fmt.Println("*pointer =", *pointer)

*pointer = "jellyfish"
fmt.Println("*pointer =", *pointer)

fmt.Println("creature =", creature)

// Output
// creature = shark
// pointer = 0xc000010200
// *pointer = shark
// *pointer = jellyfish
// creature = jellyfish
```
