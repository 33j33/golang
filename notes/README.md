### Links

[fmt cheat sheet] https://yourbasic.org/golang/fmt-printf-reference-cheat-sheet/

[go-rest-api boilerplate] https://github.com/Massad/gin-boilerplate/blob/master/main.go

 ### Resources
 
 https://gobyexample.com/  
 https://www.golangprograms.com/   
 https://yourbasic.org/golang/   
 https://zetcode.com/all/#go   
 https://docs.microsoft.com/en-us/learn/paths/go-first-steps/
 https://www.digitalocean.com/community/books/how-to-code-in-go-ebook

 --
 
 https://gophercises.com/     
 https://www.calhoun.io/lets-learn-algorithms/
 
 [map, package, interface exercice] https://docs.microsoft.com/en-us/learn/modules/go-methods-interfaces/3-challenge
 
 ### Some Golang Gotchas
 
 - [Some Gotchas in Golang] https://www.golangprograms.com/go-programming-language.html
 
 - A variable is exported (it is available for use outside its package) if it begins with capital letter. (https://tour.golang.org/basics/3)
 - There can only be one main() function
 - Go is a "pass by value" programming language, unless you pass around pointer reference. Whenever you pass a value to a function, Go takes that value and creates a local copy (a new variable in memory). Changes you make to that variable in the function don't affect the one you sent to the function.
 - When you declare variables outside of a function, you must do it by using the `var` keyword.
 - you can use the (`a := 3`) colon equal sign only inside a function. When you declare variables outside of a function, you must do it by using the `var` keyword.
 - if you want to export a struct and init this struct value outside of it's package than all fields of the struct must start with capital letter, otherwise you will get an error "Unexported field 'fieldName' usage"
      ```golang
      type Item struct {
         Value string  // uppercase V
         Priority int  // uppercase P
         Index int     // uppercase I
      }
     ```
- 

