# Class 19 Reading Notes

## Regex Tutorial

- sequence of characters used to check whether a pattern exists in a given text

### How to

- import re
  - library that supports regex

- re library has some useful functions
  - comp chaile()
  - search()
  - findall()
  - sub()
  - split()
  - many more!

### Basic Patterns: Ordinary Characters

- easily tacke many basic patterns in Py using ordinary characters

- ordinary characters can be used to perform simple exact matches

```py
pattern = r"Cookie"
sequence = "Cookie"

if re.match(patter, sequence):
    print("Match!")

else: print("Not a match!")
```

- this example is a match

- the match function returns a match object if the text matches the pattern

- **r** in front of the string meant raw, literal string btw
  - for example \ is just a backlash with an r, rather than being an escape sequence

### Wild Card CHaracters: Special Characters

- characters that do not match themseles as seen, but have a special meaning when used in REGEX

- reserved metacharacters basically

- . - A period. Matches any signle character except the newline character

```py
re.search*(r'Co.k.e', 'Cookie').group()
```

- returns Cookie

- ^ - A caret. Matches the start of the string

```py
re.search(r'^Eat', "Eat cake!").group()
```

- this will return Eat

- $ - matches the end of a string

```py
re.search(r'cake$', "Cake! Let's eat cake").group()
```

- this will return the last 'cake'

- [abc] - Matches a, or b, or c

- [a-zA-Z0-9] - matches any letter from (a-z) (A-z) or (0-9)

- \ 

  - if a character following the \ is a **recognized escape character** then the special meaning of the term is taken [scenario 1]

  - else if the character following the \ is not, then the \ is trated like any other character [scenario 2]

  - \ can be used in front of all the metacharacters to remove their special meaning [scenario 3]

```py
# Scenario 1

re.search(r'Not a\sregular character', 'Not a regular character').group()
```

- the \s defines a space, and is an escape character

```py
# scenarion 2

re.search(r'Just a \regular character', 'Just a \regular character').group()
```

- this returns 'Just a \regular character'

```py
# scenario 3

re.search(r'Just a \\sregular character', 'Just a \sregular character').group()

```

- returns 'Just a \\sregular character'

- \w matches any single letter, digit, or underscore

- \W matches any character not covered with \w

```py
print("lowercase w:", re.search(r'Co\wk\we', 'Cookie').group())
```

- returns Lowercase w: Cookie

- \s matches a signle whitespace, like spaces, newlines, tabs

- \S matches any not in that

- \d matches decimal digit 0-9

- \D matches not a decimal

- \t matches tab

- \n matches newline

- \r matches return

- \A matches only at the start of the string

- \Z matches only at the end of the string

## shutil - High-level file operations

- includes high-level file operations such as copying and archiving

