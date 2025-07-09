# Final-Project-Statistical-Modelling-with-Python

## Project/Goals
The goal of this project was to explore if there’s any relationship between the number of bikes available at a station and the nearby environment, like restaurants and bars. Using bike station data from Vitória (Brazil), my hometown, I worked through multiple APIs, built datasets, joined and analyzed them, and finally built a regression model to test for any patterns.

## Process
### (your step 1)
I started by pulling data from the CityBikes API, which gave me the location and bike availability for each station in Vitória. I parsed that into a clean DataFrame so I could use it across the rest of the project.

### (your step 2)
Then, I connected to both the Foursquare and Yelp APIs to gather points of interest (POIs) — like restaurants and bars — around each station. This part took some extra effort since the APIs behave differently and needed different handling.

### (your step 3)
Next, I joined the bike data with the Yelp POIs to create a single dataset. I used visualizations to explore patterns, and stored the full dataset in an SQLite database.

### (your step 4)
Finally, I built a regression model using statsmodels to see if Yelp ratings had any effect on bike availability. I also outlined how I could reframe the problem into a classification one.

## Results
From the API comparison, Yelp clearly offered better coverage for Vitória. It consistently returned more POIs per station, and included richer details like ratings, categories, and full business names. Foursquare was limited and ran into some access issues.

The regression model showed a small but statistically significant positive relationship: stations near higher-rated places had slightly more bikes. However, the R² value was very low, meaning ratings alone don’t explain much, which makes sense, since bike usage depends on many other things too.

## Challenges 
This project had its ups and downs. There were moments where everything worked smoothly, and others where I spent hours debugging or trying to understand why an API wasn’t returning data. The Foursquare API was the biggest roadblock, it either returned very few results or hit a credit limit fast, which forced me to rely more on Yelp.

Keeping everything structured across different notebooks and CSVs also took some extra attention. Overall, it was time-consuming, but nice once everything clicked together.

## Future Goals
If I had more time, I’d explore more features to improve the model, like time-of-day usage, weather, or POI diversity beyond restaurants. I’d also implement the classification version of the model and test how well it could predict bike availability categories. Finally, I’d invest more time in making the Foursquare integration more robust, or even add other sources of spatial data.