### Lab 2: Working with CSV and Shapefile data, data Joins and Field Calculator on QGIS

In this first actual assignment for the semester you will need to implement things we learned in class to wrangle data and creating a data visualization on QGIS.

Here we will explore some NYC 311 aggregated data and analyze the trends around illegal fireworks in the month of June 2021.  


#### 1. Download and load data for the assignment:
#### Datasets
- CSV file with the count of 311 complaints in NYC by zip code for June 2021. This data contains 3 columns:
  1. Zip code where the 311 complaint was recorded
  2. Count of all types of 311 complaints by zip code for the month of June 2021
  3. Count of 311 complaints related to illegal fireworks in June 2021 by zip code.

- NYC zip code shapefile

Load the data into QGIS, note that the csv data should be added through the Layer - Add Delaminated Text layer menu. It is zip code level so you will need to chose "no geometry" when adding it.

* Important: Remember to save your project and locate your data in a place that is permanent before starting the project.


#### 2. Field Calculator: Create a new field to express the % of illegal fireworks complaints.

Now that both datasets were added to your project, use the field calculator in the "compByZip" layer. It it available from the layer Attribute Table and looks like (not surprisingly) a calculator. ![.](https://github.com/avigailvantu/UDM2021/blob/main/class2/field_calc_Icon.png)

In this image the field calculator is fourth from the right end.

Once the field calculator opens write an expression to calculate the % of fireworks related complaints by zip code. Note that the data is already aggregated by zip code so what we need to do is to create a new field that divides the number of fireworks related complaints and divides it by the total 311 complaints (both columns given in the data), and finally to get a % and not a fraction multiply by 100.

Once you have your expression ready (with no errors) click OK to create the new field (column).

![.](https://github.com/avigailvantu/UDM2021/blob/main/class2/fieldCalc.png)

- remember:  name your new field, this will be the name of your new column.

#### 3. Time to Join layers!

Since the 311 data has no x,y coordinates it needs to be merged with the zip code layer to be visualized. All we need to merge both layers is a common column which luckily we have! This is the zip code column.

Using the "Joins" option on the shapefile layer properties join the CSV file using zip code as a the join field and the target field (note the naming is slightly different since these are two columns from two layers).

Here is how the window looks like once you hit the + sign in the Joins tab of the layer's properties:

![.](https://github.com/avigailvantu/UDM2021/blob/main/class2/joins_window.png)

- Make sure your layers are joined, two ways to do so:
  1. open the attribute table, scroll to the right and see the columns from the csv file exist in your layer
  2. The csv is in the layer's Joins tab

  ![.](https://github.com/avigailvantu/UDM2021/blob/main/class2/JoinsTab.png)  

  #### 4. Start styling your data:

  Now we can start exploring the data and start to understand the share of illegal fireworks complaints.

  Create 3 maps, all in zip code level:
  1. Quantile representation of all 311 complaints
  2. Quantile representation of illegal fireworks
  3. Quantile representation of the precent illegal fireworks takes up from the total 311 complaints
  Style your maps, chose the same colors for all 3 maps.


  Export these maps as images using the map layout interface.

  #### 5. Delivery:
   Submit:
  1. 3 maps with proper map elements.
  2. A brief write up (up to two paragraphs) discussing your understanding of these 3 maps and the way this data representation helps with your understanding of the trends.
  3. One paragraph: do you have any ideas on how to improve this data visualization to be more truthful and insightful?
