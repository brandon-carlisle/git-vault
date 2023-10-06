Struct - data structure that is a collection on properties that are related together.

## Making a struct
Whenever we want to make a struct, we have to first define all of the properties/fields that the struct will have.

```go
type person struct{
	firstName string
	lastName  string
}
```

We can then use that type to create a person:

```go
type person struct {
	firstName string
	lastName string
}

func main() {
	alix := person{
	firstName: "Alix",
	lastName: "Perez",
	}

fmt.Println(alix.firstName)
fmt.Println(alix.lastName)
}
```
