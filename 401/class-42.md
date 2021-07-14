# Class 42 Reading Notes

## Dunder Methods

- double underscore = dunder

- used to enhance your classes

```py
class blahBlah():
    def __init__:
        self.volume = volume
```

this   ``__init__`` turns this class into a constructor! 

### STR and REPR

```py
def __str__(self):
    pass
    #  The “informal” or nicely printable string representation of an object. This is for the enduser.

def __repr__(self):
    pass
    # The “official” string representation of an object. This is how you would make an object of the class. The goal of __repr__ is to be unambiguous.
```

## Iterators

- iterators are loops or anything that repeats. We don't want to repeat forever

Here's and example of an iterator

```py
class BoundedRepeater:
    def __init__(self, value, max_repeats):
        self.value = value
        self.max_repeats = max_repeats
        self.count = 0

    def __iter__(self):
        return self

    def __next__(self):
        if self.count >= self.max_repeats:
            raise StopIteration
        self.count += 1
        return self.value
```

