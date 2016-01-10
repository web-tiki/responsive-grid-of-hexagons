#CSS and HTML responsive grid of hexagons.

**[View live demo](http://web-tiki.github.io/responsive-grid-of-hexagons/)**

![Responsive grid of hexagons demo](http://i.imgur.com/COH7pIV.png)

##Features
* The hexagon grid is responsive according to the width of the container
* Hexagons keep their aspect ratio according to their width
* The number of hexagons per row is adaptive and changes from 5 to 2 on media query break points
* A title and short text slide in on hover
* Focused hexagons are highlighted and can be cycled through with tab

## Customizing the hexagon grid
**Text and hover effect:**  
The CSS for the text and hover effect is identified in the `hexagons.css` stylesheet. You can remove it completly or change the hover effect, font, size...  
**Changing the number of hexagons per row:**  
The sizing and spacing defines the number of hexagons per row. The CSS properties for that are all in the media queries.
## Spacing and sizing calculations
Everything works in percents to make the hexagon grid responsive.
### Width of the hexagons
```
w = width of the hexagon
n = number of hexagons per odd row
m = width of all left and right margins

w = (100 - m) / n
```
### Height of the hexagons
The height of the hexagons it defined by the bottom padding on the `.hex` element. This way they keep their aspect ratio and height changes according to the width.
```
height = width * sin(60deg)
```
## Spacing
### Horizontal
Horizontal margins are only applied in between hexagons. They are fluid and equal to 1% of width.  
Even numbered rows are pushed to the right with left margin on the first hexagon 
```
m = left margin on first hexagon of even rows
w = width of hexagons
s = space between hexagons

m = (w + s)/2
```
### Vertical
To make the vertical spacing between the hexagons the same as the horizontal spacing, the top and bottom margins of the even rows are negative.

```
m = margin top and bottom  
h = 1/2 height of hexagon
s = horizontal spacing between hexagons


m = - h + h * cos(60deg) + s * sin (60deg)
```
