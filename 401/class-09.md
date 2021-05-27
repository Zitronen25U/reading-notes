# Class 09 Reading Notes

## Dunder Methods

### What are Dunder Methods

- special methods are a set of predefined methods you can use to enrich your classes

- double underscore (dunder)

- ex. __init__ __str__

- TREAT THEM LIKE NORMAL LANGUAGE FEATURE

- BEFORE

```py
class NoLenSupport:
    pass

>>> obj = NoLenSupport()
>>> len(obj)
TypeError: "object of type 'NoLenSupport' has no len()"
```

- After

```py
class LenSupport:
    def __len__(self):
        return 42

>>> obj = LenSupport()
>>> len(obj)
42
```

### Special Methods and the Python Data Model

- design is known as the Python Data model

- a powerful AP with lots of cool things

### Enriching a Simple Account Class

### Object Initialization: __init__

- cool constructor thing

### Object Representation: __str__, __repr__

- common practice to provide a string representation of your object for the consumer of your class

1. __repr__ "string" representation of an object. This is how you would make an object a class

2. __str__ " informal or nicely printable string representation of an object

### Iteration: __len__, __getitem__, __reversed__

- iterates over our account of an object

### Operator Overloading for Comparing Accounts: __eq__, __lt__

```py
from functools import total_ordering

@total_ordering
class Account:
    # ... (see above)

    def __eq__(self, other):
        return self.balance == other.balance

    def __lt__(self, other):
        return self.balance < other.balance
```

### Operator Overloading for Merging Accounts: __ad__

- everything is an obj in py

```py
def __add__(self, other):
    owner = '{}&{}'.format(self.owner, other.owner)
    start_amount = self.amount + other.amount
    acc = Account(owner, start_amount)
    for t in list(self) + list(other):
        acc.add_transaction(t)
    return acc
```

### Callable Python Objects: __call__

- can make an obj callable like a regular function by adding this

```py
class Account:
    # ... (see above)

    def __call__(self):
        print('Start amount: {}'.format(self.amount))
        print('Transactions: ')
        for transaction in self:
            print(transaction)
        print('\nBalance: {}'.format(self.balance))
```

### Context Manager Support and the With Statement: __enter__, __exit__

```py
class Account:
    # ... (see above)

    def __enter__(self):
        print('ENTER WITH: Making backup of transactions for rollback')
        self._copy_transactions = list(self._transactions)
        return self

    def __exit__(self, exc_type, exc_val, exc_tb):
        print('EXIT WITH:', end=' ')
        if exc_type:
            self._transactions = self._copy_transactions
            print('Rolling back to previous transactions')
            print('Transaction resulted in {} ({})'.format(
                exc_type.__name__, exc_val))
        else:
            print('Transaction OK')
```

## Basic Statistics in Python - Probability

### What is probablity 

- an **event** is some outcome of interest

### From statistics to probability

```py
import random
def coin_trial():
heads = 0
for i in range(100):
    if random.random() <= 0.5:
        heads +=1
    return heads
def simulate(n):
    trials = []
    for i in range(n):
        trials.append(coin_trial())
    return(sum(trials)/n)
simulate(10)
>>> 5.4
simulate(100)
>>> 4.83
simulate(1000)
>>> 5.055
simulate(1000000)
>>> 4.999781
```

### The data and the distribution

- The most important qualities to notice about the normal distribution is its symmetry and its shape.

```py
import csv
with open("wine-data.csv", "r", encoding="latin-1") as f:
    wines = list(csv.reader(f))
```

