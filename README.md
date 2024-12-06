# Estimating Daily Average Air Quality with Ambient Air Pollution Particle Concentration
Bella Chen 

Instructors: Dr. Lozinski，Catherine Banach

AOS C 214 Introduction to Machine Learning for the Physical Sciences 

Final Project

[Link](https://colab.research.google.com/drive/1BNgsVq78X7P-FjYC2qsxJKYtYb44Ictk?usp=sharing) to Google Colab Notebook

## Introduction 
Air quality is a persistent environmental challenge with significant implications for public health and well-being. According to World Health Organization (WHO), an estimation of 4.2 million deaths can be attributed to outdoor air pollution annually (Shaddick et al., 2020). The Air Quality Index (AQI) is a standardized measurement used to represent air quality, including capturing the concentrations of ambient air pollution such as particulate matter (PM) and ground-level ozone. [AQI](https://www.airnow.gov/aqi/aqi-basics/) is ranged from 0 - 500 with different categories as below: 

  0 - 50: Good 
  
  51–100: Moderate air quality 
  
  101–150: Unhealthy for sensitive groups 
  
  151–200: Unhealthy 
  
  201–300: Very unhealthy 
  
  301–500: Hazardous

Understanding the AQI in our surroundings is crucial for assessing environmental risks and their impact on public health. Understanding the relationships between air quality and ambient air pollutants is crucial for designing targeted mitigation strategies, improving public health outcomes, and informing policies to address air pollution in the most affected areas. This machine learning model aims to predict AQI levels in California, enabling better decision-making, public awareness, and proactive measures to mitigate health risks associated with air pollution. 

## Data
Three data sets were used in this project: daily AQI summary including daily mean PM<sub>2.5</sub> concentration, Ozone concentration, and NO<sub>2</sub> concentration along with geographical coordinates in the year 2022 provided by US EPA[2](https://www.epa.gov/outdoor-air-quality-data/download-daily-data). Parameters such as daily observations and county FIPS were ignored and cleaned after merging the data together. 


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

![Map](https://github.com/bellac-00/bellac-00.github.io/blob/main/Plots/AQI.png)

PM<sub>2.5</sub> 

![pm](https://github.com/bellac-00/bellac-00.github.io/blob/main/Plots/PM.png)

O<sub>3</sub>

![o](https://github.com/bellac-00/bellac-00.github.io/blob/main/Plots/Ozone.png) 

NO<sub>2</sub>

![n](https://github.com/bellac-00/bellac-00.github.io/blob/main/Plots/NO2.png) 

The AQI map for 2023 shows better air quality in northern California. While in southern California, especially urbanized areas regions like Los Angeles, experiences higher AQI. By observing the distribution of all 3 air pollution factors, NO<sub>2</sub> concentrations in 2020 are closely linked to higher AQI values observed in southern California. The ozone distribution also correlates with AQI, as higher ozone concentrations in the southern regions often result in poorer air quality. Another major determinant of AQI, PM<sub>2.5</sub> level, shows a similar pattern, with higher concentrations in southern urban centers leading to elevated AQI values. Overall, the distribution of these pollutants influences the AQI significantly, with areas of higher pollutant concentrations consistently corresponding to poorer air quality.

## Methods 
The data was collected was U.S. EPA. Data preprocessing involved removing irrelevant columns, handling missing values, and standardizing units. The datasets were merged by date and county, with additional features like pollutant interactions. Three models (linear regression, LightGBM, and random forest regression) were trained and evaluated using metrics such as RMSE, R², and REC curves. Interpolated AQI values were visualized on a geographic grid, and feature importance was analyzed to identify key predictors. 

## Model Prediction and Results 
For all models, the maximum tolerance (ϵ) is set to 20, as it effectively captures moderate changes in AQI, providing a balanced evaluation of the model's prediction accuracy.

**Linear Regression Model** 

Here is the performance of a linear model represented by the REC curve is shown below: 

![lr](https://github.com/bellac-00/bellac-00.github.io/blob/main/Plots/linear_rec.png) 

The RMSE result is **6.61** and R² is **0.879**. 


 
**Random Forest Model**

The feature importance and REC curve from the decision tree model is shown below:

![r](https://github.com/bellac-00/bellac-00.github.io/blob/main/Plots/feature_importance_rf.png) 

![rf](https://github.com/bellac-00/bellac-00.github.io/blob/main/Plots/randomforest.png) 

The RMSE result is **1.00** and R² is **0.997**. 
The PM2.5 has a more significant effect on prediction on AQI. 



**LightGBM**

The LightGBM (Gradient Boosting Machine) is a high-performance implementation of the gradient boosting framework, specifically designed for speed and efficiency while maintaining prediction accuracy (Zhang et al., 2023). 

The feature importance and and REC curve from the decision tree model is shown below:

![lgbm](https://github.com/bellac-00/bellac-00.github.io/blob/main/Plots/lgbm.png)

| Feature                          | Importance Value |
|----------------------------------|------------------|
| Daily Mean PM2.5 Concentration   | 1777             |
| Daily Max 8-hour Ozone Concentration | 457              |
| Daily Max 1-hour NO2 Concentration   | 766              |


![g](https://github.com/bellac-00/bellac-00.github.io/blob/main/Plots/gbm_rec.png)

The RMSE result is **0.0472** and R² is **0.999**. 

These results indicate that PM<sub>2.5</sub> concentration is the dominant factor in predicting air quality, as it has the highest feature importance value.

The full REC curve visualization is included to present a clear comparison. 
![rec](https://github.com/bellac-00/bellac-00.github.io/blob/main/Plots/recs.png) 

Among the three models tested, including linear regression, random forest regression, and LightGBM, all are capable of providing reliable predictions of local air quality estimation. However, the LightGBM model demonstrates the best performance compared to the others since it almost reached a 100% accuracy. 


## Discussions 

Among all three models, LightGBM  demonstrated the best prediction performance, as it achieves approximately 100% accuracy at low tolerance levels which is indicated by the REC curve. To further evaluate the reliability and robustness of this model, a k-fold cross-validation (5-fold) was performed, with the following results:

- Cross-Validation RMSE (Mean): 0.384

- Cross-Validation RMSE (Standard Deviation): 0.310

- Cross-Validation RMSE (Min): 0.106

- Cross-Validation RMSE (Max): 0.961

The mean RMSE represents the average prediction error across all folds. A value of 0.384 is relatively low, indicating that the model's predictions are close to the true values, with only small errors on average. 

According to scholarly research, LightGBM models play a crucial role in understanding air pollution patterns. With its ability to efficiently handle non-linear data and its high processing speed, LightGBM emerges as the most suitable model for this task (Ravindiran et al., 2023). In contrast, linear regression model has the poorest performance on capturing the complex air quality patterns. This is likely due to the intrinsic nature of AQI, which is influenced by multiple factors, including natural processes and human-made emissions. While the random forest model performed well overall, its predictions were relatively less accurate compared to the LightGBM model.

In conclusion, these findings suggest that the increasing concentrations of ambient air pollutants such as fine particulate matter (PM<sub>2.5</sub>), ozone, and nitrogen dioxide, are closely related to poorer air quality. This underscores the importance of utilizing advanced tree-based methods like LightGBM for reliable and accurate air quality predictions.

## Works Cited
AQI Basics | AirNow.gov. (n.d.). https://www.airnow.gov/aqi/aqi-basics/ 

Ravindiran, G., Hayder, G., Kanagarathinam, K., Alagumalai, A., & Sonne, C. (2023). Air quality prediction by machine learning models: A predictive study on the indian coastal city of Visakhapatnam. Chemosphere, 338, 139518. https://doi.org/10.1016/j.chemosphere.2023.139518

Shaddick, G., Thomas, M. L., Mudu, P., Ruggeri, G., & Gumy, S. (2020). Half the world’s population are exposed to increasing air pollution. Npj Climate and Atmospheric Science, 3(1). https://doi.org/10.1038/s41612-020-0124-2

Zhang, X., Jiang, X., & Li, Y. (2023). Prediction of air quality index based on the SSA-BiLSTM-LightGBM model. Scientific Reports, 13(1). https://doi.org/10.1038/s41598-023-32775-2


