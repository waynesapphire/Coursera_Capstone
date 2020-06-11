# Expolring Venues in Boston

## On Fullfill the Coursera Data Science Capstone Project

## Introduction

The aim of this Capston project is to discover the venues in Boston, Massachusetts according to the ratings and average costs(prices). In this notebook, we will use Foursquare API and Zomaton API to select the desired venues.

The two primary factors that people choose a place to eat when took a tour in a new city are venues ratings and their budget. This will also be the two main factors that will be taken into consideration during this project.

## Data Collecting

- Foursquare API: Fetch venues in Boston.
- Zomato API: The Zomato API provides information about various venues including the **complete address, user ratings, price range** and a lot more.


## About Boston

Boston is the capital and most populous city of the Commonwealth of Massachusetts in the United States, the city proper covers 49 square miles with an estimated population of 692,600 in 2019, also making it the most populous city in New England.
The city is the economic and cultural anchor of a substantially larger metropolitan area known as Greater Boston, a metropolitan statistical area (MSA) home to a census-estimated 4.8 million people in 2016 and ranking as the **tenth-largest** such area in the country.

## Brief View of Downton Boston

Let's use the **folium** library to create a complete map zoomed on Boston. We'll also plot a marker on the coordinates we just identified above.

## FourSquare API

We are using the Explore API from the FourSquare API which allows us to find venue recommendations within a pre-defined radius from the given coordinates.
Using the function called 'get_category_type' we've already created during the previous lab.

## Zomato API

Similar to FourSquare API, Zomato API also requires a user key to search for any given venue based on certain search filter.

## Data Cleaning

We collected data from different source, it is important for us to combine the overlapping information and as well as removing some unnecessary stuff.

As the above two maps indicated, there are many venues identified by both Foursquare and Zomato. There is a lot of overlapping. However, there are others where the data does not match.

To combine the two datasets, double check that the latitude and longitude values of each corresponding venue match. Thus, round both the latitude and longitude values up to 4 decimal places. Then, calculate the difference between the corresponding latitude and longitude values and see if the difference is less than 0.0004 which should ideally mean that the two locations are the same.

## Methodology

This project is using both FourSquare API and Zomato API to fetch data about Boston local venues in order to provide a better venues referencing for visitors based on the rating and pricing which could be usually treated as two main factors for venues selection.


### Data Collection

The corresponding data was retrieved from two APIs above, due to the limitation of the free developers account(1000 calls/day) and density of venues in downtown Boston, here we are using a radius of 5 kilometers from the center of downtown Boston. In addition to the coordinates and basic information fetched using Foursquare API, the pricing information was also retrieved using Zomato API. 

What we'll provide through those data is that identify where most popular venues are located so visitors can have much more fun without going to a lot of places. Also we'll be plotting those highly rated and poorly rated places on the map.

### Analysis

As indicated by the category composition, the top 3 favorite category is bakery shop,seafood restaurant and Italian Restaurant. Boston is a habour city where downtown area is a the place called little Italy, that could explain the why distribution favors seafood and Italian food. 

### Ratings

Rating of a venue is an important factor when a visitor decides whether it is worth it to visit.  We'll first see what is the average rating for all the venues in this area. Then, we will plot the venues on the map and color code them.

We'll first identify the various rating values and plot them as a bar plot with their counts to see the most common rating.

### Pricing

Take a look at the venues based on the price values. Here we have two price features for our venues, one is average_price which defines the average cost for one person and the other is price_range which describe how expensive of this venue is when compared to all other venues.

We will first explore the average_price using a scatter plot between the price and the count of venues with that average price.

## Clustering 

## Results and Analysis

As the result shown from the above clusters, the average price doesn't positively related to the customer satisfaction(rating). Maybe the exquisite decoration of the restaurant will increase customers' expectation of food, thus results in a more serious evaluation.

Finally, through clusters we identified that there are many venues which are relatively lower priced but have an average rating of 3.6. On the other hand, there are few venues which are high priced and not that satisfactory.

If you are not sure where to go, both North End and South End would be choices you won't regret.

## Conclusion

The objective of this project is to help people find the places/venues according to the rating and pricing. The venues has been identified using Foursquare and Zomato API, the spots have been plotted onto the map, additionally, as suggested using the clustering algorithm, the North End and South End could be the best choice for visitors. 