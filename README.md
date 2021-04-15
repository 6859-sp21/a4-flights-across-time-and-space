# NYC Subway Activity 
This visualization aims to compare NYC subway activity at stations across the city between the years 2019 and 2020. March 2020 was the start of COVID-19 pandemic lockdowns in NYC and at that point the number of subway rides dropped drastically and the numbers have not fully recovered since then. We thus compare the year of the pandemic (2020) to the previous year to get a sense of how things have changed. 

MTA [train station data](http://web.mta.info/developers/developer-data-terms.html#data) and [aggregated MTA turnstile data](https://qri.cloud/nyc-transit-data/turnstile_daily_counts_2020) was used for this visualization. We also drew inspiration from the [D3.js graph gallery](https://www.d3-graph-gallery.com/) and [this example multiple line plot](https://bl.ocks.org/d3noob/ed0864ef6ec6af1e360917c29f4b08da).

## Design Decisions

### Using Total Number of Entries Per Month 
We decided to use the total number of entries into a train station per month as our main datapoints. This allowed us to simplify the large amount of data from the original datasets but still maintain a good representation of subway activity. We considered including the total number of exits from each station, perhaps a way to toggle between entries and exists, but decided that entries would be sufficient in counting overall activity (entries + exits would be double counting). This also simplifies the amount of portrayed data so that viewers will not be overwhelmed by information. We also considered allowing the user to observe subway activity based on the time of day, but since we ended up focusing on the change between 2019 and 2020 it didn't make sense to show this additional view of the data that would all have similar downward trends. 

### Using a Map 
One of our original ideas was to use a Sankey diagram to visualize the trains and connections of the NYC subway system and have the size of the nodes correlate to the number of entries at stations. In the end we found that this visualization was difficult to read with the number of stations depicted and was too abstract for the information we were trying to portray. So, we went with a more practical map visualization. The map gives the user spatial orientation of the subway stops that they are looking at. That way, even non-New Yorkers can get an understanding of where the stations are situated relative to landmarks such as Central Park. On the other hand people familiar with the map of New York can easily pan and zoom in on their area of interest. 

### Visualizing Percent Change between 2019 and 2020 with Size and Color
After much thought and debate, we decided to have the bubbles on our map represent the percent change in ridership between 2019 and 2020. At first, we had the bubbles represent the number of entries into each station. However, we found that the differences were not as clear to see because most station's activities remained in the same order of magnitude despite less riders. 
Therefore, we decided to visualize the percent difference between 2019 and 2020. This way, we could see change relative to the station's activity pre-pandemic. The color indicates whether the change is positive or negative (increase or decrease) whereas the size indicates magnitude. Both the size and colors are based on continous spectrums as opposed to binning. Although spectrums are sometimes hard to read for users we think that the dual reinforcement with both size and color being indicators for the same value helps in this case.
We considered including both the entries map and percent difference map as options for the viewer, but again did not want to overwhelm the audience with too much information to parse. In addition, we found that the depiction of difference with the map and portrayal of entry numbers with the line plots portrayed all aspects of the data effectively on their own.

### Using a Slider to Watch Ridership Change Over Time
We included a slider that determines the month of the data included on the map. An alternative we considered was a dropdown menu, but this would add too much friction when the user tries to adjust time values. It takes many clicks with a menu to see how the map changes across the year, while a slider can achieve this with one simple drag. The user can zoom in on a given month to see the percent change for the month and quickly compare that month to another.

### Total Subway Activity Graph
We found that the map did a good job of providing an understanding of MTA ridership during a given month. However, we wanted to give the audience a way to immediately see how overall ridership changed over the two years. We decided to do this with a line graph showing ridership across the twelve months. Each year has its own corresponding colored line on the plot. The x-axis increases in time from left to right, showing the overall decrease in ridership over time in a way that is intuitive for the reader. We also considered doing a grouped bar chart with similar color encodings, but found the plot to be cluttered and the values harder to compare. 

### Station Activity View 
Since ridership depends on the station, we provided a way to get a good understand of the data from a given station. We created a plot that provides more specific values for the number of people entering the station in a given month and year. We again decided to use a line plot to show progression over time and so that the data could be compared to the total subway plot. Choosing a different type of encoding would make it more difficult to compare to that line plot.

### Vertical Line Across Both Graphs
The vertical line across both graphs acts as an indicator for which month is being shown on the map. That way the user can easily compare what they see on the chart to what they see on the map. 

### Selecting a Train 
Considering that we are dealing with subway data, it was natural to allow the user to filter their data by train. So, we decided to use a selection menu that allows the user to select their desired train and then highlighted the stations corresponding to that train in the map. We originally used a dropdown menu, but this menu did not show the user which train is currently selected. The selection menu, on the other hand, does show this information and allows the user to pick a train in an intuitive way. With this feature, the user can search for any correlations in the data depending on train. 
We also figured that a natural flow when using this visualization is to start with the map, then choose a train, and then choose a station. This way the user is progressively zooming in more and more on the data. So, we used careful messaging to encourage this. However, the user can perform these actions in whatever order they wish.

## Development Process 
Implementing this assignment was a bit challenging at times. However, we found a fair amount of resources online and the staff was helpful during office hours. We collaborated over Zoom to plan out our design and tasks. We also created a list of tasks to ensure that we completed all the features that we planned. In addition, we checked in very frequently over text to get feedback and help each other debug.

### Time spent
\>50 hours each

### Splitting the Work
We started off by gathering our data which needed a lot of cleaning in order to be usable. Violetta worked on combining datasets from the MTA website and simplified them using a python-script. Shariqah worked on getting and cleaning the MTA station data so that we could map values to the correct station locations and trains. 

Shariqah worked on the map. At first she used a geojson file and SVG to create the map. However, she transitioned to Leaflet after struggling to use the D3 zoom feature to properly update the locations of the bubbles. She also helped combine the two datasets into a usable format for our JavaScript implementation and placed bubbles for where stations should be. Shariqah implemented the baseline function for creating the line charts and the functionality for filtering by train. She also helped with styling, including the navbar and changes to the layout and messaging of the page.

Violetta worked on the slider functionality for different months could be displayed when the slider was used. Violetta also worked on stylings and interactions on top of the functionality that Shariqah implemented. She implemented the color and size mapping for the station bubbles as well as how the bubbles are highlighted when hovered, clicked, and unselected. She also worked on making it so that the graph showing station data only appeared when a station was clicked on. She added the legend and also introduced the vertical line to the two graphs. She also worked on making the page and its visuals dynamic relative to window size. 

### What took the most time?
We struggled a lot with getting lots of small things to work. It felt like every feature we wanted to implement came with a challenge that we had to spend hours figuring out. It was also hard to find solutions that were not based in Observable so that we can easily apply them in JS and html. Sometimes we struggled to find examples for our desired interactions with the map. For Violetta what took the most time was putting together the data and also making the web page dynamic. For Shariqah, getting the line plot to display the data properly took a lot of debugging in and out of office hours to complete. Getting the right mapping with zoom also took a fair amount of trial and error to achieve.
