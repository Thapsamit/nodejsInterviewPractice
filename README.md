# nodejsInterviewPractice

## Q-1 What is NPM
- NPM – or "Node Package Manager" – is the default package manager for JavaScript's runtime Node.js.
- NPM consists of two main parts:
  - a CLI (command-line interface) tool for publishing and downloading packages, and
  - an online repository that hosts JavaScript packages
- For a more visual explanation, we can think of the repository npmjs.com as a fulfillment center that receives packages of goods from sellers (npm package authors) and distributes these goods to buyers (npm package users).
- To facilitate this process, the npmjs.com fulfillment center employs an army of hardworking wombats (npm CLI) who will be assigned as personal assistants to each individual npmjs.com customer. So dependencies are delivered to JavaScript developers like this:

## Q - 2 What is Package.JSON?
- package.json job to describe the project.
- package.json will be generated when npm init is run to initialise a JavaScript/Node.js project, with these basic metadata provided by developers:
  - name: the name of your JavaScript library/project
  - version: the version of your project. Often times, for application development, this field is often neglected as there's no apparent need for versioning opensource libraies. But still, it can come handy as a source of the deployment's version.
  - description: the project's description
  - license: the project's license
- It records important metadata about a project which is required before publishing to NPM
- also defines functional attributes of a project that npm uses to install dependencies, run scripts, and identify the entry point to our package.
- 
  1. Identifying metadata properties: It basically consist of the properties to identify the module/project such as the name of the project, current version of the module, license, author of the project, description about the project etc. 
  2. Functional metadata properties: As the name suggests, it consists of the functional values/properties of the project/module such as the entry/starting point of the module, dependencies in project, scripts being used, repository links of Node project etc. 


## Q - 3 Difference between dependencies vs devDependencies vs peerDependencies?
- dependencies :- 
  - it consists of all the packages that are used in the project with its version number. example moment
  - A dependency is a library that a project needs to function effectively.
- devdependencies :- 
  - it consists of all the packages that are used in the project in its development phase and not in the production or testing environment with its version number. 
  ``` npm install <package name> --save-dev ```
- peerdependency :- 
  - peerDependencies and it consists of all the packages that are exactly required in the project or to the person who is downloading and the version numbers should also be the same. example - react
  - Peer dependencies are only encountered when you publish your own package, that is, when you develop code that will be used by other programs. 
  - Having a peer dependency means that your package needs a dependency that is the same exact dependency as the person installing your package.

## Q - 4 What is Node.js?
- Describe node.js
- JS Engine  takes the JS code & translates it into machine-readable code and executes it.
- Node.JS is JS runtime that let's execute JS code outside of a browser, that is on a server, a local machine. It uses Chrome's V8 engine to actually execute JS"
- running JavaScript in isolation is not that useful. We need to run it in some *context*. 
  - what is context?
  When JavaScript runs in a browser, there are many built-in things like Window object, the document(web page), LocalStorage, etc. are provided by the browser to work with.
  We access and manipulate this built-in stuff using JS to make the web better, more interactive, & dynamic.
- When you're running JavaScript in the context of a browser, you can only access things like DOM, BOM, LocalStorage, Timers, etc. but you can not access Operating System and stuff like File System, memory, CPU, etc.
- Think about If we can access OS stuff somehow using JavaScript then we can do a lot more useful tasks like reading/writing files, creating servers, talking to databases, & handling HTTP requests

- The creator of Node.JS, Ryan Dahl, came up with an idea to take a JS Engine (As we know It is required to run JS) and provide a richer context to it.
  So he took Chrome's V8 engine and embedded it in a C++ program named it Node.JS.
- So what he did differently was that he provided a different context, i.e. a different runtime, a different set of built-in stuff like FS module, HTTP module, OS module, and many more. 
  This new runtime called Node.JS is installable on various machines like Windows, Macs, Linux.
- So, now You can run JS code on whatever machine Node.JS can be installed cause Node has a V8 engine inside it. If you can install Node on a coffee machine you can run JS there too. 
-  Features:-
   - Here is how Node.js handles a file request:
     - Sends the task to the computer's file system.
     - Ready to handle the next request.
     - When the file system has opened and read the file, the server returns the content to the client. 
   - Node.js runs single-threaded, non-blocking, asynchronous programming, which is very memory efficient
   
## Q - 5 What is Runtime Environment
- A runtime environment is where your program will be executed. It determines what global objects your program can access and it can also impact how it runs. This article covers the two JavaScript runtime environments:
  - the runtime environment of a browser (like Chrome, or Firefox)
  - the Node runtime environment

## Q - 6 What is Local Vs Global Packages?
-local packages  = are installed in the directory where you run npm install <package-name>, and they are put in the node_modules folder under this directory
-global packages =  are all put in a single place in your system (exactly where depends on your setup), regardless of where you run npm install -g <package-name>

## Q - 7 Types of API Function in NODE.js?
- **Asynchronous, Non-blocking functions:**
   - As the name suggests, these functions operate asynchronously. What it means is that when Node.js will make a request for data to the API, it will not get blocked till the data is received. Instead, it will continue to move to the next API after calling it, and a notification mechanism from a Node.js event will respond to the server for the previous API call. To put it in layman’s terms, these functions allow working further while the request is being handled. Example: Emails, online forums
- **Synchronous, Blocking functions:**
   - Contrary to asynchronous functions, synchronous functions act as blocking functions. What it means is that these functions will make the calling system wait for a response. Thus, when a system uses synchronous APIs, it expects to get immediate data when requests are made. These types of APIs are used where availability and connectivity are high and low latency is expected. To put it in layman’s terms, the application will request and wait for a response until the value is returned. Example: Instant messaging, video meetings
- readFile for asynchronous and readFileSync for synchronous file read


## Q - 8 What is Error first Callback?
- Error- First Callback in Node.js is a function which either returns an error object or any successful data returned by the function.
  - **The first argument** in the function is reserved for the error object. If any error has occurred during the execution of the function, it will be returned by the first argument.
  - **The second argument** of the callback function is reserved for any successful data returned by the function. If no error occurred then the error object will be set to null.

## Q - 9 What is callback?
- A callback function is a function passed into another function as an argument, which is then invoked inside the outer function to complete some kind of routine or action.

## Q -10 What is Callback Hell?
- When multiple asynchronous functions are chained together then callback hell situation comes up.
- If we want to wait for something in JavaScript, we need to use a callback.
- Callback Hell is essentially nested callbacks stacked below one another forming a pyramid structure. Every callback depends/waits for the previous callback, thereby making a pyramid structure that affects the readability and maintainability of the code. 

## Q - 11 How Node.js Handles concurrency when it is single Threaded?
- Node js uses an event loop to maintain concurrency and perform non-blocking I/O operations.
- As soon as Node js starts, it initializes an event loop. The event loop works on a queue (which is called an event queue) and performs tasks in FIFO(First In First Out) order. 
- It executes a task only when there is no ongoing task in the call stack.
- The event loop continuously checks the call stack to check if there is any task that needs to be run. Now whenever the event loop finds any function, it adds it to the stack and runs in order.  

## Q-12 How to handle concurency

![alt text](https://media.geeksforgeeks.org/wp-content/uploads/20210916203407/WorkingofNodejs1.png)
- Node.js works asynchronously. In other words, it does not block incoming requests from clients when the operating system has one I/O intensive request. Instead, it passes this I/O request to the internal C++ threads and takes up the next job from the event queue.
- For every I/O request, the event loop receives, passes it on to the internal C++ threads for processing and makes itself available for the other requests, and starts processing those.
-  Then it uses the concept of callback functions from JavaScript to receive the responses of the tasks that were sent to the internal C++ threads earlier for processing and delivers them to the client.


## Q - 13 Could we run an external process with Node.js?
- Yes. Child process module enables us to access operating system functionaries or other apps.
- You can use child process to run system commands, read large files without blocking event loop, decompose the application into various “nodes” (That’s why it’s called Node).

## Q - 14 What are the key features of Node.js?
- **Asynchronous and Event driven** – All APIs of Node.js are asynchronous. This feature means that if a Node receives a request for some Input/Output operation, it will execute that operation in the background and continue with the processing of other requests. Thus it will not wait for the response from the previous requests.
- **Fast in Code execution** - Node.js uses the V8 JavaScript Runtime engine, the one which is used by Google Chrome. Node has a wrapper over the JavaScript engine which makes the runtime engine much faster and hence processing of requests within Node.js also become faster.
- **Single Threaded but Highly Scalable** – Node.js uses a single thread model for event looping. The response from these events may or may not reach the server immediately. However, this does not block other operations. Thus making Node.js highly scalable
- **No Buffering** – Node.js applications never buffer any data. They simply output the data in chunks.

##  Q - 15 Explain how does Node.js work?
- A Node.js application creates a single thread on its invocation. Whenever Node.js receives a request, it first completes its processing before moving on to the next request.
- Node.js works asynchronously by using the event loop and callback functions, to handle multiple requests coming in parallel. An Event Loop is a functionality which handles and processes all your external events and just converts them to a callback function. It invokes all the event handlers at a proper time. Thus, lots of work is done on the back-end, while processing a single request, so that the new incoming request doesn't have to wait if the processing is not complete.
- While processing a request, Node.js attaches a callback function to it and moves it to the back-end. Now, whenever its response is ready, an event is called which triggers the associated callback function to send this response.

## Q - 16 Node.Js Major Topics:-
- Node.js Data Types
  - Node.js Architecture
  - Node.js Events
  - Node.js File System
  - Node.js Streams
  - Node.js Multithreading
  - Node.js Web Module
  - Node.js Middleware
  - Node.js RESTFul API
  - Node.js Routing
  - Node.js Caching
  - Node.js Error Handling
  - Node.js Logging
  - Node.js Internationalization
  - Node.js Testing
  - Node.js Miscellaneous
  
## Q-17 Explain the concept of URL module in Node.js?
- The URL module in Node.js splits up a web address into readable parts.
- Use require() to include the module. Then parse an address with the url.parse() method, and it will return a URL object with each part of the address as properties.
- it  has properies like host,pathname,search,query,hostname

# Data Types:-


## Q - 18 What are the data types in Node.js?
- **Primitives**:
 - String
 - Number
 - BigInt
 - Boolean
 - Undefined
 - Null
 - Symbol
- **Objects**:
 - Function
 - Array
 - Buffer

## Q - 19 Explain String data type in Node.js?
- Functions like indexOf(),split(),join(),match(),concat()

## Q - 20 Explain Number data type in Node.js?
- The number data type in Node.js is 64 bits floating point number both positive and negative.  ex - parseInt(),parseFloat() etc

## Q - 21 Bigint in Node.js
- BigInt values represent numeric values which are too large to be represented by the number primitive.
- A BigInt value, also sometimes just called a BigInt, is a bigint primitive, created by appending n to the end of an integer literal, or by calling the BigInt() function ( without the new operator ) and giving it an integer value or string value.
```
/**
 * BigInt Data Type
 */
const maxSafeInteger = 99n; // This is a BigInt
const num2 = BigInt('99'); // This is equivalent
const num3 = BigInt(99); // Also works

typeof 1n === 'bigint'           // true
typeof BigInt('1') === 'bigint'  // true
```

## Q - 22  Explain Symbol data type in Node.js?
- Symbol is an immutable primitive value that is unique. It's a very peculiar data type. Once you create a symbol, its value is kept private and for internal use.
```
/**
 * Symbol Data Type
 */
const NAME = Symbol()
const person = {
  [NAME]: 'Ritika Bhavsar'
}

person[NAME] // 'Ritika Bhavsar'
```

# Node.js Architecture


## Q - 23 How does Node.js works in detail?

![alt-text](https://github.com/learning-zone/nodejs-basics/raw/master/assets/event-loop.png)

- Node.js is completely event-driven. Basically the server consists of one thread processing one event after another.
- A new request coming in is one kind of event. The server starts processing it and when there is a blocking IO operation, it does not wait until it completes and instead registers a callback function.
- The server then immediately starts to process another event ( maybe another request ). 
- When the IO operation is finished, that is another kind of event, and the server will process it ( i.e. continue working on the request ) by executing the callback as soon as it has time.
- Node.js Platform does not follow Request/Response Multi-Threaded Stateless Model.
- It follows Single Threaded with Event Loop Model. Node.js Processing model mainly based on Javascript Event based model with Javascript callback mechanism.
- **Single Threaded Event Loop Model Processing Steps:**
  - Clients Send request to Web Server.
  - Node.js Web Server internally maintains a Limited Thread pool to provide services to the Client Requests.
  - Node.js Web Server receives those requests and places them into a Queue. It is known as Event Queue.
  - Node.js Web Server internally has a Component, known as Event Loop. Why it got this name is that it uses indefinite loop to receive requests and process them.
  - Event Loop uses Single Thread only. It is main heart of Node.js Platform Processing Model.
  - Event Loop checks any Client Request is placed in Event Queue. If no, then wait for incoming requests for indefinitely.
  - If yes, then pick up one Client Request from Event Queue
    - Starts process that Client Request
    - If that Client Request Does Not requires any Blocking IO Operations, then process everything, prepare response and send it back to client.
    - If that Client Request requires some Blocking IO Operations like interacting with Database, File System, External Services then it will follow different approach
      - Checks Threads availability from Internal Thread Pool
      - Picks up one Thread and assign this Client Request to that thread.
      - That Thread is responsible for taking that request, process it, perform Blocking IO operations, prepare response and send it back to the Event Loop
      - Event Loop in turn, sends that Response to the respective Client.


## Q - 24 What are the core modules of Node.js?
- Node.js has a set of core modules that are part of the platform and come with the Node.js installation. These modules can be loaded into the program by using the require function.
example assert,http,fs,path,util etc


## Q - 25 What is Reactor Pattern in Node.js
![alt-text](https://github.com/learning-zone/nodejs-basics/raw/master/assets/reactor-pattern.jpg)

- Reactor Pattern is used to avoid the blocking of the Input/Output operations. It provides us with a handler that is associated with I/O operations. When the I/O requests are to be generated, they get submitted to a demultiplexer, which handles concurrency in avoiding the blocking of the I/O mode and collects the requests in form of an event and queues those events.
**Reactor Pattern comprises of:**
1. Resources: They are shared by multiple applications for I/O operations, generally slower in executions.

2. Synchronous Event De-multiplexer/Event Notifier: This uses Event Loop for blocking on all resources. When a set of I/O operations completes, the Event De-multiplexer pushes the new events into the Event Queue.

3. Event Loop and Event Queue: Event Queue queues up the new events that occurred along with its event-handler, pair.

4. Request Handler/Application: This is, generally, the application that provides the handler to be executed for registered events on resources.






