# Avocado Price Prediction Project Overview    ![](/images/avocado.png)

* Built a price prediction model with Time Series Forecasting and deep learning method,LSTM(Long-Short Term Memory).
* Predicted the price of avocado for the next 30 days.
* Analyzed the data to explore how the price of avocado alters based on its size,types, seasons or regions.
* Explored the dataset with bar charts, heatmaps, line plots and various distribution plots.


## ***About the Data*** :

* Average price of avocados of the USA in the period of 3 years.(2015-01-04 to 2018-03-25)
    
* Collected the data from a website called "data.world", contributed by Caroline Horn.
  *Link : https://data.world/caroline/avocado-prices 
    
    
## ***Data Features*** :

* Date : Dates that the avocado was sold
* AveragePrice : Average Price of Single Avocado of that date
* type : Type of Avocados => Organic and Conventional
* year : The year that the avocado was sold
* Region : City or region of USA
* Total Volume : Total number of avocados sold on that date
* 4046 : Total number of avocados with PLU code 4046 Sold 
* 4225 : Total number of avocados with PLU code 4225 Sold
* 4770 : Total number of avocados with PLU code 4770 Sold
   - PLU Code : Code which identifies the size of Avocados


## ***Section 1*** : Exploratory Data Analaysis
* By plotting different types of bar charts and line plots to analyze how the price and the total volume change over time. 
* Pie charts were used to explore the proportions between categorical features. 
* Analyzed the distributions of price and total volume sold with boxplots. 
* From the exploratory data analysis, we can explore more in-depth information of the data and able to spot out which features affect the average price.
* Here are some highlights :


![](/images/avocado_avg_price.jpg) 
![](/images/avocado_total_byregions.jpg)
![](/images/avocado_pie.jpg)
![](/images/avocado_season.jpg)
![](/images/avocado_distribution.jpg)
![](/images/avocado_heatmap.jpg)




## ***Section 2*** : Price Prediction Of The Next 30 Days With Time Series Forecasting With LSTM
* Preprocessing : 

    * Scaled the data(data['AveragePrice'] with MinMaxScaler and separate the data into train_set(80% of data) and test_set(20% of data).
    * Separate the train_set into X_train,y_train datasets. X_train takes a range of 100 data(time_steps) at a time, while y_train takes the values from the 100th data.
    * Separate the test_set into X_test,y_test datasets. 
    * Reshaped the X_train and X_test into 3-Dimensionals as LSTM only accepts 3-Dimensional input shape(batch_size,time-steps,sequence-lengths).

* Constructing LSTM Model : 

    * Built the LSTM model with 2 more hidden LSTM layers with the Dropout of 0.2 on each LSTM layer.
    * Flatten the layers and add a Dense layer at the end. Used 'mean_squared_error' loss function and adam optimizer algorithm.
    * To find the optimal number of units(units with the least Root Mean Squared Error), ran the model with 4 different numbers of units(16,32,64,128).
    * Fit X_train and y_train with 32 units and resulted RMSE of 0.125.
    
* Price prediction for the following 30 days :

    * Take the last 100 data from the y_test dataset.
    * As the price of each day was predicted based on its previous 100 data, I saved each day's predicted price into the  'res' list and added again to the 'inputs' list to use as an input for the prediction of the next day.
    
![](/images/avocado_predicted_1.jpg)

![](/images/avocado_predicted_2.jpg)


## *Conclusion* :
* The average price of avocados gets affected by the total volume sold.
* Most sales happened during the summer and the least sales during the fall.
* Highest price during fall and lowest price during spring and summer.
* Avocados in northern and eastern areas of the USA had the higher average price than the southern and western areas.
* Most consumed avocados were conventional type and bought in smaller bags.
* The average price and the total volume sold had increased from early 2015 to early 2018.
* By using my LSTM model, the average price after one month(2018-04-24) was around $1.33, approximately 0.015 dollars higher than a month before.
* To increase the sales of avocados, the producers should find a solution to reduce the transportation costs, particularly to the north and east parts of the USA,in addition, especially during the fall season. Furthermore, the producers should produce more 4225 and 4046 conventional avocados as the demands are higher. For organic avocados producers, they should find a solution to reduce the price to raise the total sales as the consumers are sensitive towards the price.
