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

## HYPOTHESES

1. The more listings there are in a neighbourhood, the higher the average prices of the listings will be.
2. The listings that have more reviews also have higher prices.
3. The less available a listing is, higher its price will be.
4. Higher the required min stay is, higher its price will be.

## KEY QUESTIONS & INSIGHTS

**1. Are there certain room types that exist in certain neighbourhoods?**

<img width="748" alt="Screenshot 2024-05-30 at 14 49 44" src="https://github.com/slcnyrnc/2023-NYC-Airbnb-Analysis/assets/167687192/79905dea-c2f4-4325-9d7f-d5034949fccb">

Entire home/apts and private rooms dominate across all neighbourhood groups. On the contrary hotel rooms have a very low share in all neighbourhood groups and almost non existent in the Bronx and Staten Island.
- In Brooklyn, Manhattan and Staten Island, entire homes/apts has dominance over private rooms.
- In the Bronx and Queens, private rooms are slightly more common than entire homes/apts.

**2. What is the average price of a room per neighborhood?**

<img width="891" alt="Screenshot 2024-05-30 at 14 50 58" src="https://github.com/slcnyrnc/2023-NYC-Airbnb-Analysis/assets/167687192/e07fbd6e-3e25-4dcc-9b77-638d3481ab7d">

- Manhattan consistently emerges as the most expensive area, while the Bronx tends to have lower prices on average across all room types.

**3. What is the average price of a room per room type?**

<img width="541" alt="Screenshot 2024-05-30 at 15 20 50" src="https://github.com/slcnyrnc/2023-NYC-Airbnb-Analysis/assets/167687192/0354051b-bd5c-4318-927a-b418d491d4d7">

- Hotel rooms has the highest average prices across all the room types followed by entire home/apts.

**4. What is the number of listings per neighbourhood?**

<img width="587" alt="Screenshot 2024-05-30 at 14 57 47" src="https://github.com/slcnyrnc/2023-NYC-Airbnb-Analysis/assets/167687192/47834ef4-1c9a-4505-a899-d20171537427">
<img width="419" alt="Screenshot 2024-05-30 at 14 52 37" src="https://github.com/slcnyrnc/2023-NYC-Airbnb-Analysis/assets/167687192/68381dac-703b-4402-8c17-e25f42c6d633">

- Number of listing are mostly gathered in the center of NYC in Manhattan and Brooklyn and together they consist of the 80% of the listings of NYC.
- Staten Island has only around 1% of the listings.

**5. What is the distribution of room types?**

<img width="518" alt="Screenshot 2024-05-30 at 15 13 42" src="https://github.com/slcnyrnc/2023-NYC-Airbnb-Analysis/assets/167687192/7ff237aa-c1b1-4eb6-bfb2-749b6b324079">

- Entire homes/apts dominate the room types as 57% and 42% percent consisting of 99% of all the room types.

**6. What percentage of rooms are available?**

<img width="583" alt="Screenshot 2024-05-30 at 15 07 08" src="https://github.com/slcnyrnc/2023-NYC-Airbnb-Analysis/assets/167687192/035b4b61-5247-4909-84ff-21597e8aed81">

- Least available places around the year are grouped in the center again in Manhattan and Brooklyn despite having the most listings in the city.
- The neighbourhoods in the outskirts of the city (in Staten Island and The Bronx) have the most availability. These results supports again the idea that the most popular areas are Manahattan and Brooklyn.
- Despite not being so popular and having lower number of listings Staten Island has higher average prices than Brooklyn which is the most popular area after Manhattan. This could be because Staten Island is apparently known for offering more space, larger properties, and a quieter, more suburban lifestyle compared to other boroughs. Many homes in Staten Island are single-family houses with yards, which are rare and highly valued in New York City it seems. This probably atttracts certain individuals/groups/families. This can drive up the average price, even if the number of listings is very few. In relation with that, the number of listings being very few indicates a limited supply of available homes. When supply is limited, prices can remain high which can explain the situation in Staten Island.

These insights are already proving two of my hypothesis wrong:
- The more listings there are in a neighbourhood, the higher the average prices of the listings will be.
- The less available a listing is, higher its price will be.

## EXPLORATORY DATA ANALYSIS

**Linear Regression Analysis (Supervised MAchine Learning)**

To test the hypotheses I conducted a linear regression:

- No of reviews: Slope value shows us negative relationship meaning that as number of reviews rises, prices slightly drops.
<img width="634" alt="Screenshot 2024-05-30 at 14 34 55" src="https://github.com/slcnyrnc/2023-NYC-Airbnb-Analysis/assets/167687192/a23780c4-be27-4caa-9ef4-8ef777adfa5e">

- Availability: Slope value shows us a positive relationship meaning that as an accomodation has more availability, prices slightly increase.
<img width="681" alt="Screenshot 2024-05-30 at 14 35 28" src="https://github.com/slcnyrnc/2023-NYC-Airbnb-Analysis/assets/167687192/21a7ab9d-ef87-4c84-a5af-da5f0cfa9a84">

- Min Nights: Slope value shows us a noticable negative relationship meaning that as required minimum stay has increases, prices slightly decrease.
<img width="658" alt="Screenshot 2024-05-30 at 14 35 52" src="https://github.com/slcnyrnc/2023-NYC-Airbnb-Analysis/assets/167687192/a2ecb2bd-bf6e-4523-858b-09ad36b7b3c6">

However, the results show that none of the linear models represented by the regression line covered all of the data points and the nature of the relationship between the variables is not very clear.

In summary, none of the results were a good predictor of the price of listing, that a regression is definetly not the best model to represent this data and can’t accurately predict the influence of the selected variables on the price of a listing. Therefore I need to try another approach to test my hypotheses.

**Clustering Analysis (Unsupervised Machine Learning)**

<img width="986" alt="Screenshot 2024-05-30 at 14 39 37" src="https://github.com/slcnyrnc/2023-NYC-Airbnb-Analysis/assets/167687192/f11d1219-11db-4a5e-bef7-8cac59d4c7cf">

Neighbourhood Boroughs (1=Manhattan, 2=Brooklyn, 3=Queens, 4=The Bronx, 5=Staten Island):
- Most entries in the clusters 'green' and 'red' are from Manhattan.
- For 'black' and 'gray', the median is 2.0, indicating a significant presence of Brooklyn in this cluster.

Room Types (1=Entire home/apt, 2=Private room, 3=Shared room, 4=Hotel room):
- All clusters have predominantly Entire home/apts.

No of Reviews:
- Clusters 'green' have many listings with few to no reviews.
- Clusters 'black' and 'gray' has the highest number of reviews showing more engagement.

Availability:
- Clusters 'gray' and 'green' show high availability throughout the year meaning these listings are available for the majority of the year.
- Cluster 'red' has a significant difference between mean and median which could mean that some listings with very high availability skewing the average.
- Cluster 'black' has the lowest availability

Min Nights:
- Cluster 'black' and 'red' have high median minimum nights, suggesting longer stay requirements.
- Cluster 'green' has a low median minimum night requirement, indicating more flexibility for short stays.

Price:
- Cluster 'red' has the highest mean and median prices, indicating premium or luxury listings.
- Cluster 'green' also shows high prices but significantly lower than red cluster.
- Cluster 'black' and 'gray' have relatively lower prices, with 'black' cluster being the most affordable.

## FINAL RESULTS

Each cluster serves distinct market segments, from moderate and accessible accommodations (Clusters 'gray' and 'black') to premium and ultra-luxury options (Clusters 'green' and 'red'). This segmentation allows for targeted marketing and pricing strategies based on the specific characteristics and demands of each cluster.

- Cluster 'gray': Ideal for shorter stays with more availability and flexibility as well as moderate prices, making it suitable for more frequent, possibly budget-conscious travelers.
- Cluster 'green': Targets affluent guests looking for short-term stays at premium prices.
- Cluster 'red': Caters to a niche market of ultra-wealthy guests for long-term stays at extremely high prices. 
- Cluster 'black': Best suited for long-term guests seeking moderate prices.

**Revisiting Hypotheses**

**Hypothesis 2:** The listings that have more reviews also have higher prices.
- The analysis shows that Clusters 'black' and 'gray' have the highest number of reviews, yet they have relatively lower prices. This contradicts the hypothesis, suggesting that more reviews do not necessarily correlate with higher prices.

**Hypothesis 3:** The less available a listing is, the higher its price will be.
- The analysis supports this hypothesis to some extent. Cluster 'black' has the lowest availability and also the lowest prices, which contradicts the hypothesis. However, Cluster 'red' with significant differences in availability shows high prices. More precise data on availability and price correlations are needed for a definitive conclusion.

**Hypothesis 4:** The higher the required minimum stay, the higher its price will be.
- The analysis supports this hypothesis. Cluster 'red', which has high minimum stay requirements, also has the highest prices. Similarly, Cluster 'black' has high minimum nights and is moderately priced, indicating a trend where longer stay requirements correlate with higher prices.

## RECOMMENDATIONS: 

- Adjusting prices to match cluster characteristics is recommended—premium prices for Clusters 1 and 2, budget-friendly prices for Clusters 0 and 3.
- Ideally dynamic pricing should be used for high-availability clusters (0 and 1) during peak times, and long-term stays for Cluster 3should be promoted.
- The hosts should encourage reviews in Clusters 1 and 2 with incentives to improve listing visibility and attractiveness.
- The hosts should emphasize unique amenities of Entire home/apts to attract guests seeking privacy and exclusivity.
- It's better to offer short-term booking flexibility for Cluster 2 and promote long-term stay benefits for Clusters 2 and 3.

## NEXT STEPS:

- The regression analysis and clustering of New York City Airbnb data were mostly inconclusive, failing to find clear correlations affecting accommodation prices due to limited variability and diversity in the dataset. 
- To gain actionable insights and optimize host performance, a more varied dataset is needed.
- Future work will focus on expanding the dataset to include a broader range of factors and scenarios for a more thorough analysis.

## VISUALISATIONS

The business case with extra visualizations for this project can be found in Tableau Public: <LINK>
