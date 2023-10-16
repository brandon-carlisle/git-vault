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
_, err := http.Get(link) // blocking call
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

The way we can solve this is Go Routines.

## Go Routines
To create a new Go Routine is place the "go" keyword in front of a function call.
![[Screenshot 2023-10-16 at 18.31.20.png]]
This then "spawns/creates" a new go routine separate to our "main" routine.

As soon a Go runs into the blocking call inside of the new go routine, Go will move back onto the loop and create a new routine.

We can now do this:
```go
for _, link := range links {
	go checkLink(link)
}
```

But, when we run the program now, it breaks. This is because of "child" routines.
![[Screenshot 2023-10-16 at 18.46.05.png]]

Here's what happens when we've spawned all of our child go routines, we get an early exit:
![[Screenshot 2023-10-16 at 18.47.56.png]]

We can solve this with Channels.
## Channels
Channels are used to communicate between different running Go routines.
![[Screenshot 2023-10-16 at 18.51.52.png]]

We can use a channel to make sure that the main routine is aware of when each of the child routines have completed their code.

Channels are values, and they are typed just like any other variable.
![[Screenshot 2023-10-16 at 18.53.46.png]]

Because channels are values, we must treat them as such when trying to communicate between routines. 

We make the channel:
```go
func main() {
links := []string{
"http://google.com",
"http://facebook.com",
}

// Initialise the channel variable of type channel string
c := make(chan string)

for _, link := range links {
go checkLink(link, c)
}
}
```

Then for the checkLink function to use the channel, it must accept a channel in its parameters:
```go
func checkLink(link string, c chan string) {
//...
}
```

How do we communicate?
![[Screenshot 2023-10-16 at 19.04.25.png]]

We send a value into the channel:
```go
func checkLink(link string, c chan string) {
_, err := http.Get(link)

if err != nil {
	fmt.Println(link, "might be down!")
	// send message into channel
	c <- "might be down I think."
	return
}

fmt.Println(link, "is working ok!")
c <- "its working ok"
}
```

We wait for a value to be sent inside of our main channel:
```go
func main() {
links := []string{

"http://google.com",

"http://facebook.com",

"http://stackoverflow.com",

"http://go.dev",

"http://amazon.com",

}

  

c := make(chan string)

  

for _, link := range links {

go checkLink(link, c)

}

  

fmt.Println(<-c)

}
```