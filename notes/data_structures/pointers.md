
- https://www.digitalocean.com/community/conceptual_articles/understanding-pointers-in-go
- https://exercism.org/tracks/go/concepts/pointers
- https://blog.logrocket.com/how-to-use-pointers-in-go/


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


type Person struct {
    Name string
    Age  int
}

var peter Person
peter = Person{Name: "Peter", Age: 22}

var p *Person
p = &peter

// We could have also created a new Person and immediately stored a pointer to it:
var p *Person
p = &Person{Name: "Peter", Age: 22}

// When we have a pointer to a struct, we don't need to dereference the pointer before accessing one of the fields:

var p *Person
p = &Person{Name: "Peter", Age: 22}

fmt.Println(p.Name) // Output: "Peter"
                    // Go automatically dereferences 'p' to allow
                    // access to the 'Name' field

```

Slices and maps are already pointers. Slices and maps are special types because they already have pointers in their implementation. This means that more often than not, we don't need to create pointers for these types to share the memory address for their values.

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
