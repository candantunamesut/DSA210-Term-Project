# DSA210-Term-Project

This project aims to analyze how seasonal trends and critic/audience opinions affect movies' popularity and box office value. Along with the relationship seasonal increase/decrease in certain genres (as an example: spike in popularity for holiday movies during the period between Christmas - New Years), there will also be comparison between the relation between general audience rating vs critics' rating and how high the revenue of the movie is. 

## Motivation
With the increased digitalization of the world, online streaming platforms have become a major source for streaming movies and series and are considered to have replaced the physical streaming (cinemas/box office) industry. Digitalization has also contributed to social media spaces majorly being the host platforms for discussions and generating engagament for visual media like movies and series. Since movies' and their online discussion spaces are personal interests of mine, I intend to question some of the major factors affecting movies' popularity and plan to focus on the global annual calendar/major events along with online engagement on search engines.

## **Research Questions:** 
Aiming to answer questions like:
- To what extent do seasonal trends and annual events (Halloween, Christmas, summer and winter breaks for students) affect the popularity of certain genres of movies based on search engine data?
- To what extent do critic ratings and general public opinion (rating) correlate with a movie's box office revenue? Which rating is more indicative of box office success?

## **Hypotheses:**
### Critic score (tomatoMeter) & box office revenue:
H0: There is no significant relationship between critic score and box office revenue.
Ha: There is a significant relationship between critic score and box office revenue.

### Audience score & box office revenue:
H0: There is no significant relationship between audience score and box office revenue.
Ha: There is a significant relationship between audience score and box office revenue.

### Seasonal trends:
H0: There is no significant difference in popularity of genres across seasons.
Ha: There is a significant difference in popularity of genres across seasons.

## Datasets
The project will feature the following data:
* title: title of movie
* genre: genre of movie
* interest_over_time: interest for a movie genre over time on Google (search engine)
* date: date belonging to the interest trend retrieved on Google Trends (YYYY-MM-DD)
* tomatoMeter: the average score (0-100) given to the movie by critics
* audienceScore: the average score (0-100) that represents how the movie is perceived by the general public
* boxOffice: box office revenue (in dollars) 

The mentioned features will be collected from the following sources:
* Google Trends: to track Google searches about trending movies at certain times: search data over time will be retrieved via Pytrends using [pytrends](https://pypi.org/project/pytrends/) library on Python and stored on pandas
    * interest data trend of certain genres over time will be collected to examine how the popularity of different genres change depending on the season of the year (genres will be imported from the Rotten Tomatoes dataset) 
* Rotten Tomatoes: usage of a [Rotten Tomatoes Movies dataset](https://www.kaggle.com/datasets/andrezaza/clapper-massive-rotten-tomatoes-movies-and-reviews?resource=download&select=rotten_tomatoes_movies.csv) imported from Kaggle user Andrea Villa to access title, genre, critic scores (tomatoMeter), audience scores and box office revenue data
    * genre, box office, critic score (tomatoMeter), audience score will be retrieved from Rotten Tomatoes

Additionally, long-short term memory technique will be implemented using an IMDb reviews dataset retrieved on Kaggle (including user-reviews and sentiment-value features). Such data will contribute to showing how reviews and their sentiment value correlate with the other features included in the project (Rotten Tomatoes scores by critics and the audience, seasonal interest on Google etc.)

## Data Analysis
- Tracking popularity of movie trends over time.
- Determining seasonal trends.
- Comparing discussions on social media with the success of the movie.
- Identifying correlations between social media engagement and movie popularity, seasonal trends and movie popularity, critic reviews and movie popularity.
- Applying regression analysis to predict success of movie in box office and streaming platforms.


# Results, Limitations and Challenges

## Critic & Audience Scores’ Relation with Box Office Revenue:

In order to understand if a movie’s ratings correlate with how high their box office revenue (in dollars) is, two scores -one being the average of multiple critics and the other one that represents the general audiences’ opinion- on the movie were compared to see if either show any relation. A dataset containing values of over 130 thousand movies, their scores, genres, box office revenue values (and more) scrapped by user Andrea Milla from the website Rotten Tomatoes was retrieved from Kaggle and used in the experiment. The correlation values of both scores were compared with a heatmap to examine if there is indeed any relation. The hypotheses of the experiment were tested using Pearson Correlation. The scatterplots of both comparisons were saved as png files, along with the correlation heatmap of the three data features and can be found in the results folder.

### Results: 

Pearson correlation was found to be:
- Between audience score & box office revenue: 0.08
    - which means there was a weak positive correlation between the two values.
- Between critic score & box office revenue: -0.01
    - which means there was no correlation between the two values.

P-value was found to be:
- For audience score & box office revenue: 
- For critic score & box office revenue: 
Comparing these values with α = 0.05: we can reject the null hypothesis for the audience score-box office revenue test whereas we cannot reject the null hypothesis for the critic score-box office test. There is a significant relationship between audience rating and box office revenue meanwhile there is no significant relationship between critic scores and box office revenue.

Additionally, on the correlation heatmap, we can observe the pearson correlation between audience score and critic score to be 0.64: which indicates a strong positive correlation between the two values. 

### Limitations: 
The dataset originally consisted of over 140k+ movies; and cleaning out empty/missing values for box office, tomatometer and audience rating columns left out 130k+ movies. This led to some of the dataset not being used. Additionally, some of the movies’ box office revenues were low enough to mean that their rating values might not have been accurate. Due to lack of popularity, a small amount of movies’ tomatometer (critic rating) value is 0, which could be tied to no critics reviewing the movie. This can also be said for movies with a small amount of voters which would affect the audience rating value.


## Seasonal Genre Popularity Trends: 

In order to understand the relationship between seasonal-annual events/days and movie genre popularity, Google Trends’ search popularity data of genres was retrieved using the Python library pytrends. A dataset containing values of over 130 thousand movies, their scores, genres, box office revenue values (and more) scrapped by user Andrea Milla from the website Rotten Tomatoes was retrieved from Kaggle and used in the experiment. The correlation values of both scores were compared with a heatmap to examine if there is indeed any relation. The hypotheses of the experiment were tested using ANOVA. 

### Results: 

### Limitations & challenges: 
The greatest challenge in testing the relation between seasons/annual important dates and movie genres’ popularity was how frequently the system failed to fetch the requested data due to Google Trends’ 429 (TooManyRequests) error. My first approach to discover if there is an existing seasonal trend amongst genres was to request information from Google Trends for every single movie in the Rotten Tomatoes Movies dataset, but this approach proved to be unachievable due to how great the number of movies the dataset consisted of was. I moved on to requesting search data for genres instead, and used the Rotten Tomatoes dataset to create a list of movie genres and fetched data for these genres. Though the number was down from 130k+ to 20-30, the issue still persisted, and I had to move on to a retry based code to ensure I could retrieve data for the most number of genres possible. Genre names had to be cleaned due to special characters and NaN values corrupting data. Despite using the retry based mechanism, I had to improvise using sleep time as well to not overexhaust the system and prevent Trends from flagging my IP adress. Using the retry mechanism and delay times together, in the last retrieval attempt dated 25/04/2025, I was able to retrieve data for 33 out of 34 genres which left out data for only the “Sports & Fitness” genre. This was the most successful attempt and took 49 minutes and 6 seconds. Additionally, to prevent the context of search keywords and retrieving data of non-movies, I added the keyword “movies” to the end of the genre names retrieved from the Rotten Tomatoes dataset. 
