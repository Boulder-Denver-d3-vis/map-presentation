## Setup

***

Load d3, fetch your data with ```d3.csv()``` and your JSON geometry with ```d3.json()```

Then, loop over our edu data and turn strings into numbers:

```javascript
    var svg, path, fields;
    svg = d3.select("#container").append("svg");
    fields = [ "1990-advanced", "1990-bachelors", "1990-hs", "1990-not-hs", "2000-advanced",
    "2000-bachelors", "2000-hs", "2006-advanced", "2006-bachelors", "2006-hs", "2007-advanced",
    "2007-bachelors", "2007-hs", "2008-advanced", "2008-bachelors", "2008-hs", "2009-advanced",
    "2009-bachelors", "2009-hs"];

    d3.json("data/us.json", function(us) {
      d3.csv("data/education.csv", function(edu) {
        edu.forEach(function(d) { 
          fields.forEach(function(field) {
            d[field] = parseFloat(d[field]);
          });
        })
        svg.append("text").attr("transform", "translate(0,20)").text("We have " + edu.length + " edu entries.");
        console.log(edu[50]);
      });
    });
```
