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
