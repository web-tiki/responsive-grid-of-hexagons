
# CSS and HTML responsive grid of hexagons.

**[View live demo](http://web-tiki.github.io/responsive-grid-of-hexagons/)**

![Responsive grid of hexagons demo](http://i.imgur.com/COH7pIV.png)

## Flexbox vs CSS grid
This branch uses **flexbox** to layout the hexagons. Another version using **CSS grid layout** is availbale on the [css-grid branch](https://github.com/web-tiki/responsive-grid-of-hexagons/tree/css-grid).  
CSS grid has lower browser support than flexbox (see [canIuse](https://caniuse.com/#feat=css-grid)) but makes the hexagon spacing easier to understand and work with.

## Features
* The hexagon grid is responsive according to the width of the container (`#hexGrid`)
* Hexagons keep their aspect ratio according to their width
* The number of hexagons per row is adaptive and changes from 5 to 2 on media query break points
* A title and short text slide in on hexagon hover and focus
* Hexagons and can be cycled through with tab (keyboard navigation)

## Text and hover effect:
The CSS for the text and hover effect is identified in the `hexagons.css` stylesheet. You can remove it completely or change the hover effect, font, font-size...  

## Changing the number of hexagons per row:
The width of the `.hex` elements defines the number of hexagons per row. The CSS properties that need to be changed are all in the media queries under the `HEXAGON SIZING AND EVEN ROW INDENTATION` comment.  
Each media query changes the number of hexagons per row.

To **change the number of hexagons per row**, you need to:

### Width of `.hex`
Customize the with of the `.hex` elements with:
```
w = width of the .hex elements in percent
x = the number of hexagons you want on the odd rows (1st, 3rd, 5th...)

w = 100 / x
```

Example for 8 hexagons on odd rows (this means there will be 7 hexagons on even rows):
```
w = 100 / 8 = 12.5%
```

### Indent even rows
The even rows (2nd, 4th,6th...) are indented with `margin-left` on the first hexagon of even rows.

**The selector:**  
You can select that hexagon with the `.hex:nth-child(an+b)` selector (more info on on the `nth-child()` pseudo-class on [MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/:nth-child)). To determine the selector, you can use this rule:

```
.hex:nth-child(an+b)

x = the number of hexagons on odd rows(1st, 3rd, 5th...)
Y = the number of hexagons on even rows(2nd, 4th, 6th...)
a = x + y
b = x + 1
```

Example for 8 hexagons on odd rows (this means there will be 7 hexagons on even rows):
```
x = 8
y = 7
a = 8 + 7 = 15
b = 8 + 1 = 9

The selector is : .hex:nth-child(15n+9)
```

**Value of margin-left:**  
The value of margin left is **half the width of one hexagon** so for 8 hexagons on odd row :
```
with of hexagons = 12.5% (see "width of .hex")
margin-left = 12.5 / 2 = 6.25%
```
-------------

Created by [web-tiki](https://web-tiki.com)
