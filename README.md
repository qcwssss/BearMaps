# BearMaps
BearMaps is an map-like web app, on which the users can view and access the geo-info.
I also deployed the program on Heroku server, you can open the web link above and see how it works.
#### You can view my BearMaps on Heroku server. [BearMaps_Link](http://bearmaps-fa20-cq210829.herokuapp.com/)
 
## Description
A Google Map-like web application based on UCB CS61B assginments.
This map app has several features:
  - 1. support autocomplete system in the query box by implementing Trie data structure. 
  - 2. a location-search function to find the nearest vertices based on the user input using KD-Tree data structures.
  - 3. a turn-by-turn navigation function that draw a closest route using A* search algorithm and generated a sequence of navigation instructions .

**The images below displays the above functions.**
     
   - ***1. autocomplete*** <img width="960" alt="bearmaps3" src="https://user-images.githubusercontent.com/83999326/135198580-090af6c9-1d3a-4b03-8881-1089b92bfbcc.png">
   - ***2. navigation*** <img width="960" alt="bearmaps4" src="https://user-images.githubusercontent.com/83999326/135198586-23a6c751-4fde-41ec-ac66-61dc8d607aa3.png">
   - ***3. location search*** <img width="960" alt="bearmaps2" src="https://user-images.githubusercontent.com/83999326/135198588-0b6bc783-ad5e-4452-aa2f-3c8ea54b0a0a.png">


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
  - `KDTree pointSet` - a k-dimensional tree data structure stores all the points associated with the reachable `Nodes` in this graph.

## Algorithms
### AugmentedStreetMapGraph
- `closest`
  - The `closest` method takes in map coordinates, `(lon, lat)`, and returns the `id` of the graph `Node`, whose associated map `Point`, is closest to the given coordinates. We pass the given coordinates into our `KDTree`’s `nearest` method to get the nearest `Point`. We then use the `nodePoint` map to find the graph `Node` associated with the returned `Point`.

## Acknowledgements
Adapted from Project2 of UCB CS61B-Data Structures course, taught by Josh Hug.

My solutions for other projects, labs and homeworks of this course can be found at [CS61B_20Fall_Assignments](https://github.com/qcwssss/CS61B_20Fall). 
