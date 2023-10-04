In Go there are two "types" of arrays:
 1) Array - fixed length list of things
 2) Slice - An array that can grow or shrink

In both data structures, every single item must be of the same type.

### Making a slice
![[Screenshot 2023-10-03 at 16.16.05.png]]

### Adding to a slice
![[Screenshot 2023-10-03 at 16.17.49.png]]

### Selecting from elements from a slice
Selecting items from a slice works similar to JavaScript:
```go
fruits := string[]{"Apple", "Banana", "Orange", "Passionfruit"}

// Selecting a single item
fruits[1] // "Banana"
```

We can also select a range of items with this syntax:
```go
fruits := string[]{"Apple", "Banana", "Orange", "Passionfruit"}

// fruits[startingIndexIncluding : upToNotIncluding]
fruits[1 : 3] // "Banana" ""
```

## For Loops
Looping over the slice and printing each element looks like this:
![[Screenshot 2023-10-03 at 16.22.59.png]]

How the loop breaks down:
![[Screenshot 2023-10-03 at 16.24.32.png]]

