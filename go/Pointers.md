![[Screenshot 2023-10-06 at 17.27.38.png]]

## Pass by Value
Go is a "pass by value" language. Meaning whenever we pass some value into a function, go will take that value/struct and copy all of that data and place it inside of a new "container" in our memory with a new memory address.

![[Screenshot 2023-10-06 at 17.28.17.png]]

## Pointer Operations

![[Screenshot 2023-10-06 at 17.41.48.png]]

![[Screenshot 2023-10-09 at 15.32.45.png]]

## Type Description
When we see a * in front of a type, this is a type description.
![[Screenshot 2023-10-06 at 17.54.29.png]]

## Pointer Shortcut
We can drop some code to make it easier to write when working with functions with receivers that have a type of *pointer.

So instead of this:
```go
alix := person {
	firstName: "Alex",
	lastName: "Perez",
}

alixPointer := &alix

func (pointerToPerson *person) updateName(newFirstName string) {
	(*pointerToPerson).firstName = newFirstName
}
```