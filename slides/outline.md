## Draw USA and States

Using our ```us``` object, pull in the d3 geo libs, set a projection, and use it to draw.

```
var width = 960,
    height = 500;

var projection = d3.geo.albersUsa()
    .scale(1000)
    .translate([width / 2, height / 2]);

var path = d3.geo.path()
    .projection(projection);

var svg.attr("width", width)
    .attr("height", height);
```
