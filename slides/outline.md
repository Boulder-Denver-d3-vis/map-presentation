## Draw the States:

***

Set a projection, and configure it. (AlbersUsa info [here](https://github.com/mbostock/d3/wiki/Geo-Projections#wiki-standard-projections)

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
[Result](step2.html)
