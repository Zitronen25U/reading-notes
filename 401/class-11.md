# Class 11 Reading Notes

## What is Jupyter lab?

### Video Notes

- supports file formats

### Text editor

- syntax and indent

- fulll support for system shells

### Common formats

- all img's can be converted to text or notebooks

### This video is funny lol

### Notebooks

- work with data and code together

- when opens, you're in command mode
  - navigate
  - framework
  - use arrow keys to nav
  - For cells
    - add above (a)
    - b add below
    - c copy
    - v paste
    - cut x
    - dd delete
    - undo z
    - redo shift + z
    - md with m
    - y = code

- edit mode
  - press enter to edit
  - shift enter to see resluts of typed content
  - y to change to code
  - shift + enter will run that cell

- menu options
  - many helpful commands

## NumPy Tutorial: Data Analysis with Python

- commonly used python data analysis package.

### Lists of List for CSV Data

- In the below code, we:
  - Import the csv library.
  - Open the winequality-red.csv file.
  - With the file open, create a new csv.reader object.
  - Pass in the keyword argument delimiter=";" to make sure that the records are split up on the semicolon character instead of the default comma character.
  - Call the list type to get all the rows from the file.
  - Assign the result to wines.

```py
import csv
with open('winequality-red.csv', 'r') as f:
    wines = list(csv.reader(f, delimiter=';'))

print(wines[:3])

[['fixed acidity', 'volatile acidity', 'citric acid', 'residual sugar', 'chlorides', 'free sulfur dioxide', 'total sulfur dioxide', 'density', 'pH', 'sulphates', 'alcohol', 'quality'], ['7.4', '0.7', '0', '1.9', '0.076', '11', '34', '0.9978', '3.51', '0.56', '9.4', '5'], ['7.8', '0.88', '0', '2.6', '0.098', '25', '67', '0.9968', '3.2', '0.68', '9.8', '5']]

qualities =
[float(item[-1]) for item in wines[1:]]
sum(qualities) / len(qualities)

# 5.6360225140712945 is the result
```

### Numpy 2-Dimensional Arrays

- create an array using the **numpy.array** function

- if you pass in a list of lists, it will auto create a NumPy array with the same number of rows and collumns

### Alternate ways to create arrays

- numpy.zeros

### Using NumPy to read in Files

- use **numpy.genfromtxt** 

- reads in our initial data

### Indexing NumPy arrays

- we have arrays, but how do we access them?

- use the bracked notation to access row, then column 

- ex. [3,4]

### Slicing NumPy Arrays

- use a colon. 

- indicates we want to select all elements fro the starting index up to but not including the end index

- wines[0: 3, 3]

