# READING NOTES FOR CLASS 3!

## HTML

### Chapter 3: “Lists” 

- 3 types of lists
  - ordered lists - ol
  - unordered lists  - ul
  - definition lists - dl 

### Chapter 13: “Boxes”

- box dimensions
  - width 
  - height 
  - both measured in px

- limiting width and height
  - min-width
  - max-width
  - min-height
  - max-height

- overlow tells the browser what to do with content that doesn't fit in box
- hides extra content outside of the box

- border seperates boxes
- margin is the space in between the borders of adjacent boxes
- padding is the space between the border of a box and any content contained within that box

- border width
- border style 
  - solid
  - dotted
  - dashed
  - double
  - groove
  - ridge
  - inset
  - outset
  - hidden/none

- border color
- There are shorthand border codes you can find

- display types
  - inline
  - block
  - inline-block
  - none

- you can use images as borders
  - border-image
  - slices image into 9 parts to be used as border

- box shadow
  - put shadow around box
  - values
    - horizontal offset
    - vertical offset
    - blur distance
    - spread of shadow

- round corners
  - border-radius
  - makes borders round!



## Javascript

### Chapter 2: “Basic JavaScript Instructions

- Arrays
  - stores list of values
  - accessed as values on a list, counting up from 0
  - can update and assign variables from an array later in the code

### Chapter 4: “Decisions and Loops”

- if else statemetns
  - if evaluates if its true
  - else is what to do if it's false

- switch statements
  - default option that is run if none of the cases match
  - if a match is found, that code is run then a break statement stops the rest of the switch

- Truthy & Falsy
  - values that are treated as true or false
  - every value in JS can be treated as true or false
  - for example
    - 0 is technically a value, but outputs a false statement
    - null can be a string value, but is also false
    
  - checking equality 
    - unary operator sees an if statement and checks if an element is present
  
  - * LOOPS 

  - Check a condition. If it returns a true value, runs the code
    - For most common loop. 
      - condition is usually a counter
    - While for when you don't know how many times the loop needs to run
      - can be something other than a counter
    - Do While always will run the statements at least once
      - will run even if value is false

- counters 
  - typically uses i. 
