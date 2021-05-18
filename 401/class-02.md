# Class 02 Reading

## In Tests We Trust - TDD with Python

### So you wanna do some tests?

### Unit Tests and TDD

- unit tests are some pieces of code to exercise the input, the output, and the behavior of your code.

- you can write them anytime you want

- tests first is a strategy

- TDD = test driven development

### Details!

1. Test Name

- tests are live doucumentation. BE DESCRIPTIVE
- file name should be same name as module name

2. Convention:

- AAA
  - Arrange (you need to organize data needed to execute that piece of code)
  - Act (execute code being tested)
  - Assert( check output of code and see if its what you were expecting)

### The Cycle

- made of 3 steps

1. Write a unit test and make it fail
2. Write the feauture and make the test pass
3. Refactor the code to make it pretty

### TDD is not about the money/tests

## Recursion

### What is recursion

- the process in which a funciton calls itself directly or indirectly is called recursion

- makes problem solving easy

### What is a base condition in recursion

- solution to the base case is provided and the solution of the bigger problem is expressed in terms of smaller problems

### how a particular problem is solved using recursion

- the idea is to represent a problem in terms of one or more smaller problems

### Why stack overflow error occurs in recursion

- if the base case is not reached or not defined

### Difference between direct and indirect recursion

- a function "fun" is called direct recursive if it calls the same funciton "fun"

- it is indirect recursive if this "fun" function calls another function, and that function calls "fun"

### What is difference between tailed and non-tailed recursion

- is a tail recursive when recursive call is the last thing executed by the function

### How memory is allocated to different function calls in recursion

- example

```py
Python3
# A Python 3 program to
# demonstrate working of
# recursion
 
def printFun(test):
 
    if (test < 1):
        return
    else:
 
        print(test, end=" ")
        printFun(test-1)  # statement 2
        print(test, end=" ")
        return
 
# Driver Code
test = 3
printFun(test)
 
# This code is contributed by
# Smitha Dinesh Semwal

```

```py
# Python code to implement Fibonacci series
 
# Function for fibonacci
def fib(n):
 
    # Stop condition
    if (n == 0):
        return 0
 
    # Stop condition
    if (n == 1 or n == 2):
        return 1
 
    # Recursion function
    else:
        return (fib(n - 1) + fib(n - 2))
 
 
# Driver Code
 
# Initialize variable n.
n = 5;
print("Fibonacci series of 5 numbers is :",end=" ")
 
# for loop to print the fiboancci series.
for i in range(0,n):
    print(fib(i),end=" ")

```

### For Best Case

- T(n) =   θ(2^n\2)

```py
# Python3 code to implement factorial
 
# Factorial function
def f(n):
 
    # Stop condition
    if (n == 0 or n == 1):
        return 1;
 
    # Recursive condition
    else:
        return n * f(n - 1);
 
 
# Driver code
if __name__=='__main__':
 
    n = 5;
    print("factorial of",n,"is:",f(n))
     
    # This code is contributed by pratham76.

```
