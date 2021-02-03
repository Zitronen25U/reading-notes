
# HTML & CSS

## CHAPTER 15: Layout

### Key Concepts

- Building blocks
  - CSS treats each HTML element as if it is in its own box
  - will either be a block-level box or an inline box

- **Block-Level**
  - Start on new line
  - ex h, p, ul, li

- **Inline Elements**
  - flow in between surrounding text
  - ex: img, b, i

- If one block element sits inside another, the outer box is known as the containing element (container);

- position
  - normal flow
    - every block element appears on new line causing each item to appear lower down the page
  - relative
    - this moves an element from the position it would be in normal, shifting it to the top, right, bottom or left of where it would have been placed.
  - Absolute
    - does not affect the position of any surrounding elements
  - fixed 
    - positions in relation to users browser
  - foating
    - position things to the far left or far right of normal flow elements

- z-index 
  - controls which element appears on top

- clear 
  - no element should touch the left or right hand sides of a box
  - left
    - left side wont touch
  - right
    - right side wont
  - both
    - neither left or right
  - non 
    - elements **CAN** touch

- **Liquid Layouts**
  - uses percentages to specify the width of each box so that the design will stretch to fit the size of the screen

- Grids
  - can break pages apart by px size into grids

- **Multiple Style Sheets**
  - can use style sheets to control the layout and another to control the fonts and other things
  - can use @import and a URL to get a styles page