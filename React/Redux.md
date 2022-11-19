## What is Redux?
Redux is a state-management system for cross component or app-wide state.

![[Screenshot 2022-11-17 at 14.55.52.png]]

## Redux vs React Context

![[Screenshot 2022-11-17 at 15.02.45.png]]

## How Redux Works
Core Redux concepts:
- central data (state) store
- components never directly manipulate the store data
- we use a concept called reducers (functions)
- components 'dispatch(trigger)' certain 'actions' that are forwarded to the reducer

![[Screenshot 2022-11-17 at 17.06.58.png]]

![[Screenshot 2022-11-17 at 17.15.58.png]]

## Redux & Side Effects (and Asynchronous code)
