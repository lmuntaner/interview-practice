# React Questions

From [this](https://dev.to/tylermcginnis/react-interview-questions) article and others.

**What is the virtual DOM?**

**What is a High Order Component? Some use cases.**

**Why ReactJS uses className over class attribute?**

**What happens when you call setState?**

The first thing React will do when setState is called is merge the object you passed into setState into the current state of the component.

This will kick off a process called reconciliation.

**What is the reconciliation process.**

The end goal of reconciliation is to, in the most efficient way possible, update the UI based on this new state.

To do this, React will construct a new tree of React elements.

React will diff this new tree against the previous element tree.

By doing this, React will then know the exact changes which occurred, and by knowing exactly what changes occurred, will able to minimize its footprint on the UI by only making updates where absolutely necessary.

**What's the difference between an Element and a Component in React?**

Simply put, a React element describes what you want to see on the screen.

A React component is a function or a class which optionally accepts input and returns a React Element or another React Component (typically via JSX).

**What is JSX?**

[JSX Live Compiler](https://jsbin.com/hajabex/2/edit?output)

**What are refs in React?**

Refs are an escape hatch which allow you to get direct access to a DOM element or an instance of a component.

**What are keys in React and why are they important?**

There are classic diffing algorithms with O(n³) time complexity, which might be used for creating a tree of React elements. Those are not performant enough.

Instead, React implements a heuristic O(n) algorithm with an assumption that the developer can hint at which child elements may be stable across different renders with a key prop.

Keys are what help React keep track of what items have changed, been added, or been removed from a list.

It's important that each key be unique among siblings.

**What is the difference between a controlled component and an uncontrolled component?**

A controlled component is a component where React is in control and is the single source of truth for the form data.

An uncontrolled component is where your form data is handled by the DOM, instead of inside your React component.

**Which is the suggested React Way? Controlled or Uncontrolled components? Why?**

It's typically recommended that you favor controlled components over uncontrolled components. The main reasons for this are that controlled components support instant field validation, allow you to conditionally disable/enable buttons, enforce input formats, and are more "the React way".

**What does shouldComponentUpdate do and why is it important?**

It's a lifecycle method that allows us to opt out of this reconciliation process for certain components.

**What is the second argument that can optionally be passed to setState and what is its purpose?**

A callback function which will be invoked when setState has finished and the component is re-rendered.

Something that's not spoken of a lot is that setState is asynchronous, which is why it takes in a second callback function. Typically it's best to use another lifecycle method rather than relying on this callback function, but it's good to know it exists.

**What is wrong with this code?**

```javascript
this.setState((prevState, props) => {
  return {
    streak: prevState.streak + props.count
  }
})
```

Nothing is wrong with it 🙂. It's rarely used and not well known, but you can also pass a function to setState that receives the previous state and props and returns a new state, just as we're doing above. And not only is nothing wrong with it, but it's also actively recommended if you're setting state based on previous state.

**How React Event system is different from DOM event system?**

Explain the Synthetic Event wrapper.

Event object is reused.

Returning `false` does not stop propagation.

React doesn’t actually attach events to the child nodes themselves. React will listen to all events at the top level using a single event listener.

This is good for performance and it also means that React doesn’t need to worry about keeping track of event listeners when updating the DOM.

**How to prevent components from re-rendering?**

There are different options:

* `shouldComponentUpdate` method
* `PureComponent` React Component
* `React.memo` hoc

