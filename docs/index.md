# Homework 5 – Data Visualization 

## Overview
For this assignment, I created two visualizations using the **BFRO Bigfoot Sightings dataset**, loaded directly from a public GitHub dataset link provided in the assignment. 
First visualization is interactive and allows viewers to filter Bigfoot sightings by the U.S. state.  
The second visualization aggregates the same dataset (sightings) by year to show the long-term reporting patterns.
---

## The Data & Analysis

### Data  
[Please click here to view the dataset](https://raw.githubusercontent.com/UIUC-iSchool-DataViz/is445_data/main/bfro_reports_fall2022.csv)

### Analysis Notebook  
[Please click here to view the Jupyter Notebook](https://github.com/mutneja3/data-viz-hw5/blob/main/analysis.ipynb)

---

## Visualization 1 —> Interactive Geographic Map of Sightings

This visualization maps individual Bigfoot sightings using **latitude** (y-axis) and **longitude** (x-axis) as geographic coordinates.  
Each circle represents a single sighting, and **season** is encoded using color ('season:N'), which allows viewers to compare sightings across different times of the year.  
Tooltips display here additional sighting information (date, state, title, season), enabling richer exploration without cluttering the chart.

### Encoding Choices
- **longitude → x-axis (quantitative)**  
- **latitude → y-axis (quantitative)**  
- **season → color (nominal)**  
- **date/state/title → tooltip**  

A categorical color scheme is appropriate because “season” is a nominal variable. By using the distinct colors it allows easy comparison of seasonal patterns across the states.

### Data Transformations
In the notebook, I performed several preprocessing steps:
- I converted the `date` column to a datetime object using `pd.to_datetime` 
- Extracted `year` for later aggregation 
- Removed rows with missing latitude/longitude values since they cannot be plotted  
- Filled missing season values with `"Unknown"`  

By doing these transformations I ensured that the plotted data is clean, complete, and compatible with Altair encodings.

### Interactivity
I added an Altair dropdown menu using `selection_point` bound to the `state` field. 
This help the end users to **filter the map by U.S. state**, greatly reducing visual clutter.  
As the dataset contains hundreds of points, the interactive filter makes it easier to see regional patterns that would be hidden in a static scatterplot.  
With the help of the interactivity it helps in the exploratory analysis and also allows meaningful comparisons between the different states.

### Embedded Plot 1 
<iframe src="plot1.html" width="750" height="500"></iframe>

---

# Visualization 2 —> Number of Sightings per Year

The second visualization is a bar chart showing the **number of Bigfoot sightings recorded each year**.  
This aggregated view here highlights long-term patterns, such as peaks in reporting across decades.

### Encoding Choices
- **year → x-axis (ordinal)**  
- **count of sightings → y-axis (quantitative)**  

Here, I intentionally used a **single consistent blue color** for all the bars. Because only one variable is being displayed, a multicolor scheme would add unnecessary noise and distract from temporal trends in the below bar chart.

### Data Transformations
To create this visualization, I:
- Extracted the year from the `date` field  
- Grouped sightings by year using `df.groupby("year").size()`  
- Reset the index into a tidy dataframe (`year_counts`)  

This transformation compresses many individual observations into an interpretable trend line and makes it easier to identify spikes or declines in reported sightings across the decades.

### Embedded Plot 2
<iframe src="plot2.html" width="750" height="500"></iframe>

---

## Summary of Interactivity
I have implemented the Interactivity in the **first** visualization using a dropdown menu that filters by state.  
This interactive control allows the viewer to isolate specific regions, explore differences in seasonal reporting, and better interpret patterns within a dense national dataset.
Without interactivity, the geographic visualization would be overly crowded, making trends difficult to see.  
The combination of an interactive geographic plot and a static summary provides both exploratory and high-level insights.

---

## End of Assignment
