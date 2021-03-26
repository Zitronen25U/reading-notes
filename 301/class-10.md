# Reading Notes for Class 10

## The JavaScript Call Stack - What It Is and Why It's Necessary

- The JS engine (which is found in a hosting environment), is a single threaded interpreter comprising of a heap and a single call stack.

- the call stack is primarily used for function invocation (call)

- stack is synchronous, one at a time, top to bottom

- in asynchronous JS, we have a callback function, an event loops, and a task queue

### What is the call stack?

- a call stack is a data structure that uses the Last in, First Out (LIFO) priciple to temporarily store and manage function invocation (call)

- the last function in is the first to be pushed out of the stack

```js
unction firstFunction(){
  throw new Error('Stack Trace Error');
}

function secondFunction(){
  firstFunction();
}

function thirdFunction(){
  secondFunction();
}

thirdFunction();
```

- this will produce an error. Stack trace error. 

### Temporarily store

- when a function is invoked, the function, its params, and variables are pushed into the call stack to form a stack frame.

- this is memory in the tack. 

- the memory is cleared when the function returns as it is pop out of the stack

### Manage function invocation (call) 

- the call stack maintains a record of the position of each stack frams

- it knows the next function and will remove it after exec

- makes it synchronous (ONE AT A TIME)

### How does the call stack handle function calls?

```js
function firstFunction(){
  console.log("Hello from firstFunction");
}

function secondFunction(){
  firstFunction();
  console.log("The end from secondFunction");
}

secondFunction();
```

### This is what happens when the code is run:

1. When secondFunction() gets executed, an empty stack frame is created. It is the main (anonymous) entry point of the program.
2. secondFunction() then calls firstFunction()which is pushed into the stack.
3. firstFunction() returns and prints “Hello from firstFunction” to the console.
4. firstFunction() is pop off the stack.
5. The execution order then move to secondFunction().
6. secondFunction() returns and print “The end from secondFunction” to the console.
7. secondFunction() is pop off the stack, clearing the memory.

### What causes a stack overflow?

- occurs when there is a recursive function (a function that calls itself) without an exit point. 

-EXAMPLE

```js
function callMyself(){
  callMyself();
}

callMyself();
```

- this will run until maximum call size is reached

### In summary

- The key takeaways from the call stack are:

1. It is single-threaded. Meaning it can only do one thing at a time.
2. Code execution is synchronous.
3. A function invocation creates a stack frame that occupies a temporary memory.
4. It works as a LIFO — Last In, First Out data structure.

## JavaScript error message && debugging

- reading and debugging is life

### Types of error messages

- **Reference Errors**

- use a var that is not yet declared you get this

- common with const and let

- **Syntax Error**

- occurs when you have something that cannot be parsed in terms of syntax.

- when you try to parse an invalid obj using json.parse

- **Range Errors**

- try to mess with an obj with some kind of length and give it an invalid length.

- an array cannot have a negative length for example

- **Type Errors**

- called when type is incorrectly called

```js
var foo = {}
foo.bar // undefined
foo.bar.baz // Uncaught TypeError: Cannot read property 'baz' of undefined
```

- FIX

```js
var foo = { bar: {} }
foo.bar.baz // undefined but you avoid the error
```

### Debugging

- most simple way is console.log()

- the breakpoint can also be achieved by putting a debugger statement in your code in the line you want to break

- you can add conditional breakpoints by right clicking a previous breakpoint

- in node.js with VSC, you can press the debug tab and add a configuration

### Tools to avoid runtime errors

- quokka to eval code as you type

- eslint to make sure your style guide is consistent and it will grab errors

[Return!](/class301main.md)