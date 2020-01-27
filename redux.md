# Questions on Redux

**What is the flow of Redux?**

**What are the 3 principles of Redux?**

* Single source of truth
* State is Read only
* Changes are made with pure functions

**What is an Action?**

**Why is Redux so popular?**

**What is a Reducer?**

**What is `redux-thunk`? What does it do?**

**What is the Redux Middleware? What are some use cases?**

**Why is immutability important?**

**Redux style guide:**

Essential:

* Do not mutate state
* Reducers must have no side effects
* Do not put non-serializable values in State or Actions
* Only one Redux store per app

Strongly recommended:

* Use Redux Toolkit for writing Redux logic
* Use Immer for writing immutable updates
* Structure files as Feature folders or Ducks
* Put as much logic as possible in reducers
* Reducers should own state shape
* Name state slices based on stored data
* Treat reducers as state machines
* Normalize complex nested/relational state
* Model actions as events, not setters
* Write meaningful action names
* Allow many reducers to respond to the same action
* Avoid dispatching many actions sequentially
* Evaluate where each piece of state should live
* Connect more components to read data from the store
* Use the object shorthand form of `mapDispatch` with `connect`
* Call `useSelector` multiple times in function components
* Use static typing
* Use Redux DevTools Extensions for debugging

Recommended:

* Write actions types as `domain/event`
* Write actions using the Flux standard action convention
* Use Action creators
* Use thunks for async logic
* Move complex logic outside components
* Use selector functions to read from store state
* Avoid putting form state in Redux
