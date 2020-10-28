# CSS 

## What is CSS

- CSS
    - Cascading Style Sheet
    - How does it differ from HTML?
        - Done after HTML, different language
        - Reads from top to bottom

- can add directly to html page, or can be a seperate linked page
- scalability
- include values like size of text or images
- easier troubleshooting

Applies to different HTML elements
Can use an id or class to target different areas of a webpage

## Reading Assignment

## Chapter 10

### Understanding CSS

Imagine there is an invisible box around every HTML element. 

- Associates style rules with HTML elements 
- two parts
    - Selector
    - declaration

- Css declaratioins sit inside curly brackets "{}" and each is made up of two parts
    - a property
    - a value

- the "<link>" element can be used to tell HTML document where to find the CSS file used to style the page
- href specifies the path to the CSS file
- type specifies the type of document being linked. value should be text/css
- rel specifies the relatioinship between the HTML and the file it is linked to. the value should be stylesheet when linking to a CSS file

### AN HTML PAGE CAN USE MORE THAN ONE CSS STYLE SHEET

- can place CSS within HTML by using the style command

### HOW CSS RULES CASCADE 

- the later rule will take precedence over the first. Called **Last Rule**
- Specific rules will take precidence over general rules. 

#### Using external Style Sheets

- All of your web pages can share the same style sheet
- Site will load faster because of only 1 style sheet
- No repeating code


## CH 11: COLOR

### Foreground Color

- can specify color properties in 3 ways
    - RGB
    - HEX codes
    - Color Names

### Background Color

- expressed in same ways as foreground 

### Understanding COLOR

- Every color is a mix of RGB
- all values range form 0 to 255
- RGB, HEX CODES, COlor names, Hue, saturation, brightness

### Contrast

- ensure's text is legible 
- increase hight and weight of font to make it easier to read

### opacity

- between 0 and 1. .5 is 50%

### CSS3 HSL Colors

- CSS 3 introduced Hue, Saturation, and lightness colors
- Hue expressed as angles between 0-360
- saturation is a %
- lithness is a % with 0 being white, 50 being normal, and 100 being black

>expressed as background-color: hsla(#,%,%,#) 

- 