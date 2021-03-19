# Class 05 Notes

## Thinking in React

- **HOW YOU SHOULD BE THINKING IN REACT DEVELOPMENT**

### Start with a Mock

- start with a simple mock design

### Step 1: Break the UI into a component Hierarchy

- draw boxes around every component and subcomponent 

- How do you know what should be its own component?

- **Single Responsibility Principle** 
  - A component that does only 1 thing. If it ends up growing, it should be decomposed into smaller subcomponents

### Step 2: Build a static Version in React

- ***DONT USE STATE AT ALL***

- Build a top down or bottom up

- at the ned of this step, you will have a library of reusable components

### **PROPS VS STATE**

- make sure to understand the difference

### Step 3 Identify the Minimal (but complete) Representation of UI state

-Think of all of the pieces of data in our example application. We have:
  -The original list of products
  -The search text the user has entered
  -The value of the checkbox
  -The filtered list of products

### ASK 3 Questions to figure out which one is state

1. Is it passed in from a parent via props? Is so, its not state
2. Does it remain unchanged over time? If so, its not state!
3. Can you compute it based on any other state or props? Then its not state!

### Step 4: Identify Where Your State Should Live

- **this is the most challenging**

- FOr each piece of state in your app
  - identify every component that renders something based on that state
  - Find a common owner component (single parent)
  - Either the common owner or another component higher up should own the state
  - you can create a new component soley for holding state

### Step 5: add inverse data flow

[RETURN](class301main.md)