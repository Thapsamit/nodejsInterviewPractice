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

## Q - 26 What is Async-Await in JS?
- The async and await keywords enable asynchronous, promise-based behavior to be written in a cleaner style, avoiding the need to explicitly configure promise chains.
```
const getData = async() => {
	var data = "Hello World";
	return data;
}

getData().then(data => console.log(data)); // returns a promise

```
- **Async:** - It simply allows us to write promises based code as if it was synchronous and it checks that we are not breaking the execution thread.It Returns a promise.
- **Await:** - Await function is used to wait for the promise. It could be used within the async block only. It makes the code wait until the promise returns a result.
- Await expressions make promise-returning functions behave as though they're synchronous by suspending execution until the returned promise is fulfilled or rejected.
```
async function getPromise(){
  const gitUsers = await fetch('https://api.github.com/users')
  const res = await gitUsers.json();
  console.log("promise resolved")
  return res;
}
console.log("Before")
const gP= getPromise()
console.log(gP.then(data=>console.log(data)))
console.log("after")
```

## Q - 27 What are the global objects of node.js?
- Node.js Global Objects are the objects that are available in all modules. Global Objects are built-in objects that are part of the JavaScript and can be used directly in the application without importing any particular module.
- example:-
  1 - **Global** - It is a global namespace. Defining a variable within this namespace makes it globally accessible.
  2 - **process** - It is an inbuilt global object that is an instance of EventEmitter used to get information on current process.
  3 - **console:** - It is an inbuilt global object used to print to stdout and stderr.
  4 - **setTimeout(), clearTimeout(), setInterval(), clearInterval():** - The built-in timer functions are globals
  5 - **__dirname:** - It is a string. It specifies the name of the directory that currently contains the code.
  6 - **__filename:** - It specifies the filename of the code being executed.

## Q - 29 What is chrome v8 engine?
- V8 is a C++ based open-source JavaScript engine developed by Google. It was originally designed for Google Chrome and Chromium-based browsers ( such as Brave ) in 2008, but it was later utilized to create Node.js for server-side coding.
- V8 is the JavaScript engine i.e. it parses and executes JavaScript code. The DOM, and the other Web Platform APIs ( they all makeup runtime environment ) are provided by the browser.
- It provides a runtime environment for the execution of JavaScript code. 
- The best part is that the JavaScript engine is completely independent of the browser in which it runs.
- Other js engine are Rhino and SpiderMonkey.

## Q - 30 How V8 compiles JavaScript code?
- Compilation is the process of converting human-readable code to machine code. There are two ways to compile the code
- **Using an Interpreter:** The interpreter scans the code line by line and converts it into byte code.
- **Using a Compiler:** The Compiler scans the entire document and compiles it into highly optimized byte code.
- The V8 engine uses both a compiler and an interpreter and follows just-in-time (JIT) compilation to speed up the execution. JIT compiling works by compiling small portions of code that are just about to be executed. This prevents long compilation time and the code being compiles is only that which is highly likely to run.
- JIT compiles on the go 

# NODE.JS EVENTS

## Q - 31 What is EventEmitter in Node.js?
- The EventEmitter is a class that facilitates communication/interaction between objects in Node.js.
- The EventEmitter class can be used to create and handle custom events.
- EventEmitter is at the core of Node asynchronous event-driven architecture.
- An emitter object basically has two main features:
  - **Emitting name events.**
  - **Registering and unregistering listener functions.**
```
/**
 * Callback Events with Parameters
 */
const events = require('events');
const eventEmitter = new events.EventEmitter();

function listener(code, msg) {
   console.log(`status ${code} and ${msg}`);
}

eventEmitter.on('status', listener); // Register listener
eventEmitter.emit('status', 200, 'ok');

// Output
status 200 and ok

```
## Q - 32 How does the EventEmitter works in Node.js?

- Event Emitter emits the data in an event called message
- A Listener is registered on the event message
- when the message event emits some data, the listener will get the data
![alt-text](https://github.com/learning-zone/nodejs-basics/raw/master/assets/eventEmitter_works.png)

 - .emit() - this method in event emitter is to emit an event in module
 - .on() - this method is to listen to data on a registered event in node.js
 - .once() - it listen to data on a registered event only once., after emitting once it removes the listener for an event immedietely
 - .addListener() - it checks if the listener is registered for an event.(alias for on),Adds a listener to the end of the listeners array for the specified event.
 - .removeListener() - it removes the listener for an event.,Removes a listener from the listener array for the specified event.
 - .listenerCount(type) -	Returns the number of listeners listening to the type of event.
 - .removeAllListeners([event]) -	Removes all listeners, or those of the specified event.
  
 
## Q - 33 How Event loops works?
- The event loop allows Node.js to perform non-blocking I/O operations despite the fact that JavaScript is single-threaded. It is done by offloading operations to the system kernel whenever possible.
- And Ready to handle next task
- Node.js is a single-threaded application, but it can support concurrency via the concept of event and callbacks.
- Node thread keeps an event loop and whenever a task gets completed, it fires the corresponding event which signals the event-listener function to execute.
  
**Features of Event Loop:**  
  - Event loop is an endless loop, which waits for tasks, executes them and then sleeps until it receives more tasks.
  - The event loop executes tasks from the event queue only when the call stack is empty i.e. there is no ongoing task.
  - The event loop allows us to use callbacks and promises.
  - The event loop executes the tasks starting from the oldest first.
![alt-text](https://github.com/learning-zone/nodejs-basics/raw/master/assets/nodejs-event-loop.png)  
  
 
## Q - 34 What is the difference between process.nextTick() and setImmediate()?
- **process.nextTick() - The process.nextTick() method adds the callback function to the start of the next event queue. It is to be noted that, at the start of the program process.nextTick() method is called for the first time before the event loop is processed.
- **setImmediate():** -  is used to execute a function right after the current event loop finishes. It is callback function is placed in the check phase of the next event queue.

```
/**
 * setImmediate() and process.nextTick()
 */
setImmediate(() => {
  console.log("1st Immediate");
});

setImmediate(() => {
  console.log("2nd Immediate");
});

process.nextTick(() => {
  console.log("1st Process");
});

process.nextTick(() => {
  console.log("2nd Process");
});

// First event queue ends here
console.log("Program Started");

// Output
Program Started
1st Process
2nd Process
1st Immediate
2nd Immediate

```
## Q - 35 What is callback function in Node.js?
- A callback is a function which is called when a task is completed, thus helps in preventing any kind of blocking and a callback function allows other code to run in the meantime.
- Callback is called when task get completed and is asynchronous equivalent for a function.
- Using Callback concept, Node.js can process a large number of requests without waiting for any function to return the result which makes Node.js highly scalable.


## Q - 36 What are the difference between Events and Callbacks?
- **events**
  - Node.js events module which emits named events that can cause corresponding functions or callbacks to be called. 
  - Functions ( callbacks ) listen or subscribe to a particular event to occur and when that event triggers, all the callbacks subscribed to that event are fired one by one in order to which they were registered.
- **callbacks** 
  - A callback function is a function passed into another function as an argument, which is then invoked inside the outer function to complete some kind of routine or action.
- Callback functions are called when an asynchronous function returns its result, whereas event handling works on the observer pattern. The functions that listen to events act as Observers. Whenever an event gets fired, its listener function starts executing. Node.js has multiple in-built events available through events module and EventEmitter class which are used to bind events and event-listeners
- Any asynchronous method expects one of the arguments to be a callback.
- An asynchronous function is one where some external activity must complete before a result can be processed; it is "asynchronous" in the sense that there is an unpredictable amount of time before a result becomes available. Such functions require a callback function to handle errors and process the result.

## Q - 37 What are the timing features of Node.js?
- The Timers module in Node.js contains functions that execute code after a set period of time. 
  - **setTimeout():** - This function schedules code execution after the assigned amount of time ( in milliseconds ). Only after the timeout has occurred, the code will be executed. This method returns an ID that can be used in clearTimeout() method. 
  - **setImmediate()** - The setImmediate() method executes the code at the end of the current event loop cycle. The function passed in the setImmediate() argument is a function that will be executed in the next iteration of the event loop.
  ```
// Setting timeout for the function
setTimeout(function () {
    console.log('setTimeout() function running...');
}, 500);

// Running this function immediately before any other
setImmediate(function () {
   console.log('setImmediate() function running...');
});

// Directly printing the statement
console.log('Normal statement in the event loop');

// Output
// Normal statement in the event loop
// setImmediate() function running...
// setTimeout() function running...	
  ```




