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

So .then callback will only be executed if we get a successful promise, the .catch callback will only be executed if there is an error caught and finally, the .finally method will execute its callback no matter what. This is useful for things like that always need to happen at the end of a chain, such as a loading spinner:

![[Screenshot 2022-09-11 at 17.44.11.png]]

## Throwing Errors Manually
When we get a 404 from the API, such as searching for a country that doesn't exist, the promise doesn't actually get rejected.

![[Screenshot 2022-09-11 at 18.16.10.png]]
![[Screenshot 2022-09-11 at 18.16.23.png]]
Note: Can ignore the TypeError and focus on the GET 404 error.

We will have to reject the promise ourself, manually incase we get a 404 (ok: false):

![[Code_P8vIMCkvJu.png]]

First we check if the response .ok is falsy, then if it is, we create the new error (we throw) and pass in a message which will be the error message. Using the throw keyword will immedietly terminate the current function, just like return.

The effect of creating and throwing an error in any of the then methods will be that, the promise will be immeditely reject. So basically the promise returned by the .then method will be a rejected promise. The rejection will then propogate down to the catch handler that we made before.

So now we get the error message displayed:

![[chrome_B69rMiUP0R.png]]

Why should we bother handling these errors?

1) Handling these errors is the only we we can display an error message on the screen for a user
2) Bad practice to leave errors unhandled

What if the first fetch was successful but the second(neighbour) fetch was not? We could copy the throw new error code to the second fetch, but it would be repeatigng code. So refactoring and handling the second fetch:

![[Code_hjADNvV2U3.png]]
Exporting the functionality of getting the JSON and throwing an error.

![[Code_B77F6dSWvD.png]]
Calling that function inside of our original function and passing in the URL and error message we want to display.

## Asynchronous Behind the Scenes: The Event Loop
REVIEW: JAVASCRIPT RUNTIME

![[Screenshot 2022-09-12 at 20.03.43.png]]

HOW ASYNCHRONOUS JAVASCRIPT WORKS BEHIND THE SCENES

![[Screenshot 2022-09-12 at 20.21.58.png]]

## The Event Loop in Practice
1) Top level code gets executed first
2) async tasks run in the web API context such as fetching data or loading images
3) Microtasks (callbacks inside of promises) get prio over regular callbacks
4) All other callbacks that aren't in the microtask queue get executed sequentially

Demo:

![[Screenshot 2022-09-12 at 21.39.52.png]]

![[Screenshot 2022-09-12 at 21.40.22.png]]

## Building a Simple Promise
Building a promise based on the idea of the lottery - A fufilled promise means to win the lottery and a rejected promise means to lose the lottery:

The new Promise object takes in one arguement, which is the so called executor function. As soon as the promise contructor runs, it will automatically run the executor function that we pass in. 

As it runs the executor function, it will pass in two other arguments:
1) Resolve
2) Reject

The executor function will contain the async behaivour that we are trying to handle with the promise.

![[Code_o3VDeplvxW.png]]

![[Code_BUrseBtNAn.png]]
Encapsulating the promise function into some async code, such as a setTimeout function:

![[Screenshot 2022-09-13 at 14.24.19.png]]

Most of the time, we normally only consume promises. Sometime we only build promises to wrap old callback based functions into promises - which is a process called 'Promisification'.

Promisifying basically means to convert callback based asyncronous behavour to promise based.

Promisifying the setTimeout function:

![[Screenshot 2022-09-13 at 14.36.03.png]]

Consuming that promise:

![[Screenshot 2022-09-13 at 14.39.51.png]]

This is much better than the callback hell of the setTimeout that looked like this:

![[Screenshot 2022-09-13 at 14.44.18.png]]

VS

![[Screenshot 2022-09-13 at 14.46.10.png]]

Promisifying the geolocation API:

![[Screenshot 2022-09-13 at 15.07.21.png]]

## Consuming Promises with Async/Await
SInce ES2017 there is now an easier way to consume promises, called async/await.

We use the async keyword before the function, and then the code inside of the function will keep running in the backing. Then when the function is done, it will automatically return a promise.

Inside an async function, we can have one or more await statements:

![[Screenshot 2022-09-13 at 18.19.56.png]]

The await keyword will essentially wait for the result of the promise. Or you could say the await will stop the code execution at this point of the function until the promise is fufilled.

Isn't await stopping the execution and blocking a bad thing?
No, because the entire function is running asyncronously in the background, therefore it is not blocking the main thread of execution.

As soon at the fetch promise is resolved, then the value of whole await expression will be the resolved value of the promise.

![[Screenshot 2022-09-13 at 18.26.03.png]]

![[Screenshot 2022-09-13 at 18.26.17.png]]

Async/Await is simply just syntactic sugar over the .then method, we are still using promises, this is just a different way of consuming them.

Getting the data from the API using async await:

![[Screenshot 2022-09-13 at 18.35.39.png]]

We now no longer need to use the .then method, or return any promises manually ^.

![[Screenshot 2022-09-13 at 18.35.58.png]]

![[Screenshot 2022-09-13 at 18.45.51.png]]

![[Screenshot 2022-09-13 at 18.46.06.png]]

## Error Handling With try...catch
In async await functions we can't use the .catch method we were using before, because there isn't anything to attach it to, so we have to use try..catch statements (can be used seperately to async await)

Simple demo of try catch:

![[Screenshot 2022-09-13 at 19.53.37.png]]

The catch part will get access to any error that occurs inside of the try block. Then we can do something with it, such as displaying an alert with the error message.

![[Screenshot 2022-09-13 at 19.53.54.png]]

Handling errors in async await functions:

![[Screenshot 2022-09-13 at 19.58.06.png]]
All we need to do is to wrap our code inside of the async function into a catch...try block, and the error will propogate down like before.

Adding back the renderError function to display the error message on screen:

![[Screenshot 2022-09-13 at 20.02.43.png]]
![[Screenshot 2022-09-13 at 20.03.02.png]]
![[Screenshot 2022-09-13 at 20.03.28.png]]

Like before, the fetch won't reject the promise if there is an error such as a 403 or 404, so we need to manually throw an error, by checking if the response .ok is false or not:

![[Screenshot 2022-09-13 at 20.10.51.png]]

## Returning Values from Async Functions
Async functions automatically return a promise, see how we try to return something out of the async function, but when we log it to the console, we only get a promise and not the value we specified:

![[Screenshot 2022-09-13 at 20.21.42.png]]

![[Screenshot 2022-09-13 at 20.22.14.png]]

In a normal function, the return value would be 100 and we would see it in the console.

The value that we return from an async function (100), will become the fufilled value of the promise that is returned by the function.

Because a promise is returned, all we need to do is use .then on the promise:

![[Screenshot 2022-09-13 at 20.27.18.png]]
![[Screenshot 2022-09-13 at 20.27.34.png]]

## Running Promises in Parallel
Lets say we want to get data about 3 countries at the same time, but the order doesn't matter:

![[Screenshot 2022-09-14 at 14.34.32.png]]

Here, this looks right, but what we actually did was run each ajax call one after another, even though we don't need them in order.

We can see this in the network tab:

![[Screenshot 2022-09-14 at 14.39.11.png]]

Instead of running these promises in sequence, we can actually run them in parallel (all at the same time), meaning we save valuable loading time.

We do this by using the Promise.all() function, which takes in an array of promises, and it will return a new promise.

