# Homework 5 – Data Visualization 

## Overview
For this assignment, I created two visualizations using the **BFRO Bigfoot Sightings dataset**, loaded directly from a public GitHub dataset link provided in the assignment.  
The first visualization is interactive and allows the user to filter sightings by state.  
The second visualization aggregates the sightings by year to show long-term trends.

---

## The Data & Analysis

### Data  
[Please click here to view the dataset](https://raw.githubusercontent.com/UIUC-iSchool-DataViz/is445_data/main/bfro_reports_fall2022.csv)

### Analysis Notebook  
[Please click here to view the Jupyter Notebook](https://github.com/mutneja3/data-viz-hw5/blob/main/analysis.ipynb)

---

## Visualization 1 —> Interactive Geographic Map of Sightings
Here in this visualization plot I have shown Bigfoot sightings on a map using their recorded geographic coordinates.  
In this visualization each point represents an individual sighting, and color encodes the **season**, which helps in allowing comparisons across time of year.  
The tooltip here reveals more detailed information including the date, state, and the title of the report.

### **Interactivity**
I implemented a dropdown menu that let the users **filter the map by U.S. state**.  
This improves clarity by reducing visual clutter and allows users to focus on a specific region.  

### Embedded Plot 1 
<iframe src="plot1.html" width="750" height="500"></iframe>

---

## Visualization 2 —> Number of Sightings per Year
The second visualization is a bar chart showing the **count of sightings recorded each year**.  
I grouped the dataset by year and calculated the number of sightings.  
Here, the encoding uses the year on the x-axis and the total number of sightings on the y-axis.  
The simple, single-color bar style keeps the focus on the temporal trends.

This non-interactive aggregation complements the first plot by showing long-term reporting patterns and highlighting peaks in Bigfoot sightings.

### Embedded Plot 2
<iframe src="plot2.html" width="750" height="500"></iframe>

---

## Summary
I added Interactivity in the first visualization via an Altair dropdown selection.  
This feature will allow viewers to dynamically explore sighting patterns across states, which would be difficult to see in a static geographic scatterplot.  
It enhances clarity, reduces clutter, and helps the user meaningfully interact with a dense dataset.

---

## End of Assignment
