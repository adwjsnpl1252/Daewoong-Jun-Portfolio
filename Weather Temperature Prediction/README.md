# Weather Temperature Prediction Project Overview
![](/images/weather.jpg)

* Built a weather temperature prediction model using RandomForestRegressor and resulted with r2 score of 0.990 and RMSE of 0.609
* Scraped more than 140 thousand rows of weather dataset from "https://www.wunderground.com" by utilizing Beautifulsoup and requests in Python.
* Successfully cleaned the dataset by handling the missing data, modifying the data type and columns of the dataset, and removing the misleading values, irrelevant data, and outliers.
* Conducted an exploratory data analysis to investigate the temperature change over the past ten years in Toronto and detect which features had affected the temperature with Plotly and Matplotlib.

## ***About the Data*** :

* Web scraped historical weather data from "https://www.wunderground.com/history/daily/ca/toronto/CYTZ/".
* Contains weather dataset from 2010 January 1st to 2020 December 31st.

    
## ***Data Features*** :

* Date : Dates that the weather data was recorded
* Time : Time that the weather data was recorded
* Temperature : The temperature recorded at that time 
* Dew Point : The dew point recorded at that time
* Humidity : The humidity recorded at that time
* Wind : The wind direction recorded at that time
* Wind Speed : The wind speed recorded at that time
* Wind Gust : The wind gust recorded at that time
* Pressure : The pressure recorded at that time
* Precipitation : The precipitation recorded at that time
* Condition : The condition of the sky at that time


## ***Section 1*** : Cleaning the Dataset

* Merged the dataset from 2010 to 2020 scraped weather datasets
* Removed the missing values
* Removed misleading values, irrelevant values and outliers


## ***Section 2*** : Exploratory Data Analysis

* No significant temperature change over the past 10 years.
* In 2014 and 2015, it was relatively cold compare to other years.
    * There was an extreme month in 2015(February), it was the coldest month ever
* In 2012 and 2020, it was comparatively hot compare to other years.
    * There was an extreme month in 2020(July), it was the coldest month ever
* In each season, it was colder from midnight to early morning and warmer during noon.
* Temperature mostly gets affected by depending on the month, dew point, wind speed, wind gust, wind direction, and condition of the day.
* Dew point was the major increase of temperature(As Dew Point increases, it will increase the temperature).
* Wind Speed and Gust were the main features to drop the temperature(Temperature will drop when 'Wind Speed' and 'Wind Gust' increase).
* Temperature changes depending on the month/season.
* When it's windy or snowy, the temperature drops. On the other hand, when it is fair and rainy, the temperatures tend to be higher.
* When the wind blows north-west or west, the temperature relatively gets lower. On the other hand, when it blows south or southeast, the temperatures tend to rise.

* Here are some highlights:
![](/images/weather_temp.png)
![](/images/weather_tdist.png)
![](/images/weather_heatmap.png)
![](/images/weather_condition.png)
![](/images/weather_season_dist.png)
![](/images/weather_tempcorr.png)
![](/images/weather_corr2.png)
![](/images/weather_sfeatures.png)
![](/images/weather_sfeature.png)
![](/images/weather_features1.png)
![](/images/weather_features2.png)
## ***Section 3*** : Building a Prediction Model

* Setting dummies to categorical variables using One hot encoding
* Separated the dataset into train set and test set with sklearn.model_selection.train_test_split
* Trained the RandomForestRegressor model with the train set
* With the model, predicted the temperature for January 2021 and gave r2 score of 0.81 and a Root Mean Squared Error of 2.294
* Improved the model by parameter tuning with GridsearchCV and after the tuning, further improved the model to have r2 score of 0.990 and Root Mean Squared Error of 0.609.


