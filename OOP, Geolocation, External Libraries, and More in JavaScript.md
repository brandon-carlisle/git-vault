# OOP, Geolocation, External Libraries, and More in [[JavaScript]]
## How to Plan a Web Project
![[Screenshot 2022-09-06 at 21.40.07.png]]

![[Screenshot 2022-09-06 at 21.47.11.png]]

![[Screenshot 2022-09-06 at 21.47.22.png]]

![[Screenshot 2022-09-06 at 21.53.54.png]]

![[Screenshot 2022-09-07 at 18.31.56.png]]


## Using the Geolocation API
![[Screenshot 2022-09-06 at 23.01.43.png]]


## Working with localStorage
We use local storage to persist data after page reload or closing the page.

Local storage is a simple key/value store, so we pass in a key as a string and a value as a string. We can pass objects in as values by using JSON stringify.

Setting local storage: 

![[Screenshot 2022-09-09 at 15.03.52.png]]

Getting local storage:

![[Screenshot 2022-09-09 at 15.13.03.png]]

When we convert objects to strings and then back to objects again, they will lose the prototype chain that we set up with classes. 

Del