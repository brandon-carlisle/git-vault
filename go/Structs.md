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

## Embedding a struct
We can embed structs together.

```go
type contactInfo struct {
	email string
	zipCode int
}

type person struct {
	firstName string
	lastName string
	contact contactInfo
}
```

or shorthand:
```go
type person struct {
	firstName string
	lastName string
	contactInfo
}
```

And then we can use it like this:
```go
func main() {
	alix := person{
	firstName: "Alix",
	lastName: "Perez",  
	contact: contactInfo{
		email: "alix@perez.com",
		zipCode: 46903,
		},
	}

	fmt.Printf("%+v", alix)
}
```

## Structs with receiver functions
```go
func (p person) print() {
	fmt.Printf("%+v", p)
}

func main() {
	alix := person{
	firstName: "Alix",
	lastName: "Perez",
	contactInfo: contactInfo{
		email: "alix@perez.com",
		zipCode: 46903,
		},
	}
	
	alix.print()
}
```

## Structs with [[Pointers]]
```go
type person struct {
	firstName string
	lastName string 
	contactInfo
}

func (pointerToPerson *person) updateName(newFirstName string) {
	(*pointerToPerson).firstName = newFirstName
}

alix := person{
	firstName: "Alix",
	lastName: "Perez",
	contactInfo: contactInfo{
	email: "alix@perez.com",
	zipCode: 46903,
	},
}

alixPointer := &alix
alixPointer.updateName("John")
```
