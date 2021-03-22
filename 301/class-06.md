# Reading Notes for Class 06

## What Is Node and When Should I Use It?

### Node.JS is a JS runtime built on the Chrome's V8 JS engine

- node.js is an event based, non blocking, asynchronous I/O rontime that uses Google's V8 JS engine and libuv Library (WHAT LOL)

### V8 JS Engine

- is an open source JS engine that runs in google chrome and other based browsers.

- designed with performance in mind and is responsible for compiling JS directly to native machine code that your PC can execute

- the creater of Node (Ryan Dahl) enhanced the V8 engine and added a
  - file system
  - API
  - HTTP library
  - many OS related Utility methods

### How do I install Node.js

- **Binaries vs. Version Manager**

- you can install from the official page, but you could get a version manager instead

- this can allow you to install mutliple versions of Node and switch between them at will

### Node.js has excellent Support for Modern JS

- has excellent support for JS, ES6 and more

### Introducing NPM

- node comes with package manager called npm

- npm is the worlds largest software registry 

### Installing a package Globally

- npm install -g xxxxx

### Working with package.json file

- you'll notice node_modules

- npm saved lodash and any libraries that lodash depends on

- can be created at any time using npm install


### What is Node.js used for

- designed to automate the process of developing a modern JS app

- lets us run JS on the server

- node.js


### Node.js execution model

1. Node apps pass async tasks to the event loop along witha  callback

2. the event loop efficiently manages a thread pool and executes tasks efficiently

3. and executes each callback as tasks complete


### Downsides?

- node runs a single thread. Blocking I/O calls should be avoiced.

- CPU intense

### Advantages?

- your brain no longer needs to switch modes

- you can do everything in one language(happy!)


## 6 Reasons for Pair Programmin

### Greater efficiency

- takes a little longer, but produces higher-quality code that doesn't

### Engaged Collaboration

- the experience is more engaging. Both are more focused than if they were alone

### Learning from fellow Students

- devs have different skills and experiences. It's helpful to lean on eachother to learn!

### Social Skills

- someone may have different coding style. Communication is key, and paired programming makes those different styles easier to translate


### Job Interview Readiness

- often in an interview, you will work with a current employee and applicant 

### Work Environment readiness

- many companies utilize pair programming to train fresh hires from CS-degree programs