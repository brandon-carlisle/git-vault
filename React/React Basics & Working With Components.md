## What Are Components? And Why Is React All About Them?
To make building complex UI's, React embraces a concept called 'components'. - React is all about components.

All user interfaces in the end, are made up of components.

Components are - resuable building blocks in your user interface. Components in the end are just a combination of HTML, CSS and possibly JavaScript code (incase you need logic).

You don't have to reuse a component to make it a component, it is just one of its traits that it is reusable.

We build all these individual components and then we tell React how to compose them together into a final UI.

## React Code Is Written In A "Declarative Way"!
React uses a 'declarative' approach for building components.

We just need to define the desired target state(s) and let react figure out the actual JavaScript DOM instructions.

## Writing More Complex JSX Code
In react, we can write HTML inside of JavaScript using something called JSX.

![[Screenshot 2022-09-29 at 18.07.12.png]]

In a react component, we can only return one 'root' element. A workaround of this is to just wrap our JSX inside of another div like in the example above.

## Outputting Dynamic Data & Working with Expressions in JSX
We can pass in JS values just like we were using template literals, but we just use the curly braces to do this:

![[Screenshot 2022-09-29 at 18.30.15.png]]

## Passing Data via "props"
In react we can make our components reusable by passing in parameters and using a concept called props.

![[Screenshot 2022-09-30 at 14.09.40.png]]

- Components can't just use data stored in other components.

Instead of this, we can pass data to the custom component by adding an attribute, and then inside of the custom component we get access to these attributes.

Just as HTML elements can have attributes, in React, our own custom components can also have attributes - this concept is just called 'props' which just means properties.

- We can set properties (props) of our own custom compoenents.

