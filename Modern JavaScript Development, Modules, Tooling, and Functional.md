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

