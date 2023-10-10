## Purpose of Interfaces
We know:
- Every value has a type
- Every function has to specify the type of its arguments or receivers 
Does this mean
- Every function we write down has to be rewritten to accommodate different types even if the logic in it is the same?
![[Screenshot 2023-10-10 at 16.05.14.png]]

This is what interfaces aim to solve.

## Problem without Interfaces
```go
type englishBot struct{}
type spanishBot struct{}

func main() {
eb := englishBot{}
sb := spanishBot{}  

printGreeting(eb)
printGreeting(sb)
}

func printGreeting(eb englishBot) {
fmt.Println(eb.getGreeting())
}  

func printGreeting(sb spanishBot) {
fmt.Println(sb.getGreeting())
}  

func (eb englishBot) getGreeting() string {
// custom logic for generating an english greeting
return "Hi there"
}

func (sb spanishBot) getGreeting() string {
// custom logic for generating an spanish greeting
return "Hola"
}
```