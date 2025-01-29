# Toronto Ambulance: where do you need us?

A data visualization of Toronto Paramedic Services dispatches from 2010, compared to Toronto population size.

*Erin Cameron*

---

### Introduction
Emergency Medical Services (EMS) are a crucial part of urban infrastructure, ensuring that critical care reaches those in need as fast as possible. In this analysis, I explore Toronto Paramedic Services (TPS) dispatch data to understand where ambulances are most frequently deployed, and whether patterns emerge based on location and time.

Using Python and geospatial visualization techniques, I dive into the data to uncover trends that could help optimize emergency response strategies. The dataset consists of ambulance dispatch records, each containing details such as general location, timestamp, and dispatch priority. The goal is to map these locations and examine patterns across different time periods.

### Data Exploration
The dataset consists of ambulance dispatch records, each containing details such as general location, timestamp, and dispatch priority. The goal is to map these locations and examine patterns across different time periods.

To begin, the dispatch incident data was loaded and subsetted for dates within the year 2010. Missing values and NaNs were identified and handled appropriately to ensure data integrity. Similarly, population data was loaded and refined by renaming columns to align with the dispatch dataset, facilitating an accurate merge of relevant postal codes. After these preprocessing steps, the datasets were transformed and exported into parquet and CSV formats for further analysis.

Additionally, an exploratory analysis was conducted to examine the structure of the datasets, including column attributes, dataframe shapes, and data types. This foundational work set the stage for in-depth visualizations and insights.

### Data Visualization & Summary Statistics:
Dispatch Volume Heatmaps:   
Using `Folium`, I created heatmaps to visualize the density of ambulance dispatches across Toronto’s FSAs. These maps highlight areas with consistently high emergency call volumes.

Statistics:   
* The total number of dispatches in 2010 was `204805`.
* The highest dispatch volume day of the year was `Monday, July 5th, 2010`, with `727` dispatches.
* The highest dispatch volume by FSA was `4481` dispatches in the FSA `M6K`.
* The average time between dispatches was `153.98 seconds`, or `2.57 minutes`.
* The highest dispatch volume month was `July` with `19399` dispatches total.
* The peak hour for dispatch volume was `12:00 hours`.
* Dispatch Volume by Incident Type:

```
    Incident_Type
    Airport Standby               34
    Emergency Transfer          3743
    Fire                        1094
    Medical                   186600
    Motor Vehicle Accident     13334
```
* Number of dispatches by Priority:
```
    Priority_Name    Priority_Number
    Delta            1                 70751
    Charlie          4                 58526
    Bravo            5                 34691
    Alpha            3                 31629
    Echo             9                  4567
    Alpha1           11                 3190
    Alpha2           12                 1179
    Alpha3           13                  272
``` 

### Conclusion
This analysis provides valuable insights into Toronto’s EMS demand, highlighting opportunities for optimizing resource allocation. Future studies could incorporate more recent data, weather conditions, road conditions, or hospital capacities to refine emergency response strategies further. This investigation highlights the need for further data analysis on more robust datasets to garner insights into operational bottlenecks. 

Investigational Insights:
* **High-Demand Areas**: Certain FSAs consistently show high dispatch volumes, indicating potential hotspots for EMS demand.
* **Peak Demand Hours**: Dispatch frequency spikes during specific times of the day, likely aligning with work hours, commute hours, and nightlife activity.
* **Seasonal Trends**: Higher call volumes appear to occur in certain months, which suggest links to environmental factors such as good weather. The highest dispatch volume month was July.
* **Priority Analysis**: The dataset reveals the most common emergency priority levels requiring ambulance response.
* **Average Dispatch Intervals**: Understanding the average time between dispatches helps gauge system load and efficiency.

### Next Steps
* Expand the analysis to include more years of data
* Investigate response times and patient outcomes
* Explore the impact of city events on EMS demand
