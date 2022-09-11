# Asynchronous [[JavaScript]]: Promises, Async/Await, and AJAX
## Asynchronous JavaScript, AJAX and APIs
Syncronous code:
![[Screenshot 2022-09-10 at 12.24.58.png]]

Asyncronous code:
![[Screenshot 2022-09-10 at 12.29.51.png]]

![[Screenshot 2022-09-10 at 12.33.32.png]]

What are AJAX Calls?
![[Screenshot 2022-09-10 at 12.36.04.png]]

What is an API?
![[Screenshot 2022-09-10 at 12.42.14.png]]

## Our first AJAX Call: XMLHttp Request
In JavaScript there are multiple ways of doing AJAX calls, but starting with the most old school way:

![[Screenshot 2022-09-10 at 14.00.24.png]]

![[Screenshot 2022-09-10 at 14.00.44.png]]
If we call this function multiple times, and reload the page a few times, we will get the countries in a different order. This is because it is non blocking, and we may get the data back in a different order.

## How the Web Works: Requests and Responses
What happens when we access a webserver:
![[Screenshot 2022-09-10 at 14.10.14.png]]

![[Screenshot 2022-09-10 at 14.24.35.png]]


## Welcome to Callback Hell
In our first AJAX call example, as we called the function multiple times - we made multiple AJAX calls at the same time. As they were running in paralel, and we could not control which one finished first.

Lets say we want to get data about a certain country, and then make a call about the neighbouring country and display it next to the first one. Here we would NEED the order to matter. So we need to implement a sequence of AJAX calls.

![[Screenshot 2022-09-10 at 14.52.04.png]]

In the code above we have callbacks inside of callbacks, imagine if we then wanted to get the neighbours, neighbours country and so on. 

- Callback hell is when have a lot nested callbacks, in order to execute async tasks in sequence.
- This happens for all async tasks which are handled by callbacks, not just AJAX calls.

Another, more obvious example of callback hell:

![[Screenshot 2022-09-10 at 14.58.14.png]]

## Promises and the Fetch API
Transforming the 'old' method of using AJAX calls from the previous example into the new modern way using the fetch API:

![[Screenshot 2022-09-10 at 19.40.14.png]]
![[Screenshot 2022-09-10 at 19.40.51.png]]

What are promises?

![[Screenshot 2022-09-10 at 19.44.28.png]]

![[Screenshot 2022-09-10 at 19.48.43.png]]

## Consuming Promises
![[Screenshot 2022-09-10 at 20.03.34.png]]

![[Screenshot 2022-09-10 at 20.03.48.png]]
Simplifing the code from above using arrow functions:

![[Screenshot 2022-09-10 at 20.06.21.png]]

## Chaining Promises
Creating the functionality from before of been able to add neighbour countries based on the first country:

![[Screenshot 2022-09-10 at 20.19.26.png]]
![[Screenshot 2022-09-10 at 20.19.39.png]]
Here, instead of having callback hell, we now have easier to read code. This is called a 'flat chain of promises'.
## Handling Rejected Promises
In promises we can get a failed to fetch error if the user loses internet connection while trying to make a request, so we have to handle these rejected promises:

![[Screenshot 2022-09-11 at 17.17.56.png]]

There are two ways on handling rejections in promises:

The first is passing a second callback function into the .then method on the fetch method -
![[Screenshot 2022-09-11 at 17.22.54.png]]
![[Screen Recording 2022-09-11 at 17.22.19.mov]]

We have now 'handled/caught' the error. But what if we first fetch on the first country was succesful but the second one failed?

Instead of having to add another callback for each fetch request we can add the catch method to the end of the chain, and it will still catch any errors no matter where they are in the chain:

![[Screenshot 2022-09-11 at 17.36.45.png]]

![[Screenshot 2022-09-11 at 17.36.58.png]]

So .then callback will only be executed if we get a 