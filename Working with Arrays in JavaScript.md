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

Here's an example but with a for of loop:

![[Code_UaKuhqaQS2.png]]

Here is the same 