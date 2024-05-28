# NYC-Airbnb-Analysis-2023

## BUSINESS PROBLEM

In the highly competitive Airbnb market in New York City, hosts and property managers aim to maximize rental income and optimize listing performance. The goal of this analysis is to provide Airbnb hosts with useful information that they can use to improve the performance of their listings, hone their pricing tactics, raise occupancy rates, and eventually boost overall income. 

I will try to find important patterns and trends by analyzing key metrics, conducting linear regression analysis, and performing cluster analysis. With these insights, hosts can make sure their properties are both profitable and appealing to guests by setting fair and competitive prices. 

## DATA SOURCE

In this project, I will analyze the Airbnb New York City data from 2023 and see which insights can be extracted from raw data.

Airbnb is a platform that allows house and apartment owners to rent their properties to guests for short-term stays.

This public dataset was accessed from Kaggle (https://www.kaggle.com/datasets/godofoutcasts/new-york-city-airbnb-2023-public-data/data) on May 5 and the original source can be found on InsideAirbnb website. Inside Airbnb is an independent, non-commercial set of tools and data that allows us to explore how Airbnb is really being used in cities around the world. By analyzing publicly available information about a city’s Airbnb’s listings, Inside Airbnb provides filters and key metrics so we can see how Airbnb is being used to compete with the residential housing market.

## METHODOLOGY
- Sourcing open data
- Exploratory analysis through visualizations (scatterplots, correlation heatmaps, pair plots, and categorical plots);
- Geographical visualizations AND Geospatial analysis using a shapefile;
- Regression analysis (Supervised machine learning);
- Cluster analysis (Unsupervised machine learning)
- Analysis narrative and final results (creating data dashboards)

## TECH STACK

- Python:
    pandas & numpy - for data analysis
    seaborn, matplotlib, sklearn, and folium - for data visualization
    json and geojson - for spatial analysis
- Tableau
- GitHuB

## DATA LIMITATION & BIAS 

- The dataset on Airbnb contains personal information, including host names, listing names, and exact locations.
- This data may pose privacy risks and inconsistencies due to self-reported information from hosts and guests. 
- Biased reviews may influence future guests' decisions and may not accurately reflect listing quality.
- The dataset may not represent the entire Airbnb market in New York City, may be biased towards certain types of hosts or guests, and may not fully comply with regulatory requirements or licensing laws.
- The analysis is sourced from Inside Airbnb, but may still have inherent biases.

## KEY QUESTIONS
1. Are there certain room types that exist in certain neighbourhoods?
2. What is the average price of a room per neighborhood?   
3. What is the average price of a room per room type?
4. What is the number of listings per neighbourhood?
5. What is the geographical distribution of listings by neighbourhood group?   
6. What is the distribution of room types?
7. What percentage of rooms are available?

## HYPOTHESES

1. The more listings there are in a neighbourhood, the higher the average prices of the listings will be.
2. The listings that have more reviews also have higher prices.
3. The less available a listing is, higher its price will be.
4. Higher the required min stay is, higher its price will be.

## EXPLORATORY DATA ANALYSIS

To test the hypotheses I conducted a linear regression:

- No of reviews: Slope value shows us negative relationship meaning that as number of reviews rises, prices slightly drops.
- Availability: Slope value shows us a positive relationship meaning that as an accomodation has more availability, prices slightly increase. 
- Min Nights: Slope value shows us a noticable negative relationship meaning that as required minimum stay has increases, prices slightly decrease.

However, the results show that none of the linear models represented by the regression line covered all of the data points and the nature of the relationship between the variables is not very clear.

In summary, none of the results were a good predictor of the price of listing, that a regression is definetly not the best model to represent this data and can’t accurately predict the influence of the selected variables on the price of a listing. Therefore I need to try anothe approach.

## KEY INSIGHTS

Entire home/apts and private rooms dominate across all neighbourhood groups. On the contrary hotel rooms have a very low share in all neighbourhood groups and almost non existent in the Bronx and Staten Island.
- In Brooklyn, Manhattan and Staten Island, entire homes/apts has dominance over private rooms.
- In the Bronx and Queens, private rooms are slightly more common than entire homes/apts.

- Manhattan consistently emerges as the most expensive area, while the Bronx tends to have lower prices on average across all room types.
   
- Hotel rooms has the highest average prices across all the room types followed by entire home/apts.

- Number of listing are mostly gathered in the center of NYC in Manhattan and Brooklyn and together they consist of the 80% of the listings of NYC.
- Staten Island has only around 1% of the listings.

- Manhattan leads with the higest average prices for listings, followed by Staten Island and Brooklyn. The Bronx has the cheapest average prices of accomodations.

- Entire homes/apts dominate the room types as 43% and 42% persent respectively consisting of 85% of all room types

- Least available places around the year are grouped in the center again in Manhattan and Brooklyn despite having the most listings in the city.
- The neighbourhoods in the outskirts of the city (in Staten Island and The Bronx) have the most availability. These results supports again the idea that the most popular areas are Manahattan and Brooklyn.
- Despite not being so popular and having lower number of listings Staten Island has higher average prices than Brooklyn which is the most popular area after Manhattan. This could be because Staten Island is apparently known for offering more space, larger properties, and a quieter, more suburban lifestyle compared to other boroughs. Many homes in Staten Island are single-family houses with yards, which are rare and highly valued in New York City it seems. This probably atttracts certain individuals/groups/families. This can drive up the average price, even if the number of listings is very few. In relation with that, the number of listings being very few indicates a limited supply of available homes. When supply is limited, prices can remain high which can explain the situation in Staten Island.

These insights are already proving two of my hypothesis wrong:
- The more listings there are in a neighbourhood, the higher the average prices of the listings will be.
- The less available a listing is, higher its price will be.

## FINDINGS
Neighbourhood Boroughs:
1=Manhattan, 2=Brooklyn, 3=Queens, 4=The Bronx, 5=Staten Island

- Most entries in the clusters 1 and 2 are from Manhattan.
- For clusters 0 and 3, the median is 2.0, indicating a significant presence of Brooklyn.

Room Types:
1=Entire home/apt, 2=Private room, 3=Shared room, 4=Hotel room

All clusters have predominantly Entire home/apts.

No of Reviews:
- Clusters 1 and 2 have many listings with few to no reviews.
- Clusters 0 and 3 has the highest number of reviews showing more engagement.

Availability:
- Clusters 0 and 1 show high availability throughout the year meaning these listings are available for the majority of the year.
- Cluster 3 has the lowest availability.

Min Nights:
- Clusters 2 and 3 have the highest median nights requirement indicating long-term stays.
- Cluster 2 has the lowest minimum nights requirement indicating shorter-term stays.

Price:
- Cluster 2 has an extremely high average price indicating luxury or premium listings.
- Cluster 1 cluster also shows high prices but not as extreme as the red cluster.
- Clusters 0 and 3 clusters have lower prices indicating more budget-friendly options.


## RECOMMENDATIONS: 
Each cluster serves distinct market segments, from moderate and accessible accommodations (Clusters 0 and 3) to premium and ultra-luxury options (Clusters 1 and 2). This segmentation allows for targeted marketing and pricing strategies based on the specific characteristics and demands of each cluster.

- Cluster 0: Ideal for shorter stays with more availability and flexibility as well as moderate prices, making it suitable for more frequent, possibly budget-conscious travelers.
- Cluster 1: Targets affluent guests looking for short-term stays at premium prices.
- Cluster 2: Caters to a niche market of ultra-wealthy guests for long-term stays at extremely high prices. 
- Cluster 3: Best suited for long-term guests seeking moderate prices.

- Adjust prices to match cluster characteristics—premium rates for Clusters 1 and 2, budget-friendly rates for Clusters 0 and 3.
- Use dynamic pricing for high-availability clusters (0 and 1) during peak times, and promote long-term stays for Cluster 3.
- Encourage reviews in Clusters 1 and 2 with incentives to improve listing visibility and attractiveness.
- Emphasize unique amenities of Entire home/apts to attract guests seeking privacy and exclusivity.
- Offer short-term booking flexibility for Cluster 2 and promote long-term stay benefits for Clusters 2 and 3.

## NEXT STEPS:

- The regression analysis and clustering of New York City Airbnb data were inconclusive, failing to find clear correlations affecting accommodation prices due to limited variability and diversity in the dataset. 
- To gain actionable insights and optimize host performance, a more varied dataset is needed.
- Future work will focus on expanding the dataset to include a broader range of factors and scenarios for a more thorough analysis.

## VISUALISATIONS

The business case with extra visualizations for this project can be found in Tableau Public: <LINK>
