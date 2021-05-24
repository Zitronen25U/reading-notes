# Class 06 Reading Notes

## How to use the Random Module

### What is random module??

- access to functions that support many operations.

- generate random numbers

### When to use it?

- when you want to pick a random number in a given range?

### Random Functions

1. Randint

- random interger

```py
import random
print random.randint(0, 5)
```

2. Random

- if you want a larger number,  you can multiply it

```py
import random
random.random() * 100
```

3. Choice

- generate a random value from the sequence sequence

```py
random.choice( ['red', 'black', 'green'] ).

import random
myList = [2, 109, False, 10, "Lorem", 482, "Ipsum"]
random.choice(myList)
```

4. Shuffle

- shuffles the elements in list in place, so they are in a random order

```py
from random import shuffle
x = [[i] for i in range(10)]
shuffle(x)

Output:
# print x  gives  [[9], [2], [7], [0], [4], [5], [3], [1], [8], [6]]
# of course your results will vary
```

5. Randrange

- generate a randomly selected element form range(start, stop, step)

```py
random.randrange(start, stop[, step])

import random
for i in range(3):
    print random.randrange(0, 101, 5)
```


### Example

```py
import random
import itertools

outcomes = { 'heads':0,
             'tails':0,
             }
sides = outcomes.keys()

for i in range(10000):
    outcomes[ random.choice(sides) ] += 1

print 'Heads:', outcomes['heads']
print 'Tails:', outcomes['tails']
```

```py
$ python random_choice.py

Heads: 4984
Tails: 5016
```

## What is Risk Analysis?

### What is it?

- In any software, using risk analysis at the beginning of a project highlights the potential problem areas.

### Why use Risk Analysis?

- In any software, using risk analysis at the beginning of a project highlights the potential problem areas.

### Possible Risks

1. Use of new hardware
2. Use of new technology
3. Use of new automation tool
4. The sequence of code
5. Availability of test resources for the application

### Unavoidable Risks

1. The time that you allocated for testing

2. A defect leakage due to the complexity or size of the application

3. Urgency from the clients to deliver the project

4. Incomplete requirements

### Risk Magnitude Indicators

- High: means the effect of the risk would be very high and non-tolerable. The company might face loss.

- Medium: it is tolerable but not desirable. The company may suffer financially but there is a limited risk.

- Low: it is tolerable. There lies little or no external exposure or no financial loss.

### Risk Identification

- Business Risks: may come from your company or your customer, not from your project.

- Testing Risks: software testing tools being used.

- Premature Release Risk: a fair amount of knowledge to analyze the risk associated with releasing unsatisfactory or untested software is required

- Software Risks: You should be well versed with the risks associated with the software development process

### The perspective Risk Assesment

- Effect – In case you identify a condition, event or action and try to determine its impact.

- Cause – Initialize scanning the problem and reach to the point that could be the most probable reason behind that.

- Likelihood – say that there is a probability that a requirement won’t be satisfied.

### How to perform Risk Analysis?

- Searching the risk

- Analyzing the impact of each individual risk

- Measures for the risk identified
