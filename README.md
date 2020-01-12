# Motivation

In Hong Kong, hotel industry has dominated short-term apartment rental market until Airbnb came into the town. Under keen compeition from hotels and listings on Airbnb website, Airbnb hosts are looking for optimizing their nightly rental price in order to stand out from others. 

This project aims at creating the best model to predict the prices of Airbnb appartments in Hong Kong using machine learning regressors.
Besides available features given in the original dataset, walkability features based on location data will be introduced to the model: the property's proximity to popular venues and MTR station around the district. This will allow our model to take locaton features into consideration as well. 

Before a bunch of modeling, data preprocessing is tedious but necessary step to ensure that our datasets are relatively clean. Otherwise, our final model is nothing but 'Garbage-in, Garbage-out'.

After data preprocessing, I have also conducted exploratory data analysis (EDA) to facilitate understanding of the dataset we collected.


# Data Source
- Inside Airbnb HK Listing Data
  
  As Airbnb does not release official data on the listings, the data of Airbnb listing data is collected from InsideAirbnb.com, a non-commercial website that shares publicly available data about worldwide Airbnb properties. In our project, we downloaded one of the datasets called listings which scraped on 10/6/2019, containing 106 attributes for 12,107 Airbnb listings in Hong Kong.

    [Detailed Listings and Calendar data for Hong Kong (Date Compiled: 10 June 2019)](http://insideairbnb.com/get-the-data.html)
  
 - Proximity to nearness MTR station for each listing      
    ```Tool: Google Map Distance Matrix API```
 
    [Measurement of point-2-point distance](https://github.com/marco-cheung/exploring-airbnb_hk/blob/master/Google%20Distance%20Matrix%20API%20(point-2-point).ipynb)
    
  - Nearby Point-of-interest (POI) per neighbourhood       
     ```Tool: Foursquare Venue Explore API```
    
    [Search for nearby popular venues per neighbourhood/district in Hong Kong](https://developer.foursquare.com/docs/api/venues/explore)


# Workflow
[This notebook](https://github.com/marco-cheung/exploring-airbnb_hk/blob/master/Predicting%20Airbnb%20prices%20with%20machine%20learning%20models.ipynb) covers:
(1) Data cleansing
(2) Exploring nearby popular venues per Neighborhood (District) in Hong Kong using Foursquare API
(3) Measuring walkability score per listing within the neighbourhood
(4) Exploratory Data Analysis (EDA)
(5) Handling multi-collinearity problems
(6) Feature Selection before modeling
(7) Modeling (eight regression models in total)
(8) Comparing model performance
(9) Selecting best model


# Regression Models used for comparison:
- Ordinary Linear Regression (our base model)
- Lasso
- Ridge
- KNN
- Decision Tree
- Gradient Boost
- Random Forest
- Extra Tree

#Conclusions and Recommendations

Random Forest Model, the best performing model, was able to predict 54% of the variation in price with an RMSE of 0.48. Such limited explanatory power of our model could be due to omitted variable bias (e.g. review score sentimental analysis) and the need to construct model with deep learning. 

From the analysis of feature importances, we can see that there are some statisfically significant features affecting airbnb pricing:

- Room Type (Entire Home/Apartment)
- Number of accommodates, host profile (number of listings and host duration on website)
- Location (e.g. walkability to the nearest popular venues and proximity to MTR station)
- Number of bathrooms
- Days available to be booked in the next 30 days 
- Number of reviews of the apartment
- Minimum nights required for booking
