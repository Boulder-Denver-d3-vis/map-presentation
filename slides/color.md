## Color!

***

Create a linear scale between two shades.

```javascript
scale = d3.scale.linear()
        .domain(d3.extent(edu, function(d,i) { return d[field];}))
        .range(["#ffeda0", "#f03b20"])
        .interpolate(d3.interpolateHcl);
```

* We're going from Reddish to Yellowish as percentages go from low to high.

* We wrap the color step in a function that takes a field and an associated scale. 

* This lets us do things like add a dropdown to pick which piece of data we want to display.

```javascript
function colorStates(field, scale) {
  d3.selectAll(".states path")
    .attr("fill", function(d) {  
      // We need to check if data exists, othewise color grey
      return d.data ? scale(d.data[field]) : "#333";
    })
```

Let's [take a look!](step3.html)
