
# Responsive grid of hexagons with CSS grid layout.
This branch uses **css grid** to layout the hexagons.

CSS grid layout makes the spacing calculations easier to understand and work with.
The features are the same but browser support is not as good a the flexbox version.

## Features
*Same as flexbox version*

## Text and hover effect:
*Same as flexbox version*

## Changing the number of hexagons per row:
*Same as flexbox version* except that the width of the hexagons is defined by the `grid-column-end: span 2;` (each hexagon spans on 2 columns) property and only needs to be defined once. The number of columns is changed with the `grid-template-columns` property in the media queries.

To **change the number of hexagons per row**, you need to:

### Change the number of columns

with the `grid-template-columns` property. 
The value `repeat(4,1fr)` repeats 4 times `1fr` so it makes 4 columns.   
As each hexagon spans 2 columns, there are 2 hexagons on even rows.


### Indent even rows
The even rows (2nd, 4th,6th...) are indented with `grid-column-start: 2;` on the first hexagon of even rows.

**The selector:**  
*Same as flexbox version*

**Value of margin-left:**
*Not needed anymore*

**More info on CSS grid layout:** [MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout)


Created by [web-tiki](https://web-tiki.com)
