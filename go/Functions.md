Here is how we define a function:

![[Screenshot 2023-10-03 at 16.03.14.png]]

## Receiver functions
![[Screenshot 2023-10-03 at 17.19.13.png]]
![[Screenshot 2023-10-03 at 17.19.43.png]]

![[Screenshot 2023-10-03 at 17.21.42.png]]
![[Screenshot 2023-10-03 at 17.22.41.png]]

## Return multiple values
In Go, you can return multiple values from a function. Here is how:

```go
func deal(d deck, handSize int) (deck, deck) {
	return d[:handSize], d[handSize:]
}
```
