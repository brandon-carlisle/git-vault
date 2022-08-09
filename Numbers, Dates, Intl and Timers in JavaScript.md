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

------------------------------

There might be situations where we do need numbers bigger than this, such as when we work with database IDs or some data from API's. So we need to use BigInt.

We use the n prefix at the end of a large number to convert it to a bigint, like here:

![[Screenshot 2022-08-07 at 17.32.09.png]]
![[Screenshot 2022-08-07 at 17.32.38.png]]

When doing operations with bigints all the usual operators still work the same. We cannot mix BigInt numbers with regular numbers, otherwise we will get a TypeError.

The above statement is true apart from the comparison operator and the loose type equality operator ( == ).

## Creating Dates
In JavaScript there is 4 ways to make dates, but they all use the Date contructor. 

The first way is this:

![[Screenshot 2022-08-07 at 18.55.00.png]]
![[Screenshot 2022-08-07 at 18.56.04.png]]

The second way is to parse the date from a string like this:

![[Screenshot 2022-08-07 at 18.58.27.png]]
![[Screenshot 2022-08-07 at 18.58.52.png]]
The third way is we can pass numbers in to create a date:

![[Screenshot 2022-08-07 at 19.04.41.png]]
![[Screenshot 2022-08-07 at 19.05.00.png]]
Notice that the months are zero based, aka they start at 0 instead of one.

Finally we can also pass in the amount of milliseconds past, since the beggining of the unix time:

![[Screenshot 2022-08-07 at 19.16.28.png]]
![[Screenshot 2022-08-07 at 19.16.43.png]]

------------------------

These dates are just another type of special object, so they have methods like arrays or strings. We can use these methods to get or set components off a date.

![[Screenshot 2022-08-07 at 19.21.44.png]]
![[Screenshot 2022-08-07 at 19.22.05.png]]
Never use getYear, always use getFullYear!

Some more methods here:
MDN reference on Date methods: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date#instance_methods

## Operations with dates
We can do calculations with dates. For example, we can subtract one date from another date, to calculate the time between them, this works because whenever we attempt to convert a date to number - then the result will be the timestamp in milliseconds.

Here's a date converted to a number:

![[Screenshot 2022-08-09 at 15.35.27.png]]
![[Screenshot 2022-08-09 at 15.35.43.png]]

Once we've converted the date to a number (milliseconds), we can then do mathmatical operations on it and the convert it back to a date(hours,days etc).

Here's a functions that takes in to dates, and returns the number of days passed between them:

![[Screenshot 2022-08-09 at 15.45.25.png]]

If we need more precise calculations, including time changes due to daylight saving and other edge cases, we should use a date library like MomentJS.

## Internationalizing Dates (Intl)
JavaScript has a internationalisation API. It allows us to format numbers and strings according to different lanuages. With this, we can make our app support different languages for users around the world. For example, currencies or dates are represented in a completely different wayin Europe or the USA or Asia. 

![[Screenshot 2022-08-09 at 16.24.11.png]]
Here we created a new date as usual, then used the Intl namespace (api) + the DateTimeFormat method and passed in the "locale string" to tell JS the language and country of the date. Then we use the format method and pass in the date we originally created.

Result:

![[Screenshot 2022-08-09 at 16.27.49.png]]

List of locale strings to pass into DateTimeFormat: http://www.lingoes.net/en/translator/langcode.htm

We can customize this further, say if we want to display the minutes and hours as well as the date. We just need to create a config object (the options object in screenshot) and pass it as a second argument to the DateTimeFormat method:

![[Screenshot 2022-08-09 at 16.36.49.png]]

Result:

![[Screenshot 2022-08-09 at 16.37.08.png]]

In most cases we can not specify the locale manually and get it from the users browser:

![[Screenshot 2022-08-09 at 16.39.22.png]]

