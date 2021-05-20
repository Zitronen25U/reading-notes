# Class 04 Notes

## Classes and Objects

### Classes and Objects

- Objects are an encapsulation of variables and functions

- defined with (self)

### Accessing Object Variables

- assign a new variable to the class object you created

```py
class MyClass:
    variable = "blah"

    def function(self):
        print("This is a message inside the class.")

myobjectx = MyClass()

myobjectx.variable
# So for instance the below would output the string "blah":

class MyClass:
    variable = "blah"

    def function(self):
        print("This is a message inside the class.")

myobjectx = MyClass()

print(myobjectx.variable)
```

### Accessing Object Functions

- access the variable

```py
class MyClass:
    variable = "blah"

    def function(self):
        print("This is a message inside the class.")

myobjectx = MyClass()

myobjectx.function()
```

## Thinking Recursively in PY

### Dear Pythonic Santa Claus

```py
houses = ["Eric's house", "Kenny's house", "Kyle's house", "Stan's house"]

def deliver_presents_iteratively():
    for house in houses:
        print("Delivering presents to", house)
```

```py
houses = ["Eric's house", "Kenny's house", "Kyle's house", "Stan's house"]

# Each function call represents an elf doing his work 
def deliver_presents_recursively(houses):
    # Worker elf doing his work
    if len(houses) == 1:
        house = houses[0]
        print("Delivering presents to", house)

    # Manager elf doing his work
    else:
        mid = len(houses) // 2
        first_half = houses[:mid]
        second_half = houses[mid:]

        # Divides his work among two elves
        deliver_presents_recursively(first_half)
        deliver_presents_recursively(second_half)
```

### Recursive Functions in Python

- Is a function defined in terms of itself via self-referential expressions

- functions will continue to call itself and repeat until some conditions is met to return a result

- STEPS

1. Decompose the original problem into simpler instances of the same problem

```py
n! = n x (n−1) x (n−2) x (n−3) ⋅⋅⋅⋅ x 3 x 2 x 1
n! = n x (n−1)!
```

2. As the large problem is broken, they must become so simple that they can be solved without further subdivision

```py
n! = n x (n−1)! 
n! = n x (n−1) x (n−2)!
n! = n x (n−1) x (n−2) x (n−3)!
⋅
⋅
n! = n x (n−1) x (n−2) x (n−3) ⋅⋅⋅⋅ x 3!
n! = n x (n−1) x (n−2) x (n−3) ⋅⋅⋅⋅ x 3 x 2!
n! = n x (n−1) x (n−2) x (n−3) ⋅⋅⋅⋅ x 3 x 2 x 1!
```

### Maintaining State

- call has its own execution context
  - thread the state through each recursive call so current state is part of the current calls execution context
  - keep the state in global scope

### Recursive Data Structures in PY

- A data structure is recursive if it can be deﬁned in terms of a smaller version of itself. 

- A list is an example of a recursive data structure.

```py
def attach_head(element, input_list):
    return [element] + input_list
```

1. Starting with an empty list, you can generate any list by recursively applying the attach_head function, and thus the list data structure can be defined recursively as:

2. Recursion can also be seen as self-referential function composition. We apply a function to an argument, then pass that result on as an argument to a second application of the same function, and so on. Repeatedly composing attach_head with itself is the same as attach_head calling itself repeatedly

### Pesky Details

- PY doesn't support tail-call elimination
  - can cause stack overflow

## Pytest Fixtures and Coverage

### Improve your Python testing even more

- fixtures and code coverage

### Fixtures

- you're going to write a test suite, not just one test

- each test aiming to check diff part of code

- objects contain data you want to share across tests

- these are known as fixtures

### Coverage

- checking that your tests run all of the code

- covers all possibilities

- THERES A PACKAGE

### --cov

- pytest --cov=mymul .

- coverage html

```py
def test_even_numbers():
   with pytest.raises(NoEvenNumbersHereException):
       only_odd_mul(2,4)

```