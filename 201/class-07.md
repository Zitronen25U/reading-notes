# Class 07 Reading Notes

## Domain Modeling

### What is it

- process of creating a conceptual model in code for a specific problem. Describes the various entities, their attributes and behaviors as well as the constraints
- can validate the understanding of a specifi problem among various stakeholders. 
- model its behaviors with small methods that focus on doing one job well
- create instances using the >new keyword
- store the newly created object in a var
- use the >this variable within methods so you can access the objects and properties from inside

## HTML Book

### Tables

- A table represents the info in a grid format
- allows us to udnerstand complex data by referencing information on two axes
  - each block in the grid is referred to as a **table cell**
- > table> element is used to create a table. 
  - written out by rows
- > tr> indicates the start of each row
  - > td> is used to follow 

- > table>
- > tr>
- >   td>

- table heads are used with the <th> tag

- to have table spread across the entire page, use the > colspan within the <td> tag
  - > td colspan> 

- if you want entries to span down across more than one row
  - > td rowspan> 

- Three elements that help distinguish between the main content of the table and the first and last rows
  - >thead> 
    - headings of table sit inside this elements
  - >tbody>
    - body should sit inside
  - >tfoot>
    - the footer belongs inside here

## JavaScript

### Constructing an Object

- the new keyword and the object constructor create a blank object
- EX
  - > var hotel = new Object();
  - it is a constructor function

- can delete objects with
  - > delete tag
    - > delete hotel.name = park
    - name is deleted and replaced with park

- can construct many objects by placing in the brackets
  - > function hotel(name, rooms, booked)

### THIS

- the keyword this is commonly used inside a function
- referes to an object within a specified function

### Arrays

- secretly a special type of object
- they holy a related set of key/value pairs

### Built in Objects

- browsers come witha  set of built in objects
  - things like window size

- objects you create will usually be specifically written to suit your needs


### OBJECTS ARE CONFUSING