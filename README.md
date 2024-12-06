# Estimating Daily Average Air Quality with Ambient Air Pollution Particle Concentration
Bella Chen 

Instructors: Dr. Lozinski，Catherine Banach

AOS C 214 Introduction to Machine Learning for the Physical Sciences 

Final Project

## Introduction 
Air quality is a persistent environmental challenge with significant implications for public health and well-being. The Air Quality Index (AQI) is a standardized measurement used to represent air quality, including capturing the concentrations of ambient air pollution such as particulate matter (PM) and ground-level ozone. Understanding the AQI in our surroundings is crucial for assessing environmental risks and their impact on public health. This model aims to predict AQI levels in California, enabling better decision-making, public awareness, and proactive measures to mitigate health risks associated with air pollution.

## Data
Three data sets were used in this project: daily AQI summary including daily mean PM<sub>2.5</sub> concentration, Ozone concentration, and NO<sub>2</sub> concentration in the year 2022 provided by US EPA[1](https://www.epa.gov/outdoor-air-quality-data/download-daily-data). County site locations are used for interpolation onto a uniform grid. Parameters such as daily observations and county FIPS were ignored and cleaned after merging the data together.

Here's an illustration of data: 
<table border="1">
  <thead>
    <tr>
      <th>Date</th>
      <th>Daily Mean PM2.5 Concentration (ug/m3)</th>
      <th>Daily AQI Value</th>
      <th>County</th>
      <th>Daily Max 8-hour Ozone Concentration (ppm)</th>
      <th>Daily Max 1-hour NO2 Concentration (ppb)</th>
      <th>Site Latitude</th>
      <th>Site Longitude</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>2023-01-01</td>
      <td>3.7</td>
      <td>21.0</td>
      <td>Alameda</td>
      <td>0.034</td>
      <td>12.8</td>
      <td>37.687526</td>
      <td>-121.784217</td>
    </tr>
    <tr>
      <td>2023-01-01</td>
      <td>3.7</td>
      <td>21.0</td>
      <td>Alameda</td>
      <td>0.034</td>
      <td>23.6</td>
      <td>37.743065</td>
      <td>-122.169935</td>
    </tr>
    <tr>
      <td>2023-01-01</td>
      <td>3.7</td>
      <td>21.0</td>
      <td>Alameda</td>
      <td>0.034</td>
      <td>13.7</td>
      <td>37.814781</td>
      <td>-122.282347</td>
    </tr>
    <tr>
      <td>2023-01-01</td>
      <td>3.7</td>
      <td>21.0</td>
      <td>Alameda</td>
      <td>0.034</td>
      <td>15.3</td>
      <td>37.793624</td>
      <td>-122.263376</td>
    </tr>
    <tr>
      <td>2023-12-30</td>
      <td>2.3</td>
      <td>13.0</td>
      <td>Yolo</td>
      <td>0.041</td>
      <td>11.9</td>
      <td>38.534450</td>
      <td>-121.773400</td>
    </tr>
  </tbody>
</table>



## Methods 

## Modelling 

## Results 

## Conclusion 

## Works Cited

