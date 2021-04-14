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
And so we decided to visualize the percent difference between 2019 and 2020. CONTINUE HERE AHHHHHHHHHHHHHHHHHHHH *********************

We also considered having all bubble be the same size and color be an indicator but we found that having the dual reinforcement of the same value was both helpful and visually appealing. 

### Total Subway Activity Graph

### Station Activity View 

### Vertical Line Across Both Graphs
The vertical line across both graphs acts as an indicator for which month is being shown on the map. That way the user can easily compare what they see on the chart to what they see on the map. 

### Selecting a Train 

## Development Process 
An overview of your development process. Describe how the work was split among the team members. Include a commentary on the development process, including answers to the following questions: Roughly how much time did you spend developing your application (in people-hours)? What aspects took the most time?
Remember to acknowledge all appropriate sources not just in your write-up but also directly on your visualization itself (including the source of your data, and any example visualization you drew inspiration from).
### Splitting the Work
### Time spent
### What took the most time?
