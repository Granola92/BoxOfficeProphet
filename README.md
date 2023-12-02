# BoxOfficeProphet
Anticipating Movie Triumphs


Amdrew notes


Prophet1.csv is our dataset for now. It contains movies going back 50 years. The imdb threshold was pretty high, but even then a lot of the movies were missing box office data.

I believe the ones with missing box office data are flops. Easiest to filter them out and convert everything to integers, but the unkowns can still give useful data.

Please note that the budget can be in different currencies and you need to convert them. There's no mention on whether its inflation adjusted, so just check if the numbers make any sense after the conversion. There should be a crazy ratio with revenue unless it is a super good or bad movie. All box office numbers are USD so do not convert them. There are a few foreign films. Most are in dollars as most big films are intended for a western market. Some market should not be compared to hollywood films, but some markets may be comparible. It's up to you how you want to treat them. I might add the country of origin from imdb in the future, but its in a different section, and I don't think it will make things simpler because it lists multiple countries and it seems kinda dicey.

Remember that some of these parameters come from different times. Name, content rating, release date, genre, keyword, stars, directors, writers, runtime, and budget are all parameters that can be known pre-release. Opening weekend revenue and sentiment(imdb score is a rough estimator) are things that would be known during the theatre showing. Gross north american revenue,world revenue, awards, and nominations will only be known after the theatres stop showing it. Only use parameters from earlier in time to predict parameters from later in time.

Awards and nominations has a bug. I'm pretty sure any strings should be 0

Genres are in lists. The lists come in alphabetical order, not related to which genre is most fitting. There are only a few genres so maybe make a binary column for each genre.

Stars, directors, writers, and keywords are in order of importance. Directors 3 is none for 99% so usei it or don't. There is more detail to be added later on writers, as some writers do the screenplay while others do the story.

There are so many keywords that you cannot make binary columns for them. They are all useful metrics still, so what you will probably need to do is make a separate dataframe with keywords as the index. Same goes for actors, writers, and directors

Get used to converting all the numbers from strings to floats becuase I get them as strings in the html

More about the revenues. All imdb data comes from boxofficemojo. If it is incomplete in imdb, it is incomplete in boxofficemojo. I will still go datascrape boxofficemojo because even if the data is incomplete it will be more detailed. If some box office data is missing I took out all box office data, because I found cases where they were able to hide american box office numbers but not other countries. The gross world revenue is a sum of all countries, so it looks super small, but its missing american numbers. Gross revenue is not comparable so all we can really gather is that it was probably a flop. 



glhf
