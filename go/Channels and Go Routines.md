Channels and Go Routines in Go are both structures inside of Go that are used for handling concurrent programming.

We have a program that checks if a list of links responds to a get request, telling us if the website is up for down.

```go
func main() {
links := []string{
"http://google.com",
"http://facebook.com",
"http://stackoverflow.com",
"http://go.dev",
"http://amazon.com",
} 

for _, link := range links {
checkLink(link)
}
}

func checkLink(link string) {
_, err := http.Get(link)
if err != nil {
fmt.Println(link, "might be down!")
return
} 

fmt.Println(link, "is working ok!")
}
```

This works, but the problem is we are running each check in serial.
![[Screenshot 2023-10-16 at 18.21.11.png]]

This means we have to wait for google.com to respond to even start on the next link and so on. It would be better if we could run all the checks for every link in parallel.
![[Screenshot 2023-10-16 at 18.21.30.png]]

