# General Programming Questions

**What is currying?**



**Can you name two programming paradigms important for JavaScript app developers?**

JavaScript is a multi-paradigm language, supporting imperative/procedural programming along with OOP (Object-Oriented Programming) and functional programming. JavaScript supports OOP with prototypal inheritance.

Red flags:
No clue what a paradigm is, no mention of prototypal oo or functional programming.

**What is functional programming?**

Functional programming produces programs by composing mathematical functions and avoids shared state & mutable data.

Good to hear:
- Pure functions / function purity.
- Avoid side-effects.
- Simple function composition.
- Examples of functional languages: Lisp, ML, Haskell, Erlang, Clojure, Elm, F Sharp, OCaml, etc…
- Mention of features that support FP: first-class functions, higher order functions, functions as arguments/values.

Red flags:

- No mention of pure functions / avoiding side-effects.
- Unable to provide examples of functional programming languages.
- Unable to identify the features of JavaScript that enable FP.

**What is the difference between classical inheritance and prototypal inheritance?**

*Class Inheritance*

Instances inherit from classes (like a blueprint — a description of the class), and create sub-class relationships: hierarchical class taxonomies.

Instances are typically instantiated via constructor functions with the `new` keyword. Class inheritance may or may not use the `class` keyword from ES6.

*Prototypal Inheritance*

Instances inherit directly from other objects.

Instances are typically instantiated via factory functions or `Object.create()`.

Instances may be composed from many different objects, allowing for easy selective inheritance.

Red Flags:
- No preference for prototypal inheritance & composition over class inheritance.

**What does “favor object composition over class inheritance” mean?**

It means that code reuse should be achieved by assembling smaller units of functionality into new objects instead of inheriting from classes and creating object taxonomies.

In other words, use can-do, has-a, or uses-a relationships instead of is-a relationships.

Good to hear:

- Avoid class hierarchies.
- Avoid brittle base class problem.
- Avoid tight coupling.
- Avoid rigid taxonomy (forced is-a relationships that are eventually wrong for new use cases).
- Avoid the gorilla banana problem (“what you wanted was a banana, what you got was a gorilla holding the banana, and the entire jungle”).
- Make code more flexible.

Red Flags:

- Fail to mention any of the problems above.
- Fail to articulate the difference between composition and class inheritance, or the advantages of composition.

**What is asynchronous programming, and why is it important in JavaScript?**

Synchronous programming means that, barring conditionals and function calls, code is executed sequentially from top-to-bottom, blocking on long-running tasks such as network requests and disk I/O.

Asynchronous programming means that the engine runs in an event loop. When a blocking operation is needed, the request is started, and the code keeps running without blocking for the result. When the response is ready, an interrupt is fired, which causes an event handler to be run, where the control flow continues. In this way, a single program thread can handle many concurrent operations.

User interfaces are asynchronous by nature, and spend most of their time waiting for user input to interrupt the event loop and trigger event handlers.

Node is asynchronous by default, meaning that the server works in much the same way, waiting in a loop for a network request, and accepting more incoming requests while the first one is being handled.

Good to hear:

- An understanding of what blocking means, and the performance implications.
- An understanding of event handling, and why its important for UI code.

Red flags:

- Unfamiliar with the terms asynchronous or synchronous.
- Unable to articulate performance implications or the relationship between asynchronous code and UI code.
