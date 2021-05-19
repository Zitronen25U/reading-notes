# Class 03 Reading Notes

## Reading and Writing Files in Python

### What is a file?

- set of bytes used to store data

- organized in specific format

- composed of three main parts

1. Header: Metadata about the contents of the file
2. Data: contents of the file as written
3. End of file (EOF): special character that indicates end

### File Paths

- string that represents location of file

- 3 parts

1. Folder Path: the file folder location on the file system where subsequnt folders are seperated by a / in Unix or \ in Windows

2. File Name: the actual name of the file
3. Extension: the end of the file path (.) for file type

### Opening and Closing a File in Python

- file = open('blah.txt')

### Iterating Over Each Line in the File

```py
>>> with open('dog_breeds.txt', 'r') as reader:
>>>     # Read and print the entire file line by line
>>>     line = reader.readline()
>>>     while line != '':  # The EOF char is an empty string
>>>         print(line, end='')
>>>         line = reader.readline()
Pug
Jack Russell Terrier
English Springer Spaniel
German Shepherd
Staffordshire Bull Terrier
Cavalier King Charles Spaniel
Golden Retriever
West Highland White Terrier
Boxer
Border Terrier
```

OR

```py
>>> with open('dog_breeds.txt', 'r') as reader:
>>>     # Read and print the entire file line by line
>>>     for line in reader:
>>>         print(line, end='')
```

### Working with bytes

- use 'rb' after open(file.txt, 'rb')

- can use byte strings to work with file

## Python Exceptions: An Introduction

### Exceptions vs Syntax Errors

- sytax err occurs when the parser detects an incorrect statement

```py
>>> print( 0 / 0 ))
  File "<stdin>", line 1
    print( 0 / 0 ))
                  ^
SyntaxError: invalid syntax
```

- exeption error occurs when sytactically correct Python results in an error

```py
>>> print( 0 / 0)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ZeroDivisionError: integer division or modulo by zero
```

### Raising and Exception

- can use raise to throw an exception if a condition occurs

```py
x = 10
if x > 5:
    raise Exception('x should not exceed 5. The value of x was: {}'.format(x))
```

- this will output the following

```py
Traceback (most recent call last):
  File "<input>", line 4, in <module>
Exception: x should not exceed 5. The value of x was: 10
```


### The AssertionError Exception

- instead of waiting for error, you can make an assertion(tests!)

- if a condition is met, it is true, if not, false

- if false, program will throw assertion error

### The try and except Block: Handling Exceptions

```py
def linux_interaction():
    assert ('linux' in sys.platform), "Function can only run on Linux systems."
    print('Doing something.')
```

```py
try:
    linux_interaction()
except:
    pass
```

### The else Clause

- using the else statement, you can instruct a program to execute a certain block of code only in the absence of exceptions.

### Cleaning Up After Using finally

- finally is last step

```py
try:
    linux_interaction()
except AssertionError as error:
    print(error)
else:
    try:
        with open('file.log') as file:
            read_data = file.read()
    except FileNotFoundError as fnf_error:
        print(fnf_error)
finally:
    print('Cleaning up, irrespective of any exceptions.')
```


