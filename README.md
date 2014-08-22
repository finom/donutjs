donut.js
========

Simplest cross-browser (VML+SVG) donut chart generator

[Live example](http://jsbin.com/fuxesa/3)

![Demo screenshot](http://i.imgur.com/aTPdXPh.png)

## Usage
```js
var myDonutDiv = donut(options); // returns div with donut
```
### Options
- ``el`` (Node) -- DOM node where donut should be placed (optional)
- ``data`` (Array) -- array of objects (eg ``{value: 42}``)
- ``size`` (Number) -- diameter of donut (100 by default)
- ``weight`` (Number) -- weight of arcs (size minus donut hole diameter) (20 by default)
- ``colors`` (Array) -- list of colors (``['#555']`` by default)

```js
var myDonut = donut({
  el: document.getElementById( 'container' ),
  size: 150,
  weight: 30,
  data: [{
    value: 1,
    name: 'A'
  },{
    value: 2,
    name: 'B',
    customData: 'Yeah'
  },{
    value: 3,
    name: 'C'
  },{
    value: 4,
    name: 'D'
  }],
  colors: [ '#80a8cc', '#da3b3e', '#ffa921', 'red' ]
});
```

If weight === size/2 then you get pie chart:

![Donut](http://i.imgur.com/SzBRLVS.png)

```js
var myDonut = donut({
  el: document.getElementById( 'container' ),
  size: 150,
  weight: 75,
  ...
});
```

### Methods
- ``setColor(arc, color)`` -- sets arc color
- ``data(arc[, data])`` -- gets or sets data depending on second parameter

```js
var arc = document.getElementById( 'container' ).querySelector( '[data-name="B"]' );
alert(donut.data(B_Arc).customData);

donut.setColor(arc, '#8dc700');
```

### 

**Lisensed under WTFPL**
