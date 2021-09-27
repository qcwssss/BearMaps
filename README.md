# BearMaps Design Document

## Description
A Google Map-like web application based on UCB CS61B assginments.


## Classes and Data Structures
### RasterAPIHandler
This class provides `static` methods that allow processing requests from the web browser for map images. These images will be rastered into one large image to be displayed to the user.

This class does not have any instance variables.

### Point
Represents a point on the map.

* Instance Variables
  -  `x` - the x-axis (or equivalent) coordinate of a point.
  -  `y` - the y-axis (or equivalent) coordinate of a point.
  
### AugmentedStreetMapGraph
An augmented graph that is more powerful than a standard StreetMapGraph. Specifically, it supports the following additional operations such as finding a node in the graph whose associated `(lon, lat)` coordinates are closest to some given coordinates.

* Instance Variables
  - `HashMap<Point, Node> nodePointMap` - a map keeping track what graph Node is associated with a certain Point on the map.
  - `KDTree pointSet` - a k-dimensional tree data structure storesall the points associated with the reachable `Nodes` in this graph.


