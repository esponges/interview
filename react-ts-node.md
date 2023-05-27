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
- What's the DOM?
- How does the DOM differ from the Virtual DOM?
- Why React? Do you know other frameworks? How would you compare them?
- What is JSX? How it differs from markup languages like HTML?
- Do you know memoization? How would you implement it in React?
- What is the difference between `useMemo` and `useCallback`? When and why would you use each one?
- What the is a dependency array in React hooks? Why is it important?
- What could cause an infinite loop in React? How would you fix it?
- Do you know what is a Higher Order Component (HOC)? How would you implement it?


### Advanced
- To assess the performance of a React application: What would you do? What tools would you use? What metrics would you look at?
- What debugging tools do you use? How would you debug an unknown codebase?

## Coding
- What's an abstraction in programming? How would you implement it and why?
> An abstraction is a way of hiding the implementation details and showing only the functionality to the users. It helps the user to avoid writing the low-level code.


## TypeScript
- What is TypeScript? Why would you use it?
- What is the difference between `interface` and `type`?
- What's a generic type? How would you use it?
- Explain what's the type inference in TypeScript.

## Javascript
- What's a closure? How would you use it?
- What's currying? (hint: relates to invoking a closure fn like this: `fn(1)(2)(3)`)
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
- 
> A closure is a function that has access to its outer function scope even after the outer function has returned. This means a closure can remember and access variables and arguments of its outer function even after the function has finished.
- Please tell me about promises? Would you use async/await or then/catch? Why?
- What web APIs do you know? How would you use them?
- What's the difference between local storage and session storage and cookies?
> Local storage and session storage are both mechanisms that allow a browser to store key/value pairs locally within the user's browser. Cookies are small pieces of data that are stored on the client's browser. They are sent to the server with each request. Cookies are used to store user information such as preferences.
- When would you use a cookie over local storage?
> TODO: get details regarding to security, capacity, etc.
- Have you worked with advanced web APIs like IndexedDB, WebSockets, WebWorkers, etc?
- What does mutation mean? 
- What's a pure function? How would you implement it and why?
> It always returns the same result if the same arguments are passed in. It does not depend on any state, or data, change during a program’s execution. It must only depend on its input arguments. It cannot produce any side effect. It easy to test and debug.
> Make the candidate explain the difference between mutation and reassignment. (Hint: use `const` with `Array.push` and `let` to explain the difference)
- What's the difference between `==` and `===`?
