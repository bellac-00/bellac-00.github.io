# Estimating Daily Average Air Quality with Ambient Air Pollution Particle Concentration
Bella Chen 

Instructors: Dr. Lozinski，Catherine Banach

AOS C 214 Introduction to Machine Learning for the Physical Sciences 

Final Project

## Introduction 
Air quality is a persistent environmental challenge with significant implications for public health and well-being. The Air Quality Index (AQI) is a standardized measurement used to represent air quality, including capturing the concentrations of ambient air pollution such as particulate matter (PM) and ground-level ozone. Understanding the AQI in our surroundings is crucial for assessing environmental risks and their impact on public health. This model aims to predict AQI levels in California, enabling better decision-making, public awareness, and proactive measures to mitigate health risks associated with air pollution.

## Data
Three datasets are used in this project:  Daily AQI][3] summary in the year 2022 provided by the EPA includes the monitor site locations, ozone AQI, and particulate matter AQI values. Monitor site locations are used for interpolation onto a uniform grid. Ozone AQI is ignored and only particulate matter AQI is used as the prediction target. Specifically, log(AQI) is used due to the wide range of raw AQI values. A cleaned up snippet of this dataset is shown below:   

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Date Local</th>
      <th>Latitude</th>
      <th>Longitude</th>
      <th>AQI</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>2022-02-28</td>
      <td>30.497478</td>
      <td>-87.880258</td>
      <td>35</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2022-03-01</td>
      <td>30.497478</td>
      <td>-87.880258</td>
      <td>50</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2022-03-02</td>
      <td>30.497478</td>
      <td>-87.880258</td>
      <td>51</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2022-03-03</td>
      <td>30.497478</td>
      <td>-87.880258</td>
      <td>40</td>
    </tr>
    <tr>
      <th>4</th>
      <td>2022-03-04</td>
      <td>30.497478</td>
      <td>-87.880258</td>
      <td>77</td>
    </tr>
  </tbody>
</table>  

## Methods 

