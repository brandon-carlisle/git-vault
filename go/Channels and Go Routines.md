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