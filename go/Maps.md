A map is a collection of key - value pairs, like an object in JavaScript.

Both the keys and values are statically typed - 
- All the keys in a map must be of the same type
- All the values in a map must be of the same type
- The keys and values do not need to be of the same type

![[Screenshot 2023-10-10 at 14.11.53.png]]

## Declaring a Map
```go
colors := map[string]string{
	"red": "#FF0000",
	"green": "#00FF00",
	"blue": "#0000FF",
}
```
```go
var colors map[string]string
```
```go
colors := make(map[string]string)

colors["white"] = "#FFFFFF"
```


## Accessing a value
```go
fmt.Println(colors["white"])
```

## Delete keys and values
```go
delete(colors, "white")
```

## Iterating over a Map
```go
func printMap(c map[string]string) {
	for key, value := range c {
	fmt.Println(key, value)
  }
}
```

## Difference between Maps and [[Structs]]
![[Screenshot 2023-10-10 at 15.15.06.png]]

### When to use
- If we want to represent a collection of very closely related properties
- 