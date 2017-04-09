donutjs [![npm version](https://badge.fury.io/js/donutjs.svg)](https://badge.fury.io/js/donutjs)
========

Simple, cross-browser (VML+SVG) donut and pie charts generator

[Live demo](http://jsbin.com/dutexejisa/)

![Demo screenshot](http://i.imgur.com/aTPdXPh.png)

## Usage
For CJS env the library is published as `donutjs`
```
npm install --save donutjs
```

```js
const myDonutDiv = donut(options); // returns div with donut
```

### Options
- ``el`` (Node) -- a DOM node where donut should be placed (optional)
- ``data`` (Array) -- array of objects (eg ``{value: 42, name: 'some name'}``)
- ``size`` (Number) -- diameter of the donut (100 by default)
- ``weight`` (Number) -- weight of arcs (size minus donut hole diameter) (20 by default)
- ``colors`` (Array) -- list of colors (``['#555']`` by default)

```js
const myDonut = donut({
  el: document.getElementById('container'),
  size: 150,
  weight: 30,
  data: [{
    value: 1,
    name: 'A'
  },{
    value: 2,
    name: 'B',
    customData: 'Hello World'
  },{
    value: 3,
    name: 'C'
  },{
    value: 4,
    name: 'D'
  }],
  colors: ['#80a8cc', '#da3b3e', '#ffa921', 'red']
});
```

If ``options.weight === options.size/2`` then you get a pie chart:

![Donut](http://i.imgur.com/SzBRLVS.png)

```js
const myDonut = donut({
  el: document.getElementById('container'),
  size: 150,
  weight: 75, // <--
  ...
});
```

### Methods
- ``setColor(arc, color)`` -- sets arc color
- ``data(arc[, data])`` -- gets or sets data depending on second parameter existence

```js
const arc = document.getElementById('container').querySelector('[data-name="B"]');

alert(donut.data(B_Arc).customData);

donut.setColor(arc, '#8dc700');
```
