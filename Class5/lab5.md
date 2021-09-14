# UDM Lab 5:

## OpenStreetMap using QGIS & Creating Isochrons

As we all know by now, publicly available data comes from different sources. So far we focused mostly on data that comes from official and governmental sources. But there are many more sources to retrieve data from! As we mentioned in class today there are more and more ways for getting data for areas of the world that are "data poor".

One important way to get data from alternative sources is by using Volunteered geographic information (VGI). VGI means the data was crowdsourced from people and one of the most dominant forms of VGI is the open source community around [OpenStreetMap (OSM)](https://www.openstreetmap.org/#map=14/-42.4782/-73.7652&layers=D). OSM's mission is to create an open sourced map for the entire world. The data is added by individuals and is then available for anyone to use free of charge.

Among many other types, data collected on OSM includes amenity data on places like hospitals, schools, fire stations and even.. coffee shops. In addition, infrastructure data like roads and buildings is also available. Generally speaking the OSM data is considered to be very valuable, but not 100% accurate (since it is VGI). It is most useful in areas of the world which lack administrative datasets (e.g. open and census data).

As a side note, OSM operates through local chapters that are in charge of gathering mappers to edit and add data in their city or community. You can find out more about it [here](https://wiki.openstreetmap.org/wiki/Foundation/Local_Chapters).

OSM data can be accessed using multiple methods. Today, we will learn a method that fetches that data using an API. It is quite easy and straight forward and will load the results straight into our QGIS project as a layer.

### Install the QuickOSM plugin

 1. On QGIS's menu bar go to Plugins
 2. On the right menu, make sure you are viewing All
 3. In the search box type : QuickOSM, and chose it from the options below.
 4. Click "Install Plugin" and wait until it's done (should take a few sec).

### Make sure the install worked:

  1. After QGIS is done installing go to the Vector menu. You should see QuickOSM as an option in the menu. Choose QuickOSM--> QuickOSM.
  2. The QuickOSM window will open and you will see the parameters you can change and chose for the data download (Key, Value, and a dropdown with the geographic unit that we are interested in).

### Download OSM data for Hanoi, Vietnam.
  1. Download and load our area of interest for Hanoi on NYU Classes.
  2. Display this Shapefile in your QGIS project

### 1. Get Fast food data for Hanoi 🍔
We have multiple options on how to query the data for Hanoi. We could add the city name and instead of boundary chose key --> Amenity. However, it is useful to try using the Layer Extent option that queries data within a specific polygon, in our case the Hanoi province. This methods will come out handy if you need to get data based on a geographical unit and not for a whole city or country.
1. Go to the QuickOSM window and set the following query conditions: Key= amenity, Value= fast_food.
2. Change the In dropdown to: layer extent and choose your Hanoi polygon.
3. Click Run. This could take a few minutes. Once done, you can remove the un-needed layer types: lines and polygons are not needed this time.
4. You should end-up with two layers: one for the Hanoi boundary (polygon type) and a second one for fast food (point layer).

### Load another layer for Hanoi
1. We will also upload another layer for smaller boundaries within the Hanoi area of interest. Data can be accessed within NYU classes. (Hanoi Smaller)
2. Download and visualize this layer.

### Calculate how many points are there in each polygons
To do se we will use the "Count points in polygon" function.
1. Go to Vector ...
2. In the Polygon dropdown chose the Hanoi_Smaller boundaries layer
3. In the Points dropdown chose the fast food point layer
5. Symbolize and visualize the NUMPOINTS column. Use the best method to slice the data based on the data.

### 2. Download all amenity type data for Hanoi
- Use the same parameters we did for the Fast Food assignment. But now query all amenity data. This will take a few minutes again. Once ready remove any non-point layer types.
- Look at the new layer and investigate the categories. In particular, the amenity column.

### Clip data to the Hanoi polygon.
- Before filtering the data further, we see the data is around our Hanoi BUT also all around it.
- To "get rid" of data outside of our polygon we will clip the point layer to the Hanoi polygon.
- Vector --> Geoprocessing tools --> clip
- In Input layer: choose: amenity , and for overlay choose the Hanoi boundary.
- Run the Clip.
- In a few seconds you should see a new layer named: Clipped. This is the point layer that includes all points inside the Hanoi boundary.
- Now you can remove the initial amenity layer and rename the clipped layer: amenity_clipped

### Select university amenity:
- In the attribute table, go to "select by expression"
- amenity='university' and click "Select features"
- Now export the selection to a new layer: right click the layer and export selected features.  (save selected features by)
- when exporting the layer make sure to unselect all columns and then select only: full_id, osm_id, amenity, name.
- once you save the layer it will display on the map. hide all other point layers.

### Convert multypoint to point layer:
- Go to vector- geometry tools - extract vertics.
- the newly created layer is the university point layer.

### Calculate proximity analysis using Open Route Service
A great way to create a meaningful analysis is to do a network analysis. This type of analysis is common in cases where we want to understand access of a population to specific amenity (e.g. schools or hospitals). It is also a common method for emergency management. To do so we will first need to download another plugin named Open Route Service. This is another API based plugin that uses Open Street Map to calculate distances.

- Download Open Route Service as a plugin.
- To calculate proximity using the ORS service you will need an account and to acquire an API key.
  1. Create account on https://openrouteservice.org/dev/#/login
  2. Get an API token: go to the dev dashboard. On the bottom fill out the "Request a token" section and you should be getting a token.
- Once you have the token open your ORS plugin navigate to the ORS plugin (web-->ORS tools--> ORS tools)
- Go to the plugin setting and copy paste your newly created API key in the API KEY field, insert https://api.openrouteservice.org in the Base URL. This key should be saved for next uses of the plugin.

### Analyzing access to Universities in Hanoi
- In batch jobs choose Isochrons From Layer
- In the Input Layer choose: UniversityOSM
- In Travel Mode choose: driving-car
- For Dimension: distance
- And finally in the range write: 500,1500,3000 (this will determine the distance buffers that will be generated).
- Run the plugin.

You should be getting an Isochrons layer with 3 500M, 1500M and 3000M distance layers. The polygons are a little "funny" looking because they relay on the local street network in order to be generated (which explains why these are not perfect looking round polygons).  


Finally, create a map of 500, 1500, 3000 m proximity. Note that no submission is required for this lab.  
