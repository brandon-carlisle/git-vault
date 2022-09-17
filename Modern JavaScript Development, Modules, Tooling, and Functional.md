# Modern [[JavaScript]] Development: Modules, Tooling, and Functional
## An Overview of Modern JavaScript Development

![[Screenshot 2022-09-14 at 19.05.16.png]]

## An Overview of Modules in JavaScript
![[msedge_wW77rb6WeY.png]]

![[msedge_FNBwHbUt5j.png]]

![[msedge_fNii2sqNZN.png]]

## Exporting and Importing in ES6 Modules
To create a new module:

Create a file with its name in camelCase. Import the module with its file path. Add module type to script tag in HTML.

![[Screenshot 2022-09-15 at 16.57.28.png]]
![[Screenshot 2022-09-15 at 16.57.40.png]]
Notice the exporting module log gets ran first.

Defining variables:

Variables that are defined inside a module, are scoped to that module (by default, all top level variables are private inside that module).

![[Screenshot 2022-09-15 at 17.01.42.png]]
![[Screenshot 2022-09-15 at 17.01.53.png]]
If we wanted to use these variables inside the script.js module, then we would have to use exports:

In ES Modules, there are two types of exports - named exports and default exports.

Using named exports/imports:

![[Screenshot 2022-09-15 at 17.07.30.png]]
![[Screenshot 2022-09-15 at 17.07.40.png]]
Notice with named imports we need to make sure the name is the same of the thing we want to inport, and to add the curly braces when we import it.

Exports always need to happen in top level code!

Exporting multiple things from a module using names exports:

![[Screenshot 2022-09-15 at 17.14.47.png]]
![[Screenshot 2022-09-15 at 17.14.57.png]]
We can use aliases (change the name) of these imports like this:

![[Screenshot 2022-09-15 at 17.16.13.png]]
This also works in the export as well ^.

We can also import all the exports of a certain module at the same time

This works like importing an object, so see syntax below on how to use from the shopping cart module:

![[Screenshot 2022-09-15 at 17.21.26.png]]

---------------------

Default Exports:

Usually we use default exports when we only want to export one thing per module.

![[Screenshot 2022-09-15 at 17.43.21.png]]
![[Screenshot 2022-09-15 at 17.43.29.png]]
We can give the import any name we want using default exports.

Note: Try not to mix named imports with default imports.

## Top-Level await (ES2022)
In ES2022, we can now use the await keyword outside of async functions, this only works in modules.

Demo with a fetch request:

![[Screenshot 2022-09-16 at 14.24.51.png]]

This looks great but it actually blocks the execution on the entire module now. This wasn't the case while using async functions. This can be useful in some situations, but most of the time not.

Many times, we have a situation where we do have an async function that we want to return some data.

Here we just want to return the last post from some API, using an async function. As it is an async function, whenever we return something from it, it will always return a promise. 

![[Screenshot 2022-09-16 at 14.38.22.png]]
![[Screenshot 2022-09-16 at 14.38.38.png]]
The way to get around the before would be to then call the .then method on the returned value, but this looks messy.

We can use top level await here on the returned value of the function call to get the data from it, and not the promise:

![[Screenshot 2022-09-16 at 14.40.23.png]]
![[Screenshot 2022-09-16 at 14.40.32.png]]

Another implication of using top level await is that, if one module imports a module that has a top level await - then the importing module will wait for the imported module to finish the blocking code.

## The Module Pattern
The module pattern is the 'old way' of implementing modules in JavaScript. Just like in regular modules, the main goal of the module pattern is to encapsulate functionality, to have private data and to expose a private API.

The best way of doing all that is, by using a function. Functions give us private data by default, and return values (which can become our public api).

How the module pattern is implemented:

We start with an IIFE, because then we don't need to call it ourselfs, and we can ensure it is called immedietly and once.

The only purpose of the IIFE is to create a new scope, and return data once.

![[Screenshot 2022-09-16 at 14.58.27.png]]
Right now all of the data is private, because it is inside the scope of the function.
All we have to do is to return some of the data to make it public and store the IIFE into a variable.

![[Screenshot 2022-09-16 at 15.02.08.png]]
Now we can access the data we made available outside of the function.

![[Screenshot 2022-09-16 at 15.04.59.png]]
![[Screenshot 2022-09-16 at 15.05.13.png]]
Even though the IIFE has actually finished running already, and we can still access the data that we returned, is because of closures! 

Closures allow a function to have access to all the variables that were present at its birthplace.

The problem with the module pattern is, if we wanted one module per file we would have to create different scripts and link all of them in the HTML file. This makes it difficult, because we have to be careful on the order in which we link them etc. We also wouldn't be able to bundle them together using a module bundler such as parcel and webpack.

## CommonJS Modules
Besides native ES Modules and the module pattern, there are also other module systems that have been used in the past.

Two examples are AMD modules and CommonJS modules.

CommonJS modules are important because they have been used in Node.js for all of its existence. Almost all the modules in the NPM repo, use CommonJS module system.

What does it look like?

![[Screenshot 2022-09-16 at 15.49.57.png]]

## Review: Writing Clean and Modern JavaScript
![[Screenshot 2022-09-17 at 21.19.03.png]]

![[Screenshot 2022-09-17 at 21.22.39.png]]

## Declarative and Functional JavaScript Principles
