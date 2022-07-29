# Working with Arrays in [[JavaScript]]
## Simple Array methods
#### Slice method
![[Code_S81Ngf5vDy.png]]

#### Splice method
Works in same was a slice but it mutates the original array.

![[Code_HNCbtcVr0n.png]]

Works great for removing last element from an array

![[Code_nUNaPzQDJ4.png]]

#### Reverse
The reverse method DOES mutate the original array!

![[SitApp_IY8cV1p2HJ.png]]

#### Concat
The concat method is used to join two arrays. Does not mutate orignal array.

![[SitApp_tnCrvciCbz.png]]

#### Join
Returns a string with each element joined together with specified argument like so:

![[SitApp_itKZ2YNKSF.png]]

#### At method
![[SitApp_lgcImK8y8s.png]]

Useful for getting last array element
![[SitApp_B2qgMKKqgg.png]]

Note: Also works on strings

## For Each method
The for each method is used to loop over arrays, but we call the for each method and pass in a callback function with our code. The callback function argument is the current element of the array as seen below.

Unlike a for of loop, you cannot break out of a for each loop.

Here's an example but with a for of loop:

![[Code_UaKuhqaQS2.png]]

Here is the same idea but with the forEach method:

![[Code_5VawqNYG7t.png]]

------------------

What if we want to access the index of the current element?

Here's an example but with a for of loop:

![[SitApp_0wcQdpB3xv.png]]

Here is the same idea but with the forEach method:

![[SitApp_0g0fW5uGhp.png]]

## Data Transformations: Map, Filter & Reduce
### Map
Similar to for each, but map creates a brand new array based on the original. It maps the values of the original array to a new array. 

![[chrome_nDc9yNwaD2.png]]

### Filter
Used to filter for elements in the original array that satify certain condition, then returns the passed elements into a new filtered array.

![[chrome_RlvEBaRXP5.png]]

### Reduce
Reduces all array elements into one single value.

