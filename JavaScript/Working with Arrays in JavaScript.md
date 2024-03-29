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
The concat method is used to join two arrays. Does not mutate original array.

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

![[chrome_ylWMNKSZKR.png]]

### Chaining
We can chain these methods together.

![[Code_lyyD6pC8oO.png]]
 For debugging we can inspect the current array using the array parameter on each step. 

### The find method
Used to find an element from an array based on a condition. Returns the first found element of the specified condition. 

![[X7uOKkzGbD.png]]

![[U4N9C6ZF4s.png]]

### the findIndex method
Similar to the find method, but instead of finding the element it returns the index of the found element instead.

![[SitApp_rZiAC9IMA0.png]]

### Some and Every methods

#### Some
Similar to the includes method, but instead of testing for equality, we can test for a certain condition.

![[GbPQyT4nC2.png]]

#### Every
Similar to the some method, but only returns true if all the elements pass the condition we pass in.

### Flat and flatMap

Great for nested arrays!

#### Flat

Flattens arrays of arrays into one array:

![[MdTpmu2YL1.png]]

Flat method only goes one level deep of arrays unless we pass in the depth argument:

![[Code_HpSaOw3w2h.png]]

![[Code_MKPrMDOxh7.png]]

#### flatMap
It's pretty common to first map an array and the use the flat method, so we can use the flatMap method instead:

![[Code_LEK20vI0yk.png]]

Note: Flatmap only goes one level deep.

## Sorting Arrays
By default, the sort method sorts alphabetically, even numbers in an array. This is because the sort method sorts numbers as if they were strings, like in example below:

![[chrome_4THk8UrP9h.png]]

We can change the default for numbers by passing in a callback function:

![[chrome_YO8HhH1edc.png]]

Note: This mutates the original array.

Here's a simplified version of this:

![[chrome_ao7G1rC83B.png]]

## More ways of creating and filling arrays
#### Fill method:

![[SitApp_OjybcOirnF.png]]

![[SitApp_GabMlgtc3T.png]]

Doesn't have to be empty array.

#### Array.from
![[SitApp_pexauXHfnR.png]]

![[SitApp_brkFjzNRQH.png]]

## Which array method to use? 

![[k1nOgcSQm9.png]]