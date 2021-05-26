# Class 08 Reading Notes

## List Comprehensions in Python

### Provides Concise way to create lists

- It consists of brackets containing an expression followed by a for clause, then
zero or more for or if clauses.

- The result will be a new list resulting from evaluating the expression in the
context of the for and if clauses which follow it.

- The list comprehension always returns a result list.

```py 
new_list = []
for i in old_list:
    if filter(i):
        new_list.append(expressions(i))
```

- you can obtain the same thing using list comprehension

```py
new_list = [expression(i) for i in old_list if filter(i)]
```

### Syntax

- starts with a []

```py
[ expression for item in list if conditional ]
```

- equivalent to

```py
for item in list:
    if conditional:
        expression
```

### Breakdown

```py
new_list = [expression(i) for i in old_list if filter(i)]
```

- new_list
  - the new list

- expression(i)
  - expression is based on the variable used for each element in the old list

- for i in old_list
  - the word for followed by the variable name to use, followed by the word in the old list

- if filter(i)
  - apply a filter with an if-statement

### Examples

- create a simple list

```py
x = [i for i in range(10)]
print x

# This will give the output:
[0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
```

- create a list using loops and list comprehension

```py
# You can either use loops:
squares = []

for x in range(10):
    squares.append(x**2)
 
print squares
[0, 1, 4, 9, 16, 25, 36, 49, 64, 81]

# Or you can use list comprehensions to get the same result:
squares = [x**2 for x in range(10)]

print squares
[0, 1, 4, 9, 16, 25, 36, 49, 64, 81]
```

- Multiplying parts of a list

```py
list1 = [3,4,5]
 
multiplied = [item*3 for item in list1] 
 
print multiplied 
[9,12,15]
```

- show the first letter of each word

```py
listOfWords = ["this","is","a","list","of","words"]

items = [ word[0] for word in listOfWords ]

print items
```

- lower/upper case converter

```py
>>> [x.lower() for x in ["A","B","C"]]
['a', 'b', 'c']

>>> [x.upper() for x in ["a","b","c"]]
['A', 'B', 'C']
```

- Parsing a file using list comprehension

```py
# Then create the filter by using list comprehension:

fh = open("test.txt", "r")

result = [i for i in fh if "line3" in i]

print result
```