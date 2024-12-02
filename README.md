# Road Accident Analysis using Power BI

## Overview
This project involves building an interactive Power BI dashboard to analyze road accident data in the United Kingdom. While the project was independently created, it draws inspiration from the YouTube tutorial: [Road Accident Dashboard in Power BI](https://www.youtube.com/watch?v=Hn9f13uoLAQ). The tutorial's description provides all necessary resources, including:
- The dataset used for the analysis.
- Sample images of the completed dashboard.

## Key Features
- **Primary KPIs:**
  - Total Casualties and Total Accidents for the current year.
  - Year-over-Year (YoY) growth for both metrics.
  - Casualties categorized by accident severity.
- **Secondary KPIs:**
  - Analysis of casualties by vehicle type.
  - Total accidents and casualties visualized by location.
- **Trend Analysis:**
  - Monthly comparison of casualties for the current and previous year.
  - Casualties analyzed by road type, area (urban/rural), and time of day (day/night).

## Installation and Usage

1. **Install Power BI Desktop:** Download and install the latest version from the [official Power BI website](https://powerbi.microsoft.com/).
2. **Access Dataset:** Download the UK road accident dataset from the YouTube tutorial's description.

## Data Transformation and DAX Measures
The project employs calculated measures using DAX (Data Analysis Expressions) to create KPIs and analyze trends. Here are some key measures:

- **Current Year-to-Date Casualties:**
  ```DAX
  CY Casualties = TOTALYTD(SUM(Data[Number_of_Casualties]), 'Calendar'[Date])
  ```

- **Year-on-Year Casualty Growth:**
  ```DAX
  YoY Casualties = ([CY Casualties] - [PY Casualties]) / [PY Casualties]
  ```

- **Accidents by Month Comparison:**
  ```DAX
  CY Monthly Accidents = CALCULATE(COUNT(Data[Accident_Index]), DATESMTD('Calendar'[Date]))
  ```

## Dashboard Visuals
- **KPI Cards:** Showcase total casualties and accidents, along with YoY growth.
- **Bar Charts:** Visualize casualties by vehicle type and accident severity.
- **Line Graphs:** Compare monthly trends for the current and previous year.
- **Heatmaps:** Highlight high-accident areas categorized by time and location.

## Acknowledgments
- This project was created with reference to [this YouTube tutorial](https://www.youtube.com/watch?v=Hn9f13uoLAQ). The tutorial provides comprehensive resources, including the dataset and dashboard visuals, which greatly aided in the development process.
- Data sourced from UK road accident records.

