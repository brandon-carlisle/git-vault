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

