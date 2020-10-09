
Explatory data analysis is one of the key functions of R.  Being able to quickly identify possible trends in data to dive deeper into is an essential part of any evaluation. The package 'ggplot2' creates a process for users to form graphs and visualizations of their data to help achieve this.  Although helpful, 'ggplot2' requires users to create an individual chunk of code for each graph, and does not lend itself to a rapid overview of general trends.

However, the 'esquisse' add-in allows users to rapidly view and alter visualizations via an interface, allowing several different types of visualizations to be created with ease in the matter of seconds.

# Installation
In order to utilize 'esquisse' we must first install it to our system.  There are two ways to do this, the first being the standard installation process from CRAN and the second option is to install the developer version from Github.  The recommended route is to install the program from Github as that has the most up to date updates and bug fixes.

CRAN 
install.packages("esquisse")


Github
remotes::install_github("dreamRs/esquisse")


# Launching 'esquisse'
Once installed, you have two options to launch 'esquisse'. The first route is through the Menu bar at the top of the RStudio page (Tools > Addins > Browse Addins > Select 'esquisse' > select the execute button at the bottom of the panel).  The easier version launches the interface with a small bit of code.

esquisse::esquisser()


# Loading Data
Once you launch the 'esquisse' interface, you will be brought to an initial screen where you select your dataset that you will be examining.  If you have a dataset (or multiple) loaded into Rstudio already, it will automatically pull those into the selection menu.

![Initial Start-up Screen](https://github.com/Mkulbida/mikekulbida/blob/master/images/Initial.png)

We would then like to choose a dataset to analyze, which can be done by selecting the drop down menu under "Select a Dataset."  If you do not have a dataset loaded into R (as in this example) 'esquisse' will automatically import all of the standard datasets from 'ggplot2'. In this example we will be utilizing the "txhousing" data set, which examines housing sales in cities across Texas from 2003 to 2015.

![](https://github.com/Mkulbida/mikekulbida/blob/master/images/select_df.png)

From this window you can also change the vector of a particular variable by using the "Coerce" drop down menus towards the bottom of the page as well as select which variables you would like to be included in the analysis.  For this example however we do not need to utilize either of these and we are free to initialize the tool by selecting the "Validate Imported Data" button.

![](https://github.com/Mkulbida/mikekulbida/blob/master/images/validate_data.png)

# Building your Visualization
### Selecting a Graph Type
Now that we have selected our data that we will be exploring and initialized the interface, we are brought to an empty interface with several different options.

![](https://github.com/Mkulbida/mikekulbida/blob/master/images/blank_interface.png)



At the top left of the interface, we can see a yellow circle that says "auto" which allows you to select the type of graph you would like to create.  As everything in this interface can be edited, you can change the type of graph with ease by clicking on this, or stay with the "auto" selection which will change the type of the graph to best display the inputs you have selected. As you progress with creating your visualization, certain types will be unavailable to select if they do not allow from proper visualization of your variables. 

![](https://github.com/Mkulbida/mikekulbida/blob/master/images/select_graph_type.png)

### Graphing Variables

Now that we have decided to stick with the "auto" graph type selection, we will start to build our visualization.  We would like to get a better idea about the effect of available housing supply on the median sale price of homes in 7 cities across Texas. The different variables measured in the data set are located at the top of the interface, and are color-coded by type (discrete, continuous, time, id).

First we would select our x-variable, which in this case would be the number of houses for sale.  This is categorized in the data set as "listings" and so we would drag and drop the "listings" oval into the box labeled "X" directly below.  Our y-variable would be the median housing price, which is contained in the "median" variable, and we would drag and drop that into the "Y" box.  Since we would like to identify trends in individual cities as well as overall, moving the "cities" variable into the "Color" box will color code each individual city to allow for easy identification. This can be done with several other inputs to the graph including size and group by.

![Initial Graph](https://github.com/Mkulbida/mikekulbida/blob/master/images/First_graph.png)



# Clean-up
Texas has quite a few cities that are measured by this data set, and right now there is not much of anything that someone could gather by looking at this graph.  With 'esquisse' it is a breeze to clean and alter your visualization to meet your wishes.

It's fairly clear that we cannot analyze every city in Texas at the same time, so we will narrow it down to the 6 largest cities and include Waco because watching Fixer Upper with Chip and Joanna Gaines happens to be one of my favorite ways to kill time. In order to do this we simply click on the "Data" tab at the bottom of the interface.

![](https://github.com/Mkulbida/mikekulbida/blob/master/images/edit_data.png)

In order to eliminate the locations we do not want to analyze, we simply remove them from the "city" window by clicking on the x next to their name.  This will remove them from the analysis, but if you wish to add them back in at a later time you can select them from a list that shows up below the window with all the excluded selections. 

In this window you can filter any of the variables to get the paramaters you would like for your analysis.  In this instance we will filter the year to include only 2008 to 2015 by using the sliders in order to measure the impact of the Great Recession on housing inventory and prices. 



# Make it look Pretty
Now that we have our data paramaters defined, we can alter the plot of the graph.  
By selecting the "Plot Options" panel at the bottom of the interface we are able to quickly edit several key parts of the graph to our liking including the values covered by the x and y axis, point size, color pallate, and the location of the legend within the graph.  

![](https://github.com/Mkulbida/mikekulbida/blob/master/images/plot_options.png)


A helpful key function of this panel is the "smooth-line" button, which when selected produces a line of best fit to each of the cities, allowing you to quickly observe the trends over time as well as potential outliers.

![Graph with Smooth Line](https://github.com/Mkulbida/mikekulbida/blob/master/images/smooth_line.png)



# Title and Labels
Our graph is almost complete, and the last piece to edit are the custom labels and title.  We can address this by selecting the "Labels & Title" panel at the bottom-left of the interface.

![](https://github.com/Mkulbida/mikekulbida/blob/master/images/labels_title.png)


In this panel, we can easily add information to our graph to beter define it to anyone who may view it.  We can add in labels for the graph overall, the x and y-axis, as well as the legend (called "Color label" in this example) to allow us to create a finished product.

![Final Product](https://github.com/Mkulbida/mikekulbida/blob/master/images/final_graph_w_labels.png)

# Exporting your Visualization

Although it may be interesting to build visualizations like this for the fun of it (I thoroughly enjoyed it), this interface allows you to export your graphs to Rstudio, Powerpoint, or save it as a .png file.  This can be done by selecting the "Export & code" panel on the bottom-right of the interface. 

![](https://github.com/Mkulbida/mikekulbida/blob/master/images/select_code.png)


By selecting the "Insert code in script" link on this panel, you can insert the code chunk required to build this graph directly into your open RStudio file.  The code will include the library() function for any packages required to build the graph, which will always be 'ggplot2' and 'dplyr'. The ease at which 'esquisse' allows a user to create and edit visualizations makes this program a must have.

![](https://github.com/Mkulbida/mikekulbida/blob/master/images/codechunk.png)
![](https://github.com/Mkulbida/mikekulbida/blob/master/images/final_product.png)
