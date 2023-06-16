This is a set of questions and answers about React, TypeScript, and Node.js. It is a work in progress.

# Table of Contents
## React
* Basic
- What's the difference between a class component and a functional component? Which one should I use?

- What are the main lifecycle methods in React? What are they used for? If you have knowledge both in class and functional components how would you compare them?

- What is the difference between state and props?

- What's a global store? What's the difference between it and a state? When you should use each one?

- How would can you updated a value without re-rendering the component? (Hint: use `useRef` hook)

- What is the difference between controlled and uncontrolled components?
> A controlled component is a component that renders form elements and controls them by keeping the form data in the component's state. An uncontrolled component is a component that renders form elements and controls them by using refs to get their values.

- What's the DOM?

- How does the DOM differ from the Virtual DOM? Do you know what's the reconciliation process?

- What is the `key` prop? Why is it important when rendering lists of elements? Why is bad to use the index as the key?

- Why React? Do you know other frameworks? How would you compare them?

- What is JSX? How it differs from markup languages like HTML?

- Do you know memoization? How would you implement it in React?

- What is the difference between `useMemo` and `useCallback`? When and why would you use each one? What's React.memo?

- What the is a dependency array in React hooks? Why is it important?

- What could cause an infinite loop in React? How would you fix it?

- Do you know what is a Higher Order Component (HOC)? How would you implement it? Why would you use HOCs?
> A HOComponent is a function that takes a component and returns a new enhanced component. It's used to share common functionality between components without repeating code.


### Advanced
- To assess the performance of a React application: What would you do? What tools would you use? What metrics would you look at?

- What debugging tools do you use? How would you debug an unknown codebase?

- What's the difference between `==` and `===`? And why is it important in React?
> `==` compares the values of the variables and `===` compares the type and the value of the variables _and_ memory location. In react is important to use __reference equality__ since it's used by the hooks dependencies array to determine if the component should re-render/update or not.

- How would you change the shape of data that changes frequently inside a component? (Hint: use `useMemo` hook, use `useState` and `useEffect` hooks)

- How do you usually organize your React code? What are the main folders and files you use?

- Have you heard of SSR? What is it? How would you implement it and why?

## Coding
- What's an abstraction in programming? How would you implement it and why?

> An abstraction is a way of hiding the implementation details and showing only the functionality to the users. It helps the user to avoid writing the low-level code.

- It's required to investigate an implementation of a new feature, this feature is something you've never seen before. How would you approach this task?

- You're required to contribute in a language/framework you've never used before. You're not sure if you'll ever have to contribute again to that project. How would you approach this task?

- Have you heard about the SOLID principles? What are they? Can they be applied to React? How?

- What's an MVC? Can it be applied to React? How?

## TypeScript
- What is TypeScript? Why would you use it?

- What are the main mistakes/errors that TypeScript helps to avoid?

- What is the difference between `interface` and `type`?

- What's a generic type? How would you use it?

- Explain what's the type inference in TypeScript.

## Javascript
- What's a closure? How would you use it?Why to use it? 

> A closure is a function that returns another function and has access to the scope of the outer function. It's used to encapsulate data and behavior. To create private variables and methods. When you know the arguments of the outer function ahead of time but you may not know the arguments of the inner function until it is invoked and it's used by several functions with different outer arguments. 
```javascript
function outer() {
  let counter = 0;
  function inner() {
    counter++;
    console.log(counter);
  }
  return inner;
}
```

- What's currying? (hint: relates to invoking a closure fn like this: `fn(1)(2)(3)`)

- When would you curry a function? and a closure?
> When you know the arguments for the closure function ahead of time, you can use currying to create a new function with the arguments already set.
> A closure is a function that has access to its outer function scope even after the outer function has returned. This means a closure can remember and access variables and arguments of its outer function even after the function has finished.

- Please tell me about promises? Would you use async/await or then/catch? Why?

- What web APIs do you know? How would you use them?

> Web APIs are APIs that can be accessed using the browser. They are built into the browser and are able to expose data from the browser and surrounding computer environment and do useful complex things with it. They are not part of the JavaScript language itself, rather they are built on top of the core JavaScript language, providing you with extra superpowers to use in your JavaScript code. 

> The most common web APIs are:
> - DOM API
> - Fetch API
> - Web Storage API
> - Web Audio API
> - Web Socket API
> - Web Workers API

- Have you worked with advanced web APIs like IndexedDB, WebSockets, WebWorkers, etc?

- What's the difference between local storage and session storage and cookies?

> Local storage and session storage are both mechanisms that allow a browser to store key/value pairs locally within the user's browser. Cookies are small pieces of data that are stored on the client's browser. They are sent to the server with each request. Cookies are used to store user information such as preferences.
- When would you use a cookie over local storage?

> Cookies will be used when you want to have user information that can be accessed by the server and can be sent to the server, while local storage can't be directly sent. Local storage will be used when you want to store user information that can be accessed by the client. Local storage has more capacity than cookies. Cookies can be expired. Local storage is a bit slower than cookies since it lives in the user hard drive while cookies live in the browser memory.

- What does mutation mean? When is okay to mutate? When is not okay to mutate?

> Mutation is when you change the value of a variable after it has been initialized. It's a change in the state of an object or variable. It's a side effect. It's not okay to mutate when you are using a pure function. It's okay to mutate when you are using a closure function.

- What's a pure function? How would you implement it and why?
> It always returns the same result if the same arguments are passed in. It does not depend on any state, or data, change during a program’s execution. It must only depend on its input arguments. It cannot produce any side effect. It easy to test and debug.
> Make the candidate explain the difference between mutation and reassignment. (Hint: use `const` with `Array.push` and `let` to explain the difference)

- Why do we say that Javascript is a single-threaded language? How it relates to the event loop?
