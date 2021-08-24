### Lab 4

### Assignment #2: your first QGIS project

In this assignment you will be retrieving data, conducting some analysis, visualizing and interpreting the results of your analysis. By the end of this assignment you should acquire the tools to start and complete your own urban data project!

Note that this is an individual assignment which needs to be completed by each student separately.

The assignment main goal is to investigate the 311 Noise complaint data and analyze some spatial trends with the data (e.g. which areas had more Ice Cream truck noise complaints compared to those areas that had more construction complaints) as well as to examine diffrent ways to display the infromation. You will be graded based on your ability to follow the instructions below but also on your ability to demonstrate creativity in the data you add and the insights/interpretations you come up with. Keep the text short (no more than 4 paragraphs). 

#### 1. Download and load data for the assignment:
#### Datasets

  1. 311 noise complaint data from the NYC Open Data portal. *Do not download the entire data* Use the following parameters to filter your data:
  - Include only 311 "Noise" complaints types
  - Filter the date when the complaints were created in the system, only include complaints for the following dates:
    April 1st, 2021 - July 31st, 2021
  - Filter the 'borough' column so that you only download complaints in Manhattan.
  *Hint: after applying those three conditions, you should have about 80,000 results.*

  - Download the filtered data as a CSV file.

  2. NYC Neighborhood Tabulation Area polygons (shapefile)
  - Find the NTA data on NYC Open Data Portal. Download the entire data in a shapefile format.

##### 2. Load data into QGIS.

Import both the 311 noise data as well as the NTA boundaries on your map.

*Hint: make sure to add the 311 data as a point layer and visualize it on the map using the layer's latitude and longitude coordinates.*

- Review both of the layers' coordinate systems as well as the porject's, make sure they are all identical.  
- Remember to save your project and locate your data in a place that is permanent before starting the project (not your downloads folder).


#### 3. Filter the NTA data

We have filtered the 311 data to only include Manhattan complaints. Therefore, we will not need the other 4 boroughs in the NTA layer.

You can use whatever method you choose to only disaply Manhattan NTA's. 

Here are some ideas:
- In the layer's properties build a query (source--> query builder). Use the layer's query builder to only include boro_name 'Manhattan'.
OR
- In the layer's attribute table use the "select features using an expression" to choose only Manhattan NTAs. Then export the layer's selected features and save them as a new layer.
OR


#### 4. How many noise complaints exist in each 311 NTA

Now that we have both layers we are ready to conduct some analysis.

Although we are able to visualize the 311 data using the lat and lon information the number of points on the map makes it very difficult to make sense of hot spots and trends in the data.

We will therefore want to *count* the number of points per each NTA polygon. Using the 'Count Points in Polygon' analysis tools on QGIS we can do that quite easily!

- Count the number of noise complaints per NTA in the borough of Manhattan.

* Hint: here's how to access the analysis tool: Vector--> Analysis tools --> Count Points in polygon  


Tip: this is a good time to take a coffee break :) the analysis may take a little bit of time (~ a few seconds to 30-40 min depending on your computer). Be patient and make sure your computer is connected to the electricity before executing the analysis.


#### 5. Visualize the data

Now that we have the 311 noise analysis completed we can start making sense of the data.

1. Visualize the 311 noise complaint point data. Choose a symbolization method that displays noise complaints categorized by the complaint descriptor. There are way too many categories in the descriptor. To simplify things--display the data using the following four categories:
  1. Noise coming from Ice Cream truck
  2. Noise coming from Construction
  3. Noise coming from animals
  4. Noise coming from loud music/party
  5. Other (all the rest)
Adjust the symbol fill and stroke colors and sizes. Use *your judgment* to display the information in the *best* visual way you can come with.   
2. In addition to (1), also create a visual representation of the number of 311 noise complaints in each NTA using the output generated from the 'count points in polygon' analysis. To divide the data into bins use a method that you think tells a good and clear data story.  

#### 6. Get creative with data!

Now it's time for you to add your point of view to the project.

- In preparation for interpreting the 311 noise data, find one more datasets that can enhance your insights on the data. This part is up to you. The data can be geographic/population/demographic/economic or any other data that you think could help you better understand and later explain 311 noise complaints in Manhattan.


Here's one example for population data by NTA https://data.cityofnewyork.us/City-Government/New-York-City-Population-By-Neighborhood-Tabulatio/swpk-hqdp


#### 7. Export outputs and interpret your maps:

- Export two-three maps (but no more than 3):
1. Point representation: 311 complaints by descriptor
2. Graduated map of noise complaints by NTA
3. Map of your data (or a combination or 1 or more of the analyses).

- Interpret the data (2-4 paragraphs, no more than 4):
1. Which areas of Manhattan had the largest number of 311 noise complaints? What are some reasons you can think of for these trends?
2. What are some trends you noticed regarding the descriptor for noise complaints?
3. How did the additional data and map changed or reinforced your insights from Q(1)?


#### 8.Delivery:

1. Submit a url of your Github markdown (.md) file which includes the maps and insights to NYU Brightspace. Here's a markdown cheat sheet to help you with the your first .md file https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet
2. Prepare a 5 min presentation to be delivered in class with your main takeaways and insights from the project. Briefly describe your workflow and decisions around analyzing and visualizing the data. Make sure to spend the majority of your presentation on the individual part of the assignment (*your data*) and on your insights.
