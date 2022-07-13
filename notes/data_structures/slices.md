### Slices

- https://yourbasic.org/golang/slices-explained/
- https://yourbasic.org/golang/append-explained/
- https://www.tugberkugurlu.com/archive/working-with-slices-in-go-golang-understanding-how-append-copy-and-slicing-syntax-work
- https://github.com/golang/go/wiki/SliceTricks

### Random Slice facts

**Calling append on a Sliced Slice May Modify the Original Slice**   
We have previously went over how append function in Go works by appending elements to the end of a slice, and returning the updated slice. This can sort of give you the impression that the append function is a pure function, and doesn't modify your state. However, we have seen from how append works that it may not be the case. If we combine this with the fact that the new slice, which is returned by slicing an existing slice, is still referring to the same backing array as the original slice.

```golang
a := []int{2,3,4}
s = a[:]
s = append(s, 5, 6)
printSlice(s) // [2 3 4 5 6]
fmt.Println(a) // [2 3 4]
s = a[:2]
s = append(s, 7)
printSlice(s) // [2 3 7]
fmt.Println(a) // [2 3 7]
// If the backing array is too small, a new array is created
// and original is not modified, but if it isn't the backing array is modified. 
```

#### Slice Exercises

1. Write a program which prompts the user to enter integers and stores the integers in a sorted slice. The program should be written as a loop. Before entering the loop, the program should create an empty integer slice of size (length) 3. During each pass through the loop, the program prompts the user to enter an integer to be added to the slice. The program adds the integer to the slice, sorts the slice, and prints the contents of the slice in sorted order. The slice must grow in size to accommodate any number of integers which the user decides to enter. The program should only quit (exiting the loop) when the user enters the character ‘X’ instead of an integer. 
  ```golang
    func createSliceFromInput() {
      var s []int = make([]int, 3)
      var in string
      fmt.Println("Please enter an interger(X to exit):")
      for {
        fmt.Scanln(&in)
        if in == "X" {
          fmt.Println(s, len(s), cap(s))
          break
        }
        ap, err := strconv.Atoi(in)
        if err != nil {
          fmt.Println("Wrong input")
          continue
        }
        s = append(s, ap)
        sort.Ints(s)
        fmt.Println(s, len(s), cap(s))
        fmt.Println("Please again enter an interger(X to exit):")
      }
    }

   ```
2.
