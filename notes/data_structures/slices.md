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
