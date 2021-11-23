## Lab 12: Creating a Dashboard with Google Data Studio 

### Data: 

For this assignment we will use data on Covid-19 cases and vaccinations worldwide from Our World in Data (https://ourworldindata.org/coronavirus-source-data). 
* First download the Covid-19 vaccinations data by country.
* Examine the data and its columns

### Getting started with Google Data Studio: 

Same as other Google products Google Data Studio is a free product that can be accessed using a Gmail account (your NYU account should work just fine here). It enables creating interactive data dashboards using data of your choice in just a few minutes. Dasboards are a very common tool these days for communicating data to non technical audience. Tools such as Tableau and Data Studio create pretty visualizations that can explain large amounts of data. In particular, summarization, % and comparisons are often the core of those dashboards. The result is usually displayed in one or two pages including a veriaty of data infographivs, tables and maps. 

1. Login to your Data Studio account. Go to: https://datastudio.google.com/u/0/. Once you’re logged-in the default page will look somwhat similiar to your drive. Note that all your previous work (if any) will be available here. Click on "create" or "blank report" to start working on a dashboard. ![](https://github.com/avigailvantu/UDM2021/blob/main/class12/Screen%20Shot%202021-11-23%20at%2012.07.42%20PM.png)
2. The "add data to report" interface will automatically open, promoting you to add data from Google spreadsheet or your computer. Choose the 'file opload' option and drag the vaccintation data you downloaded earlier.  
3. Name your newly created dashboard: "Covid-19: International  
Overview"

### Make sure your data has a spatial column
It is important to make sure that Google Studio knows how to read the spatial columns. In this data we will treat the country name as the spatial column. 
* Go to "resources"-->"manage added data sources" and "edit" on the vaccintations.csv data 
* You will now be able to view each field's name (=column) and its data type 
* Make sure the "location" column is of geo type (world icon). If not, click on the type and change it to "geo" and in the drop-dosn choose "country". This will enable Google to automatically match the country data with its boundaries and display the data. ![](https://github.com/avigailvantu/UDM2021/blob/main/class12/Screen%20Shot%202021-11-23%20at%205.57.34%20PM.png)

### Finally, start working on the data dashboard: 

