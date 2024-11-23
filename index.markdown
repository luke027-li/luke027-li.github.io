---
layout: default
title: "License Data Visualizations"
---

# License Data Visualizations

## Overview
This project visualizes license data from Fall 2022. The visualizations provide insights into:
- The most common license types.
- Temporal trends in license issuance for selected categories.

## The Visualizations
### Visualization 1: Top 10 License Types
<iframe src="bar_chart.html" width="800" height="600" style="border:none;"></iframe>

This bar chart visualizes the top 10 license types by their frequency in the dataset. The purpose of this visualization is to highlight the most common license types issued and provide an easy way to compare their counts.

**Encoding Types**

x-axis: The license type  is encoded as a categorical variable, allowing clear differentiation between each license type.
y-axis: The count of licenses is encoded as a quantitative variable to show the magnitude of each license type's frequency.
Color: A quantitative colormap is applied to emphasize the magnitude of the counts, with darker colors representing higher counts.

**Colormap**

A sequential colormap is used, where the intensity of the color increases with the count of licenses. This helps emphasize which license types are more common while maintaining a clean and readable design.

**Transformations**

The license Type column was aggregated using value_counts() to calculate the frequency of each license type.
The top 10 license types were extracted using .head(10).
The data was reformatted into a simple structure with two columns: LICENSE DESCRIPTION and Count.
### Visualization 2: License Trends Over Time

<iframe src="scatter_plot.html" width= "1000" height="600" style="border:none;"></iframe>
This scatter plot highlights how licenses were issued over time, focusing on the top 10 categories.
Each point represents the number of licenses issued on a specific effective date for a particular city. The visualization enables exploration of temporal patterns and differences across these cities.

**Encoding Types**

x-axis: The effective date (EFFECTIVE DATE) is encoded as a temporal variable, enabling the visualization of time trends.
y-axis: The count of licenses is encoded as a quantitative variable to reflect the magnitude of licenses issued on specific dates.
Color: Each city is assigned a unique color to distinguish trends for different cities.
Tooltip: Tooltips provide details about the effective date, city, and count of licenses for each data point, enabling users to explore specific data points.

**Colormap**

A categorical color scheme is used to assign a unique color to each city, making it easier to visually separate trends.

**Interactivity**

This plot includes two major interactivity features to enhance user exploration:

Interactive Legend:

The city legend is interactive, allowing users to isolate specific cities on the scatter plot.
Single Click on a City in the Legend: When a user clicks on a city in the legend, the scatter plot updates to display data points for that city only. All other cities are hidden from the plot.
Clicking the City Again: Clicking the same city again toggles the plot back to display all cities. This feature allows users to focus on one city at a time or view all cities for comparison.
This behavior is achieved using Altair’s selection_multi() with bind="legend", allowing users to dynamically adjust which cities are displayed.

Tooltips:

Hovering over a data point shows:
City Name: The city represented by the point.
Effective Date: The date the licenses were issued.
Number of Licenses: The count of licenses issued for that city on that date.
These tooltips make it easier for users to identify specific data points and understand the underlying data.

**Transformations**

The EFFECTIVE DATE column was converted to datetime format for temporal analysis.
The dataset was filtered to include only cities ranked 5th to 10th in total license count.
Data was grouped by EFFECTIVE DATE and CITY, and the count of licenses issued for each city on each date was calculated.



## Access the Data and Analysis
- [The Data](https://github.com/UIUC-iSchool-DataViz/is445_data/raw/main/licenses_fall2022.csv)
- [The Analysis](https://github.com/luke027-li/luke027-li.github.io/blob/main/hw6.ipynb)

---
