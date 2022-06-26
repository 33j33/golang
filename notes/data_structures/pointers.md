

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

#### Function Pointer Receivers

```golang
func main() {
	var creature Creature = Creature{Species: "shark"}

	fmt.Printf("1) %+v\n", creature)
	changeCreature(&creature)
	fmt.Printf("3) %+v\n", creature)
}

func changeCreature(creature *Creature) {
	creature.Species = "jellyfish"
	fmt.Printf("2) %+v\n", creature)
}

// Output
// 1) {Species:shark}
// 2) &{Species:jellyfish}
// 3) {Species:jellyfish}

```

#### Method Pointer Receivers

A receiver in go is the argument that is defined in a method declaration. The receiver in this method is `c *Creature`

```golang

type Creature struct {
	Species string
}

func (c *Creature) Reset() {
	c.Species = ""
}

func main() {
	var creature Creature = Creature{Species: "shark"}

	fmt.Printf("1) %+v\n", creature)
	creature.Reset()
	fmt.Printf("2) %+v\n", creature)
}

// Output
// 1) {Species:shark}
// 2) {Species:}
```
