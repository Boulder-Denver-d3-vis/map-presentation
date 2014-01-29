## Draw USA and States:

***

Set a projection, and set it up.

```javascript
var width = 960, height = 500;

var projection = d3.geo.albersUsa()
    .scale(1000).translate([width / 2, height / 2]);

var path = d3.geo.path().projection(projection);

```

Draw some lines!

```javascript
svg.append("g")
  .classed("states", true)
  .selectAll("path")
  .data(topojson.feature(us, us.objects.states).features)
  .enter()
  .append("path")
  .attr("d", path)
```
