## Color!

***

This is a very, very simple color scheme. We're just going from Red to Blue for percentages 0 to 100.

We wrap the color step in a function that takes a field. This lets us do things like add a dropdown to pick year and level of education.

```javascript
function colorStates(field) {
  var colorScale = d3.scale.linear()
    .domain([0,100])
    .range(["#f00", "#00f"])
    .interpolate(d3.interpolateHcl);
  d3.selectAll(".states path")
    .attr("fill", function(d) {  
      // We need to check if data exists, othewise color grey
      return d.data ? colorScale(d.data[field]) : "#333";
    })
```
