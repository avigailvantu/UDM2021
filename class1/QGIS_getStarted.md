## Class 1: Get started with QGIS

Welcome to Github! Today we will go through our first experience with a very popular mapping tool called QGIS.

#### 🦑 Downloading QGIS 3 🦀
To get started you will need to download QGIS. Note that QGIS is an open source tool, it's totally free and can be downloaded on any OS (i.e. both MacOS and Windows).

Here's a link to QGIS's download page:

[https://qgis.org/en/site/forusers/download.html]

Any version of QGIS 3 should work for our class but I'm using 3.8.3.

### The QGIS interface

Open QGIS and create a new project. You should see QGIS' main interface.
![alt text](https://github.com/avigailvantu/c4sue2021/blob/main/labs/class_1/QGISInterface.jpg)

#### 1. Menu bar:
Among many other functionalities, the menu bar at the top of the project will allow you to run analysis, load data, and save a project.  

#### 2. Browser & layer panel:
This section on the left part of your QGIS project includes some online maps you can display and the layers that are loaded into your current project.  

#### 3. Map area
Most of your QGIS project will be the map area where the data will be displayed.

#### 4. Status bar:
The bottom part of your QGIS interface will show the coordinate system for the project as well as the scale.

### First project: Display a map of the world.

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
