[fmt cheat sheet] https://yourbasic.org/golang/fmt-printf-reference-cheat-sheet/

https://gobyexample.com/string-formatting

- `Printf` - "Print Formatter" this function allows you to format numbers, variables and strings into the first string parameter you give it
- `Print` - "Print" This cannot format anything, it simply takes a string and print it
- `Println` - "Print Line" same thing as Printf() however it will append a newline character\n

### Format Specifiers

#### General

- `%v` - value in default format
- `%T` - type of the variable/constant

#### Boolean

- `%t` (true or false)

#### Integers

- `%b` - base 2
- `%o` - base 8
- `%d` - base 10
- `%x` - base 16

#### Floating Point

- `%e` - scientific notation with e
- `%f` - decimals
- `%g` - large decimals

#### String

- `%s` - string
- `%q` - string with quotes

