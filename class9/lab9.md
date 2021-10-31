## Class 9: Getting started  with Google Earth Engine

Google Earth Engine (GEE) is a cloud based and free platform hosted by Google for accessing and analyzing satellite imagery. The GEE platform allows access to both archives and up-to-date datasets for areas of all areas of the world.

### 1. Getting Started with GEE:
To launch GEE you will need to go to [this address](code.earthengine.google.com). You will be directed to a welcome page and will need to choose the Google account you want to create your GEE account with. To get access to a GEE account you will need to submit an application. Once you choose a Gmail account you want to create your GEE account with you will need to follow the instructions to apply for access.

Once you submit the request form you will need to wait for an email confirmation. It best if you use your NYU email to create an account.

Once your GEE account is approved you will get an email notification and a few links to get you started.

Note: it most likely won't but it may take a few days to get access so make sure to follow this step as soon as possible.

### 2. Accessing GEE's interface:

Once your account has been approved you should be able to access GEE's main interface using the following address:

https://code.earthengine.google.com/

 This interface includes multiple functions to store, view, and share data and analysis results. The most important part of this interface is the code editor that appears at the center of the page.

 ![GEE Interface](https://github.com/avigailvantu/UDM2021/blob/main/class9/GEEinterface.png)

 #### 1. GEE's code editor:
 This is where we will write the scripts to access, display and analyze the data. This is a Java Script code editor with some GEE specific commands (more on that later). In the editor you can load existing code or create new ones and run it directly into Google's cloud. Once your code is ready to run you'll click the "run" button. This will execute the code and run the script in your browser.

   #### 2. Inspector, console and tasks tabs:

   These 3 tabs in the right side of the GEE interface provide information and display the results of your script.

   The *inspector* tab will allow you to explore the results of an analysis for a particular area. This is a great tool to validate and test your code while working on developing it or while trying to understand someone else's script. When activated the info on the inspector will show the layers values where the cursor is placed.  

   The *console* tab along with the map displays the results of a given script.

   The *tasks* tab shows historical and ongoing tasks like importing or downloading data or analysis results.

  #### 3. Get Link, run and search:

  The *get link* function allows you to copy the link for the script you are working on and share it with someone else.  

  The *run* button simply runs the script.

  The *search* button allows access to GEE's database.

  #### 4. The Map:
  The maps default view is Google Maps' display and there is also the option to shift to the satellite view (upper right side of the map).

  Often times we will display more than one type of data. Once the code was executed the *layer manager* allows displaying selected layers on the map and hiding the rest of the layers. Using the layer's settings there is the option of adjusting the view parameters for a given layer.  

  #### 5. Scripts, codes and assets tabs:
  The *scripts* tab allows you an easy way to store, create and archive scripts. This section is divided into: owner, reader and writer categories so that shared scripts will appear in a different location than those you write yourself. These section also represent the permissions you may have on certain scripts. Click on the red "new" section to create a new script.

  The *asset* tab can be used to upload data and images into GEE (e.g. shapefiles or tiff files). These assets can then be used for further computation and analysis. In addition to downloading analysis results into your drive, there is also the option to save it in the asset manager.
