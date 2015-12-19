#CSS and HTML responsive grid of hexagons.

[View live demo](http://web-tiki.github.io/responsive-grid-of-hexagons/)


![Responsive grid of hexagons](http://i.imgur.com/COH7pIV.png)

# Spacing and sizing calculations
Everything here works in percents to make this grid responsive.


## Width of the hexagons

```
w = width of the hexagon  
n = number of hexagons per odd row  
m = width of all left and right margins

w = (100 - m) / n
```

## Height of the hexagons
The height of the hexagons it defined by the padding bottom on the .hex element. This way the height changes according to the width of the hexagons and they keep their aspect ratio.

```
height = width * sin(60deg)
```
## Spacing
### Horizontal
Horizontal margins are only applied in between hexagons. They are fluid and equal to 1% of width.

Each even row is pushed to the right (1/2 hexagon width + 1/2 hexagon horizontal spacing)

### Vertical
To make the vertical spacing between the hexagons the same as the horizontal spacing, the top and bottom margins of the even rows are negative.

```
m = margin top and bottom  
h = 1/2 height of hexagon  


m = - h + h * cos(60deg) + sin (45deg)
```
