## Class 9: Getting started with JavaScript for GEE

No prior knowledge in coding is needed to get started with some simple codes in GEE's Code Editor. Here we will cover some useful lines of code for you to get started with GEE.

In Earth Engine we will usually use images or image collections. **Images** are georefrenced, with a particular resolution and with a set projection. As it names implies, **image collections** are collections of images and are usually composed of satellite imagery from different dates. On top of their similarity to images, these collections can also be reduced, filtered and sorted.

* The **Map** function applies a function of a set of images (or an entire image collection) and **reduce** aggregates collections into one image (by averaging/minimizing/maximizing etc ).

* **ee.image()** this argument is used to specify which image we use for our code. An image ID needs to go inside the parentheses and it can be found in the data catalog page for a particular data collection "code snippet" section.

* **Map.setCenter()** argument is used to set the center (alt, lon) and the zoom level of the map. Note that this is solely a visualization specification and won't impact the analysis or data query.
* **addLayer()** is used to add a particular image into the map view on GEE's code editor.
This argument can be customized so that only a value range will be displayed on the map and to display an image using chosen color palette (this part of the argument is called visParams).  

### Write a simple code to display the Hansen Global Forest Change data

NASA provided a pretty cool data which reflects the results of a time-series analysis using Landsat images from 2000 to nowdays (https://developers.google.com/earth-engine/datasets/catalog/UMD_hansen_global_forest_change_2020_v1_8)

The results provide a multi band data documenting areas where there was forest gain and loss over this period of time.

* Let's start with writing a simple code to display this data.
* First visualize the data, write this code into your code editor and click Run:

```javascript
var gfc = ee.Image('UMD/hansen/global_forest_change_2020_v1_8');
Map.addLayer(gfc);
```

The first line defines the data as a variable and the second line displays the data on the map.

* Now let's display one band at a time. The main 3 bands for this image collection are: "treecover2000", "loss", and "gain".
start by displaying the tree cover 2020 layer using the following visualization parameters.


Using your previous code, add this variable to the code:

```javascript
var VisParamTS = {
  bands: ['treecover2000'],
  min: 0,
  max: 80,
  palette: ['white', 'green']
};
```

Next, change your Map.addLayer() argument so that you add the tree cover band:

```javascript
Map.addLayer(gfc,VisParamTS, 'treecover');
```
* Now, let's add another band: forest loss

add another var function to define the visualization parameters for the new layer:

```javascript
var VisParamLoss = {
  bands: ['loss'],
  min: 0,
  max: 1,
  palette: ['white', 'red']
};
```
To display this band as a new layer add a Map.addLayer() function below the one you already have:

```javascript
Map.addLayer(gfc,VisParamLoss, 'loss');
```

Once you run this code you should have two layers ( 1. a red and white one for forest loss and 2. a green and white one which displays the tree cover layer).

* Finally, using the same technique let's add another layer to display all three bands in one layer (tree cover, loos and gain):

```javascript

Map.addLayer(gfc, {bands: ['loss','treecover2000', 'gain'],
  min: [0,0,0],
  max: [1,100,1]},
  'forest loss, cover, gain'

);
```

The full code for this lab can be found [here](https://code.earthengine.google.com/683dd5c24d5bfa1eea3c7304bac96238).
