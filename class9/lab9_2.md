## Class 9: Exploring datasets on Google Earth Engine

One of the most existing reasons to use and love GEE is their abundant (and free!!) data catalog.

There are a variety of datasets included in the catalog ranging from SRTM (elevation) data to nighttime lights and land cover data. GEE has a highly detailed page for each data which aims at helping developers and analysts get stared with using given data.

I recommend taking some time to explore these datasets before your next project. GEE's data catalog can be explored here: https://developers.google.com/earth-engine/datasets

### 1. Understanding the data catalog information page through Landsat 8 data:

To better understand how to utilize GEE's datasets we'll start by exploring one of its most popular data: the Landsat 8 imagery.

In this dataset page (https://developers.google.com/earth-engine/datasets/catalog/LANDSAT_LC08_C02_T1_L2) there is a detailed documentation of important components of the data:

* **Datasets availability:** details the dates the imagery exists and can be queried. For Landsat 8, the data starts from April 2013 through today. When working with image collections you will find the dates specification quite useful.
* **Dataset provider:**  which company/academic institution or organization are in charge of updating and possibly curating the data. In some cases we will want to access the methodology behind the data or credit the provider.
* **Earth Engine Snippet:** this snippet will be used in the script to specify the image or image collection we are interested in accessing.
* **Tags:** will helps us find some related datasets that could enrich our analysis/project.
* **Description:** this section will provide important information about how the data was collected and how to interpret it.
* **Bands:** provides a description of all bands included in this data. Oftentimes the satellite records images using more than one band. Those can later be either used in conjunction or separately.

In our case (Landsat 8) there are many bands available. For example, SR_B2 is the blue band, SR_B3 is the green band and SR_B5 is the near infrared band.

* **Code example:** this section is pretty useful in providing a quick code to run and view the data using the GEE interface. The easiest is to click "open in code editor" to get started quickly.

### 2. Exploring the data catalog information page through Landsat 8's data:

![LANDSAT 8:](https://github.com/avigailvantu/UDM2021/blob/main/class9/landsat8.png)

To access USGS Landsat 8 Level 2, Collection 2, Tier 1 data we'll need to use ee.ImageCollection("LANDSAT/LC08/C02/T1_L2") as a code snippet in the GEE code editor.

By scrolling all the way down on this dataset page you can find an example code on how to use this data. Copy-paste it into your GEE code editor https://code.earthengine.google.com/

Once copied, "Run" the code and wait a few seconds for the results of the analysis to be generated.

You should be zoomed into Nevada and see a satellite image on the map view. Explore the maps by zooming in and out on the map.

### 3. Understanding the code:
Let's try to break down this code slightly:


```javascript
var dataset = ee.ImageCollection('LANDSAT/LC08/C02/T1_L2')
    .filterDate('2021-05-01', '2021-06-01');
```

The script starts with defining a variable which is the data we will be working with: the Landsat 8 data collection. We query this data collection using the code snippet we've seen on the data catalog : LANDSAT/LC08/C02/T1_L2. Next we filter the date for the images we want to access: in this case from May 1st to June 1st 2021.

Next is a scaling function which we will not delay on. Later on 3 bands are being used for the visualization:
```javascript
var visualization = {
  bands: ['SR_B4', 'SR_B3', 'SR_B2'],
  min: 0.0,
  max: 0.3,
};
```

Looking into the bands tab we can easily see that the visualization is using the following bands:
red (SR_B4), blue (SR_B2) and green (SR_B3) aka RBG.

The two last lines specify the center of the map: Map.setCenter(-114.2579, 38.9275, 8)

and adds the dataset and visualization variables as a map layer called "True color"

 ### 4. Test things out yourself:

 Finally, we can change things up a bit in the code.

 * Filter dates: we can specify any date within the available data (from 2013 to Oct 2021. Try filtering April 2021 through August 2021.  
 * Change the center of the map to Downtown Brooklyn 40.693921073613296, -73.98712431082116
 * Only display the red band (SR_B4).
 * Rename the layer name to : " Red band"

 After the above mentioned changes my map looks like this:

 ![s](https://github.com/avigailvantu/UDM2021/blob/main/class9/Screen%20Shot%202021-11-01%20at%208.29.13%20PM.png)

 ### 4. Use the inspector tool to query the map results:

 Finally, once you click on the "inspector" tool you'll be able to query the value for a particular pixel on the map. 
