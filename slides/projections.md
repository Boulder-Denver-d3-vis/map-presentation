## A brief word on Projections

A geographical projection is the formula applied to the spherical earth in order to get a flat 2-d representation.

There are lots of different ways to do this, with tradeoffs for each one.

* d3.geo includes [most of the basics](https://github.com/mbostock/d3/wiki/Geo-Projections)
* The d3-geo-projection project has [many more](https://github.com/d3/d3-geo-projection/)
* Jason Davies has implemented [some unusual examples](http://www.jasondavies.com/maps/)

***

We're going to use Albers' USA, an equal-area conic projection centered over the USA. [More info here](http://en.wikipedia.org/wiki/Albers_projection) We have some shape distortion, but minimal area distortion.
