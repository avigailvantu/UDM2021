# Class 6: Data for Social Good Continued: Facebook and GADM administrative boundaries.

Last week we explored some data sources for using data from organizations and companies that curate and release data for areas of the world that are "data poor". Facebook for Good has recently released a few datasets that are delivered in easy-to-use formats and allow us a better understanding of areas of the world that otherwise would have limited data sources. 

## Get data

### 1. Facebook Movement Range Maps data
One of the datasets from Facebook are the Movement Range Maps which capture changes in peopele's movement around the COVID-19 crisis and include an health emergency as well as government issued lockdowns.

Get data: 
* [Go to HDX's data platform](https://data.humdata.org/), search for the Facebook data page
* Navigate to the Movement Range Maps data.
* Download the entire data, it is likely to be named: "movement-range-data[yesterday's-date].zip".
* note that since this data is updated constantly you will have a large/different date ranges than I do in this tutorial.
* Add the txt file as delimited layer
* make sure these boxes are checked:
    1. Custom delimited
    2. First record has field names
    3. in the geometry definition: No Geometry  
    4. Click add


![alt text](https://github.com/avigailvantu/UDM2021/blob/main/Class%206/addData.png)

### 2. ADD GADM administrative boundaries
GADM stands for Database of Global Administrative Areas and as its name suggests it provides administrative data for many areas of the world. There are 3 levels of data, when 0 is the largest and 2 is the smallest:
* Level 0: country
* Level 1: regions
* Level 2: counties
* Some data (such as Brazil) include level 3 data

For our project we will work withe level 2 data.

* Go to https://gadm.org/download_country_v3.html and navigate to Country: Brazil
* Download the Shapefile option.
* This option will download the Brazil administrative boundaries in the 3 levels available.
* You do not need to unzip the downloaded file. In your QGIS browser, navigate to the location of the GADM data, add the 'gadm36_BRA_2,shp' file to your project.

### Filter the FB data based on dates

* Right click the Facebook Movement Range layer  --> Filter
* A window will open where you can write your query.
* The ds column is the date column. Choose in the "field" window. In "Values" click "All" to view all dates available in the data.
* filter about a week of data, for example these dates:
"ds" > '2021-01-01'  AND "ds"<'2021-01-07'
We do so to minimize the data (otherwise it will be too big and QGIS will run very slowly)
* Click OK to finalize the filtering


![] (https://github.com/avigailvantu/UDM2021/blob/main/Class%206/QueryBuilder.png)


### Join GADM and Facebook Movement Range Maps datasets

Because GADM is the spatial layer and the FB data is the non-sptial we will join the FB data into the GADM data.

In the layer properties go to Joins and click the + sign. In the joins pop-up window set these parameters:
* Join layer: Facebook Movement Map Range layer
* Join field: Polygon Id
* Target field: GID 2

Once you finalize this join you should be able to have the Facebook data columns appearing on the GADM layer.

### Symbolize:

The column we want to visualize here is the: *'all_day_ratio_single_tile_users'*. According FB this columns indicates the "proportion of users staying put within a single location". You can read more about the data [here](https://s3.us-east-1.amazonaws.com/hdx-production-filestore/resources/435ed157-6f7a-4e8f-a63a-2aa177b9bd05/readme.txt?AWSAccessKeyId=AKIAXYC32WNARK756OUG&Expires=1632071771&Signature=cDM3x5Nk483V8pRox0j0F8k%2BriQ%3D).

In the layer's symbolization, choose this column and apply a graduated symbolization. Pick the mode that looks best to you.

You may notice that a few counties did not merge in the join process. This is because the Facebook data excludes areas with small sample size (small amount of  FB users contributing data in these areas).

### Interpretations:
To wrap up this map, you may want to display the one of the XYZ tiles (Google maps, OSM). This will help with navigation.

* Looking at the map you created, what are some trends in the "stay put" trends in Brazil? Which areas have seen a bigger proportions of people staying put?
* Based on your understanding of the data, can you think of any limitations this data can introduce in making conclusions about the entire Brazilian population?

![](https://github.com/avigailvantu/UDM2021/blob/main/Class%206/mapFB.png)
