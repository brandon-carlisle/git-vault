# Numbers, Dates, Intl and Timers in [[JavaScript]]
## Converting and Checking Numbers
In JavaScript, all numbers internally are represented as floating point numbers.

MDN Docs on Number methods: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number#static_properties

## Math and Rounding
MDN Docs on Math and rounding methods: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math#static_methods

## The Remainder Operator
It simply returns the remainder of a division. 

![[Screenshot 2022-08-06 at 12.53.06.png]]

We can use the remainder operator to check if a number is even or odd. If we take any number and (x % 2), if it is even the result will be 0, if not it will be odd.

![[Screenshot 2022-08-06 at 12.59.56.png]]

Whenever we need to do something every (n)th time, we can use the remainder operator, like this we color each every second row of our app:

![[Screenshot 2022-08-06 at 13.10.56.png]]

![[Screenshot 2022-08-06 at 13.11.27.png]]

## Numeric Separators
Starting for ES2021 we can use a feature called numeric separators to format numbers in a way that is easier for us and other developers to read and understand.

We can use underscores as 'thousand' markers, like we would in real life when writing large numbers to make it much easier to read:

![[Screenshot 2022-08-06 at 13.18.42.png]]

## Working with BigInt
BigInt is a special type of integer that was introduced in ES2020. Numbers are represented internally as 64 bits (exactly 64 1's or 0's to represent any number), but only 53 bits are used to store the digits themselves, the rest are used to store the position of the decimal point and the sign.

If there are only 53 bits to store the number, that means there is a limit on how big the number can be.

![[Screenshot 2022-08-07 at 17.26.30.png]]
![[Screenshot 2022-08-07 at 17.26.54.png]]
This is the largest number we can store safely in JS. (aka we will lose precision when working with a number bigger than this)

There might be situations where we do need