# BoxOfficeProphet
Anticipating Movie Triumphs

This project by Harty Gold details the work in creating a linear regression model that attempts to predict movie financial and critical success using scraped data
from IMDb, Rotten Tomatoes, BoxOfficeMojo & Wikipedia.

Additional package installation required: Currency Converter https://pypi.org/project/CurrencyConverter/, 
Unidecode https://pypi.org/project/Unidecode/

There are 4 main data sources for our project. They are listed below, along with the main outputs from each source. In order to analyze useful data, a cut-off of 5,000 IMDb user reviews was set for movies from 2002 to 2022. This was done to filter out movies that were either lacking in data due to less popularity or that were from before the digital age, when online rating platforms were popularized.

*1.* IMDb: Movie Name, Release Date, Genres , Movie Cast, Directors, Writers, Runtime, Award Nominated, Awards Won, Gross Revenue (US+Canada), Opening Weekend Revenue (US+Canada), Gross Revenue (Worldwide), Estimated Budget, IMDb score, IMDb review count, Keywords, Production Company

2. Rotten Tomatoes : Critic Score, Critic Review Count, Audience Score, Audience Review Count, Producer Names

3. BoxOfficeMojo: Revenue by country, & more granular financial metrics

4. Wikipedia: Years Active for Actors
The main method of data scraping was through the BeautifulSoup package that parses the HTML of individual webpages.
