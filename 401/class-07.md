# Class 07 Reading Notes

## Python Scope

### Scope

- rules how variables and names are looked up in your code

- follows the LEGB rule

- LEGB
  - Local
  - Enclosing
  - Global
  - Built-in

### Understanding Scope

1. Global Scope

- The names that you define in this scope are available to all your code

2. Local Scope

- The names that you define in this scope are only available or visable to the code within the scope

### Names and Scopes in Python

- python is dynamically-typed

- functions and classes are available after you define them with def or class

### Python Scope vs Namespace

- scopes are implemented as dictionaries called **namespaces**

- Names at the top level of a module are stored in the module’s namespace. In other words, they’re stored in the module’s .__dict__ attribute.

```py
>>> import sys
>>> sys.__dict__.keys()
dict_keys(['__name__', '__doc__', '__package__',..., 'argv', 'ps1', 'ps2'])
```

### Using the LEGB Rule for PYthon scope

- **LOCAL** 
  - is the code block or body of any python funciton (lambda)
  - only visible to code inside of funciton

- **Enclosing**
  - is a special scope that only exists for nested functions
  - contains names you define in the enclosing funciton

- **Global**
  - top most scope
  - all are visible to everywhere in the stack

- **built-in Scope**
  - created whenever you run a script

### Functions: The Local Scope

```py
>>> def square(base):
...     result = base ** 2
...     print(f'The square of {base} is: {result}')
...
>>> square(10)
The square of 10 is: 100
>>> result  # Isn't accessible from outside square()
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
    result
NameError: name 'result' is not defined
>>> base  # Isn't accessible from outside square()
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
    base
NameError: name 'base' is not defined
>>> square(20)
The square of 20 is: 400
```

### Nested Functions: The Enclosing Scope

```py
>>> def outer_func():
...     # This block is the Local scope of outer_func()
...     var = 100  # A nonlocal var
...     # It's also the enclosing scope of inner_func()
...     def inner_func():
...         # This block is the Local scope of inner_func()
...         print(f"Printing var from inner_func(): {var}")
...
...     inner_func()
...     print(f"Printing var from outer_func(): {var}")
...
>>> outer_func()
Printing var from inner_func(): 100
Printing var from outer_func(): 100
>>> inner_func()
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
NameError: name 'inner_func' is not defined
```


### Modules: The Global Scope

```py
>>> __name__
'__main__'
```

### builtins: The Built-In Scope

```py
>>> dir()
['__annotations__', '__builtins__',..., '__package__', '__spec__']
>>> dir(__builtins__)
['ArithmeticError', 'AssertionError',..., 'tuple', 'type', 'vars', 'zip']
```

### Modifying the Behavior of a Python Scope

- Python provides two keywords that allow you to modify the content of global and nonlocal names. These two keywords are:

1. global
2. nonlocal

### The global Statement

```py
>>> counter = 0  # A global name
>>> def update_counter():
...     counter = counter + 1  # Fail trying to update counter
...
>>> update_counter()
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
  File "<stdin>", line 2, in update_counter
UnboundLocalError: local variable 'counter' referenced before assignment

>>> counter = 0  # A global name
>>> def update_counter():
...     global counter  # Declare counter as global
...     counter = counter + 1  # Successfully update the counter
...
>>> update_counter()
>>> counter
1
>>> update_counter()
>>> counter
2
>>> update_counter()
>>> counter
3
```

