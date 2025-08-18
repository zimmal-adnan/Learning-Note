# LEARNING NOTES

## Setup

- Go to the terminal and write `npm create vite@latest` then follow the steps.
- If you want redux write `npm install redux`
- If you are using it for React do `npm install redux react-redux`
  - For the redux logger use `npm install redux-logger`

## What is React Redux?

- React Redux is a state container
  - Instead of prop drilling, states will be held inside a store.
  - The states can be accessed by any component in a much modular manner.

## The Three Core Concepts in Redux

- Store:

  - One store for the entire application.
  - Holds the state of the application.
  - Allows access to state with `getState()`
  - Allows state to be updated when the component sends a `dispatch(action)`

- Action:
  - Describes changes in the application.
  - Carries information from the component to the redux store.
  - Plain JS objects.
  - 'type' property indicates the type of action being performed.
- Reducer:
  - Ties the store and actions together.
  - Carries out the state changes depending on the action.

## The Main Flow

- Component:
  - App loads the initial state defined in the Reducer (`useSelector()` gives the current state of the user).
- Action:
  - The `dispatch(Action Creator Function)` in the component calls the action creator (in the 'actions' file) which creates an action object.
  - The `dispatch` sends this action object to the Redux store.
- Reducer:
  - Store forwards the action object to the reducer.
  - Reducer returns a new state object with updated values.
- Store:
  - The state inside the store updates.
  - Store notifies React about the change
- Component:
  - React re-renders it with the new data (with the help of `useSelector()`)
