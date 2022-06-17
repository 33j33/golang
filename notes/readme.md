### Links

[fmt cheat sheet] https://yourbasic.org/golang/fmt-printf-reference-cheat-sheet/

[go-rest-api boilerplate] https://github.com/Massad/gin-boilerplate/blob/master/main.go

 ### Resources
 
 https://gobyexample.com/  
 https://www.golangprograms.com/   
 https://yourbasic.org/golang/   
 https://zetcode.com/all/#go   
 
 --
 
 https://gophercises.com/     
 https://www.calhoun.io/lets-learn-algorithms/
 
 ### Some Golang Gotchas
 
 - [Some Gotchas in Golang] https://www.golangprograms.com/go-programming-language.html
 
 - A variable is exported (it is available for use outside its package) if it begins with capital letter. (https://tour.golang.org/basics/3)
 - There can only be one main() function
 - Go is a "pass by value" programming language, unless you pass around pointer reference. Whenever you pass a value to a function, Go takes that value and creates a local copy (a new variable in memory). Changes you make to that variable in the function don't affect the one you sent to the function.
 - When you declare variables outside of a function, you must do it by using the `var` keyword.
