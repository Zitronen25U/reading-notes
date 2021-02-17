# Charts

## EASILY CREATE STUNNING ANIMATED CHARTS WITH CHART.JS

- Charts are better at displaying data visually than tables
- Chart.js plugin is a great start that uses HTML5

### Start with downloading Chart.js

- How to

1. copy the Chart.min.js out of the unzipped folder
2. put inot the dir you're working with.
3. create a new HTML page and import the script 

- > <script src='Chart.min.js'></script>

### Drawling a line chart

- first thing is to create a canvas element in our HTML in which chart can draw our chart
  - ><canvas></canvas>

- create a script that will retrieve the items of the script
- use the getElementById
- can pass in things like fill color, stroke color, pointstrokecolor, data and more

### Pie chart

- much easier. only need to supply a value and a color for each section

> var pieData = [
  {
    value: 20
    color: "____"
    };
    {
      value: 40,
      color:"____"
    };
    {
      value: 10,
      color:"___"
    };
];

- then add the options:

> var pieOptics = {
  segmentShowStroke: false,
  animateScale: true
};

### Bar Charts

- similar to line charts, except that it adds labels, and puts the value's for the line in a **dataasets** tag

## Basic Usage of Canvas

- canvas tag look like an img tag without the src and alt attributes.
- only has width and height attributes
- can be set using DOM properties
- auto set at 300x150px
- renders with getcontext('2d') for 2d graphics

## Drawing shapes

### THE GRID:

- first, you gotta start with rectagles
- >fillRect(x, y, width, height)
- draws a filled rectangle
- > strokeRect(x, y, width, height)
- draws a rectangle outline
- > clearRect(x, y, width, height)
- clears the rectangle area, making it fully transparent

### Drawing Paths

1. Create Path

2. use drawing commands

3. once created, you can stroke or fill the path to render it

- >beginPath()
  - creates a new path

- Path Methods
  - > closePath()
    - adds a stright line to the path
  - > stroke()
    - draws the shape by stroking its outline
  - > fill()
    - draws a solid shape by filling the paths content area

### There are basically an infinite amount of shapes you can make with this

## Styles and Colors
- FillStyle = color for shapes
- strokeStyle = color for outlines


### Line Styles

- lineWidth = value
- lineCap = type sets appearence of the ends of lines
- lineJoin = type set corner appearence
- miterLimit = value establishes limit
- getLineDash() returns the current line dash pattern array containing an even number of non negative numbers (WHAT!?)
- setLineDash(segments) set the current line dash pattern
- lineDashOffset = value



### Drawing Text

- >fillText(text, x, y., [, maxWidth])
- fills a given text at the given xy pos
- >strokeText(text, x, y [, maxWidth ])

### Styling Text

- font = value (css)
- textAlign
- textBaseline = top, hanging, middle, alphabetic, ideographic, bottom
- direction ltr, rtl, inherit. default is inherit

