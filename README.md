# BoxOfficeProphet
Anticipating Movie Triumphs

This project by Harty Gold details the work in creating a linear regression model that attempts to predict movie financial and critical success using scraped data
from IMDb, Rotten Tomatoes, BoxOfficeMojo & Wikipedia.

Additional package installation required: Currency Converter https://pypi.org/project/CurrencyConverter/, 
Unidecode https://pypi.org/project/Unidecode/

There are 4 main data sources for our project. They are listed below, along with the main outputs from each source. In order to analyze useful data, a cut-off of 5,000 IMDb user reviews was set for movies from 2002 to 2022. This was done to filter out movies that were either lacking in data due to less popularity or that were from before the digital age, when online rating platforms were popularized.

1. **IMDb:** Movie Name, Release Date, Genres , Movie Cast, Directors, Writers, Runtime, Award Nominated, Awards Won, Gross Revenue (US+Canada), Opening Weekend Revenue (US+Canada), Gross Revenue (Worldwide), Estimated Budget, IMDb score, IMDb review count, Keywords, Production Company

2. **Rotten Tomatoes:** Critic Score, Critic Review Count, Audience Score, Audience Review Count, Producer Names

3. **BoxOfficeMojo:** Revenue by country, & more granular financial metrics

4. **Wikipedia:** Years Active for Actors

The main method of data scraping was through the BeautifulSoup package that parses the HTML of individual webpages.

Data Preparation:

1. For IMDB, the BeautifulSoup package is used to scrape a list of movies that meet our cutoff requirements of being post 2002 and contain at least 5000 IMDB reviews. The list is then used to generate a list of URLs to scrape further detailed movie data for each individual movie.

2. For RottenTomatoes, the user and critic reviews were gathered and averages are calculated. 

3. For BoxOfficeMojo, BeautifulSoup is used 

4. For Wikipedia data, a list of actors is generated from the unique values that appear in the list of stars for each movie in the IMDB dataframe. Multiple URL links are generated as Wikipedia have variances in the link formatting. All of the various URL cases are tried and the one that does not return nothing is used to find the years active for each actor listed.

5. Linear regression was the ideal model type selected. Originally starting with 250 input features, it was later narrowed down to 40 relevant ones, by removing features until R-squared decreased

6. A LASSO regression was implemented in the final step to decrease tolerance for model complexity.


#Details
- The folder "Data Collected" consists of all the data collected through web scraping and processing.
- The folder "Data CLeaning" consists of all processing scripts, such as scaling and inflation accounting.
- The folder "Data Scraping" consists of all scraping scripts to find and create the main dataframes.
- The folder "Final Model" contains scripts that are used for the main model.
- Start from Final Model 1 to replicate results, running the consecutive files in the order listed in the file name.
