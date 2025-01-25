# python-api-challenge-
What is the weather like as we approach the equator?

This project had two deliverables, WeatherPy and VacationPy. 

## WeatherPy
In this deliverable, a Python script to visualize the weather of over 500 cities of varying distances from the equator was created. 

OpenWeatherMap API was used to retrieve weather data from the cities list generated in the starter code. I then created a series of scatter plots to showcase the following relationships:

* Latitude vs. Temperature
* Latitude vs. Humidity
* Latitude vs. Cloudiness
* Latitude vs. Wind Speed

The four sctter plots were saved as png files. 

I then computed the linear regression for each relationship. I separated the plots into Northern Hemisphere (greater than or equal to 0 degrees latitude) and Southern Hemisphere (less than 0 degrees latitude). I defined a function in order to create the linear regression plots.

Next, I created a series of scatter plots and included the linear regression line, the model's formula, and the r^2 values. 

I created the following plots:

* Northern Hemisphere: Temperature vs. Latitude
* Southern Hemisphere: Temperature vs. Latitude
* Northern Hemisphere: Humidity vs. Latitude
* Southern Hemisphere: Humidity vs. Latitude
* Northern Hemisphere: Cloudiness vs. Latitude
* Southern Hemisphere: Cloudiness vs. Latitude
* Northern Hemisphere: Wind Speed vs. Latitude
* Southern Hemisphere: Wind Speed vs. Latitude

### The following were the findings of the linear regression performed on each plot: 

### Northern Hemisphere: Temperature vs. Latitude

* In the plot that depicts the northern hemisphere, a negative trend can be seen; as the latitude increased, the maximum temprature decreased. The regression line also models the trend in the data. The r^2 value, which is -0.739, indicates that about 73.9% of the variance in the temperature is explained by the latitude. The intercept, which is the value of Y when X=0, is 33.73; this signifies that when the value of x is 0, this model predicts that the maximum temprature to be 33.73 C. To circle back to the question we started this project with, as we approach the equator from the north, the temprature is warmer. This findings align with the general understanding of how latitude influences climate in the northern hemisphere. 

### Southern Hemisphere: Temperature vs. Latitude

* The southern hemisphere plot, on the other hand, shows a positive trend in which the temperature slightly increases as the latitude approaches the equator. The maximum temprature predicted as per this model is around 28.23 C when the value of x is 0 - which is the equator. Unlike in the northern hemisphere, the r-squared value indicates that only 19.7% of the variance in the max temp can be explained by latitude. This indicates that latitude alone is not a sufficient predictor of temprature in the southern hemisphere.  

### Northern Hemisphere: Humidity vs. Latitude

* The plot showing the relationship between latittude and humidity in the northern hemisphere shows a slight positive trend in that as the latitude increased the humidity also slightly increased. However, according to the r-sqauared value indicates that only 17.3% of the variance in humidity can be explained by latitude. This suggests that in the northern hemisphere, other factors may be present that affect humidity on top of latitude. 

### Southern Hemisphere: Humidity vs. Latitude

* In the southern hemisphere plot as well, there seems to be a weak corelation between latitude and humidity. As seen in the r-squared value, only 8.3% of variation in humidity is accounted for latitude as a factor. Similar to the northern hemisphere data, other factors may contribute more significantly to humidity variation than latitude alone. 

### Northern Hemisphere: Cloudiness vs. Latitude

* Northern Hemisphere: there is a very weak positive corelation beween cloudiness and latitude in this plot. Also, only 6.3% of the variability in cloudiness is explained by latitude in this particular dataset. The scatterplot also shows variability at all latitudes signifying the weak correlation between latitude and cloudiness. 

### Southern Hemisphere: Cloudiness vs. Latitude

* Southern Hemishere: the r-squared value in this dataset is 0.0027, which shows that there is almost no correlation between latitude and cloudiness. Also, the latutude explains only 0.27% of the variation in cloudiness. Also, there is no pattern seen in how the sctters are plotted. With this dataset in consideration, there is no significant relationship between cloudiness and latitude in the southern hemisphere. 

### Northern Hemisphere: Wind Speed vs. Latitude

* Northern Hemisphere: There is no clear pattern that can be seen in the scatterplot. The r-squared value of 0.0007 indicates that there is an alomost nonexistent corelation between latitudes and wind speed in the norhern hemisphere represented by this dataset. 

### Southern Hemisphere: Wind Speed vs. Latitude

* Southern Hemisphere: There is a less than 1% corelation between latitude and wind speed in the southern hemisphere dataset as well. As the latitude gets closer to the equator, win speed decreased insignificantly. 

*Note: Future running of the random city generation part of this script may generate new cities. Consequently, the results of the scatter plots and the line regressinon calculation on the plots might render different results. The results of any new regression calculation and its inmplications might be slightly different.* 

## VacationPy

In this deliverable, I used weather data, geoViews Python library, and the Geoapify API to plan future vacations.

After importing the csv file I generated in WeatherPy, I created a map that displays a point for every city in the city_data_df DataFrame. The size of the point is the humidity in each city.

I then narrowed down the city_data_df DataFrame to find what I consider ideal weather condition. The criteria I used are: 

* Temperature: I set the temperature to be between 21 and 27C.
* Wind Speed: Less than 4m/s would be ideal for city exploration as the gentle winds can be comfortable.
* Cloudiness: Less than 25% would be clear skies with a little barrier from the harsh sunlight. 

*I had walking and exploring in mind for this criteria.*

Based on the criteria, I was able to generate 15 cities that met the specifications. I then created a new DataFrame called hotel_df to store the city, country, coordinates, and humidity. For each city, I used the Geoapify API to find the first hotel located within 10,000 meters of the coordinates. I then added the hotel name and the country as additional information in the hover message for each city on the map. 

