# NYC Subway Activity 
This visualization aims to compare NYC subway activity at stations across the city between the years 2019 and 2020. March 2020 was the start of pandemic lockdowns in NYC and at that point the number of subway rides dropped drastically and the numbers have not fully recovered since then. We thus compare the year of the pandemic (2020) to the previous year to get a sense of how things have changed. 

MTA turnstile and train station data was used for this visualization. 
********(Do this more properly***********

## Design Decisions

### Using Total Number of Entries Per Month 
We decided to use the total number of entries into a train station per month as our main datapoints. This allowed us to simplify the large amount of data from the original datasets but still maintain a good representation of subway activity. We considered including the total number of exits from each station, perhaps a way to toggle between entries and exists, but decided that entries would be sufficient in counting overall activity (entries + exits would be double counting). We also considered allowing the user to observe subway activity based on the time of day, but since we ended up focusing on the change between 2019 and 2020 it didn't make sense to show this additional view of the data that would all have similar downward trends. 

### Using a Map 
One of our original ideas was to use a Sankey diagram to visualize the trains and connections of the NYC subway system and have the size of the points correlate to the number of entries at stations. In the end we found that this idea was too abstract for the information we were trying to portray and so we went with a more practical map visualization. The map gives the user spatial orientation of the subway stops that they are looking at, that way even non-New Yorkers can get an understanding of where the stations are situated relative to landmarks such as Central Park. On the other hand people familiar with the map of New York can easily pan and zoom in on their area of interest. 

### Visualizing Percent Change between 2019 and 2020 with Size and Color
After much thought and debate we decided to have the bubbles on our map represent the percent change in ridership between 2019 and 2020. At first we had the bubbles represent the number of entries into each station however we found that the differences were not as clear to see because most station's activities remained in the same order of magnitude despite less riders. 
And so we decided to visualize the percent difference between 2019 and 2020, this way we could see change relative to the station's activity pre-pandemic. The color indicates where the change is positive or negative (increase or decrease) whereas the size inidcates magnitude. Both the size and colors are based on continous spectrums as opposed to binning. Although spectrums are sometimes hard to read for users we think that the dual reinforcement with both size and color being indicators for the same value helps in theis case. 

### Total Subway Activity Graph

### Station Activity View 

### Vertical Line Across Both Graphs
The vertical line across both graphs acts as an indicator for which month is being shown on the map. That way the user can easily compare what they see on the chart to what they see on the map. 

### Selecting a Train 

## Development Process 
An overview of your development process. Describe how the work was split among the team members. Include a commentary on the development process, including answers to the following questions: Roughly how much time did you spend developing your application (in people-hours)? What aspects took the most time?
Remember to acknowledge all appropriate sources not just in your write-up but also directly on your visualization itself (including the source of your data, and any example visualization you drew inspiration from).
### Time spent
>50 hours each

### Splitting the Work
We started off by gathering our data which needed a lot of cleaning in order to be usable. Violetta worked on combining datasets from the MTA website and simplified them using a python-script. Shariqah worked on getting and cleaning the station data so that we could map values to the MTA data. 

Shariqah worked on the map. At first we used a ******************** and then we changed to leaflet. She also placed points for where stations should be. 

Shariqah also got the framework for the line chart. (add stuff if you want) 

Shariqah worked on the train functionality. 

Violetta worked on the slider functionality for different months could be displayed when the slider was used. Violetta also worked on stylings and interactions on top of the functionality that Shariqah implemented. She implemented the color and size mapping for the station bubbles as well as how the bubbles are highlighted when hovered, clicked, and unselected. She also worked on making it so that the graph showing station data only appeared when a station was clicked on. She added the legend and also introduced the vertical line to the two graphs. She also worked on making the page and its visuals dynamic relative to window size. 

### What took the most time?
We struggled a lot with getting lots of small things to work. It felt like every feature we wanted to implement came with a challenge that we had to spend hours figuring out. It was also hard to find solutions that were not based in Observable so that we can easily apply them in JS and html. For Violetta what took the most time was putting together the data and also making the web page dyanmic. For Shariqah *****
