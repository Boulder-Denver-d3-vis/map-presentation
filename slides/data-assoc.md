## Associate our data

***

  We need to associate our education data with each state. 

  Fortunately we have an ID field that is shared between the two.

***

All our fields need to be numbers, and findable by ID.

```javascript
edu.forEach(function(d) { 
  fields.forEach(function(field) {
    d[field] = parseFloat(d[field]); // Interpret as numbers
  });
  dataById[d.Code] = d; // Make an entry for each ID, from Code in the CSV.
})
```

Add each state's data to the feature it's associated with:

```javascript
states = topojson.feature(us, us.objects.states).features;
states.forEach(function(d) {
  d.data = dataById[d.id]; // Get the data for each state and store it on the feature object
});
```

