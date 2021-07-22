### Our first mini-project: Display a map of the world.

#### Display the layer:

In the status bar:
* Go to Coordinates and type: “world”
* You will see a world map displayed on a map
* Now you can easily zoom in and out using the menu bar options. You can also use the mousepad and press “command” at the same time to zoom in with more control. Switch between the zoom in zoom out and pan buttons  
* Control (command in mac) + shift + F - will zoom the map to full extent.

#### Inspect attribute table 🎨

First let's inspect the attribute table for each and every one of the objects on the map. This is where we can see a table of the data in the form of a relational data.

* Right click the layer and choose "Open attribute table". The table includes all the information we have for each data point or polygon in a given layer. In our case it is each country which is represented in a separate line.
* Scroll all the way to the right. You will see the labels, the region, the continent etc.
* We can zoom into this feature. Right click on the feature and choose “zoom into feature”  
we can also highlight many features, QGIS will display them in yellow.
* Finally we can reverse the choice and display those that we didn’t choose (useful if we want to exclude a small number of polygons)

#### Inverted polygons 🦞
* To draw water around our world map we will need to first duplicate the existing layer.  
* Then go to the layer's properties
* In symbology:
  * In the dropdown choose: “Inverted Polygons”
  * Symbol layer type: “gradient fill”
  * Spread: “repeat”

#### Apply labels 🎋
To show the labels for each and every country follow these steps:

* Go to the layer's properties
  * Labels: single labels
  * Change the font to Helvetica
  * Font size 7
  * Color: white
  * Style: bold
  * Type case: all upper case

  Your map should look something like this:

  ![alt text](https://github.com/avigailvantu/c4sue2021/blob/main/labs/class_1/Worldmap.jpg)

#### Save your project
  Create a C4SUE folder on your local machine.
  Go to Project - save as - in the files type dropdown chose QGIS files (*.qgs *.QGS).

  ###### 👏🏻 VOILA! You made it through the first tutorial. 👏🏻
