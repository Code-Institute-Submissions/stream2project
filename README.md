* [About the project](#about-the-project)
* [Technologies used](#technologies-used)
* [Credits](#credits)
* [Testing](#testing)
* [Deployment](#deployment)
* [Note](#note)
* [Exclusions from the Dataset](#exclusions-from-the-dataset)

### ABOUT THE PROJECT:

   The Significant earthquakes dashboard is a graphical visualisation of earthquakes that occurred within the period of 2006 to 2016.

   It uses various kinds of charts (bar chart, row chart, pie chart, choropleth map, bubble chart and a data table) to show at a glance where and when the earthquake occurred, the total number of deaths and injuries that resulted from the earthquake, the total number of houses damaged and destroyed by the earthquake and the focal depth & magnitude of the earthquake.

   The data set used for the dashboard on this website is culled from the following database National Geophysical Data Center / World Data Service (NGDC/WDS): Significant Earthquake Database. [National Geophysical Data Center, NOAA.](http://dx.doi.org/10.7289/V5TD9V7K">doi:10.7289/V5TD9V7K)

   The dashboard displays information on destructive earthquakes from 2006 to 2016 (with the exclusion of Haiti, Japan: Honshu, China: Sichuan) that meet at least one of the following criteria: 10 0r more deaths and Magnitude 7.5 or greater.

   The website consists of one page, the dashboard page.

   The dashboard page includes details of what the website is about, where the data set was gotten from, definitions of variables used in the data set (in a modal accessed from the table chart), what the information on the dashboard represent and how to use the dashboard.

   It also displays a graphical representation of the data set used, showing:

   - A bar chart with the total number of deaths by location name
   - A choropleth map of the world showing the total number of injuries by country. All the areas coloured light blue show counties where no earthquakes occurred.
   - A row chart showing earthquake count by country. This shows the country where an earthquake occurred and the number of times it occurred in the given timeframe of 2006 to 2016.
   - A bubble chart showing the relationship between the focal depth, primary magnitude and the total number of death.
   - A pie chart showing the years between 2006 and 2016 an earthquake occurred and the count.
   - A table showing all the relevant data for the earthquakes that occurred within the period of 2006 and 2016.

### TECHNOLOGIES USED:

   The website was designed using the following technologies:

   - *Bootstrap and CSS*: this was used for the page layout design, look and feel of the website.
   - *D3.js*: is a JavaScript library for visualizing data using web standards.
   - *DC.js*: is a javascript library for dimensional charting built to work natively with crossfilter and rendered using d3.js. It has been used in this project to render charts that are data driven and reactive which provide instant feedback to user interaction.
   - *Javascript*: used for the data table pagination
   - *Python*: is used to build the backend of the project, to link the frontend with the database.
   - *Mongo DB*: is a noSQL database, which has been used in this project to store the earthquake data.
   - *Crossfilter.js*: used to ensure that the charts on the dashboard have filtering capabilities.
   - *HTML*: is used to build the webpages
   - *Flask*: is a microframework for Python and is used in this project as a development server and debugger

### CREDITS:

   A third party code was used for 

   1. The data table pagination, some changes were made to the code to enable it work properly with my code. Culled from [github](https://github.com/dc-js/dc.js/blob/master/web/examples/table-pagination.html) with a few minor changes made to the variable names.
   2. Dataset used sourced from [doi:10.7289/V5TD9V7K](http://dx.doi.org/10.7289/V5TD9V7K")

### TESTING:

   The application was tested manually on the following internet browsers Chrome, safari, IE and Firefox using inspect to debug any errors on the code. The application was also tested on the following

#### TEST SCENARIOS:
   1. Responsiveness of website across some devices (laptops, ipad and samsung note3) and major browsers.

   2. Ability to highlight each graph and provide a description of the information on the graph.

   3. Table chart has pagination.

   4. Table chart is scrollable on smaller devices.

   5. Definition of table chart variables pops up as a modal.

   6. Ability to reset charts after filtering chart information.

   7. Ability to filter charts.

### DEPLOYMENT:

   The project was deployed using Heroku.

### NOTE:

   when importing the earthquakes data from the results.csv file, use the mongodb shell command below to change Total_deaths to a number variable, otherwise the dashboard won't load any data when run

```db.project2.find({TOTAL_DEATHS : {$exists : true}}).forEach( function(obj){ obj.TOTAL_DEATHS = new NumberInt( obj.TOTAL_DEATHS ); db.project2.save(obj); } );```

### EXCLUSIONS FROM THE DATASET:

   Haiti, Japan: Honshu, China: Sichuan were excluded from the charts because it threw the scale of the chart off-balance and made other countries with fewer casualties less visible on the bar chart. Haiti's earthquake resulted in over 300,000 deaths.