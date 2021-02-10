# JavaScript CH 10

## Error Handlinga and Debugging

### Order of Execution

- to find the source of an error, it helps to know how the scripts are processed 
- Scripts are processed in the order of execution
- its important to know how, and what a script does in order to find its errors.
  - take into account things like global variables and function variables

- if a statement generates an error, it thorws an **exception**

### How to deal with errors

1. Debug the script to fix errors
2. handle errors gracefully 

### Browser tools and JS console

- use f12 key for bebug console (windows, chrome)
- firefox ctrl + shift + k
- safari alt + cmd + c
 
- console data can show you exactly what your errors are and potentially what line of code the error is on.

### Breakpoints

- you can pause the execution of a script on any line using breakpoints

1. Chrome
  1. select sources option
  2. select the script
  3. find the line number you want
  4. it'll stop on that line

### handling exceptions

- Try, Catch, Finally

### Debugging tips

- try another browser
- add numbers to the console
- strip it back
- explaining the code (rubber duck!)
- search in stack overflow
- code playgrounds
- validation tools

