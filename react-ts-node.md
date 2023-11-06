This is a set of questions and answers about React, TypeScript, and Node.js. It is a work in progress.

# Table of Contents
## React
* Basic
- What's the difference between a __class component__ and a __functional component__? Which one should I use?

- What are the main __lifecycle methods__ in React? What are they used for? If you have knowledge both in class and functional components how would you compare them?

- What is the difference between __state and props__?

- What's a __global store__? What's the difference between it and a state? When you should use each one?

- How would can you __update__ a value __without re-rendering__ the component? (Hint: use `useRef` hook)

- What is the difference between __controlled and uncontrolled components__?

> A controlled component is a component that renders form elements and controls them by keeping the form data in the component's state. An uncontrolled component is a component that renders form elements and controls them by using refs to get their values.

- What's the __DOM__?

- How does the DOM differ from the __Virtual DOM__? Do you know what's the reconciliation process?

- What is the __`key`__ prop? Why is it important when rendering lists of elements? Why is bad to use the index as the key?

- Why React? Do you know __other frameworks__? How would you compare them?

- What is __JSX__? How it differs from markup languages like HTML?

- Do you know __memoization__? How would you implement it in React?

- What is the difference __between `useMemo` and `useCallback`__? When and why would you use each one? What's React.memo?

- What the is a __dependency array__ in React hooks? Why is it important?

- What could cause an __infinite loop__ in React? How would you fix it?

- Do you know what is a __Higher Order Component (HOC)__? How would you implement it? Why would you use HOCs?

> A HOComponent is a function that takes a component and returns a new enhanced component. It's used to share common functionality between components without repeating code.

- Its considered a bad practice to __change a DOM element directly__. How would you do it in React?

> Using refs (or getElementyBy) to directly manipulate the DOM is generally not recommended in React, as it can lead to hard-to-debug issues and make the code harder to maintain. Instead, it's usually better to use state and props to manage the content of your components.


### Advanced
- To __assess the performance__ of a React application: What would you do? What tools would you use? What metrics would you look at?

- What __debugging tools__ do you use? How would you debug an unknown codebase?

- What's the difference between `==` and `===`? And why is it important in React?

> `==` compares the values of the variables and `===` compares the type and the value of the variables _and_ memory location. In react is important to use __reference equality__ since it's used by the hooks dependencies array to determine if the component should re-render/update or not.

- How do you usually __organize your React code__? What are the main folders and files you use?

- Have you heard of __SSR__? What is it? How would you implement it and why?

- Whats a __barrel file__? How would you use it?

> A barrel file is a way to rollup exports from several modules into a single convenient module. It's used to group exports from several files into a single file.

- What's the difference between `export default` and `export`? How would you use them?

> `export default` is used to export a single class, function, or primitive from a script file. `export` is used to export multiple classes, functions, or primitives from a script file.

- What's __tree shaking__? How is it related with performance?

> Tree shaking is a process that removes unused code from the bundle. It's related to performance because it reduces the size of the bundle.

- In a React Component method (eg. handleClick) can you `return` a `setState`? Why?

> No, `setState` cannot be returned from a handler. It must be invoked directly or React won't schedule a re-render.

- What's the use for `dangerouslySetInnerHTML`? Why is it dangerous?

> It's used to set the HTML of an element, for example, when you want to render HTML from a CMS like a `<p>hello</p>` tag. It's dangerous because it can lead to XSS attacks since a user can insert malicious code by for example adding a `<script>` tag.

- Why do we need to __build__ a React application? How does the build size affects the end user?

## Coding
- What's an __abstraction__ in programming? How would you implement it and why?

> An abstraction is a way of hiding the implementation details and showing only the functionality to the users. It helps the user to avoid writing the low-level code.

- It's required to __investigate an implementation of a new feature__, this feature is something you've never seen before. How would you approach this task?

- You're required to __contribute in a language/framework you've never used before__. You're not sure if you'll ever have to contribute again to that project. How would you approach this task?

- Have you heard about the __SOLID principles__? What are they? Can they be applied to React? How?

1. __Single Responsibility Principle__ (SRP): A component should have one and only one reason to change, meaning that a component should have only one job. Eg. a component should only render a list of items, not fetch the data and render the list.
2. __Open/Closed Principle__ (OCP). A component should be open for extension but closed for modification. Eg. a component should be able to be extended to render a list of items in a table or in a list. Splitting the code in small components (atomic design) will help to achieve this.
3. __Liskov Substitution Principle__ (LSP). A component should be replaceable with its subtypes without altering the correctness of the program. Eg. a component should be able to be replaced by a component that renders a list of items in a table or in a list.
4. __Interface Segregation Principle__ (ISP). A component should not be forced to implement methods that it does not use. Eg. a component should not be forced to implement a method to fetch data if it's not going to use it or receive objects with unnecessary properties. In React, a component could be receiving props that doesn't require, for example in an object, where we'd just needs partial elements of it.
5. __Dependency Inversion Principle__ (DIP). A component should not depend on another component. It should depend on abstractions. Eg. a component should not depend on a component that fetches data. It should depend on an abstraction that fetches data, for example a custom hook, or a library such as React Query for handling data fetching in an abstract way.

A great article (here)[https://www.everydayreact.com/articles/solid-principles-in-react]

- What's an __MVC__? Can it be applied to React? How?

> MVC stands for Model View Controller. It's a software design pattern that separates the data from the presentation. It can be applied to React by using Redux. Redux is a state management library that follows the MVC pattern. 

The user _acts_ with using an action creator. The action creator _dispatches_ an action. The action _updates_ the store with a reducer. The store _notifies_ the view. The view _re-renders_.

- What's __data serialization__? Why is it important?

> When serializing data you are converting data into a format that can be stored or transmitted and reconstructed later even by different applications. The most common types of serialization are JSON and XML. Serialization could lead to performance and security issues if not done properly.

## TypeScript
- __What is TypeScript__? Why would you use it?

- What are the __main mistakes/errors__ that TypeScript helps to avoid?

- What is the __difference__ between `interface` and `type`?

- What's a __generic type__? How would you use it?

- Explain what's the __type inference__ in TypeScript.

- How does the __error checking in TypeScript__ works in our IDE? Why it's better than using __PropTypes__?

> The IDE uses the TypeScript compiler to check for errors. The TypeScript compiler is a program that runs in the background and checks for errors. It's configured in the `tsconfig.json` file. It's better than PropTypes because it checks for errors in the whole codebase, not only in the component where the PropTypes are defined and will throw errors only during runtime. 

## Javascript
- What's a __closure__? How would you use it?Why to use it? 

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

- What's __currying?__ (hint: relates to invoking a closure fn like this: `fn(1)(2)(3)`)

- __When would you__ curry a function? and a closure?

> When you know the arguments for the closure function ahead of time, you can use currying to create a new function with the arguments already set.
> A closure is a function that has access to its outer function scope even after the outer function has returned. This means a closure can remember and access variables and arguments of its outer function even after the function has finished.

- Please tell me about __promises__? Would you use async/await or then/catch? Why?

- What __web APIs__ do you know? How would you use them?

> Web APIs are APIs that can be accessed using the browser. They are built into the browser and are able to expose data from the browser and surrounding computer environment and do useful complex things with it. They are not part of the JavaScript language itself, rather they are built on top of the core JavaScript language, providing you with extra superpowers to use in your JavaScript code. 

> The most __common web APIs__ are:
> - DOM API
> - Fetch API
> - Web Storage API
> - Web Audio API
> - Web Socket API
> - Web Workers API

- Have you worked with __advanced web APIs__ like IndexedDB, WebSockets, WebWorkers, etc?

- What's the `window` object? Why is it important?
> The window object represents the browser's window. It's the global object in the browser. It's used to access the browser's history, location, document, and other properties of the browser window. It's only available client-side. As a Javascript developer you will require the window object to anything related to the browser APIs like the DOM, cookies, local storage, etc.

- What's the difference between __local storage and session storage and cookies__?

> Local storage and session storage are both mechanisms that allow a browser to store key/value pairs locally within the user's browser. Cookies are small pieces of data that are stored on the client's browser. They are sent to the server with each request. Cookies are used to store user information such as preferences.

- When would you use a __cookie over local storage__?

> Cookies will be used when you want to have user information that can be accessed by the server and can be sent to the server, while local storage can't be directly sent. Local storage will be used when you want to store user information that can be accessed by the client. Local storage has more capacity than cookies. Cookies can be expired. Local storage is a bit slower than cookies since it lives in the user hard drive while cookies live in the browser memory.

- What does __mutation__ mean? When is okay to mutate? When is not okay to mutate?

> Mutation is when you change the value of a variable after it has been initialized. It's a change in the state of an object or variable. It's a side effect. It's not okay to mutate when you are using a pure function. It's okay to mutate when you are using a closure function.

- What's a __pure function__? How would you implement it and why?

> It always returns the same result if the same arguments are passed in. It does not depend on any state, or data, change during a program’s execution. It must only depend on its input arguments. It cannot produce any side effect. It easy to test and debug.
> Make the candidate explain the difference between mutation and reassignment. (Hint: use `const` with `Array.push` and `let` to explain the difference)

- Why do we say that Javascript is a __single-threaded__ language? How it relates to the event loop?

## Node.js
- What is __Node.js__? Why would you use it? What's the difference between Node.js and Express.js?
> Node.js is a JavaScript runtime built on Chrome's V8 JavaScript engine. It's used to build fast and scalable network applications. It's used to build back-end services like APIs, web servers, and microservices while Express.js is a framework that runs on top of Node.js. It's used to build web applications and APIs.

- What's the difference between __`require` and `import`__? How would you use them?
> `require` is used to import CommonJS modules while `import` is used to import ES6 modules. `require` is a function while `import` is a statement. `require` is synchronous while `import` is asynchronous. `require` is used to import a module while `import` is used to import a module or a variable.

- In Express.js, what's the difference between __`app.use` and `app.get`__? How would you use them?
> `app.use` is used to mount middleware while `app.get` is used to handle GET requests. `app.use` is used to mount middleware at a path while `app.get` is used to handle GET requests at a path.

- What's a __middleware__? How would you use it? Why would you use it?
> Middleware is a function that has access to the request and response objects. It can execute any code, make changes to the request and response objects, end the request-response cycle, and call the next middleware function in the stack.

- What's a __handler__ function? How would you use it? Why would you use it?
> A handler function is a function that handles a request. It usually doesn't have business logic.

- What's a __service__ function? How would you use it? Why would you use it?
> A service function is a function that its usually used for business logic. It's used to separate the business logic from the controller. It makes the controller more readable and easier to test. It can be used to request data from an API, to make calculations, etc.

- What do you understand for __scaffolding__? How would you'd scaffold an Express.js application?
> Scaffolding is the process of generating a skeleton of an application. It's used to generate the basic structure of an application.

- What's an __idempotent operation__? How would you use it? Why would you use it?
> An idempotent operation is an operation that can be applied multiple times without changing the result beyond the initial application. E.g. you wanto to make a payment. You send the request to the server. The server processes the request and sends a response. If you send the same request again, the server will process the request and send the same response. The result is the same. This way if the client doesn't receive a response from the server it can retry the request without worrying about duplicate payments.

- Which TCP protocols you know?
> TCP stands for Transmission Control Protocol. It's a connection-oriented protocol. It's used to send data over the internet. It's used by HTTP, HTTPS WS (Chats), FTP(files), SMTP(emails), etc. For web development, the most common protocols are HTTP and HTTPS.
