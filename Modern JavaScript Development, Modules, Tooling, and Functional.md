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

