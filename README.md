# Estimating Daily Average Air Quality with Ambient Air Pollution Particle Concentration
Bella Chen 

Instructors: Dr. Lozinski，Catherine Banach

AOS C 214 Introduction to Machine Learning for the Physical Sciences 

Final Project

## Introduction 
Air quality is a persistent environmental challenge with significant implications for public health and well-being. According to World Health Organization (WHO), an estimation of 4.2 million deaths can be attributed to outdoor air pollution annually (Shaddick et al., 2020). The Air Quality Index (AQI) is a standardized measurement used to represent air quality, including capturing the concentrations of ambient air pollution such as particulate matter (PM) and ground-level ozone. AQI is ranged from 0 - 500 with different categories as below [1](https://www.airnow.gov/aqi/aqi-basics/): 

  0 - 50: Good 
  
  51–100: Moderate air quality 
  
  101–150: Unhealthy for sensitive groups 
  
  151–200: Unhealthy 
  
  201–300: Very unhealthy 
  
  301–500: Hazardous

Understanding the AQI in our surroundings is crucial for assessing environmental risks and their impact on public health. Understanding the relationships between air quality and ambient air pollutants is crucial for designing targeted mitigation strategies, improving public health outcomes, and informing policies to address air pollution in the most affected areas. This model aims to predict AQI levels in California, enabling better decision-making, public awareness, and proactive measures to mitigate health risks associated with air pollution. 

## Data
Three data sets were used in this project: daily AQI summary including daily mean PM<sub>2.5</sub> concentration, Ozone concentration, and NO<sub>2</sub> concentration along with geographical coordinates in the year 2022 provided by US EPA[2](https://www.epa.gov/outdoor-air-quality-data/download-daily-data). Parameters such as daily observations and county FIPS were ignored and cleaned after merging the data together. The data was cleaned and processed by removing unnecessary and overlapped columns, handling units (e.g., ug/m³, ppm, ppb), and interpolating AQI values over a fine geographic grid. This allowed for spatial visualization of air quality across California, ensuring accurate alignment with geographic boundaries. 


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

Bewlos are the air quality and ambient air pollution particulates distribution map in California: 

AQI 

![Map](https://github.com/bellac-00/bellac-00.github.io/blob/main/Plots/image.png)

PM<sub>2.5</sub> 

![pm](https://github.com/bellac-00/bellac-00.github.io/blob/main/Plots/PM.png)

O<sub>3</sub>

![o](https://github.com/bellac-00/bellac-00.github.io/blob/main/Plots/Ozone.png) 

NO<sub>2</sub>

![n](https://github.com/bellac-00/bellac-00.github.io/blob/main/Plots/NO2.png) 

The AQI map for 2023 shows better air quality in northern California. While in southern California, especially urbanized areas regions like Los Angeles, experiences higher AQI. By observing the distribution of all 3 air pollution factors, NO<sub>2</sub> concentrations in 2020 are closely linked to higher AQI values observed in southern California. The ozone distribution also correlates with AQI, as higher ozone concentrations in the southern regions often result in poorer air quality. Another major determinant of AQI, PM<sub>2.5</sub> level, shows a similar pattern, with higher concentrations in southern urban centers leading to elevated AQI values. Overall, the distribution of these pollutants influences the AQI significantly, with areas of higher pollutant concentrations consistently corresponding to poorer air quality.


## Methods 



## Modelling 

## Results 

## Discussions 

## Works Cited
AQI Basics | AirNow.gov. (n.d.). https://www.airnow.gov/aqi/aqi-basics/ 

Shaddick, G., Thomas, M. L., Mudu, P., Ruggeri, G., & Gumy, S. (2020). Half the world’s population are exposed to increasing air pollution. Npj Climate and Atmospheric Science, 3(1). https://doi.org/10.1038/s41612-020-0124-2



